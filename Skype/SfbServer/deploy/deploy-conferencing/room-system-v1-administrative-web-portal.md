---
title: 在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: 商務用 Skype Server Skype 室系統 v1 (SRS v1, 先前稱為 Lync 室系統) 系統管理網頁入口網站是一種網路入口網站, 組織可以用來維護其 Skype 會議室系統會議室。 系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置的健康情況, 例如, 透過監視音訊/視頻裝置。 有了這個入口網站, 管理員就可以遠端收集診斷資訊來監控會議室的健康情況。
ms.openlocfilehash: bf18cefbdaa5beeaef63d16b5447cce2969fc147
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234172"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a><span data-ttu-id="567ca-105">在商務用 Skype Server 中部署 SRS v1 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="567ca-105">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>

<span data-ttu-id="567ca-106">商務用 Skype Server Skype 室系統 v1 (SRS v1, 先前稱為 Lync 室系統) 系統管理網頁入口網站是一種網路入口網站, 組織可以用來維護其 Skype 會議室系統會議室。</span><span class="sxs-lookup"><span data-stu-id="567ca-106">The Skype for Business Server Skype Room Systems v1 (SRS v1, formerly known as Lync Room System) Administrative Web Portal is a web portal that organizations can use to maintain their Skype Room Systems conference rooms.</span></span> <span data-ttu-id="567ca-107">系統管理員可以使用 SRS v1 管理網頁入口網站來監視裝置的健康情況, 例如, 透過監視音訊/視頻裝置。</span><span class="sxs-lookup"><span data-stu-id="567ca-107">Administrators can use the SRS v1 Administrative Web Portal to monitor device health, for example by monitoring audio/video devices.</span></span> <span data-ttu-id="567ca-108">有了這個入口網站, 管理員就可以遠端收集診斷資訊來監控會議室的健康情況。</span><span class="sxs-lookup"><span data-stu-id="567ca-108">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="567ca-109">若要使用此功能, 必須在每個商務用 Skype Server 前端伺服器上部署 SRS v1 系統管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="567ca-109">To use this feature, the SRS v1 Administrative Web Portal needs to be deployed on every Skype for Business Server Front End Server.</span></span> <span data-ttu-id="567ca-110">本指南提供系統管理員如何安裝和設定 SRS 管理網頁入口網站的指示。</span><span class="sxs-lookup"><span data-stu-id="567ca-110">This guide provides instructions for administrators on how to install and configure the SRS Administrative Web Portal.</span></span> <span data-ttu-id="567ca-111">它適用于瞭解商務用 Skype Server 管理的管理員, 以及誰有管理員使用者許可權來修改商務用 Skype Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="567ca-111">It is intended for administrators who have knowledge of Skype for Business Server administration, and who have administrator user rights to modify the Skype for Business Server topology.</span></span>

<span data-ttu-id="567ca-112">在伺服器上部署 SRS v1 管理網頁入口網站之後, 系統管理員可以從自己的電腦或膝上型電腦登入該網站, 以檢查狀態 SRS v1 裝置。</span><span class="sxs-lookup"><span data-stu-id="567ca-112">After the SRS v1 Administrative Web Portal is deployed on the server, administrators can check the status SRS v1 devices by logging on to the site from their own computers or laptops.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="567ca-113">下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 會議室系統 V1 管理網頁入口網站](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="567ca-113">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="567ca-114">本主題內容如下:</span><span class="sxs-lookup"><span data-stu-id="567ca-114">In this topic:</span></span>

- [<span data-ttu-id="567ca-115">針對 SRS v1 管理網頁入口網站設定您的環境</span><span class="sxs-lookup"><span data-stu-id="567ca-115">Configure your environment for the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Config_Env)

- [<span data-ttu-id="567ca-116">安裝 SRS v1 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="567ca-116">Install the SRS v1 Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Install_SRS)

- [<span data-ttu-id="567ca-117">使用 SRS 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="567ca-117">Use the SRS Administrative Web Portal</span></span>](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="567ca-118">針對 SRS v1 管理網頁入口網站設定您的環境</span><span class="sxs-lookup"><span data-stu-id="567ca-118">Configure your environment for the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="567ca-119"><a name="Config_Env"> </a></span><span class="sxs-lookup"><span data-stu-id="567ca-119"></span></span>

<span data-ttu-id="567ca-120">若要使用 SRS v1 管理網頁入口網站, 您將需要安裝或設定下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="567ca-120">To use the SRS v1 Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="567ca-121">如果伺服器已設定 Kerberos 和 NTLM 驗證, 而 SRS 是在未加入網域的電腦上執行, Kerberos 驗證將會失敗, 而且使用者在管理入口網站中將不會看到 SRS 的狀態。</span><span class="sxs-lookup"><span data-stu-id="567ca-121">If the server is configured with both Kerberos and NTLM authentication, and SRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of SRS in the administrative portal.</span></span> <span data-ttu-id="567ca-122">若要解決此問題, 請使用 NTLM 驗證或 NTLM 與 TLS DSK 驗證 (沒有 Kerberos) 來設定伺服器, 或將 SRS 電腦加入網域。</span><span class="sxs-lookup"><span data-stu-id="567ca-122">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the SRS computer to the domain.</span></span>

1. <span data-ttu-id="567ca-123">在商務用 Skype Server 拓朴中安裝商務用 Skype Server 累計更新。</span><span class="sxs-lookup"><span data-stu-id="567ca-123">Install Skype for Business Server Cumulative Updates in the Skype for Business Server topology.</span></span>

    <span data-ttu-id="567ca-124">若要取得更新或查看其隨附的內容, 請參閱[商務用 Skype Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="567ca-124">To get the update or see what's included with it, see [Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

2. <span data-ttu-id="567ca-125">建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="567ca-125">Create a SIP-enabled Active Directory user.</span></span>

    <span data-ttu-id="567ca-126">SRS v1 管理網頁入口網站使用這些認證來查詢商務用 Skype Server 的資訊。</span><span class="sxs-lookup"><span data-stu-id="567ca-126">The SRS v1 Administrative Web Portal uses these credentials to query information from Skype for Business Server.</span></span> <span data-ttu-id="567ca-127">在給定範例中的使用者名稱為 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="567ca-127">The username in the examples given is LRSApp.</span></span>

3. <span data-ttu-id="567ca-128">使用 [名稱 LRSSupportAdminGroup] 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="567ca-128">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>

    <span data-ttu-id="567ca-129">建立群組範圍為全域且群組類型為安全性的群組。</span><span class="sxs-lookup"><span data-stu-id="567ca-129">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="567ca-130">加入到這個群組的 SIP 啟用的使用者, 都會獲授權查看聊天室清單並執行某些命令, 例如收集記錄。</span><span class="sxs-lookup"><span data-stu-id="567ca-130">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4. <span data-ttu-id="567ca-131">使用 [名稱 LRSFullAccessAdminGroup] 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="567ca-131">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>

    <span data-ttu-id="567ca-132">建立群組範圍為全域和群組類型做為安全性的群組。加入此群組的 SIP 啟用的使用者已獲授權使用單一 Skype 聊天室上的所有系統管理入口網站功能。</span><span class="sxs-lookup"><span data-stu-id="567ca-132">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality on a single Skype room.</span></span> <span data-ttu-id="567ca-133">若要包含對 Skype 會議室大量管理的支援, 請參閱步驟5。</span><span class="sxs-lookup"><span data-stu-id="567ca-133">To include support for bulk management of Skype rooms, refer to step 5.</span></span>

     ![具有安全性群組角色之管理員群組的清單](../../media/LRS_LRSFullAccessAdminGroup.png)

5. <span data-ttu-id="567ca-135">使用 [名稱 LRSPowerUserAdminsGroup] 建立 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="567ca-135">Create an Active Directory security group with name LRSPowerUserAdminsGroup.</span></span>

    <span data-ttu-id="567ca-136">建立群組範圍為全域且群組類型為安全性的群組。</span><span class="sxs-lookup"><span data-stu-id="567ca-136">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="567ca-137">已授權已加入此群組的 SIP 使用者可使用所有系統管理入口網站功能, 包括大量管理商務用 Skype 會議室。</span><span class="sxs-lookup"><span data-stu-id="567ca-137">SIP enabled users who are added to this group are authorized to use all admin portal functionality including bulk management of Skype for Business rooms.</span></span>

6. <span data-ttu-id="567ca-138">將 LRSFullAccessAdminGroup 新增為 LRSSupportAdminGroup 的成員。</span><span class="sxs-lookup"><span data-stu-id="567ca-138">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>

     ![[LRSSupportAdminGroup 內容成員] 頁面](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. <span data-ttu-id="567ca-140">使用 [名稱 LRSSupport] 建立啟用 SIP 的 Active Directory 使用者。</span><span class="sxs-lookup"><span data-stu-id="567ca-140">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="567ca-141">將此使用者新增至 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="567ca-141">Add this user to LRSSupportAdminGroup.</span></span>

     ![[LRSSupportAdminGroup 內容成員] 頁面](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. <span data-ttu-id="567ca-143">[針對 Visual Studio 2010 sp1 及 Visual Web 開發人員 2010 SP1, 安裝 ASP.NET MVC 4](https://go.microsoft.com/fwlink/p/?LinkId=323967)。</span><span class="sxs-lookup"><span data-stu-id="567ca-143">Install [ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).</span></span>

## <a name="install-the-srs-v1-administrative-web-portal"></a><span data-ttu-id="567ca-144">安裝 SRS v1 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="567ca-144">Install the SRS v1 Administrative Web Portal</span></span>
<span data-ttu-id="567ca-145"><a name="Install_SRS"> </a></span><span class="sxs-lookup"><span data-stu-id="567ca-145"></span></span>

<span data-ttu-id="567ca-146">下載[適用于商務用 Skype Server 2015 的 Microsoft Skype 會議室系統 V1 管理網頁入口網站](https://www.microsoft.com/en-us/download/details.aspx?id=46906)。</span><span class="sxs-lookup"><span data-stu-id="567ca-146">Download the [Microsoft Skype Room Systems v1 Administrative Web Portal for Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).</span></span>

<span data-ttu-id="567ca-147">若要安裝 SRS v1 管理網頁入口網站, 請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="567ca-147">To install the SRS v1 Administrative Web Portal, use the following steps.</span></span>

1. <span data-ttu-id="567ca-148">在商務用 Skype Server Management 命令介面中執行下列 Cmdlet, 以設定受信任的應用程式埠:</span><span class="sxs-lookup"><span data-stu-id="567ca-148">Configure the Trusted Application Port by running the following cmdlet in Skype for Business Server Management Shell:</span></span>

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. <span data-ttu-id="567ca-149">若要安裝會議室入口網站, 請下載**MeetingRoomPortalInstaller** , 然後以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="567ca-149">To install the Meeting Room Portal, download **MeetingRoomPortalInstaller.msi** and then run it as an administrator.</span></span>

3. <span data-ttu-id="567ca-150">從下列位置開啟 Web.config 檔案:</span><span class="sxs-lookup"><span data-stu-id="567ca-150">Open the Web.config file from the following location:</span></span>

    <span data-ttu-id="567ca-151">商務用 Files%\Skype for Business Server 2015 \ Web Components\Meeting 聊天室 Portal\Int\Handler</span><span class="sxs-lookup"><span data-stu-id="567ca-151">%Program Files%\Skype for Business Server 2015\Web Components\Meeting Room Portal\Int\Handler</span></span>\

4. <span data-ttu-id="567ca-152">在 web.config 檔案中, 將 PortalUserName 變更為在步驟2中建立的使用者名稱, 在「[設定您的 SRS V1 管理網頁入口網站](room-system-v1-administrative-web-portal.md#Config_Env)」區段 (步驟中的建議名稱是 LRSApp) 中。</span><span class="sxs-lookup"><span data-stu-id="567ca-152">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section "[Configure your environment for the SRS v1 Administrative Web Portal](room-system-v1-administrative-web-portal.md#Config_Env)" (the recommended name in the step is LRSApp):</span></span>

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. <span data-ttu-id="567ca-153">由於 SRS v1 管理入口網站是受信任的應用程式, 因此您不需要在入口網站設定中提供密碼。</span><span class="sxs-lookup"><span data-stu-id="567ca-153">Because the SRS v1 Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="567ca-154">如果此使用者使用的註冊機構並非是本機註冊機構, 您必須在 Web.config 檔案中加入下列一行, 以指定其註冊機構:</span><span class="sxs-lookup"><span data-stu-id="567ca-154">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. <span data-ttu-id="567ca-155">如果使用的埠不是 5061, 請在 web.config 檔案中新增下列行:</span><span class="sxs-lookup"><span data-stu-id="567ca-155">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a><span data-ttu-id="567ca-156">驗證 SRS 管理網頁入口網站的安裝</span><span class="sxs-lookup"><span data-stu-id="567ca-156">Verify Installation of the SRS Administrative Web Portal</span></span>

<span data-ttu-id="567ca-157">若要驗證 SRS v1 管理網頁入口網站的安裝, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="567ca-157">To verify installation of the SRS v1 Administrative Web Portal, do the following:</span></span>

1. <span data-ttu-id="567ca-158">在前端伺服器上, 流覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="567ca-158">On a Front End server, browse to the following URL:</span></span>

    <span data-ttu-id="567ca-159">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="567ca-159">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="567ca-160">您不應該看到任何錯誤, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="567ca-160">You should not see any errors, as shown in the following image:</span></span>

     ![[Lync Room System 管理入口網站登入] 畫面](../../media/LRS_AdminPortalSignIn.png)

2. <span data-ttu-id="567ca-162">如果您沒有看到任何錯誤, 請嘗試從拓撲中的任何其他電腦存取下列 URL:</span><span class="sxs-lookup"><span data-stu-id="567ca-162">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>

    <span data-ttu-id="567ca-163">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="567ca-163">https://\<fe-server\>/lrs</span></span>

    <span data-ttu-id="567ca-164">若要存取頁面, 您需要新增 DNS 記錄, 如「[自動用戶端登入所需的 DNS 記錄](https://go.microsoft.com/fwlink/p/?LinkId=318056)」中所述。</span><span class="sxs-lookup"><span data-stu-id="567ca-164">To access the page, you will need to add the DNS records as described in "[Required DNS Records for Automatic Client Sign-In](https://go.microsoft.com/fwlink/p/?LinkId=318056)."</span></span>

## <a name="use-the-srs-administrative-web-portal"></a><span data-ttu-id="567ca-165">使用 SRS 管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="567ca-165">Use the SRS Administrative Web Portal</span></span>
<span data-ttu-id="567ca-166"><a name="Use_Portal"> </a></span><span class="sxs-lookup"><span data-stu-id="567ca-166"></span></span>

<span data-ttu-id="567ca-167">在伺服器上部署 SRS 之後, 您可以從瀏覽器登入 SRS v1 管理網頁入口網站, 以檢查所有 SRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="567ca-167">After you deploy SRS on the server, you can check the status of all SRS rooms by signing into the SRS v1 Administrative Web Portal from a browser.</span></span>

### <a name="sign-in"></a><span data-ttu-id="567ca-168">登錄</span><span class="sxs-lookup"><span data-stu-id="567ca-168">Sign in</span></span>

1. <span data-ttu-id="567ca-169">流覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="567ca-169">Browse to the following URL:</span></span>

    <span data-ttu-id="567ca-170">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="567ca-170">https://\<fe-server\>/lrs</span></span>

2. <span data-ttu-id="567ca-171">輸入 LRSSupport 帳戶的認證, 或是新增至 LRSSupportAdminGroup 安全性群組的帳戶。</span><span class="sxs-lookup"><span data-stu-id="567ca-171">Enter the credentials for the LRSSupport account or an account that was added to the LRSSupportAdminGroup security group.</span></span>

![[Lync Room System 管理入口網站登入] 畫面](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a><span data-ttu-id="567ca-173">SRS 系統管理網頁入口網站摘要頁面</span><span class="sxs-lookup"><span data-stu-id="567ca-173">SRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="567ca-174">[摘要] 頁面提供伺服器上部署之所有 SRS 聊天室的下列資訊:</span><span class="sxs-lookup"><span data-stu-id="567ca-174">The summary page provides the following information for all of the SRS rooms deployed on the server:</span></span>

- <span data-ttu-id="567ca-175">**標記**管理員提供給聊天室的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="567ca-175">**Tag** The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="567ca-176">您可以按一下房間名稱, 在入口網站中設定標籤。</span><span class="sxs-lookup"><span data-stu-id="567ca-176">The Tag can be set in the portal by clicking on the room name.</span></span>

- <span data-ttu-id="567ca-177">**健康情況**聊天室的健康情況狀態是衍生自聊天室的匯總健康情況, 這會顯示在 [會議室設定] 頁面的 [健康情況] 區段底下。</span><span class="sxs-lookup"><span data-stu-id="567ca-177">**Health** The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

- <span data-ttu-id="567ca-178">**下次會議**排程下次會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="567ca-178">**Next Meeting** The date and time the next meeting is scheduled.</span></span>

- <span data-ttu-id="567ca-179">**SRS 版本、製造商、型號**這些值是在 SRS 中預先設定。</span><span class="sxs-lookup"><span data-stu-id="567ca-179">**SRS Version, Manufacturer, Model** These values are preset in SRS.</span></span> <span data-ttu-id="567ca-180">視製造商而定, 這些欄位可能會保留空白。</span><span class="sxs-lookup"><span data-stu-id="567ca-180">Depending on the manufacturer, these fields might be left blank.</span></span>

- <span data-ttu-id="567ca-181">**上次**重新整理顯示最後一次重新整理網頁的時間。</span><span class="sxs-lookup"><span data-stu-id="567ca-181">**Last Refresh** Displays the last time the web page was refreshed.</span></span>

![Lync Room System 管理入口網站摘要檢視](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> <span data-ttu-id="567ca-183">如果您是 [LRSPowerUserAdminsGroup] 安全性群組的一部分, 您就只會看到 [大量管理] 功能表。</span><span class="sxs-lookup"><span data-stu-id="567ca-183">You will only see the Bulk Management menu if you are part of the LRSPowerUserAdminsGroup security group.</span></span>

### <a name="srs-room-information"></a><span data-ttu-id="567ca-184">SRS 聊天室資訊</span><span class="sxs-lookup"><span data-stu-id="567ca-184">SRS Room Information</span></span>

<span data-ttu-id="567ca-185">入口網站的 [聊天室資訊] 區段可讓您查看和設定個別的 SRS 聊天室。</span><span class="sxs-lookup"><span data-stu-id="567ca-185">The Room Info section of the portal allows you to view and configure individual SRS rooms.</span></span> <span data-ttu-id="567ca-186">它包含四個區段: 設定、詳細資料、記錄和健康情況。</span><span class="sxs-lookup"><span data-stu-id="567ca-186">It contains four sections: Settings, Details, Logging, and Health.</span></span>

#### <a name="settings"></a><span data-ttu-id="567ca-187">設置</span><span class="sxs-lookup"><span data-stu-id="567ca-187">Settings</span></span>

<span data-ttu-id="567ca-188">在 [設定] 區段中, 您可以設定聊天室的密碼、房間標籤及預設音量等級。</span><span class="sxs-lookup"><span data-stu-id="567ca-188">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="567ca-189">如果您設定這些設定, 變更只會在您重新開機 SRS 主控台後進行複製。</span><span class="sxs-lookup"><span data-stu-id="567ca-189">If you configure these settings, the changes are replicated only after you restart the SRS console.</span></span> <span data-ttu-id="567ca-190">您只會看到使用版本15.12 和更新版本之 SRS 裝置的 [系統更新] 設定。</span><span class="sxs-lookup"><span data-stu-id="567ca-190">You will only see System Updates settings for SRS devices using release 15.12 and later.</span></span>

![Lync Room System 管理入口網站會議室設定](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a><span data-ttu-id="567ca-192">詳細資料</span><span class="sxs-lookup"><span data-stu-id="567ca-192">Details</span></span>

<span data-ttu-id="567ca-193">[詳細資料] 區段提供 SRS 聊天室設定的唯讀摘要, 包括: 上次重新整理的時間;下次會議;上次更新、維護和校準;預設喇叭、麥克風和鈴聲設定;新版SIP URI;螢幕數目及每個畫面的詳細資料;狀態和活動。</span><span class="sxs-lookup"><span data-stu-id="567ca-193">The Details section provides a read-only summary of the SRS room's settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

![Lync Room System 管理入口網站詳細資料檢視](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a><span data-ttu-id="567ca-195">疑難排解</span><span class="sxs-lookup"><span data-stu-id="567ca-195">Troubleshooting</span></span>

<span data-ttu-id="567ca-196">疑難排解一節可用來遠端收集記錄, 並將它們儲存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="567ca-196">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="567ca-197">您也可以重新開機 SRS 主控台 (SRS 使用者介面), 或重新開機整個系統。</span><span class="sxs-lookup"><span data-stu-id="567ca-197">You can also restart the SRS console (SRS user interface) or restart the entire system.</span></span> <span data-ttu-id="567ca-198">若要收集記錄, 請以指定的格式提供資料夾路徑, 並確認資料夾擁有對 SRS 電腦帳戶的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="567ca-198">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the SRS machine account.</span></span> <span data-ttu-id="567ca-199">如果記錄大小太大, 可能需要最多5分鐘的時間來完成收集記錄。</span><span class="sxs-lookup"><span data-stu-id="567ca-199">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="567ca-200">重新整理頁面會提供最新狀態。</span><span class="sxs-lookup"><span data-stu-id="567ca-200">Refreshing the page will give you the latest status.</span></span>

#### <a name="health"></a><span data-ttu-id="567ca-201">運行</span><span class="sxs-lookup"><span data-stu-id="567ca-201">Health</span></span>

<span data-ttu-id="567ca-202">[健康情況] 區段會顯示商務用 Skype Server 連線、音訊裝置、視頻裝置、復原狀態及螢幕裝置的健康情況的視覺指示。</span><span class="sxs-lookup"><span data-stu-id="567ca-202">The Health section gives a visual indication of the health of the Skype for Business Server connection, audio device, video device, resiliency state, and screen device.</span></span>

![Lync Room System 管理入口網站會議室健康情況](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="567ca-204">有關系統管理網頁入口網站的其他注意事項</span><span class="sxs-lookup"><span data-stu-id="567ca-204">Additional Notes about the Administrative Web Portal</span></span>

> [!NOTE]
>  <span data-ttu-id="567ca-205">只有在重新開機 SRS 系統之後, 才會套用設定變更。 > 如果 LRSApp 帳戶密碼到期, 您將無法看到聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="567ca-205">Setting changes are applied only after the SRS system is restarted.>  If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="567ca-206">設定 LRSAppuser 帳戶密碼, 使其永不過期, 或者請務必在接近到期時更新密碼。 > SRS 系統管理網頁入口網站僅支援內部部署部署。</span><span class="sxs-lookup"><span data-stu-id="567ca-206">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it is near expiration.>  The SRS administrative web portal is supported for on-premises deployments only.</span></span>

### <a name="bulk-management"></a><span data-ttu-id="567ca-207">大量管理</span><span class="sxs-lookup"><span data-stu-id="567ca-207">Bulk management</span></span>

<span data-ttu-id="567ca-208">SRS 會議室的大量管理是專為高級 IT 系統管理員設計的功能, 可簡化其工作流程, 並讓他們使用節省時間的工具, 以大量方式遠端系統管理多個會議室。</span><span class="sxs-lookup"><span data-stu-id="567ca-208">Bulk management of SRS rooms is a feature designed for advanced IT administrators, to simplify their workflow, and enable them with a time-saving convenient tool to remotely manage multiple rooms in a bulk fashion.</span></span>

<span data-ttu-id="567ca-209">若要查看這項功能, 必須將使用者設為特殊安全性群組的成員 ( **LRSPowerUserAdminsGroup**)。</span><span class="sxs-lookup"><span data-stu-id="567ca-209">In order to see this functionality, the user need to be provisioned as a member of the special security group, **LRSPowerUserAdminsGroup**.</span></span>

<span data-ttu-id="567ca-210">對於大量管理, 您可以選取的 SRS 會議室數沒有限制。</span><span class="sxs-lookup"><span data-stu-id="567ca-210">There is no limit to the number of SRS rooms you can select for bulk management.</span></span> <span data-ttu-id="567ca-211">不過, 您一次只能執行一個大量的管理作業。</span><span class="sxs-lookup"><span data-stu-id="567ca-211">However, you can perform only one bulk management operation at a time.</span></span>

<span data-ttu-id="567ca-212">若要執行大量管理作業, 請選取您要監視的聊天室, 然後按一下 [大量管理] 功能表。</span><span class="sxs-lookup"><span data-stu-id="567ca-212">To perform a bulk management operation, select the rooms you want to monitor, and click on the Bulk management menu.</span></span>

### <a name="frequently-asked-questions"></a><span data-ttu-id="567ca-213">常見問題</span><span class="sxs-lookup"><span data-stu-id="567ca-213">Frequently asked questions</span></span>

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="567ca-214">為什麼我無法登入系統管理網頁入口網站？</span><span class="sxs-lookup"><span data-stu-id="567ca-214">Why can't I sign in to the administrative web portal?</span></span>

<span data-ttu-id="567ca-215">當您開啟https://localhost/lrs時, 您可以看到 [登入] 頁面, 但是當您輸入認證時, 就無法登入。</span><span class="sxs-lookup"><span data-stu-id="567ca-215">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="567ca-216">在這種情況下, 您https://FQDNofFEserver/SRS必須開啟, 才能登入管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="567ca-216">In this case, you must open https://FQDNofFEserver/SRS to sign in to the administrative web portal.</span></span>

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a><span data-ttu-id="567ca-217">為什麼在管理網頁入口網站中看不到 SRS v1？</span><span class="sxs-lookup"><span data-stu-id="567ca-217">Why can't I see SRS v1 in the administrative web portal?</span></span>

- <span data-ttu-id="567ca-218">請確定您在部署中擁有 SRS 帳戶, 並根據 SRS 管理網頁入口網站部署建議來建立它們。</span><span class="sxs-lookup"><span data-stu-id="567ca-218">Make sure you have SRS accounts in your deployment and that they are created according to the SRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="567ca-219">在商務用 Skype 伺服器上, 確定已使用 Enable-CsMeetingRoom, 而不是 Enable-Move-csuser 來提供 SRS 帳戶。</span><span class="sxs-lookup"><span data-stu-id="567ca-219">Make sure the SRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Skype for Business Server.</span></span>

- <span data-ttu-id="567ca-220">如果您已建立 SRS 帳戶, 但在管理網頁入口網站中看不到帳戶, 請使用已選取 [ **MeetingPortal** ] 元件的商務用 Skype server 記錄工具收集伺服器記錄, 然後將其傳送給您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="567ca-220">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Skype for Business Server Logging tool with the **MeetingPortal** component selected, and then send them to your SRS support contact.</span></span>

- <span data-ttu-id="567ca-221">如果您已建立 SRS 帳戶, 但在管理網頁入口網站中看不到帳戶, 請使用 Fiddler 收集用戶端記錄, 也可以從瀏覽器開發工具複製主機日誌, 然後將其傳送給您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="567ca-221">If you have created SRS accounts and cannot see the accounts in administrative web portal, collect the client logs using Fiddler, and also copy the console log from the browser development tools, and then send them to your SRS support contact.</span></span> <span data-ttu-id="567ca-222">您也可以修改 web.config 中的 [追蹤層級] 值, 以取得更詳細的記錄。</span><span class="sxs-lookup"><span data-stu-id="567ca-222">You can also modify the trace level value in the Web.config to get a more detailed log.</span></span>

  ```
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

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a><span data-ttu-id="567ca-223">為什麼在管理網頁入口網站中看不到 SRS 的狀態？</span><span class="sxs-lookup"><span data-stu-id="567ca-223">Why can't I see the status of SRS in the administrative web portal?</span></span>

- <span data-ttu-id="567ca-224">確認 LRSApp 使用者帳戶已啟用 SIP。</span><span class="sxs-lookup"><span data-stu-id="567ca-224">Make sure that the LRSApp user account is SIP-enabled.</span></span>

- <span data-ttu-id="567ca-225">如果您仍有問題, 請從 D:\Tracing\LRSAdminLogs\,收集 SRS 系統中的**Trace .log**檔案, 然後將其傳送給您的 SRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="567ca-225">If you are still having issues, collect the **Trace.log** file in the SRS system from D:\Tracing\LRSAdminLogs\, and then send it to your SRS support contact.</span></span>

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a><span data-ttu-id="567ca-226">為什麼在管理網頁入口網站中看不到 SRS 的大量管理功能表？</span><span class="sxs-lookup"><span data-stu-id="567ca-226">Why can't I see the bulk management menus for SRS in the administrative web portal?</span></span>

<span data-ttu-id="567ca-227">確認 LRSApp 使用者帳戶已啟用 SIP, 且是 LRSPowerUserAdminsGroup 安全性群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="567ca-227">Make sure that the LRSApp user account is SIP-enabled, and is part of the LRSPowerUserAdminsGroup security group.</span></span>

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a><span data-ttu-id="567ca-228">SRS v1 管理網頁入口網站與 Microsoft 團隊聊天室搭配使用嗎？</span><span class="sxs-lookup"><span data-stu-id="567ca-228">Does the SRS v1 administrative web portal work with Microsoft Teams Rooms?</span></span>

<span data-ttu-id="567ca-229">不。</span><span class="sxs-lookup"><span data-stu-id="567ca-229">No.</span></span>


