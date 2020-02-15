---
title: 'Lync Server 2013: 跨單位部署環境中設定 Lync Server'
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
ms.openlocfilehash: 74fd0370fd0b6b6ba829f0f4e78f322b1a5ccc21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>在跨部署環境中設定 Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-02-21_

在跨內部部署組態中，部分使用者位於 Microsoft Lync Server 2013 內部部署安裝時的其他使用者位於 Lync Server 的 Office 365 版本。 若要在跨單位部署環境中設定伺服器對伺服器驗證，您必須先設定為信任的 Office 365 授權伺服器的 Lync Server 2013 內部部署安裝。 此程序的初始步驟須先藉由執行下列的 Lync Server 管理命令介面指令碼：

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

請記住，租用戶的領域名稱通常和組織名稱不同；事實上，領域名稱和租用戶 ID 幾乎相同。因此，指令碼第一行是用來為指定的租用戶傳回 TenantId 屬性值 (在這種情況下為 fabrikam.com)，接著將該名稱指派至變數 $TenantId：

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

指令碼完成之後您必須設定 Lync Server 2013 與授權伺服器之間的信任關係，Exchange 2013 與授權伺服器之間的第二個信任關係。 唯有使用 Microsoft Online Services Cmdlet 才能完成這項作業。

<div>


> [!NOTE]  
> 如果您尚未安裝 Microsoft Online Services Cmdlet，那麼，您必需先完成兩個動作才能繼續進行。 首先，下載及安裝  Microsoft Online Services 登入小幫手 64 位元版本。 完成安裝之後，請下載並安裝 64 位元版本的 Microsoft Online Services 模組適用於 Windows PowerShell。 您可以在 Office 365 網站找到有關安裝及使用 Microsoft Online Services 模組的詳細資訊。 這些說明也將告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟與同步處理。<BR>如果您尚未安裝您的指令碼會失敗，因為 Get-cstenant 指令程式將無法使用這些 cmdlet。



</div>

之後您是否已設定 Office 365，並建立 Office 365 服務主體的 Lync Server 2013 和 Exchange 2013 之後，您接著需要這些服務主體中註冊您的認證。 為了完成這項作業，您首先必須取得副檔名為 .CER 的 X.509 Base64 檔案。 接著此憑證將會套用至 Office 365 服務主體。

當您取得 X.509 憑證時，啟動的 Microsoft Online Services 模組 （按一下 [**開始]**、 [**所有程式]**、 按一下 [ **Microsoft Online Services**]，然後按一下 [ **Microsoft Online Services 模組適用於 Windows PowerShell**）。 服務模組開啟後，請輸入下列命令以匯入 Microsoft Online Windows PowerShell 模組包含可用來管理服務主體的 cmdlet:

    Import-Module MSOnlineExtended

匯入模組後，請鍵入下列命令並按下 ENTER 鍵，以連線至 Office 365：

    Connect-MsolService

按下 ENTER 鍵後，將會出現認證對話方塊。請在對話方塊內輸入您的 Office 365 使用者名稱和密碼，然後按一下 [確定]。

一旦連線至 Office 365，您就可以執行下列命令以傳回有關服務主體的資訊：

    Get-MsolServicePrincipal

您能以類似的方式為所有服務主體取得資訊：

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

下一個步驟為匯入、編碼以及指派 X.509 憑證。 若要匯入並進行編碼的憑證，使用下列 Windows PowerShell 命令，所指定的完整檔案路徑，請務必您。當您呼叫匯入方法的 CER 檔案：

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

憑證匯入且完成編碼後，接著您可以將憑證指派至 Office 365 服務主體。 若要執行該動作，首先，請使用 Get-MsolServicePrincipal 擷取 Lync Server 與 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值；AppPrincipalId 屬性值將會用來識別指派憑證的服務主體。 AppPrincipalId 屬性值，是針對 Lync Server 2013 手中時，使用下列命令來指派憑證給 Lync Server （StartDate 和 EndDate 屬性，應對應至憑證的有效期） 的 Office 365 版本：

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

這次使用 Exchange 2013 的 AppPrincipalId 屬性值時，應該重複命令。

日後如需刪除該憑證，您可透過先擷取憑證的 KeyId 來完成作業：

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

該指令將會以這種方式傳回資料：

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

接著您可以用類似這樣的命令來刪除憑證：

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

除了指派的憑證中，您也必須藉由新增您的內部部署版本的 Lync Server 2013 伺服器主體名稱，以設定 Exchange online 的 Office 365 服務主要名稱。 這可以藉由在 Microsoft Online Services PowerShell 工作階段中執行下列四種幾行：

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

