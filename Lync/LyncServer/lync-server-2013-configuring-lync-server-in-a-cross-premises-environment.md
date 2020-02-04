---
title: Lync Server 2013：在跨內部部署環境中配置 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02696b85921e2f408b7a7ec5531b0596aaef49ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>在跨內部部署環境中設定 Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-02-21_

在跨內部部署設定中，您的一些使用者是駐留在內部部署的 Microsoft Lync Server 2013，而其他使用者則是位於 Office 365 版的 Lync Server。 若要在跨內部部署環境中設定伺服器對伺服器的驗證，您必須先設定您的 Lync Server 2013 內部部署安裝，以信任 Office 365 授權伺服器。 您可以執行下列 Lync Server 管理命令介面腳本來執行此程式中的初始步驟：

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

請記住，租使用者的領域名稱稱通常與組織名稱不同;事實上，領域名稱稱幾乎總是與租使用者識別碼相同。 因此，腳本中的第一行是用來傳回指定租使用者的 TenantId 屬性值（在此例中為 fabrikam.com），然後將該名稱指派給 $TenantId 的變數：

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

在腳本完成之後，您必須設定 Lync Server 2013 與授權伺服器之間的信任關係，以及 Exchange 2013 與授權伺服器之間的第二個信任關係。 這只能使用 Microsoft Online Services Cmdlet 來完成。

<div>


> [!NOTE]  
> 如果您尚未安裝 Microsoft Online 服務 Cmdlet，您必須先執行兩個作業，然後再繼續進行。 首先，請下載並安裝64位版本的 Microsoft Online Services 登入小幫手。 安裝完成後，請下載並安裝適用于 Windows PowerShell 的 Microsoft Online Services 模組64位版本。 您可以在 Office 365 網站上找到安裝及使用 Microsoft Online Services 模組的詳細資訊。 這些指示也會告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟及同步處理。<BR>如果您還沒有安裝這些 Cmdlet，您的腳本將會失敗，因為 CsTenant Cmdlet 將無法使用。



</div>

在您設定 Office 365 之後，且為 Lync Server 2013 和 Exchange 2013 建立 Office 365 服務主體之後，您就必須使用這些服務主體註冊您的認證。 若要這樣做，您必須先取得 x.509 Base64 儲存為。CER 檔案。 此憑證隨即會套用至 Office 365 服務原則。

取得 x.509 憑證之後，請啟動 Microsoft Online Services 模組（按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft online 服務**]，然後按一下 [ **Windows PowerShell 的 microsoft online services 模組**]）。 [服務] 模組開啟後，請輸入下列內容，以匯入包含可用來管理服務主體之 Cmdlet 的 Microsoft Online Windows PowerShell 模組：

    Import-Module MSOnlineExtended

匯入模組後，請輸入下列命令，然後按 ENTER，即可連線到 Office 365：

    Connect-MsolService

按下 ENTER 後，就會出現 [認證] 對話方塊。 在對話方塊中輸入您的 Office 365 使用者名稱和密碼，然後按一下 [確定]。

一旦您連線到 Office 365，您就可以執行下列命令，以傳回服務主體的相關資訊：

    Get-MsolServicePrincipal

您應該會針對所有的服務主體取得類似以下的資訊：

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

下一步是匯入、編碼並指派 x.509 憑證。 若要匯入並編碼憑證，請使用下列 Windows PowerShell 命令，確定要指定完整的檔案路徑。CER 檔案，當您呼叫 Import 方法時：

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

在匯入並編碼憑證之後，您就可以將憑證指派給您的 Office 365 服務主體。 若要這樣做，請先使用 MsolServicePrincipal，以取得 Lync Server 和 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別指派憑證的服務主體。 使用 Lync Server 2013 的 AppPrincipalId 屬性值，請使用下列命令，將憑證指派給 Office 365 版本的 Lync Server （[開始] 和 [結束] 屬性應該對應到憑證的有效期）：

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

接著，請重複執行命令，這次是使用 Exchange 2013 的 AppPrincipalId 屬性值。

如果您稍後需要刪除該憑證，您可以先檢索憑證的 KeyId，以執行此動作：

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

該命令會傳回如下所示的資料：

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

接著，您可以使用類似以下的命令來刪除證書：

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

除了指派憑證之外，您也必須為內部部署版本的 Lync Server 2013 新增伺服器主要名稱，以設定 Exchange Online 的 Office 365 服務主體。 您可以在 Microsoft 線上服務 PowerShell 會話中執行下列四行，以完成此動作：

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

