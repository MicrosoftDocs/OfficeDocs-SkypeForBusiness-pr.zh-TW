---
title: 在商務用 Skype Server 中部署 SRS v1 系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 商務用 Skype Server Skype 聊天室 Systems server v1 (SRS v1 （以前稱為 Lync 會議室系統) 管理網頁入口網站）是一種網頁入口網站，可供組織用來維護其 Skype 室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置健康情況，例如，監控音訊/視頻裝置。 使用此入口網站，系統管理員可以遠端收集診斷資訊以監視會議室健康情況。
ms.openlocfilehash: 7d7bef99149d09ebf72c9b633370f262e535b23f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804533"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="0d99b-105">在商務用 Skype Server 中部署 SRS v1 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="0d99b-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="0d99b-106">商務用 Skype Server Skype 聊天室 Systems server v1 (SRS v1 （以前稱為 Lync 會議室系統) 管理網頁入口網站）是一種網頁入口網站，可供組織用來維護其 Skype 室系統會議室。</span><span class="sxs-lookup"><span data-stu-id="0d99b-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="0d99b-107">系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置健康情況，例如，監控音訊/視頻裝置。</span><span class="sxs-lookup"><span data-stu-id="0d99b-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="0d99b-108">使用此入口網站，系統管理員可以遠端收集診斷資訊以監視會議室健康情況。</span><span class="sxs-lookup"><span data-stu-id="0d99b-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="0d99b-109">若要使用此功能，您必須在每一部商務用 Skype Server 前端伺服器上部署 SRS v1 管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="0d99b-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="0d99b-110">本指南提供系統管理員如何安裝和設定 SRS 管理網頁入口網站的指示。</span><span class="sxs-lookup"><span data-stu-id="0d99b-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="0d99b-111">其適用于具備商務用 Skype Server 管理知識的系統管理員，以及具有管理員使用者許可權，可修改商務用 Skype 伺服器拓撲的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0d99b-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="0d99b-112">在伺服器上部署 SRS v1 系統管理 Web 入口網站後，系統管理員可以從自己的電腦或膝上型電腦登入網站，以檢查狀態 SRS v1 裝置。</span><span class="sxs-lookup"><span data-stu-id="0d99b-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d99b-113">下載 [適用于商務用 Skype Server 2015 的 Microsoft Skype 聊天室 Systems server V1 管理網頁入口網站](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="0d99b-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="0d99b-114">本主題內容：</span><span class="sxs-lookup"><span data-stu-id="0d99b-114">In this topic:</span></span>

- [<span data-ttu-id="0d99b-115">設定 SRS v1 系統管理 Web 入口網站的環境</span><span class="sxs-lookup"><span data-stu-id="0d99b-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="0d99b-116">安裝 SRS v1 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="0d99b-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="0d99b-117">使用 SRS 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="0d99b-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="0d99b-118">設定 SRS v1 系統管理 Web 入口網站的環境</span><span class="sxs-lookup"><span data-stu-id="0d99b-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="0d99b-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="0d99b-119"><a name="Config_Env"> </a></span></span>

<span data-ttu-id="0d99b-120">若要使用 SRS v1 管理網頁入口網站，您必須安裝或設定下列必要條件。</span><span class="sxs-lookup"><span data-stu-id="0d99b-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d99b-121">如果伺服器設定了 Kerberos 和 NTLM 驗證，而 SRS 是在未加入網域的電腦上執行，則 Kerberos 驗證會失敗，且使用者將不會在系統管理入口網站看到 SRS 的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d99b-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="0d99b-122">若要解決此問題，請使用沒有 Kerberos) 的 ntlm 和 TLS DSK 驗證 (來設定伺服器，或將 SRS 電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="0d99b-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="0d99b-123">在商務用 Skype 伺服器拓撲中安裝商務用 Skype Server 累計更新。</span><span class="sxs-lookup"><span data-stu-id="0d99b-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="0d99b-124">若要取得更新或查看其隨附的內容，請參閱 [更新商務用 Skype Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="0d99b-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="0d99b-125">建立 SIP-enabled Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="0d99b-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="0d99b-126">SRS v1 系統管理 Web 入口網站會使用這些認證，從商務用 Skype Server 查詢資訊。</span><span class="sxs-lookup"><span data-stu-id="0d99b-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="0d99b-127">指定範例中的使用者名稱是 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="0d99b-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="0d99b-128">使用 name LRSSupportAdminGroup 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0d99b-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="0d99b-129">以「全域」和「群組」類型為安全性的群組範圍建立群組。</span><span class="sxs-lookup"><span data-stu-id="0d99b-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="0d99b-130">新增至此群組的 SIP 啟用使用者可查看聊天室清單，並執行某些命令，例如收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0d99b-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="0d99b-131">使用名稱 LRSFullAccessAdminGroup 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0d99b-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="0d99b-132">以「全域」和「群組」類型為安全性的群組範圍建立群組。加入此群組的 SIP 啟用使用者已獲授權，可使用單一 Skype 聊天室上的所有系統管理員入口網站功能。</span><span class="sxs-lookup"><span data-stu-id="0d99b-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="0d99b-133">若要包含對 Skype 會議室大量管理的支援，請參閱步驟5。</span><span class="sxs-lookup"><span data-stu-id="0d99b-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![具有安全性群組角色的系統管理員群組清單](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="0d99b-135">使用名稱 LRSPowerUserAdminsGroup 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0d99b-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="0d99b-136">以「全域」和「群組」類型為安全性的群組範圍建立群組。</span><span class="sxs-lookup"><span data-stu-id="0d99b-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="0d99b-137">新增至此群組的 SIP 啟用使用者可使用所有系統管理員入口網站功能（包括大量商務用 Skype 會議室的大量管理）。</span><span class="sxs-lookup"><span data-stu-id="0d99b-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="0d99b-138">將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="0d99b-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 屬性成員] 頁面](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="0d99b-140">使用名稱 LRSSupport 建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="0d99b-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="0d99b-141">將此使用者新增至 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="0d99b-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![LRSSupportAdminGroup 屬性成員] 頁面](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="0d99b-143">在 [Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 上安裝 ASP.NET MVC 4](https://go.microsoft.com/fwlink/p/?LinkId=323967)。</span><span class="sxs-lookup"><span data-stu-id="0d99b-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="0d99b-144">安裝 SRS v1 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="0d99b-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="0d99b-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="0d99b-145"><a name="Install_SRS"> </a></span></span>

<span data-ttu-id="0d99b-146">下載 [適用于商務用 Skype Server 2015 的 Microsoft Skype 聊天室 Systems server V1 管理網頁入口網站](https://www.microsoft.com/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="0d99b-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="0d99b-147">若要安裝 SRS v1 系統管理 Web 入口網站，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="0d99b-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="0d99b-148">在商務用 Skype Server 管理命令介面中執行下列 Cmdlet，以設定信任的應用程式埠：</span><span class="sxs-lookup"><span data-stu-id="0d99b-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="0d99b-149">若要安裝會議室入口網站，請下載 **MeetingRoomPortalInstaller.msi** ，然後以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="0d99b-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="0d99b-150">從下列位置開啟 Web.config 檔案：</span><span class="sxs-lookup"><span data-stu-id="0d99b-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="0d99b-151">% Program Files%\Skype for Business Server 2015 \ Web Components\Meeting 聊天室 Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="0d99b-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="0d99b-152">在 Web.Config 檔案中，將 PortalUserName 變更為在步驟2中建立的使用者名稱，並在 [[設定您的 SRS v1 系統管理 Web 入口網站](room-system-v1-administrative-web-portal.md#Config_Env)」區段下， (步驟中的建議名稱是 LRSApp) ：</span><span class="sxs-lookup"><span data-stu-id="0d99b-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="0d99b-153">由於 SRS v1 管理入口網站是受信任的應用程式，因此您不需要在入口網站設定中提供密碼。</span><span class="sxs-lookup"><span data-stu-id="0d99b-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="0d99b-154">若此使用者使用不同的註冊機構，您必須在 Web.Config 檔案中新增下列一行，以指定其註冊機構：</span><span class="sxs-lookup"><span data-stu-id="0d99b-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="0d99b-155">如果使用的埠不是5061，請在 Web.Config 檔案中新增下行：</span><span class="sxs-lookup"><span data-stu-id="0d99b-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="0d99b-156">驗證 SRS 管理網頁入口網站的安裝</span><span class="sxs-lookup"><span data-stu-id="0d99b-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="0d99b-157">若要驗證 SRS v1 系統管理 Web 入口網站的安裝，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0d99b-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="0d99b-158">在前端伺服器上，流覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="0d99b-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="0d99b-159">HTTPs:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="0d99b-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="0d99b-160">您不應該看到任何錯誤，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="0d99b-160">You should not see any errors, as shown in the following image:</span></span>

     ![Lync 會議室系統管理入口網站登錄畫面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="0d99b-162">如果您未看到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL：</span><span class="sxs-lookup"><span data-stu-id="0d99b-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="0d99b-163">HTTPs:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="0d99b-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="0d99b-164">若要存取此頁面，您必須以「[自動用戶端 Sign-In 所需的 Dns 記錄](https://go.microsoft.com/fwlink/p/?LinkId=318056)」所述，新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0d99b-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="0d99b-165">使用 SRS 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="0d99b-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="0d99b-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="0d99b-166"><a name="Use_Portal"> </a></span></span>

<span data-ttu-id="0d99b-167">在伺服器上部署 SRS 之後，您可以在瀏覽器中登入 SRS v1 管理網頁入口網站，以檢查所有 SRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d99b-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="0d99b-168">登入</span><span class="sxs-lookup"><span data-stu-id="0d99b-168">Sign in</span></span>

1. <span data-ttu-id="0d99b-169">流覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="0d99b-169">Browse to the following URL:</span></span>

    <span data-ttu-id="0d99b-170">HTTPs:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="0d99b-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="0d99b-171">輸入 LRSSupport 帳戶的認證，或加入 LRSSupportAdminGroup 安全性群組的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0d99b-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![Lync 會議室系統管理入口網站登錄畫面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="0d99b-173">SRS 系統管理 Web 入口網站摘要頁面</span><span class="sxs-lookup"><span data-stu-id="0d99b-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="0d99b-174">[摘要] 頁面針對伺服器上部署的所有 SRS 聊天室，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="0d99b-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="0d99b-175">**標記** 管理員提供給會議室的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="0d99b-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="0d99b-176">您可以在入口網站中，按一下會議室名稱以設定標記。</span><span class="sxs-lookup"><span data-stu-id="0d99b-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="0d99b-177">**健全狀況** 會議室的健全狀況狀態，它是由聊天室的合計健康狀態所組成，它會顯示在 [會議室設定] 頁面的 [健康情況] 區段下。</span><span class="sxs-lookup"><span data-stu-id="0d99b-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="0d99b-178">**下一個會議** 排定下一個會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0d99b-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="0d99b-179">**SRS 版本、製造商、模型** 這些值是 SRS 中的預置。</span><span class="sxs-lookup"><span data-stu-id="0d99b-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="0d99b-180">視製造商而定，這些欄位可能會保留空白。</span><span class="sxs-lookup"><span data-stu-id="0d99b-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="0d99b-181">**上次** 重新整理顯示上次重新整理網頁的時間。</span><span class="sxs-lookup"><span data-stu-id="0d99b-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync 會議室系統管理員入口網站摘要視圖](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="0d99b-183">如果您是 LRSPowerUserAdminsGroup 安全性群組的一部分，您只會看到 [大量管理] 功能表。</span><span class="sxs-lookup"><span data-stu-id="0d99b-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="0d99b-184">SRS 聊天室資訊</span><span class="sxs-lookup"><span data-stu-id="0d99b-184">SRS Room Information</span></span>

<span data-ttu-id="0d99b-185">入口網站的 [聊天室資訊] 區段可讓您查看及設定個別的 SRS 聊天室。</span><span class="sxs-lookup"><span data-stu-id="0d99b-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="0d99b-186">包含四個區段：設定、詳細資料、記錄和健康情況。</span><span class="sxs-lookup"><span data-stu-id="0d99b-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="0d99b-187">設定</span><span class="sxs-lookup"><span data-stu-id="0d99b-187">Settings</span></span>

<span data-ttu-id="0d99b-188">在 [設定] 區段中，您可以設定會議室的密碼、會議室標記和預設磁片區層級。</span><span class="sxs-lookup"><span data-stu-id="0d99b-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="0d99b-189">如果您設定這些設定，則只有在您重新開機 SRS 主控台之後才會複製變更。</span><span class="sxs-lookup"><span data-stu-id="0d99b-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="0d99b-190">您只會看到使用版本15.12 和更新版本之 SRS 裝置的系統更新設定。</span><span class="sxs-lookup"><span data-stu-id="0d99b-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync 會議室系統管理入口網站室設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="0d99b-192">詳細資料</span><span class="sxs-lookup"><span data-stu-id="0d99b-192">Details</span></span>

<span data-ttu-id="0d99b-193">詳細資料區段提供 SRS 聊天室設定的唯讀摘要，包括：上次重新整理的時間;下一個會議;上次更新、維護和校準;預設的喇叭、mic 及鈴聲設定;版本SIP URI;每個畫面的畫面數目及詳細資料;狀態和活動。</span><span class="sxs-lookup"><span data-stu-id="0d99b-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync 會議室系統管理員入口網站詳細資料檢視](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="0d99b-195">疑難排解</span><span class="sxs-lookup"><span data-stu-id="0d99b-195">Troubleshooting</span></span>

<span data-ttu-id="0d99b-196">疑難排解區段可用於遠端收集記錄，並將其儲存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="0d99b-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="0d99b-197">您也可以重新開機 SRS 主控台 (SRS 使用者介面) 或重新開機整個系統。</span><span class="sxs-lookup"><span data-stu-id="0d99b-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="0d99b-198">若要收集記錄檔，請以指定的格式提供資料夾路徑，並確定資料夾具有 SR 電腦帳戶的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="0d99b-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="0d99b-199">如果記錄檔的大小過大，則最多可能需要5分鐘的時間來收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0d99b-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="0d99b-200">重新整理頁面可提供您最新的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d99b-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="0d99b-201">健康情況</span><span class="sxs-lookup"><span data-stu-id="0d99b-201">Health</span></span>

<span data-ttu-id="0d99b-202">「健康情況」區段供應商務用 Skype Server 連線、音訊裝置、影片裝置、恢復狀態及螢幕裝置狀況的視覺指示。</span><span class="sxs-lookup"><span data-stu-id="0d99b-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync 會議室系統管理入口網站室健康情況](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="0d99b-204">關於系統管理 Web 入口網站的其他注意事項</span><span class="sxs-lookup"><span data-stu-id="0d99b-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="0d99b-205">只有在 SR 系統重新開機之後，才會套用設定變更。 > 如果 LRSApp 帳戶密碼到期，您將無法看到聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d99b-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="0d99b-206">設定 LRSAppuser 帳戶密碼，使其永不到期，或務必在密碼即將到期時更新 >。只有內部部署部署才支援 SRS 管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="0d99b-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="0d99b-207">大量管理</span><span class="sxs-lookup"><span data-stu-id="0d99b-207">Bulk management</span></span>

<span data-ttu-id="0d99b-208">使用大量管理的 SRS 會議室是專為高級 IT 系統管理員所設計的功能，可簡化其工作流程，並可讓他們使用節省時間的便捷工具，以大量的方式遠端系統管理多個聊天室。</span><span class="sxs-lookup"><span data-stu-id="0d99b-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="0d99b-209">若要看到此功能，使用者必須布建為特殊安全性群組（ **LRSPowerUserAdminsGroup**）的成員。</span><span class="sxs-lookup"><span data-stu-id="0d99b-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="0d99b-210">您可以為大量管理選取的 SRS 聊天室數目沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="0d99b-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="0d99b-211">不過，您一次只能執行一個大量管理作業。</span><span class="sxs-lookup"><span data-stu-id="0d99b-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="0d99b-212">若要執行大量管理作業，請選取您要監視的聊天室，然後按一下 [大量管理] 功能表上的 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="0d99b-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="0d99b-213">常見問題集</span><span class="sxs-lookup"><span data-stu-id="0d99b-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="0d99b-214">為什麼我無法登入管理網頁入口網站？</span><span class="sxs-lookup"><span data-stu-id="0d99b-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="0d99b-215">當您開啟時 https://localhost/lrs ，您可以看到 [登入] 頁面，但是當您輸入您的認證時，您無法登入。</span><span class="sxs-lookup"><span data-stu-id="0d99b-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="0d99b-216">在此情況下，您必須先開啟 https://FQDNofFEserver/SRS 以登入管理 web 入口網站。</span><span class="sxs-lookup"><span data-stu-id="0d99b-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="0d99b-217">為什麼我無法看到管理網頁入口網站中的 SRS v1？</span><span class="sxs-lookup"><span data-stu-id="0d99b-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="0d99b-218">請確定您的部署中有 SR 帳戶，而且這些帳戶是根據 SRS 管理網頁入口網站部署建議所建立。</span><span class="sxs-lookup"><span data-stu-id="0d99b-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="0d99b-219">請確定已使用商務用 Skype Server 上的 Enable-CsMeetingRoom，而不是啟用 Get-csuser 來布建 SRS 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0d99b-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="0d99b-220">如果您已建立 SR 帳戶，但在管理 web 入口網站中看不到帳戶，請使用已選取 [ **MeetingPortal** ] 元件的商務用 Skype server 記錄工具收集伺服器記錄，然後將其傳送給您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="0d99b-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="0d99b-221">如果您已建立 SR 帳戶，但在管理 web 入口網站中看不到這些帳戶，請使用 Fiddler 收集用戶端記錄，並從瀏覽器開發工具複製主控台記錄檔，然後將其傳送至您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="0d99b-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="0d99b-222">您也可以修改 Web.config 中的追蹤層級值，以取得更詳細的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="0d99b-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```xml
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="0d99b-223">為什麼我無法在管理網頁入口網站中看到 SRS 的狀態？</span><span class="sxs-lookup"><span data-stu-id="0d99b-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="0d99b-224">請確定 LRSApp 的使用者帳戶已 SIP-enabled。</span><span class="sxs-lookup"><span data-stu-id="0d99b-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="0d99b-225">如果仍有問題，請從 D:\Tracing\LRSAdminLogs 收集 SRS 系統中的 **Trace .log** 檔案 \, ，然後將它傳送給您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="0d99b-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="0d99b-226">為何在管理網頁入口網站中看不到 SR 的大量管理功能表？</span><span class="sxs-lookup"><span data-stu-id="0d99b-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="0d99b-227">請確定 LRSApp 的使用者帳戶 SIP-enabled，且屬於 LRSPowerUserAdminsGroup 安全性群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="0d99b-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="0d99b-228">SRS 的管理網頁入口網站是否與 Microsoft 團隊聊天室一起運作？</span><span class="sxs-lookup"><span data-stu-id="0d99b-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="0d99b-229">否。</span><span class="sxs-lookup"><span data-stu-id="0d99b-229">No.</span></span>


