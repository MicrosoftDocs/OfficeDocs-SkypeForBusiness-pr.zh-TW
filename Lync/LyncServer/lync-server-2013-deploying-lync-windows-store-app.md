---
title: Lync Server 2013：部署 Lync Windows Store 應用程式
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
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="71ed1-102">在 Lync Server 2013 中部署 Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="71ed1-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71ed1-103">_**主題上次修改日期：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="71ed1-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="71ed1-104">在讓使用者使用 Lync Windows Store 應用程式之前，請確定您的部署符合[Lync Server 2013 的 Lync Windows store 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71ed1-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="71ed1-105">如需設定 Lync Server 2013 以支援 Lync Windows Store 應用程式的詳細資訊，請參閱 NextHop 博客文章：「Lync Server 自動探索和 Lync Windows Store App [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)」。</span><span class="sxs-lookup"><span data-stu-id="71ed1-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="71ed1-106">在伺服器環境設定正確之後，您可以搜尋「Lync」，讓使用者從 Windows 網上商店下載 Lync 應用程式。</span><span class="sxs-lookup"><span data-stu-id="71ed1-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="71ed1-107">啟用 Lync Windows Store 應用程式的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="71ed1-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="71ed1-108">Lync Server 2013 的累計更新：2013年6月新增 Lync Windows Store 應用程式用戶端的多重要素驗證支援。</span><span class="sxs-lookup"><span data-stu-id="71ed1-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="71ed1-109">除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin），在使用者登入 Lync 會議時驗證外部使用者。</span><span class="sxs-lookup"><span data-stu-id="71ed1-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="71ed1-110">若要啟用多重要素驗證，您需要在 Lync Server 2013 中部署 Active Directory Federation Services （AD FS）同盟伺服器並啟用被動式驗證。</span><span class="sxs-lookup"><span data-stu-id="71ed1-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="71ed1-111">設定 AD FS 之後，試圖加入 Lync 會議的外部使用者會得到一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼質詢，以及您已設定的任何其他驗證方法.</span><span class="sxs-lookup"><span data-stu-id="71ed1-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="71ed1-112">如果您打算針對 Lync Windows Store 應用程式設定針對多重要素驗證的 AD FS，請務必考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="71ed1-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="71ed1-113">Lync Server 2013 含 Lync Server 2013 的累積更新：至少需要6月2013。</span><span class="sxs-lookup"><span data-stu-id="71ed1-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="71ed1-114">Lync 2013 傳統型用戶端不需要 Lync Server 2013 的累計更新：年6月2013，因此可能會顯示被動驗證，因為 Lync 2013 用戶端可以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="71ed1-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="71ed1-115">不過，Lync Windows Store app 用戶端的驗證程式將無法完成，且不會顯示任何通知或錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="71ed1-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="71ed1-116">伺服器必須設定為 [被動驗證] 是提供的唯一驗證類型。</span><span class="sxs-lookup"><span data-stu-id="71ed1-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="71ed1-117">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，讓來自 Lync Windows Store 應用程式用戶端的所有要求都是由同一個前端伺服器來處理。</span><span class="sxs-lookup"><span data-stu-id="71ed1-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="71ed1-118">當您在 Lync Server 與 AD FS 伺服器之間建立信賴方信任時，請指派一個足夠長的權杖有效期，以超過 Lync 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="71ed1-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="71ed1-119">通常，240分鐘的標記生活就足夠了。</span><span class="sxs-lookup"><span data-stu-id="71ed1-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="71ed1-120">**設定多重要素驗證**</span><span class="sxs-lookup"><span data-stu-id="71ed1-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="71ed1-121">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="71ed1-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="71ed1-122">如需詳細資訊，請參閱 Active Directory Federation Services 2.0 部署<http://go.microsoft.com/fwlink/p/?linkid=267511>指南，網址為。</span><span class="sxs-lookup"><span data-stu-id="71ed1-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="71ed1-123">建立適用于 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="71ed1-123">Create certificates for AD FS.</span></span> <span data-ttu-id="71ed1-124">如需詳細資訊，請參閱與部署 AD FS 之方案的 [同盟伺服器憑證] 區段，以便與單一登入主題搭配使用[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)。</span><span class="sxs-lookup"><span data-stu-id="71ed1-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="71ed1-125">從 Windows PowerShell 命令列介面，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="71ed1-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="71ed1-126">執行下列命令以建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="71ed1-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="71ed1-127">設定下列信賴方規則：</span><span class="sxs-lookup"><span data-stu-id="71ed1-127">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="71ed1-128">可避免登入的已知問題</span><span class="sxs-lookup"><span data-stu-id="71ed1-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="71ed1-129">在執行 Lync Windows Store 應用程式的裝置上未正確設定時間與日期</span><span class="sxs-lookup"><span data-stu-id="71ed1-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="71ed1-130">裝置上的 [時間] 設定必須與伺服器上的 [時間] 設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="71ed1-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="71ed1-131">對於 Microsoft Surface 之類的裝置，以及執行未加入網域之 Windows RT 的其他裝置而言，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="71ed1-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="71ed1-132">若要從時間伺服器自動設定這些裝置上的時間，請在裝置上提升許可權的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="71ed1-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="71ed1-133">Lync Windows Store app 無法存取 Lync server 或服務</span><span class="sxs-lookup"><span data-stu-id="71ed1-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="71ed1-134">Lync Windows Store 應用程式可能無法透過網路介面卡（例如 4G LTE USB 數據機）來存取 Lync server 或服務，而不會在 Windows 8 中以物理裝置的方式進行註冊。</span><span class="sxs-lookup"><span data-stu-id="71ed1-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="71ed1-135">即使傳統型應用程式和瀏覽器能夠存取其他伺服器和網站，Lync Windows Store 應用程式也可能會有這個問題。</span><span class="sxs-lookup"><span data-stu-id="71ed1-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="71ed1-136">Lync Windows Store 應用程式無法使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 Edge 伺服器登入</span><span class="sxs-lookup"><span data-stu-id="71ed1-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="71ed1-137">如果您的拓朴是由 Lync Server 2010 與 Office 通訊伺服器 2007 R2 Edge 伺服器組成，您將需要執行 Lync Server 2010 累積更新中提供的更新版本的拓撲產生器：年 7 2013 月。</span><span class="sxs-lookup"><span data-stu-id="71ed1-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="71ed1-138">較舊版本的拓撲建立器不會建立 Office 通訊伺服器 2007 Edge 伺服器所需的對應，因此 Lync Windows Store 應用程式用戶端無法登入。</span><span class="sxs-lookup"><span data-stu-id="71ed1-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="71ed1-139">必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="71ed1-139">The following steps are required:</span></span>

1.  <span data-ttu-id="71ed1-140">安裝 Lync Server 2010 的累積更新： Lync Server 2010 pool 和 Lync Server 2010 控制器上的2013。</span><span class="sxs-lookup"><span data-stu-id="71ed1-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="71ed1-141">您可以執行下列動作，更新 Lync 自動探索設定，以指出外部 SIP 輸入點為邊緣伺服器位址：</span><span class="sxs-lookup"><span data-stu-id="71ed1-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="71ed1-142">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="71ed1-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="71ed1-143">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="71ed1-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="71ed1-144">Lync Windows Store 應用程式無法登入，因為證書名稱驗證失敗</span><span class="sxs-lookup"><span data-stu-id="71ed1-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="71ed1-145">未執行最新版本 Lync Windows Store 應用程式的 Office 365 使用者可能會發生登入問題。</span><span class="sxs-lookup"><span data-stu-id="71ed1-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="71ed1-146">這個問題通常會在使用多個網域時（例如，當 SIP URI 為**userA@domainZ.com**但邊緣伺服器為**sip.domainX.com**時）。</span><span class="sxs-lookup"><span data-stu-id="71ed1-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="71ed1-147">若要修正此問題，使用者應該安裝最新版本的 Lync Windows Store 應用程式，這也需要 Windows 8.1。</span><span class="sxs-lookup"><span data-stu-id="71ed1-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="71ed1-148">使用 Lync Windows Store 應用程式記錄來排查問題</span><span class="sxs-lookup"><span data-stu-id="71ed1-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="71ed1-149">您可以使用裝置上產生的記錄來疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="71ed1-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="71ed1-150">記錄會儲存在下列資料夾中：</span><span class="sxs-lookup"><span data-stu-id="71ed1-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="71ed1-151">% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\LocalState\\追蹤</span><span class="sxs-lookup"><span data-stu-id="71ed1-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="71ed1-152">在您從使用者取得記錄前，請確定已開啟記錄，然後要求使用者儲存記錄，讓儲存在記憶體中的所有資訊都儲存在硬碟上的檔案中。</span><span class="sxs-lookup"><span data-stu-id="71ed1-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="71ed1-153">**開啟記錄**</span><span class="sxs-lookup"><span data-stu-id="71ed1-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="71ed1-154">在裝置上開啟 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="71ed1-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="71ed1-155">從畫面右側滑動。</span><span class="sxs-lookup"><span data-stu-id="71ed1-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="71ed1-156">如果您是使用滑鼠，請指向畫面右上角，然後將滑鼠指標向下移動畫面。</span><span class="sxs-lookup"><span data-stu-id="71ed1-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="71ed1-157">選取 [**設定**]，選取 [**選項**]，然後將 [**診斷記錄**] 設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="71ed1-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="71ed1-158">如果您先前已關閉**診斷記錄**，您必須重新開機 Lync。</span><span class="sxs-lookup"><span data-stu-id="71ed1-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="71ed1-159">若要重新開機 Lync，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="71ed1-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="71ed1-160">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="71ed1-160">Restart the device.</span></span>
    
      - <span data-ttu-id="71ed1-161">結束 Lync 工作並再次啟動 app。</span><span class="sxs-lookup"><span data-stu-id="71ed1-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="71ed1-162">若要結束工作，請開啟 Windows [工作管理員]，選取 [ **Lync**]，然後按一下 [**結束**工作]。</span><span class="sxs-lookup"><span data-stu-id="71ed1-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="71ed1-163">如果沒有列出 Lync，請在 [**背景處理**程式] 下，按一下 [**更多詳細資料**]，然後尋找 lync。</span><span class="sxs-lookup"><span data-stu-id="71ed1-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="71ed1-164">**儲存記錄**</span><span class="sxs-lookup"><span data-stu-id="71ed1-164">**To save the logs**</span></span>

1.  <span data-ttu-id="71ed1-165">在裝置上開啟 Lync Windows Store 應用程式。</span><span class="sxs-lookup"><span data-stu-id="71ed1-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="71ed1-166">嘗試登入。</span><span class="sxs-lookup"><span data-stu-id="71ed1-166">Try signing in.</span></span>

3.  <span data-ttu-id="71ed1-167">從畫面右側滑動。</span><span class="sxs-lookup"><span data-stu-id="71ed1-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="71ed1-168">如果您是使用滑鼠，請指向畫面右上角，然後將滑鼠指標向下移動畫面。</span><span class="sxs-lookup"><span data-stu-id="71ed1-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="71ed1-169">選取 [**設定**]，選取 [**關於**]，然後選取 [**儲存記錄**]。</span><span class="sxs-lookup"><span data-stu-id="71ed1-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

