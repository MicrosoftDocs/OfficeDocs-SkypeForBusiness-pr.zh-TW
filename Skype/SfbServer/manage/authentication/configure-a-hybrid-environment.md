---
title: 針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。
ms.openlocfilehash: 5d56f098589355b85f942a6b1eb80d8ab6c03225
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992350"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。

**摘要：** 針對商務用 Skype Server 混合式環境設定伺服器對伺服器驗證。

在混合式設定中，您的一些使用者是駐留在內部部署的商務用 Skype Server，而其他使用者則是駐留在 Office 365 版的商務用 Skype Server 上。 若要在混合式環境中設定伺服器對伺服器的驗證，您必須先設定您內部部署的商務用 Skype 伺服器安裝，以信任 Office 365 授權伺服器。 您可以執行下列商務用 Skype Server Management 命令介面腳本來執行此程式的初始步驟：

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

請記住，租使用者的領域名稱稱通常與組織名稱不同;事實上，領域名稱稱幾乎總是與租使用者識別碼相同。 因此，腳本中的第一行是用來傳回指定租使用者的 TenantId 屬性值（在此例中為 fabrikam.com），然後將該名稱指派給 $TenantId 的變數：

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

若要執行此腳本，您必須已安裝商務用 Skype Online PowerShell 模組，並使用此模組連線到您的租使用者。 如果您還沒有安裝這些 Cmdlet，您的腳本將會失敗，因為 CsTenant Cmdlet 將無法使用。 在腳本完成之後，您必須設定商務用 Skype 伺服器與授權伺服器之間的信任關係，以及 Exchange 2013/2016 與授權伺服器之間的第二個信任關係。 這只能使用 Microsoft Online Services Cmdlet 來完成。

> [!NOTE]
> 如果您尚未安裝 Microsoft Online 服務 Cmdlet，您將需要使用 Cmdlet `install-module MSOnline`從 PowerShell 知識庫安裝它。 您可以在 Office 365 網站上找到安裝及使用 Microsoft Online Services 模組的詳細資訊。 這些指示也會告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟及同步處理。 



在您設定 Office 365 之後，且為商務用 Skype Server 和 Exchange 2013 建立 Office 365 服務主體之後，您就必須使用這些服務主體註冊您的認證。 若要這樣做，您必須先取得 x.509 Base64 憑證並儲存成。CER 檔案。 此憑證隨即會套用至 Office 365 服務原則。

取得 x.509 憑證之後，請開啟 PowerShell console，然後匯入 Microsoft Online Windows PowerShell 模組，其中包含可用於管理服務主體的 Cmdlet：

```PowerShell
Import-Module MSOnline
```

匯入模組後，請輸入下列命令，然後按 ENTER，即可連線到 Office 365：

```PowerShell
Connect-MsolService
```

按下 ENTER 後，就會出現 [認證] 對話方塊。 在對話方塊中輸入您的 Office 365 使用者名稱和密碼，然後按一下 [確定]。

一旦您連線到 Office 365，您就可以執行下列命令，以傳回服務主體的相關資訊：

```PowerShell
Get-MsolServicePrincipal
```

您應該會針對所有的服務主體取得類似以下的資訊：

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

下一步是匯入、編碼並指派 x.509 憑證。 若要匯入並編碼憑證，請使用下列 Windows PowerShell 命令，確定要指定完整的檔案路徑。CER 檔案，當您呼叫 Import 方法時：

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

在匯入並編碼憑證之後，您就可以將憑證指派給您的 Office 365 服務主體。 若要這樣做，請先使用 MsolServicePrincipal，以取得商務用 Skype 伺服器與 Microsoft Exchange 服務原則的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別指派憑證的服務主體。 使用 AppPrincipalId 的商務用 Skype 伺服器的 [] 屬性值，請使用下列命令，將憑證指派給商務用 Skype Online 版本：

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

接著，請重複執行命令，這次是使用 Exchange 2013 的 AppPrincipalId 屬性值。

如果您稍後需要刪除該憑證（例如它已過期），您可以先取得證書的 KeyId，以執行此動作：

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

該命令會傳回如下所示的資料：

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

接著，您可以使用類似以下的命令來刪除證書：

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

除了指派憑證之外，您還必須設定 Exchange Online 服務主體，並將內部部署版本的商務用 Skype Server 外部 Web 服務 Url 設定為 Office 365 服務主體。 您可以執行下列兩個命令來完成這項工作。 

在下列範例中，Pool1ExternalWebFQDN.contoso.com 是商務用 Skype 伺服器池的外部 Web 服務 URL。 您應該重複這些步驟，以新增部署中的所有外部 Web 服務 Url。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
