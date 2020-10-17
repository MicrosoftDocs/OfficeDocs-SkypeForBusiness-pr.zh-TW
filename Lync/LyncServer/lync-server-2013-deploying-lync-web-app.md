---
title: Lync Server 2013：部署 Lync Web App
description: Lync Server 2013：部署 Lync Web App。
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
ms.openlocfilehash: ce6fef02781afbd5bc5f315ce24bfb3bdb16df1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560419"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="0b2ad-103">在 Lync Server 2013 中部署 Lync Web App</span><span class="sxs-lookup"><span data-stu-id="0b2ad-103">Deploying Lync Web App in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b2ad-104">_**主題上次修改日期：** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="0b2ad-104">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="0b2ad-105">Lync Web App 是以 Lync Server 2013 安裝的網際網路資訊服務 (IIS) 網頁用戶端，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-105">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="0b2ad-106">若要在伺服器上啟用 Lync Web App 或將網頁用戶端部署至使用者，則不需要執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-106">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="0b2ad-107">每當使用者按一下會議 URL，但未安裝 Lync 2013 用戶端時，使用者就會看到可使用最新版本的 Lync Web App 加入會議的選項。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-107">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="0b2ad-108">Lync Web App 中的語音、影片和共用功能需要 Microsoft ActiveX 控制項。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-108">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="0b2ad-109">您可以在系統提示時，預先安裝 ActiveX 控制項，或允許使用者安裝它，這會在第一次使用 Lync Web App 時或第一次存取需要 ActiveX 控制項的功能時發生。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="0b2ad-110">在 Lync Server 2013 Edge Server 部署中，Lync Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-110">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="0b2ad-111">您也必須發佈簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-111">You must also publish simple URLs.</span></span> <span data-ttu-id="0b2ad-112">如需詳細資訊，請參閱設定 lync server <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">2013 的反向 proxy 伺服器</A> 及 <A href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中規劃簡易 URLs</A>。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-112">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="0b2ad-113">啟用 Lync Web App 的 Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="0b2ad-113">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="0b2ad-114">Lync Server 2013 版本的 Lync Web App 支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-114">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="0b2ad-115">除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin 碼），以驗證在使用者登入 Lync 會議時加入外部網路的使用者。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-115">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="0b2ad-116">您可以在 Lync Server 2013 中部署 Active Directory Federation Service (AD FS) 同盟伺服器並啟用被動式驗證，以啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-116">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="0b2ad-117">設定 AD FS 後，嘗試加入 Lync 會議的外部使用者會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您已設定的任何其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-117">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="0b2ad-118">如果您打算設定 AD FS 以進行多重要素驗證，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="0b2ad-118">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="0b2ad-119">如果會議參與者和召集人都位於相同的組織中，或是兩者皆來自 AD FS 同盟組織，多重因素 ADFS 驗證便會運作。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-119">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="0b2ad-120">因為 Lync server web 基礎結構目前不支援 Lync 同盟使用者，所以多重要素 ADFS 驗證無法運作。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-120">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="0b2ad-121">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 持久性，讓 Lync Web App 用戶端的所有要求都是由同一部前端伺服器處理。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-121">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="0b2ad-122">當您在 Lync Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派一個足夠長的權杖壽命，以橫跨 Lync 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-122">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="0b2ad-123">通常，在240分鐘的標記壽命已足夠。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-123">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="0b2ad-124">此設定不適用於 Lync 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-124">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="0b2ad-125">**設定 Multi-Factor 驗證**</span><span class="sxs-lookup"><span data-stu-id="0b2ad-125">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="0b2ad-126">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-126">Install an AD FS federation server role.</span></span> <span data-ttu-id="0b2ad-127">如需詳細資訊，請參閱《 Active Directory Federation Services 2.0 部署指南》，網址為 <https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="0b2ad-127">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="0b2ad-128">建立 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-128">Create certificates for AD FS.</span></span> <span data-ttu-id="0b2ad-129">如需詳細資訊，請參閱規劃及部署 AD FS 的「同盟伺服器憑證」一節，以與單一登入主題搭配使用 [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) 。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-129">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="0b2ad-130">在 [Windows PowerShell] 命令列介面中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0b2ad-130">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="0b2ad-131">執行下列命令來建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="0b2ad-131">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="0b2ad-132">設定下列信賴憑證者規則：</span><span class="sxs-lookup"><span data-stu-id="0b2ad-132">Set the following relying party rules:</span></span>
    
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

## <a name="branchcache-configuration"></a><span data-ttu-id="0b2ad-133">BranchCache 設定</span><span class="sxs-lookup"><span data-stu-id="0b2ad-133">BranchCache Configuration</span></span>

<span data-ttu-id="0b2ad-134">Windows 7 和 Windows Server 2008 R2 中的 [BranchCache] 功能可能會干擾 Lync Web App Web 元件。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-134">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="0b2ad-135">若要防止 Lync Web App 使用者發生問題，請確定未啟用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-135">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="0b2ad-136">如需停用 BranchCache 的詳細資訊，請參閱《 BranchCache 部署指南》，可在 Microsoft 下載中心 [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) 和 HTML 格式的 Windows Server 2008 R2 技術文件庫中，以 HTML 格式使用 [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) 。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-136">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="0b2ad-137">驗證 Lync Web App 部署</span><span class="sxs-lookup"><span data-stu-id="0b2ad-137">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="0b2ad-138">您可以使用 Test-CsUcwaConference Cmdlet，以驗證一對測試使用者是否可以使用整合通訊 Web API (UCWA) 參與會議。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-138">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="0b2ad-139">如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-139">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="0b2ad-140">在 Windows Server 2008 R2 上疑難排解外掛程式安裝</span><span class="sxs-lookup"><span data-stu-id="0b2ad-140">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="0b2ad-141">如果執行 Windows Server 2008 R2 的電腦上的外掛程式安裝失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-141">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="0b2ad-142">**修改 Internet Explorer 中的安全性設定**</span><span class="sxs-lookup"><span data-stu-id="0b2ad-142">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="0b2ad-143">開啟 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-143">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="0b2ad-144">依序按一下 [ **工具**] 及 [ **網際網路選項**]，然後按一下 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-144">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="0b2ad-145">向中向左下到 [ **安全性** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-145">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="0b2ad-146">清除 [ **不要將加密的頁面儲存至磁片**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-146">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="0b2ad-147">若選取此設定，當嘗試從 Lync Web App 下載附件時，也會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-147">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="0b2ad-148">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-148">Rejoin the meeting.</span></span> <span data-ttu-id="0b2ad-149">外掛程式應該不會發生錯誤的下載。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-149">The plug-in should download without errors.</span></span>

<span data-ttu-id="0b2ad-150">**修改 DisableMSI 登錄設定**</span><span class="sxs-lookup"><span data-stu-id="0b2ad-150">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="0b2ad-151">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-151">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="0b2ad-152">若要存取登錄編輯程式，請輸入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-152">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="0b2ad-153">流覽至 HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ 原則 \\ Microsoft \\ Windows \\ Installer。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-153">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="0b2ad-154">編輯或加入類型為 REG DWORD 的 DisableMSI 登錄機碼 \_ ，並將其設定為0。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-154">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="0b2ad-155">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="0b2ad-155">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b2ad-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b2ad-156">See Also</span></span>


[<span data-ttu-id="0b2ad-157">在 Lync Server 2013 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="0b2ad-157">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="0b2ad-158">Lync Server 2013 的 lync Web App 支援平臺</span><span class="sxs-lookup"><span data-stu-id="0b2ad-158">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

