---
title: Lync Server 2013：部署 Lync Windows Store 應用程式
description: Lync Server 2013：部署 Lync Windows Store 應用程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571709"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="cc775-103">在 Lync Server 2013 中部署 Lync Windows 應用商店應用程式</span><span class="sxs-lookup"><span data-stu-id="cc775-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc775-104">_**主題上次修改日期：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="cc775-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="cc775-105">讓使用者可以使用 Lync Windows Store 應用程式之前，請確定您的部署符合 [Lync Server 2013 的 Lync Windows 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc775-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="cc775-106">如需設定 Lync Server 2013 以支援 Lync Windows Store 應用程式的詳細資訊，請參閱 NextHop 的博客文章：「Lync Server 自動探索」和 Lync Windows Store App，網址為 [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) 。</span><span class="sxs-lookup"><span data-stu-id="cc775-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="cc775-107">正確設定伺服器環境之後，您可以搜尋 "Lync"，以引導使用者從 Windows 存放區下載 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc775-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="cc775-108">啟用 Lync Windows Store 應用程式的 Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="cc775-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="cc775-109">Lync Server 2013 的累計更新：六月2013新增對 Lync Windows Store 應用程式用戶端的多重要素驗證的支援。</span><span class="sxs-lookup"><span data-stu-id="cc775-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="cc775-110">除了使用者名稱和密碼之外，您還可以要求其他驗證方法，例如智慧卡或 Pin 碼，以便在外部使用者登入 Lync 會議時進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cc775-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="cc775-111">若要啟用多重要素驗證，請在 Lync Server 2013 中部署 Active Directory Federation Service (AD FS) 同盟伺服器並啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="cc775-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="cc775-112">設定 AD FS 後，嘗試加入 Lync 會議的外部使用者會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您已設定的任何其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="cc775-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="cc775-113">如果您打算設定 AD FS 以進行 Lync Windows Store 應用程式的多重要素驗證，則以下是重要考慮：</span><span class="sxs-lookup"><span data-stu-id="cc775-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="cc775-114">Lync Server 2013 （具有 Lync Server 2013 的累計更新）：至少需要6月2013。</span><span class="sxs-lookup"><span data-stu-id="cc775-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="cc775-115">Lync 2013 桌面用戶端不需要 Lync Server 2013 的累計更新：6月2013，因此可能會顯示被動驗證可正常運作，因為 Lync 2013 用戶端可以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cc775-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="cc775-116">不過，Lync Windows Store 應用程式用戶端的驗證程式會無法完成，而且不會顯示任何通知或錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="cc775-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc775-117">必須設定伺服器，讓被動驗證成為唯一提供的驗證類型。</span><span class="sxs-lookup"><span data-stu-id="cc775-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc775-118">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 持久性，使來自 Lync Windows Store 應用程式用戶端的所有要求都是由同一部前端伺服器處理。</span><span class="sxs-lookup"><span data-stu-id="cc775-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc775-119">當您在 Lync Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派一個足夠長的權杖壽命，以橫跨 Lync 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="cc775-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="cc775-120">通常，在240分鐘的標記壽命已足夠。</span><span class="sxs-lookup"><span data-stu-id="cc775-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="cc775-121">**設定 Multi-Factor 驗證**</span><span class="sxs-lookup"><span data-stu-id="cc775-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="cc775-122">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="cc775-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="cc775-123">如需詳細資訊，請參閱《 Active Directory Federation Services 2.0 部署指南》 <https://go.microsoft.com/fwlink/p/?linkid=267511> 。</span><span class="sxs-lookup"><span data-stu-id="cc775-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="cc775-124">建立 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="cc775-124">Create certificates for AD FS.</span></span> <span data-ttu-id="cc775-125">如需詳細資訊，請參閱規劃及部署 AD FS 的「同盟伺服器憑證」一節，以與單一登入主題搭配使用 [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) 。</span><span class="sxs-lookup"><span data-stu-id="cc775-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="cc775-126">在 [Windows PowerShell] 命令列介面中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cc775-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="cc775-127">執行下列命令來建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="cc775-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="cc775-128">設定下列信賴憑證者規則：</span><span class="sxs-lookup"><span data-stu-id="cc775-128">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="cc775-129">可避免登入的已知問題</span><span class="sxs-lookup"><span data-stu-id="cc775-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="cc775-130">在執行 Lync Windows Store 應用程式的裝置上，未正確設定時間及日期</span><span class="sxs-lookup"><span data-stu-id="cc775-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="cc775-131">裝置上的時間設定必須與伺服器上的時間設定同步。</span><span class="sxs-lookup"><span data-stu-id="cc775-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="cc775-132">這對 Microsoft Surface 等裝置及其他執行 Windows RT 但未加入網域的裝置尤其重要。</span><span class="sxs-lookup"><span data-stu-id="cc775-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="cc775-133">若要在時間伺服器自動設定這些裝置上的時間，請在裝置上以提升許可權的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cc775-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="cc775-134">Lync Windows Store 應用程式無法存取 Lync 伺服器或服務</span><span class="sxs-lookup"><span data-stu-id="cc775-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="cc775-135">Lync Windows Store 應用程式可能無法透過網路介面卡（如 4G LTE USB 數據機）來存取 Lync server 或服務，其不會以 Windows 8 註冊為實體裝置。</span><span class="sxs-lookup"><span data-stu-id="cc775-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="cc775-136">即使桌面應用程式和瀏覽器可以存取其他伺服器和網站，Lync Windows Store 應用程式也可能會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="cc775-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="cc775-137">Lync Windows Store 應用程式無法使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 Edge Server 登入</span><span class="sxs-lookup"><span data-stu-id="cc775-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="cc775-138">如果您的拓撲包含 Lync Server 2010 與 Office 通訊伺服器 2007 R2 Edge Server，則您需要在 Lync Server 2010：7月2013的累計更新中，執行拓撲產生器的更新版本。</span><span class="sxs-lookup"><span data-stu-id="cc775-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="cc775-139">舊版的拓撲產生器不會建立所需的 Office 通訊伺服器 2007 Edge Server 對應，所以 Lync Windows Store 應用程式用戶端無法登入。</span><span class="sxs-lookup"><span data-stu-id="cc775-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="cc775-140">需要下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cc775-140">The following steps are required:</span></span>

1.  <span data-ttu-id="cc775-141">在 Lync Server 2010 集區和 Lync Server 2010 Director 上安裝 Lync Server 2010：7月2013的累計更新。</span><span class="sxs-lookup"><span data-stu-id="cc775-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="cc775-142">執行下列動作，更新 Lync AutoDiscover 設定，以指出外部 SIP 輸入點為 Edge server 位址：</span><span class="sxs-lookup"><span data-stu-id="cc775-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="cc775-143">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="cc775-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="cc775-144">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cc775-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="cc775-145">因為憑證名稱驗證失敗，所以 Lync Windows Store 應用程式無法登入</span><span class="sxs-lookup"><span data-stu-id="cc775-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="cc775-146">未執行最新版本 Lync Windows Store 應用程式的 Microsoft 365 或 Office 365 使用者可能會發生登入問題。</span><span class="sxs-lookup"><span data-stu-id="cc775-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="cc775-147">使用多個網域時，通常會發生此問題 (例如，當 SIP URI 是 **userA@domainZ.com** ，但 Edge Server 是 **sip.domainX.com**) 。</span><span class="sxs-lookup"><span data-stu-id="cc775-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="cc775-148">若要修正此問題，使用者應安裝最新版的 Lync Windows Store 應用程式，該應用程式也需要 Windows 8.1。</span><span class="sxs-lookup"><span data-stu-id="cc775-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="cc775-149">使用 Lync Windows Store 應用程式記錄檔來疑難排解問題</span><span class="sxs-lookup"><span data-stu-id="cc775-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="cc775-150">您可以使用在裝置上產生的記錄檔來疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="cc775-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="cc775-151">記錄檔會儲存在下列資料夾中：</span><span class="sxs-lookup"><span data-stu-id="cc775-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="cc775-152">% LocalAppData% \\ \\ LyncMX \_ 8wekyb3d8bbwe \\ LocalState \\ 追蹤</span><span class="sxs-lookup"><span data-stu-id="cc775-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="cc775-153">在您從使用者取得記錄之前，請確定已開啟記錄，然後要求使用者儲存記錄，以便儲存在記憶體中的所有資訊也都會儲存至硬碟上的檔案。</span><span class="sxs-lookup"><span data-stu-id="cc775-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="cc775-154">**開啟記錄**</span><span class="sxs-lookup"><span data-stu-id="cc775-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="cc775-155">開啟裝置上的 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc775-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="cc775-156">從畫面右側滑動。</span><span class="sxs-lookup"><span data-stu-id="cc775-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="cc775-157">如果您是使用滑鼠，請指向螢幕的右上角，然後將滑鼠指標移至螢幕。</span><span class="sxs-lookup"><span data-stu-id="cc775-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="cc775-158">選取 [ **設定**]，選取 [ **選項**]，然後將 [ **診斷記錄** ] 設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="cc775-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="cc775-159">如果 **診斷記錄** 先前已經關閉，您必須重新開機 Lync。</span><span class="sxs-lookup"><span data-stu-id="cc775-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="cc775-160">若要重新開機 Lync，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="cc775-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="cc775-161">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="cc775-161">Restart the device.</span></span>
    
      - <span data-ttu-id="cc775-162">結束 Lync 工作並重新啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc775-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="cc775-163">若要結束任務，請開啟 [Windows 工作管理員]，選取 [ **Lync**]，然後按 [ **結束**工作]。</span><span class="sxs-lookup"><span data-stu-id="cc775-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="cc775-164">如果未列出 Lync，請按一下 [ **更多詳細資料** ]，然後在 [ **背景處理**程式] 下尋找 lync。</span><span class="sxs-lookup"><span data-stu-id="cc775-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="cc775-165">**儲存記錄**</span><span class="sxs-lookup"><span data-stu-id="cc775-165">**To save the logs**</span></span>

1.  <span data-ttu-id="cc775-166">開啟裝置上的 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc775-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="cc775-167">嘗試登入。</span><span class="sxs-lookup"><span data-stu-id="cc775-167">Try signing in.</span></span>

3.  <span data-ttu-id="cc775-168">從畫面右側滑動。</span><span class="sxs-lookup"><span data-stu-id="cc775-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="cc775-169">如果您是使用滑鼠，請指向螢幕的右上角，然後將滑鼠指標移至螢幕。</span><span class="sxs-lookup"><span data-stu-id="cc775-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="cc775-170">選取 [ **設定**]，選取 [ **關於**]，然後選取 [ **儲存記錄**檔]。</span><span class="sxs-lookup"><span data-stu-id="cc775-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

