---
title: 設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。
ms.openlocfilehash: fcec1e982af0c5ad778a83fe6af9b58fbd44c7e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746069"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。

**摘要：** 設定商務用 Skype Server 混合式環境的伺服器對伺服器驗證。

在混合式設定中，有些使用者是在內部部署的商務用 Skype Server 上安裝，而其他使用者則位於商務用 Skype Server Microsoft 365 或 Office 365 版本。 為了設定混合式環境中的伺服器對伺服器驗證，您必須先設定商務用 Skype Server 的內部部署安裝，以信任授權伺服器。 您可以執行下列商務用 Skype Server 管理命令介面腳本，以執行此程式的初始步驟：

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

請記住，租用戶的領域名稱通常和組織名稱不同；事實上，領域名稱和租用戶 ID 幾乎相同。因此，指令碼第一行是用來為指定的租用戶傳回 TenantId 屬性值 (在這種情況下為 fabrikam.com)，接著將該名稱指派至變數 $TenantId：

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

若要執行這個腳本，您必須已安裝商務用 Skype 線上 PowerShell 模組，並使用此模組連接至您的租使用者。 若尚未安裝這些 Cmdlet，您的腳本將會失敗，因為 Get-CsTenant Cmdlet 將無法使用。 腳本完成之後，您必須設定商務用 Skype Server 與授權伺服器之間的信任關係，以及 Exchange 2013/2016 和授權伺服器之間的第二個信任關係。 唯有使用 Microsoft Online Services Cmdlet 才能完成這項作業。

> [!NOTE]
> 若尚未安裝 Microsoft Online Services Cmdlet，您需要使用 Cmdlet 從 PowerShell 存放庫進行安裝 `install-module MSOnline` 。 有關安裝及使用 Microsoft Online Services 模組的詳細資訊，可在 Microsoft 365 網站上找到。 這些指示也會告訴您如何在 Microsoft 365 或 Office 365 和 Active Directory 之間設定單一登入、同盟及同步處理。 



在您設定 Microsoft 365 或 Office 365，且已建立商務用 Skype Server 和 Exchange 2013 的 Microsoft 365 或 Office 365 服務主體之後，您將需要使用這些服務註冊認證校長。 為了達到此目的，您必須先取得 x.509 Base64 憑證另存為。CER 檔案。 然後將此憑證套用至 Microsoft 365 或 Office 365 服務主體。

當您取得 x.509 憑證之後，請開啟 PowerShell 主控台，然後匯入 Microsoft Online Windows PowerShell 模組，其中包含可用於管理服務主體的 Cmdlet：

```PowerShell
Import-Module MSOnline
```

匯入模組後，請輸入下列命令，然後按 ENTER：

```PowerShell
Connect-MsolService
```

按下 ENTER 鍵後，將會出現認證對話方塊。 在對話方塊中輸入您的 Microsoft 365 或 Office 365 使用者名稱和密碼，然後按一下 [確定]。

當您連線至 Microsoft 365 或 Office 365 之後，您就可以執行下列命令，以傳回服務主體的相關資訊：

```PowerShell
Get-MsolServicePrincipal
```

您能以類似的方式為所有服務主體取得資訊：

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

下一個步驟為匯入、編碼以及指派 X.509 憑證。 若要匯入和編碼憑證，請使用下列 Windows PowerShell 命令，請務必指定您的完整檔路徑。CER 檔案當您呼叫 Import 方法時：

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

在匯入並編碼憑證之後，您可以將憑證指派給您的 Microsoft 365 或 Office 365 服務主體。 若要這麼做，請先使用 Get-MsolServicePrincipal 來同時檢索商務用 Skype Server 和 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別被指派憑證的服務主體。 使用商務用 Skype Server 手頭的 AppPrincipalId 屬性值，使用下列命令將憑證指派給商務線上版本 Skype：

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

您應該接著重複此命令，這次使用 Exchange 2013 的 AppPrincipalId 屬性值。

如果您稍後需要刪除該憑證，例如，如果憑證已過期，您可以先取回憑證的 KeyId，這樣做如下：

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

該指令將會以這種方式傳回資料：

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

接著您可以用類似這樣的命令來刪除憑證：

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

除了指派憑證之外，您還必須設定 Exchange Online 服務主體，並將內部部署版本的商務用 Skype Server 外部 Web 服務 URLs 為 Microsoft 365 或 Office 365 服務主體。 您可以執行下列兩個命令來執行此動作。 

在下列範例中，Pool1ExternalWebFQDN.contoso.com 是商務用 Skype Server 集區的外部 Web 服務 URL。 您應重複這些步驟，以在部署中新增所有外部 Web 服務 URLs。

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
