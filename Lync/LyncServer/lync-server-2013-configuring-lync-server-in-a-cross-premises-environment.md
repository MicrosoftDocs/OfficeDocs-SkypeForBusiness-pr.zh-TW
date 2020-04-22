---
title: Lync Server 2013：在跨部署環境中設定 Lync Server
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
ms.openlocfilehash: 44d1f06fcbdbbba7400bf45857dad9ed57971363
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="afc0f-102">在跨部署環境中設定 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afc0f-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afc0f-103">_**主題上次修改日期：** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="afc0f-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="afc0f-104">在跨內部部署設定中，您的部分使用者是駐留在 Microsoft Lync Server 2013 的內部部署安裝，而其他使用者則位於 Lync Server 的 Office 365 版本上。</span><span class="sxs-lookup"><span data-stu-id="afc0f-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="afc0f-105">為了在跨部署環境中設定伺服器對伺服器的驗證，您必須先將 Lync Server 2013 的內部部署安裝設定為信任 Office 365 授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="afc0f-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="afc0f-106">您可以執行下列 Lync Server 管理命令介面腳本，以執行此程式的初始步驟：</span><span class="sxs-lookup"><span data-stu-id="afc0f-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="afc0f-p102">請記住，租用戶的領域名稱通常和組織名稱不同；事實上，領域名稱和租用戶 ID 幾乎相同。因此，指令碼第一行是用來為指定的租用戶傳回 TenantId 屬性值 (在這種情況下為 fabrikam.com)，接著將該名稱指派至變數 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="afc0f-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="afc0f-109">在腳本完成之後，您必須設定 Lync Server 2013 與授權伺服器之間的信任關係，以及 Exchange 2013 與授權伺服器之間的第二個信任關係。</span><span class="sxs-lookup"><span data-stu-id="afc0f-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="afc0f-110">唯有使用 Microsoft Online Services Cmdlet 才能完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="afc0f-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afc0f-111">如果您尚未安裝 Microsoft Online Services Cmdlet，那麼，您必需先完成兩個動作才能繼續進行。</span><span class="sxs-lookup"><span data-stu-id="afc0f-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="afc0f-112">首先，下載及安裝  Microsoft Online Services 登入小幫手 64 位元版本。</span><span class="sxs-lookup"><span data-stu-id="afc0f-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="afc0f-113">安裝完成後，請下載並安裝 Windows PowerShell 的64位版本的 Microsoft Online Services 模組。</span><span class="sxs-lookup"><span data-stu-id="afc0f-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="afc0f-114">您可以在 Office 365 網站找到有關安裝及使用 Microsoft Online Services 模組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="afc0f-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="afc0f-115">這些說明也將告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟與同步處理。</span><span class="sxs-lookup"><span data-stu-id="afc0f-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="afc0f-116">若尚未安裝這些 Cmdlet，您的腳本將會失敗，因為 Get-CsTenant Cmdlet 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="afc0f-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="afc0f-117">在您設定 Office 365 之後，以及建立 Lync Server 2013 和 Exchange 2013 的 Office 365 服務主體後，您就必須使用這些服務主體註冊您的認證。</span><span class="sxs-lookup"><span data-stu-id="afc0f-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="afc0f-118">為了完成這項作業，您首先必須取得副檔名為 .CER 的 X.509 Base64 檔案。</span><span class="sxs-lookup"><span data-stu-id="afc0f-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="afc0f-119">接著此憑證將會套用至 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="afc0f-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="afc0f-120">當您取得 x.509 憑證之後，請啟動 Microsoft Online Services 模組（按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft online 服務**]，然後按一下 [ **Windows PowerShell 的 microsoft online services 模組**]）。</span><span class="sxs-lookup"><span data-stu-id="afc0f-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="afc0f-121">在 [服務] 模組開啟之後，請輸入下列命令，以匯入 Microsoft Online Windows PowerShell 模組，其中包含可用於管理服務主體的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="afc0f-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="afc0f-122">匯入模組後，請鍵入下列命令並按下 ENTER 鍵，以連線至 Office 365：</span><span class="sxs-lookup"><span data-stu-id="afc0f-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="afc0f-123">按下 ENTER 鍵後，將會出現認證對話方塊。</span><span class="sxs-lookup"><span data-stu-id="afc0f-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="afc0f-124">在對話方塊中輸入您的 Microsoft 365 或 Office 365 使用者名稱和密碼，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="afc0f-124">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="afc0f-125">一旦連線至 Office 365，您就可以執行下列命令以傳回有關服務主體的資訊：</span><span class="sxs-lookup"><span data-stu-id="afc0f-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="afc0f-126">您能以類似的方式為所有服務主體取得資訊：</span><span class="sxs-lookup"><span data-stu-id="afc0f-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="afc0f-127">下一個步驟為匯入、編碼以及指派 X.509 憑證。</span><span class="sxs-lookup"><span data-stu-id="afc0f-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="afc0f-128">若要匯入和編碼憑證，請使用下列 Windows PowerShell 命令，確定指定您的完整檔案路徑。CER 檔案當您呼叫 Import 方法時：</span><span class="sxs-lookup"><span data-stu-id="afc0f-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="afc0f-129">憑證匯入且完成編碼後，接著您可以將憑證指派至 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="afc0f-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="afc0f-130">若要執行該動作，首先，請使用 Get-MsolServicePrincipal 擷取 Lync Server 與 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值；AppPrincipalId 屬性值將會用來識別指派憑證的服務主體。</span><span class="sxs-lookup"><span data-stu-id="afc0f-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="afc0f-131">使用 Lync Server 2013 的 AppPrincipalId 屬性值手頭，使用下列命令將憑證指派給 Lync Server 的 Office 365 版本（StartDate 和 EndDate 屬性應對應至憑證的有效期限）：</span><span class="sxs-lookup"><span data-stu-id="afc0f-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="afc0f-132">然後您應該重複執行此命令，這次使用 Exchange 2013 的 AppPrincipalId 屬性值。</span><span class="sxs-lookup"><span data-stu-id="afc0f-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="afc0f-133">日後如需刪除該憑證，您可透過先擷取憑證的 KeyId 來完成作業：</span><span class="sxs-lookup"><span data-stu-id="afc0f-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="afc0f-134">該指令將會以這種方式傳回資料：</span><span class="sxs-lookup"><span data-stu-id="afc0f-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="afc0f-135">接著您可以用類似這樣的命令來刪除憑證：</span><span class="sxs-lookup"><span data-stu-id="afc0f-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="afc0f-136">除了指派憑證之外，您還必須為您的 Lync Server 2013 的內部部署版本，新增伺服器主要名稱，以設定 Exchange Online 的 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="afc0f-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="afc0f-137">若要執行此動作，可在 Microsoft Online Services PowerShell 會話中執行下列四行：</span><span class="sxs-lookup"><span data-stu-id="afc0f-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

