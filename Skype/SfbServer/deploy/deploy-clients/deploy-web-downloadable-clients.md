---
title: 在商務用 Skype Server 中部署 Web 可下載的用戶端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署商務用 Skype 的商務用 Skype Web App 和 Skype 會議應用程式。
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429419"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="99307-103">在商務用 Skype Server 中部署 Web 可下載的用戶端</span><span class="sxs-lookup"><span data-stu-id="99307-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="99307-104">**摘要：** 部署商務用 skype Server 所使用的商務用 Skype 2015 Web App 和 Skype 會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="99307-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="99307-105">商務用 skype Web App 是安裝在執行商務用 Skype Server 之伺服器上的網際網路資訊服務 (IIS) 網頁用戶端，而且預設會根據需要將其部署到尚未擁有商務用 Skype 用戶端的會議使用者。</span><span class="sxs-lookup"><span data-stu-id="99307-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="99307-106">這兩個會議使用者的使用者頻率高於無法從您的網路外部連線。</span><span class="sxs-lookup"><span data-stu-id="99307-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="99307-107">每當使用者按一下會議 URL，但未安裝商務用 Skype 用戶端時，使用者就會看到使用最新版的商務用 Skype Web App、Skype 會議應用程式或商務用 Skype for Mac 來加入會議的選項。</span><span class="sxs-lookup"><span data-stu-id="99307-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="99307-108">商務用 Skype Web App 中的語音、影片和共用功能，需要使用 Microsoft ActiveX 控制項，以供使用者瀏覽器做為外掛程式使用。</span><span class="sxs-lookup"><span data-stu-id="99307-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="99307-109">您可以在系統提示時，預先安裝 ActiveX 控制項，或讓使用者安裝它，這會在第一次使用商務用 Skype Web App 時，或第一次存取需要 ActiveX 控制項的功能時發生。</span><span class="sxs-lookup"><span data-stu-id="99307-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="99307-110">在商務用 Skype Server Edge Server 部署中，需要在周邊網路中使用 HTTPS 反向 proxy，才能進行商務用 Skype Web App 用戶端存取。</span><span class="sxs-lookup"><span data-stu-id="99307-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="99307-111">您也必須發佈簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="99307-111">You must also publish simple URLs.</span></span> <span data-ttu-id="99307-112">如需詳細資訊，請參閱[為商務用 Skype Server 中的簡易 URLs](../../plan-your-deployment/network-requirements/simple-urls.md)[設定反向 Proxy 伺服器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)和 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="99307-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="99307-113">啟用商務用 Skype Web App 的 Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="99307-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="99307-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="99307-115">商務用 skype Web App、Skype 會議應用程式和商務用 Skype for Mac 支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="99307-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="99307-116">除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin 碼），以驗證在使用者登入商務用 Skype 會議時加入外部網路的使用者。</span><span class="sxs-lookup"><span data-stu-id="99307-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="99307-117">您可以在商務用 Skype Server 中部署 Active Directory Federation Service (AD FS) 同盟伺服器及啟用被動式驗證，以啟用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="99307-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="99307-118">設定 AD FS 後，嘗試加入商務用 Skype 會議的外部使用者，會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您設定的任何其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="99307-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99307-119">如果您打算設定 AD FS 以進行多重要素驗證，請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="99307-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="99307-120">如果會議參與者和召集人都位於相同的組織中，或是兩者皆來自 AD FS 同盟組織，多重因素 ADFS 驗證便會運作。</span><span class="sxs-lookup"><span data-stu-id="99307-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="99307-121">因為 Lync server web 基礎結構目前不支援 Lync 同盟使用者，所以多重要素 ADFS 驗證無法運作。</span><span class="sxs-lookup"><span data-stu-id="99307-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="99307-122">如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，使來自商務用 Skype Web App 或會議應用程式用戶端的所有要求都是由同一部前端伺服器處理。</span><span class="sxs-lookup"><span data-stu-id="99307-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="99307-123">當您在商務用 Skype Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派足夠長的權杖有效期，以橫跨商務用 Skype 會議的最大長度。</span><span class="sxs-lookup"><span data-stu-id="99307-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="99307-124">通常，在240分鐘的標記壽命已足夠。</span><span class="sxs-lookup"><span data-stu-id="99307-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="99307-125">此設定不適用於 Lync 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="99307-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="99307-126">設定 Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="99307-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="99307-127">安裝 AD FS 同盟伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="99307-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="99307-128">如需詳細資訊，請參閱 [Active Directory Federation Services 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="99307-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="99307-129">建立 AD FS 的憑證。</span><span class="sxs-lookup"><span data-stu-id="99307-129">Create certificates for AD FS.</span></span> <span data-ttu-id="99307-130">如需詳細資訊，請參閱規劃及部署 AD FS 的「 [同盟伺服器憑證](https://go.microsoft.com/fwlink/p/?LinkId=285376) 」一節，以搭配單一登入主題使用。</span><span class="sxs-lookup"><span data-stu-id="99307-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="99307-131">在 [Windows PowerShell] 命令列介面中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="99307-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="99307-132">執行下列命令來建立合作關係：</span><span class="sxs-lookup"><span data-stu-id="99307-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="99307-133">設定下列信賴憑證者規則：</span><span class="sxs-lookup"><span data-stu-id="99307-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="99307-134">停用 BranchCache</span><span class="sxs-lookup"><span data-stu-id="99307-134">Disable BranchCache</span></span>
<span data-ttu-id="99307-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="99307-136">Windows 7 和 Windows Server 2008 R2 中的 [BranchCache] 功能可能會干擾商務用 Skype Web App web 元件。</span><span class="sxs-lookup"><span data-stu-id="99307-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="99307-137">若要防止商務用 Skype Web App 使用者的問題，請確定未啟用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="99307-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="99307-138">如需停用 BranchCache 的詳細資訊，請參閱 [BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="99307-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="99307-139">驗證商務用 Skype Web App 部署</span><span class="sxs-lookup"><span data-stu-id="99307-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="99307-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="99307-141">您可以使用 Test-CsUcwaConference Cmdlet，以驗證一對測試使用者是否可以使用整合通訊 Web API (UCWA) 參與會議。</span><span class="sxs-lookup"><span data-stu-id="99307-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="99307-142">如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔中的 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="99307-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="99307-143">在 Windows Server 2008 R2 上疑難排解外掛程式安裝</span><span class="sxs-lookup"><span data-stu-id="99307-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="99307-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="99307-145">如果執行 Windows Server 2008 R2 的電腦上的外掛程式安裝失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。</span><span class="sxs-lookup"><span data-stu-id="99307-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="99307-146">修改 Internet Explorer 中的安全性設定</span><span class="sxs-lookup"><span data-stu-id="99307-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="99307-147">開啟 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="99307-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="99307-148">依序按一下 [ **工具**] 及 [ **網際網路選項**]，然後按一下 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="99307-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="99307-149">向中向左下到 [ **安全性** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="99307-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="99307-150">清除 [ **不要將加密的頁面儲存至磁片**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99307-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99307-151">若選取此設定，當您嘗試從商務用 Skype Web App 下載附件時，也會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="99307-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="99307-152">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="99307-152">Rejoin the meeting.</span></span> <span data-ttu-id="99307-153">外掛程式應該不會發生錯誤的下載。</span><span class="sxs-lookup"><span data-stu-id="99307-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="99307-154">修改 DisableMSI 登錄設定</span><span class="sxs-lookup"><span data-stu-id="99307-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="99307-155">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="99307-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="99307-156">若要存取登錄編輯程式，請輸入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="99307-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="99307-157">流覽至 HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer。</span><span class="sxs-lookup"><span data-stu-id="99307-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="99307-158">編輯或加入 REG_DWORD 類型的 DisableMSI 登錄機碼，並將其設定為0。</span><span class="sxs-lookup"><span data-stu-id="99307-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="99307-159">重新加入會議。</span><span class="sxs-lookup"><span data-stu-id="99307-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="99307-160">啟用 Skype 會議應用程式以取代商務用 Skype Web App (選用，僅限商務用 Skype Server 2015) </span><span class="sxs-lookup"><span data-stu-id="99307-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="99307-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="99307-162">此程式是選用的，且適用于商務用 Skype Server 2015 CU5 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="99307-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="99307-163">如果您不使用它，外部使用者將繼續使用商務用 Skype Web App 加入會議。</span><span class="sxs-lookup"><span data-stu-id="99307-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="99307-164">啟用簡化的會議加入和 Skype 會議應用程式</span><span class="sxs-lookup"><span data-stu-id="99307-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="99307-165">當您啟用存取內容傳遞網路 (CDN) 時，使用者將能夠連線至 CDN online，並取得 Windows) 上的 Skype 會議應用程式 (和商務用 Skype for Mac (mac) ，而且會使用簡化的會議加入體驗。</span><span class="sxs-lookup"><span data-stu-id="99307-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="99307-166">允許用戶端從會議加入網頁或 Skype 會議應用程式傳送至 Microsoft 伺服器的用戶端記錄遙測 (此命令的預設值為 false) 。</span><span class="sxs-lookup"><span data-stu-id="99307-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="99307-167">傳送給 Microsoft 的資訊嚴格遵守 [隱私權和 Microsoft 小組](../../../../Teams/teams-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="99307-167">Information sent to Microsoft is in strict compliance with [Privacy and Microsoft Teams](../../../../Teams/teams-privacy.md).</span></span>

3. <span data-ttu-id="99307-168">若未提供 CDN，請先設定超時，再回到本機主控的商務用 Skype Web App 體驗。</span><span class="sxs-lookup"><span data-stu-id="99307-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="99307-169">預設值為6秒。</span><span class="sxs-lookup"><span data-stu-id="99307-169">The default value is 6 seconds.</span></span> <span data-ttu-id="99307-170">如果此值設為0，則不會有任何超時。</span><span class="sxs-lookup"><span data-stu-id="99307-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="99307-171">使用 MeetingUxUseCdn in 商務用 Skype Server 2015 累計更新5時，預設值會設為 False。</span><span class="sxs-lookup"><span data-stu-id="99307-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="99307-172">這會造成問題：商務用 Skype for Mac 用戶端無法將非同盟夥伴的會議加入為來賓，即使商務用 Skype 管理員已將 MeetingUxUseCdn 設定為 True 也是一樣。</span><span class="sxs-lookup"><span data-stu-id="99307-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="99307-173">為了運作，商務用 Skype Server 2015 必須有累計更新7、6.0.9319.534 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="99307-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="99307-174">請參閱 [啟用 Skype 會議應用程式以取代商務用 Skype Server 2015 中的商務用 Skype Web App](https://support.microsoft.com/kb/4132312)。</span><span class="sxs-lookup"><span data-stu-id="99307-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="99307-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="99307-175">See also</span></span>
<span data-ttu-id="99307-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="99307-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="99307-177">規劃會議用戶端 (Web 應用程式和會議應用程式) </span><span class="sxs-lookup"><span data-stu-id="99307-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="99307-178">在商務用 Skype Server 中設定會議加入頁面</span><span class="sxs-lookup"><span data-stu-id="99307-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="99307-179">Microsoft Online Services 隱私權聲明</span><span class="sxs-lookup"><span data-stu-id="99307-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="99307-180">授權條款和檔</span><span class="sxs-lookup"><span data-stu-id="99307-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
