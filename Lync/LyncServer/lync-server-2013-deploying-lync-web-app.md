---
title: Lync Server 2013：部署 Lync Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="09e32-102">在 Lync Server 2013 中部署 Lync Web App</span><span class="sxs-lookup"><span data-stu-id="09e32-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e32-103">_**主題上次修改日期：** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="09e32-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="09e32-104">Lync Web App 是與 Lync Server 2013 一起安裝的網際網路 Information Services （IIS） Web 用戶端，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="09e32-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="09e32-105">若要在伺服器上啟用 Lync Web App，或將 Web 用戶端部署給使用者，則無需執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="09e32-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="09e32-106">每當使用者按一下會議 URL，但沒有安裝 Lync 2013 用戶端時，系統會顯示使用最新版本的 Lync Web App 加入會議的選項。</span><span class="sxs-lookup"><span data-stu-id="09e32-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="09e32-107">Lync Web App 中的 [語音]、[影片] 和 [共用] 功能需要 Microsoft ActiveX 控制項。</span><span class="sxs-lookup"><span data-stu-id="09e32-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="09e32-108">您可以在出現提示時，事先安裝 ActiveX 控制項或允許使用者安裝，這會在第一次使用 Lync Web App 時，或第一次存取需要 ActiveX 控制項的功能時進行安裝。</span><span class="sxs-lookup"><span data-stu-id="09e32-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="09e32-109">在 Lync Server 2013 Edge 伺服器部署中，Lync Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="09e32-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="09e32-110">您也必須發佈簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="09e32-110">You must also publish simple URLs.</span></span> <span data-ttu-id="09e32-111">如需詳細資訊，請參閱為<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 設定反向 proxy 伺服器</A>以及<A href="lync-server-2013-planning-for-simple-urls.md">規劃 lync server 2013 中的簡單 url</A>。</span><span class="sxs-lookup"><span data-stu-id="09e32-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="09e32-112">啟用 Lync Web App 的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="09e32-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="09e32-113">Lync Server 2013 版本的 Lync Web App 支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="09e32-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="09e32-114">除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin），以驗證在登入 Lync 會議時從外部網路加入的使用者。</span><span class="sxs-lookup"><span data-stu-id="09e32-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="09e32-115">您可以透過部署 Active Directory Federation Services （AD FS）同盟伺服器並啟用 Lync Server 2013 中的被動式驗證，來啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="09e32-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="09e32-116">設定 AD FS 之後，試圖加入 Lync 會議的外部使用者會得到一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼質詢，以及您已設定的任何其他驗證方法.</span><span class="sxs-lookup"><span data-stu-id="09e32-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="09e32-117">如果您打算針對多重要素驗證設定 AD FS，請務必考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="09e32-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="09e32-118">如果會議參與者和召集人都在同一個組織中，或都來自 AD FS 同盟組織，則多重要素 ADFS 驗證就會運作。</span><span class="sxs-lookup"><span data-stu-id="09e32-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="09e32-119">因為 Lync server web 基礎結構目前不支援 Lync 聯盟使用者，所以多重要素 ADFS 驗證無法運作。</span><span class="sxs-lookup"><span data-stu-id="09e32-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="09e32-120">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，讓 Lync Web App 用戶端的所有要求都是由同一個前端伺服器來處理。</span><span class="sxs-lookup"><span data-stu-id="09e32-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="09e32-121">當您在 Lync Server 與 AD FS 伺服器之間建立信賴方信任時，請指派一個足夠長的權杖有效期，以超過 Lync 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="09e32-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="09e32-122">通常，240分鐘的標記生活就足夠了。</span><span class="sxs-lookup"><span data-stu-id="09e32-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="09e32-123">此設定不會套用至 Lync mobile 用戶端。</span><span class="sxs-lookup"><span data-stu-id="09e32-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="09e32-124">**設定多重要素驗證**</span><span class="sxs-lookup"><span data-stu-id="09e32-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="09e32-125">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="09e32-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="09e32-126">如需詳細資訊，請參閱 Active Directory Federation Services 2.0 部署指南，網址為<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="09e32-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="09e32-127">建立適用于 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="09e32-127">Create certificates for AD FS.</span></span> <span data-ttu-id="09e32-128">如需詳細資訊，請參閱與部署 AD FS 之方案的 [同盟伺服器憑證] 區段，以便與單一登入主題搭配使用[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)。</span><span class="sxs-lookup"><span data-stu-id="09e32-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="09e32-129">從 Windows PowerShell 命令列介面，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="09e32-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="09e32-130">執行下列命令以建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="09e32-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="09e32-131">設定下列信賴方規則：</span><span class="sxs-lookup"><span data-stu-id="09e32-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="09e32-132">BranchCache 設定</span><span class="sxs-lookup"><span data-stu-id="09e32-132">BranchCache Configuration</span></span>

<span data-ttu-id="09e32-133">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能會干擾 Lync Web App 網頁元件。</span><span class="sxs-lookup"><span data-stu-id="09e32-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="09e32-134">若要避免 Lync Web App 使用者的問題，請確定未啟用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="09e32-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="09e32-135">如需有關停用 BranchCache 的詳細資訊，請參閱 BranchCache 部署指南，此手冊位於 Microsoft 下載中心[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)的 Word 格式中，在 Windows Server 2008 R2 技術文件庫的 HTML 格式[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)中提供。</span><span class="sxs-lookup"><span data-stu-id="09e32-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="09e32-136">驗證 Lync Web App 部署</span><span class="sxs-lookup"><span data-stu-id="09e32-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="09e32-137">您可以使用 CsUcwaConference Cmdlet 來確認一組測試使用者可以使用整合通訊 Web API （UCWA）參與會議。</span><span class="sxs-lookup"><span data-stu-id="09e32-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="09e32-138">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Test CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。</span><span class="sxs-lookup"><span data-stu-id="09e32-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="09e32-139">Windows Server 2008 R2 上的外掛程式安裝疑難排解</span><span class="sxs-lookup"><span data-stu-id="09e32-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="09e32-140">如果您在執行 Windows Server 2008 R2 的電腦上安裝外掛程式失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。</span><span class="sxs-lookup"><span data-stu-id="09e32-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="09e32-141">**在 Internet Explorer 中修改安全性設定**</span><span class="sxs-lookup"><span data-stu-id="09e32-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="09e32-142">開啟 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="09e32-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="09e32-143">按一下 [**工具**]，按一下 [**網際網路選項**]，然後按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="09e32-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="09e32-144">向下滾動至 [**安全性**] 區段。</span><span class="sxs-lookup"><span data-stu-id="09e32-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="09e32-145">清除 [**不要將加密的網頁存到磁片**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="09e32-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="09e32-146">如果選取此選項，當您嘗試從 Lync Web App 下載附件時，此設定也會導致錯誤。</span><span class="sxs-lookup"><span data-stu-id="09e32-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="09e32-147">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="09e32-147">Rejoin the meeting.</span></span> <span data-ttu-id="09e32-148">外掛程式應該會下載，不會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="09e32-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="09e32-149">**修改 DisableMSI 註冊表設定**</span><span class="sxs-lookup"><span data-stu-id="09e32-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="09e32-150">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="09e32-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="09e32-151">若要存取 [登錄編輯程式]，請輸入**regedit**。</span><span class="sxs-lookup"><span data-stu-id="09e32-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="09e32-152">流覽至 HKEY\_本機\_電腦\\軟體\\原則\\Microsoft\\Windows\\安裝程式。</span><span class="sxs-lookup"><span data-stu-id="09e32-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="09e32-153">編輯或新增類型為 REG\_DWORD 的 DisableMSI 登錄機碼，並將其設為0。</span><span class="sxs-lookup"><span data-stu-id="09e32-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="09e32-154">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="09e32-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09e32-155">請參閱</span><span class="sxs-lookup"><span data-stu-id="09e32-155">See Also</span></span>


[<span data-ttu-id="09e32-156">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="09e32-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="09e32-157">Lync Web App 支援的 Lync Server 2013 平臺</span><span class="sxs-lookup"><span data-stu-id="09e32-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

