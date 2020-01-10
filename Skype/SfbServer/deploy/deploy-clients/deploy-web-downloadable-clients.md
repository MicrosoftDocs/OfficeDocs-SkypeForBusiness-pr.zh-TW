---
title: 在商務用 Skype Server 中部署網頁下載用戶端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：在商務用 Skype 中部署商務用 Skype Web App 和 Skype 會議應用程式。
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003523"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="8aa6c-103">在商務用 Skype Server 中部署網頁下載用戶端</span><span class="sxs-lookup"><span data-stu-id="8aa6c-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="8aa6c-104">**摘要：** 部署適用于商務用 Skype Server 的商務用 Skype 2015 Web App 和 Skype 會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="8aa6c-105">商務用 skype Web App 是已安裝在執行商務用 Skype Server 的伺服器上的網際網路資訊服務（IIS） web 用戶端，而且預設會依需求部署至尚未擁有商務用 Skype 用戶端的會議使用者。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="8aa6c-106">這些會議使用者的頻率通常是無法從您的網路外部連線。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="8aa6c-107">每當使用者按一下會議 URL，但沒有安裝商務用 Skype 用戶端時，系統會顯示使用最新版本的商務用 Skype Web App、Skype 會議應用程式或 Mac 版商務用 Skype 來加入會議的選項。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="8aa6c-108">商務用 Skype Web App 中的 [語音]、[影片] 和 [共用] 功能需要由使用者瀏覽器用來做為外掛程式的 Microsoft ActiveX 控制項。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="8aa6c-109">您可以在出現提示時，事先安裝 ActiveX 控制項或允許使用者安裝，這會在第一次使用商務用 Skype Web App 時，或第一次存取需要 ActiveX 控制項的功能時進行安裝。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa6c-110">在商務用 Skype Server Edge 伺服器部署中，商務用 Skype Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="8aa6c-111">您也必須發佈簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-111">You must also publish simple URLs.</span></span> <span data-ttu-id="8aa6c-112">如需詳細資訊，請參閱針對[商務用 Skype Server 中的簡單 Url](../../plan-your-deployment/network-requirements/simple-urls.md)[設定反向 Proxy 伺服器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)與 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="8aa6c-113">針對商務用 Skype Web App 啟用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8aa6c-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="8aa6c-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-114"></span></span>

<span data-ttu-id="8aa6c-115">商務用 skype Web App、Skype 會議應用程式，以及 Mac 版商務用 Skype 支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="8aa6c-116">除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin），以驗證在登入商務用 Skype 會議時，從外部網路加入的使用者。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="8aa6c-117">您可以透過部署 Active Directory Federation Services （AD FS）同盟伺服器並啟用商務用 Skype Server 中的被動式驗證，來啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="8aa6c-118">在設定 AD FS 之後，嘗試加入商務用 Skype 會議的外部使用者會有一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼質詢，以及您所使用的任何其他驗證方法已設定。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aa6c-119">如果您打算針對多重要素驗證設定 AD FS，請務必考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="8aa6c-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="8aa6c-120">如果會議參與者和召集人都在同一個組織中，或都來自 AD FS 同盟組織，則多重要素 ADFS 驗證就會運作。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="8aa6c-121">因為 Lync server web 基礎結構目前不支援 Lync 聯盟使用者，所以多重要素 ADFS 驗證無法運作。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="8aa6c-122">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，以便從商務用 Skype Web App 或會議 App 用戶端的所有要求都是由同一個前端伺服器來處理。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="8aa6c-123">當您在商務用 Skype Server 和 AD FS 伺服器之間建立信賴方信任時，請指派一個足夠長的權杖有效期，有效期能超過商務用 Skype 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="8aa6c-124">通常，240分鐘的標記生活就足夠了。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="8aa6c-125">此設定不會套用至 Lync mobile 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="8aa6c-126">設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8aa6c-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="8aa6c-127">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="8aa6c-128">如需詳細資訊，請參閱[Active Directory Federation Services 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="8aa6c-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="8aa6c-129">建立適用于 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-129">Create certificates for AD FS.</span></span> <span data-ttu-id="8aa6c-130">如需詳細資訊，請參閱和部署 AD FS 之方案的[[同盟伺服器憑證]](https://go.microsoft.com/fwlink/p/?LinkId=285376)區段，以便與單一登入主題搭配使用。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="8aa6c-131">從 Windows PowerShell 命令列介面，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8aa6c-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="8aa6c-132">執行下列命令以建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="8aa6c-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="8aa6c-133">設定下列信賴方規則：</span><span class="sxs-lookup"><span data-stu-id="8aa6c-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="8aa6c-134">停用 BranchCache</span><span class="sxs-lookup"><span data-stu-id="8aa6c-134">Disable BranchCache</span></span>
<span data-ttu-id="8aa6c-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-135"></span></span>

<span data-ttu-id="8aa6c-136">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能會干擾商務用 Skype Web App 網頁元件。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="8aa6c-137">若要防止商務用 Skype Web App 使用者的問題，請確定未啟用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="8aa6c-138">如需有關停用 BranchCache 的詳細資訊，請參閱[BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="8aa6c-139">驗證商務用 Skype Web App 部署</span><span class="sxs-lookup"><span data-stu-id="8aa6c-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="8aa6c-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-140"></span></span>

<span data-ttu-id="8aa6c-141">您可以使用 CsUcwaConference Cmdlet 來確認一組測試使用者可以使用整合通訊 Web API （UCWA）參與會議。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8aa6c-142">如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server Management Shell 檔中的[測試 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="8aa6c-143">Windows Server 2008 R2 上的外掛程式安裝疑難排解</span><span class="sxs-lookup"><span data-stu-id="8aa6c-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="8aa6c-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-144"></span></span>

<span data-ttu-id="8aa6c-145">如果您在執行 Windows Server 2008 R2 的電腦上安裝外掛程式失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="8aa6c-146">修改 Internet Explorer 中的安全性設定</span><span class="sxs-lookup"><span data-stu-id="8aa6c-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="8aa6c-147">開啟 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="8aa6c-148">按一下 [**工具**]，按一下 [**網際網路選項**]，然後按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="8aa6c-149">向下滾動至 [**安全性**] 區段。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="8aa6c-150">清除 [**不要將加密的網頁存到磁片**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8aa6c-151">如果選取此選項，當您嘗試從商務用 Skype Web App 下載附件時，此設定也會導致錯誤。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="8aa6c-152">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-152">Rejoin the meeting.</span></span> <span data-ttu-id="8aa6c-153">外掛程式應該會下載，不會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="8aa6c-154">修改 DisableMSI 註冊表設定</span><span class="sxs-lookup"><span data-stu-id="8aa6c-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="8aa6c-155">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="8aa6c-156">若要存取 [登錄編輯程式]，請輸入**regedit**。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="8aa6c-157">流覽至 HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="8aa6c-158">編輯或新增 REG_DWORD 類型的 DisableMSI 登錄機碼，並將其設定為0。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="8aa6c-159">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="8aa6c-160">[啟用 Skype 會議] App 以取代商務用 Skype Web App （選用、商務用 Skype Server 2015）</span><span class="sxs-lookup"><span data-stu-id="8aa6c-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="8aa6c-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-161"></span></span>

<span data-ttu-id="8aa6c-162">這個程式是選用的，且適用于商務用 Skype Server 2015 CU5 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="8aa6c-163">如果您不使用它，外部使用者將會繼續使用商務用 Skype Web App 加入會議。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="8aa6c-164">啟用簡化的會議加入與 Skype 會議應用程式</span><span class="sxs-lookup"><span data-stu-id="8aa6c-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="8aa6c-165">當您啟用內容傳遞網路（CDN）的存取權時，使用者將能夠連線至 CDN 線上並取得 Skype 會議應用程式（在 Windows 上）和商務用 Skype for Mac （Mac），並將使用簡化的會議加入體驗。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="8aa6c-166">[允許用戶端從會議加入網頁] 或 [Skype 會議] App 傳送至 Microsoft server （預設為 false）。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="8aa6c-167">傳送給 Microsoft 的資訊與[商務用 Skype 資料收集做法](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)嚴格相容。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="8aa6c-168">如果沒有提供 CDN，請先設定超時，然後再回到本機託管的商務用 Skype Web App 體驗。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="8aa6c-169">預設值是6秒。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-169">The default value is 6 seconds.</span></span> <span data-ttu-id="8aa6c-170">如果此值設定為0，就不會有超時。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="8aa6c-171">在商務用 Skype Server 2015 中使用 MeetingUxUseCdn 累計更新5時，預設值會設定為 False。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="8aa6c-172">這會導致 Mac 版商務用 Skype 用戶端無法將非同盟夥伴的會議作為來賓加入，即使商務用 Skype 系統管理員已將 MeetingUxUseCdn 設定為 True 也一樣。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="8aa6c-173">若要使用此功能，商務用 Skype Server 2015 必須具有累加更新7、6.0.9319.534 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="8aa6c-174">請參閱[啟用 Skype 會議應用程式，以取代商務用 Skype Server 2015 中的商務用 Skype Web App](https://support.microsoft.com/kb/4132312)。</span><span class="sxs-lookup"><span data-stu-id="8aa6c-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="8aa6c-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8aa6c-175">See also</span></span>
<span data-ttu-id="8aa6c-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="8aa6c-176"></span></span>

[<span data-ttu-id="8aa6c-177">規劃會議用戶端（Web App 與會議應用程式）</span><span class="sxs-lookup"><span data-stu-id="8aa6c-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="8aa6c-178">在商務用 Skype Server 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="8aa6c-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="8aa6c-179">Microsoft Online 服務隱私權聲明</span><span class="sxs-lookup"><span data-stu-id="8aa6c-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="8aa6c-180">授權條款與檔</span><span class="sxs-lookup"><span data-stu-id="8aa6c-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
