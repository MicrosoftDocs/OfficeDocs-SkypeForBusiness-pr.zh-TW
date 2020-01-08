---
title: Lync Server 2013：在跨內部部署環境中配置 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="dc354-102">在跨內部部署環境中設定 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc354-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc354-103">_**主題上次修改日期：** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="dc354-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="dc354-104">在跨內部部署設定中，您的一些使用者是駐留在內部部署的 Microsoft Lync Server 2013，而其他使用者則是位於 Office 365 版的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="dc354-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="dc354-105">若要在跨內部部署環境中設定伺服器對伺服器的驗證，您必須先設定您的 Lync Server 2013 內部部署安裝，以信任 Office 365 授權伺服器。</span><span class="sxs-lookup"><span data-stu-id="dc354-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="dc354-106">您可以執行下列 Lync Server 管理命令介面腳本來執行此程式中的初始步驟：</span><span class="sxs-lookup"><span data-stu-id="dc354-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="dc354-107">請記住，租使用者的領域名稱稱通常與組織名稱不同;事實上，領域名稱稱幾乎總是與租使用者識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="dc354-107">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="dc354-108">因此，腳本中的第一行是用來傳回指定租使用者的 TenantId 屬性值（在此例中為 fabrikam.com），然後將該名稱指派給 $TenantId 的變數：</span><span class="sxs-lookup"><span data-stu-id="dc354-108">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="dc354-109">在腳本完成之後，您必須設定 Lync Server 2013 與授權伺服器之間的信任關係，以及 Exchange 2013 與授權伺服器之間的第二個信任關係。</span><span class="sxs-lookup"><span data-stu-id="dc354-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="dc354-110">這只能使用 Microsoft Online Services Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="dc354-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc354-111">如果您尚未安裝 Microsoft Online 服務 Cmdlet，您必須先執行兩個作業，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="dc354-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="dc354-112">首先，請下載並安裝64位版本的 Microsoft Online Services 登入小幫手。</span><span class="sxs-lookup"><span data-stu-id="dc354-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="dc354-113">安裝完成後，請下載並安裝適用于 Windows PowerShell 的 Microsoft Online Services 模組64位版本。</span><span class="sxs-lookup"><span data-stu-id="dc354-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="dc354-114">您可以在 Office 365 網站上找到安裝及使用 Microsoft Online Services 模組的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dc354-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="dc354-115">這些指示也會告訴您如何設定 Office 365 與 Active Directory 之間的單一登入、同盟及同步處理。</span><span class="sxs-lookup"><span data-stu-id="dc354-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="dc354-116">如果您還沒有安裝這些 Cmdlet，您的腳本將會失敗，因為 CsTenant Cmdlet 將無法使用。</span><span class="sxs-lookup"><span data-stu-id="dc354-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="dc354-117">在您設定 Office 365 之後，且為 Lync Server 2013 和 Exchange 2013 建立 Office 365 服務主體之後，您就必須使用這些服務主體註冊您的認證。</span><span class="sxs-lookup"><span data-stu-id="dc354-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="dc354-118">若要這樣做，您必須先取得 x.509 Base64 儲存為。CER 檔案。</span><span class="sxs-lookup"><span data-stu-id="dc354-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="dc354-119">此憑證隨即會套用至 Office 365 服務原則。</span><span class="sxs-lookup"><span data-stu-id="dc354-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="dc354-120">取得 x.509 憑證之後，請啟動 Microsoft Online Services 模組（按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **microsoft online 服務**]，然後按一下 [ **Windows PowerShell 的 microsoft online services 模組**]）。</span><span class="sxs-lookup"><span data-stu-id="dc354-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="dc354-121">[服務] 模組開啟後，請輸入下列內容，以匯入包含可用來管理服務主體之 Cmdlet 的 Microsoft Online Windows PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="dc354-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="dc354-122">匯入模組後，請輸入下列命令，然後按 ENTER，即可連線到 Office 365：</span><span class="sxs-lookup"><span data-stu-id="dc354-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="dc354-123">按下 ENTER 後，就會出現 [認證] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="dc354-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="dc354-124">在對話方塊中輸入您的 Office 365 使用者名稱和密碼，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="dc354-124">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="dc354-125">一旦您連線到 Office 365，您就可以執行下列命令，以傳回服務主體的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="dc354-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="dc354-126">您應該會針對所有的服務主體取得類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="dc354-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="dc354-127">下一步是匯入、編碼並指派 x.509 憑證。</span><span class="sxs-lookup"><span data-stu-id="dc354-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="dc354-128">若要匯入並編碼憑證，請使用下列 Windows PowerShell 命令，確定要指定完整的檔案路徑。CER 檔案，當您呼叫 Import 方法時：</span><span class="sxs-lookup"><span data-stu-id="dc354-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="dc354-129">在匯入並編碼憑證之後，您就可以將憑證指派給您的 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="dc354-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="dc354-130">若要這樣做，請先使用 MsolServicePrincipal，以取得 Lync Server 和 Microsoft Exchange 服務主體的 AppPrincipalId 屬性值;AppPrincipalId 屬性的值將用來識別指派憑證的服務主體。</span><span class="sxs-lookup"><span data-stu-id="dc354-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="dc354-131">使用 Lync Server 2013 的 AppPrincipalId 屬性值，請使用下列命令，將憑證指派給 Office 365 版本的 Lync Server （[開始] 和 [結束] 屬性應該對應到憑證的有效期）：</span><span class="sxs-lookup"><span data-stu-id="dc354-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="dc354-132">接著，請重複執行命令，這次是使用 Exchange 2013 的 AppPrincipalId 屬性值。</span><span class="sxs-lookup"><span data-stu-id="dc354-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="dc354-133">如果您稍後需要刪除該憑證，您可以先檢索憑證的 KeyId，以執行此動作：</span><span class="sxs-lookup"><span data-stu-id="dc354-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="dc354-134">該命令會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="dc354-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="dc354-135">接著，您可以使用類似以下的命令來刪除證書：</span><span class="sxs-lookup"><span data-stu-id="dc354-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="dc354-136">除了指派憑證之外，您也必須為內部部署版本的 Lync Server 2013 新增伺服器主要名稱，以設定 Exchange Online 的 Office 365 服務主體。</span><span class="sxs-lookup"><span data-stu-id="dc354-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="dc354-137">您可以在 Microsoft 線上服務 PowerShell 會話中執行下列四行，以完成此動作：</span><span class="sxs-lookup"><span data-stu-id="dc354-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

