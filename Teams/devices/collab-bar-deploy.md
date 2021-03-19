---
title: 在 Android 上部署 Microsoft Teams 會議室
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 請閱讀本文以瞭解在 Android 上部署 Microsoft Teams 會議室。
ms.openlocfilehash: bb02ff59eb473d0db276fd773e9f1ff3f1ae0007
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875003"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a><span data-ttu-id="ab700-103">在 Android 上部署 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="ab700-103">Deploy Microsoft Teams Rooms on Android</span></span>

<span data-ttu-id="ab700-104">Android 版 Microsoft Teams 會議室的部署可以分成下列階段：</span><span class="sxs-lookup"><span data-stu-id="ab700-104">Deployment of Microsoft Teams Rooms on Android can be broken down into the following phases:</span></span>

- <span data-ttu-id="ab700-105">**網站準備就緒** 確認您的會議室 (位置) 部署需求。</span><span class="sxs-lookup"><span data-stu-id="ab700-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="ab700-106">**服務就緒** 建立資源帳戶並指派給裝置 (請參閱使用 [Microsoft 365](resource-account-ui.md) 系統管理中心建立資源) 。</span><span class="sxs-lookup"><span data-stu-id="ab700-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="ab700-107">雖然我們建議您使用專用會議室授權，但擁有適當授權的使用者帳戶也可以登錄 Android 上的 Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="ab700-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to Teams Rooms on Android.</span></span>
- <span data-ttu-id="ab700-108">**組配置與部署** 設定 Teams 會議室並連接您需要的 (請參閱製造商的檔，以) 。</span><span class="sxs-lookup"><span data-stu-id="ab700-108">**Configuration and deployment** Set up Teams Rooms and connect the peripheral devices you need (see the manufacturer's documentation for details).</span></span>

<span data-ttu-id="ab700-109">若要管理 Teams 會議室，您必須是全域系統管理員、Teams 服務系統管理員或 Teams 裝置系統管理員。有關系統管理員角色的資訊，請參閱使用 [Microsoft Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ab700-109">To manage Teams Rooms, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="ab700-110">網站準備就緒</span><span class="sxs-lookup"><span data-stu-id="ab700-110">Site readiness</span></span>

<span data-ttu-id="ab700-111">當訂購的裝置傳送給貴組織時，請與網路、設施及音訊-視覺小組合作，以確保符合部署需求，且每個網站和會議室在電源、網路和顯示方面已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="ab700-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="ab700-112">我們針對共同合作欄網站的建議為：</span><span class="sxs-lookup"><span data-stu-id="ab700-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="ab700-113">會議室大小最多 5 人</span><span class="sxs-lookup"><span data-stu-id="ab700-113">Rooms up to 5 people in size</span></span>
- <span data-ttu-id="ab700-114">專用資源帳戶</span><span class="sxs-lookup"><span data-stu-id="ab700-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="ab700-115">啟用觸控功能的顯示器</span><span class="sxs-lookup"><span data-stu-id="ab700-115">Touch-enabled displays</span></span>
- <span data-ttu-id="ab700-116">乙太網路纜線連接</span><span class="sxs-lookup"><span data-stu-id="ab700-116">Ethernet cabling</span></span>
- <span data-ttu-id="ab700-117">Microsoft Teams 媒體 (網路上) QoS 的服務品質</span><span class="sxs-lookup"><span data-stu-id="ab700-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="ab700-118">針對實體安裝考慮，請參閱製造商的檔，如果您有相關檔，請利用音訊-視覺小組的經驗，然後再安裝及安裝螢幕，然後執行纜線連接。</span><span class="sxs-lookup"><span data-stu-id="ab700-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="ab700-119">請務必查看為 [Teams](../prepare-network.md) 準備您的網路以規劃頻寬，並評估您的網路是否適合即時流量。</span><span class="sxs-lookup"><span data-stu-id="ab700-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="ab700-120">我們不建議您在 Teams 裝置與網際網路之間放置 Proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ab700-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="ab700-121">有關 Proxy 伺服器和 Teams 的資訊，請參閱 [Teams 的 Proxy 伺服器](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="ab700-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ab700-123">決策點</span><span class="sxs-lookup"><span data-stu-id="ab700-123">Decision points</span></span>|<ul><li><span data-ttu-id="ab700-124">確認您的網站符合 Microsoft Teams 共同合作條的網站就緒需求。</span><span class="sxs-lookup"><span data-stu-id="ab700-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="ab700-125">確認您為每個網站提供了足夠的頻寬。</span><span class="sxs-lookup"><span data-stu-id="ab700-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ab700-127">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ab700-127">Next steps</span></span>|<ul><li><span data-ttu-id="ab700-128">開始規劃您的共同資料條部署和組組。</span><span class="sxs-lookup"><span data-stu-id="ab700-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="ab700-129">服務整備</span><span class="sxs-lookup"><span data-stu-id="ab700-129">Service readiness</span></span>

<span data-ttu-id="ab700-130">部署 Teams 會議室之前，您必須決定是否要使用 Microsoft 365 資源帳戶、使用者帳戶，或兩者混合使用。</span><span class="sxs-lookup"><span data-stu-id="ab700-130">Before you deploy Teams Rooms, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="ab700-131">Microsoft 365 資源帳戶是專用於特定資源的信箱和 Teams 帳戶，例如會議室、投影機等。</span><span class="sxs-lookup"><span data-stu-id="ab700-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="ab700-132">這些資源帳戶可以使用您建立會議邀請時定義的規則，自動回應會議邀請。</span><span class="sxs-lookup"><span data-stu-id="ab700-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="ab700-133">除非 Teams 會議室專門供特定個人私人使用，否則我們建議您為它設定 Microsoft 365 資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="ab700-133">Unless Teams Rooms is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="ab700-134">使用資源帳戶</span><span class="sxs-lookup"><span data-stu-id="ab700-134">Using a resource account</span></span>

<span data-ttu-id="ab700-135">如果您決定設定 Microsoft 365 資源帳戶，您必須購買會議室授權。</span><span class="sxs-lookup"><span data-stu-id="ab700-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="ab700-136">會議室授權包含資源信箱，可讓貴組織人員透過 Outlook 或 Teams 預約會議室。</span><span class="sxs-lookup"><span data-stu-id="ab700-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="ab700-137">授權也會啟用視音訊會議，以及會議參與者之間的螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="ab700-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="ab700-138">如果您需要接聽或撥打外部電話號碼，您可能需要通話方案或 Microsoft 365 商務語音 [附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)。</span><span class="sxs-lookup"><span data-stu-id="ab700-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business).</span></span> <span data-ttu-id="ab700-139">如果您的組織中已啟用直接路由，則只需要會議室 SKU。</span><span class="sxs-lookup"><span data-stu-id="ab700-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="ab700-140">當您建立資源帳戶時，您可以選擇是否要讓帳戶自動接受或拒絕會議邀請、允許週期性會議、指定人員可以預先預約資源多遠等等。</span><span class="sxs-lookup"><span data-stu-id="ab700-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="ab700-141">有關 Microsoft 365 資源帳戶的資訊，請參閱使用 [Microsoft 365](resource-account-ui.md)系統管理中心建立資源帳戶 。</span><span class="sxs-lookup"><span data-stu-id="ab700-141">For more information about Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ab700-143">決策點</span><span class="sxs-lookup"><span data-stu-id="ab700-143">Decision points</span></span>|<ul><li><span data-ttu-id="ab700-144">決定是否要撥打或接聽外部電話，並確定資源帳戶的授權需求。</span><span class="sxs-lookup"><span data-stu-id="ab700-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ab700-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ab700-146">Next steps</span></span>|<ul><li><span data-ttu-id="ab700-147">準備資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="ab700-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="ab700-148">組配置與部署</span><span class="sxs-lookup"><span data-stu-id="ab700-148">Configuration and deployment</span></span>

<span data-ttu-id="ab700-149">組配置與部署規劃涵蓋下列主要領域：</span><span class="sxs-lookup"><span data-stu-id="ab700-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="ab700-150">資源帳戶資源配置</span><span class="sxs-lookup"><span data-stu-id="ab700-150">Resource account provisioning</span></span>
- <span data-ttu-id="ab700-151">裝置部署</span><span class="sxs-lookup"><span data-stu-id="ab700-151">Device deployment</span></span>
- <span data-ttu-id="ab700-152">Teams 會議室應用程式和周邊裝置組</span><span class="sxs-lookup"><span data-stu-id="ab700-152">Teams Rooms application and peripheral device configuration</span></span>
- <span data-ttu-id="ab700-153">測試</span><span class="sxs-lookup"><span data-stu-id="ab700-153">Testing</span></span>
- <span data-ttu-id="ab700-154">資產管理</span><span class="sxs-lookup"><span data-stu-id="ab700-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="ab700-155">帳戶資源配置</span><span class="sxs-lookup"><span data-stu-id="ab700-155">Account provisioning</span></span>

<span data-ttu-id="ab700-156">如果您打算使用 Microsoft 365 資源帳戶讓使用者預約共同合作橫條圖，請遵循使用 [Microsoft 365](resource-account-ui.md) 系統管理中心建立資源帳戶中的指示，為每個需要共同合作欄的 Microsoft 365 資源帳戶建立一個 Microsoft 365 資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="ab700-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="ab700-157">這也是您需要在資源帳戶新增會議室授權的地方，如果您想要撥打或接聽來自外部電話號碼的通話，請加入通話方案或商務語音授權，如果貴組織並未使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="ab700-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="ab700-158">如果您想要將 Teams 會議室指派給個別使用者供其私人使用，則不需要設定任何其他帳戶。</span><span class="sxs-lookup"><span data-stu-id="ab700-158">If you want to assign Teams Rooms to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="ab700-159">使用者可以使用個人帳戶來登錄共同合作橫條圖。</span><span class="sxs-lookup"><span data-stu-id="ab700-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="ab700-160">讓 Microsoft 365 資源帳戶的顯示名稱具有描述性且容易理解。</span><span class="sxs-lookup"><span data-stu-id="ab700-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="ab700-161">這些是使用者在搜尋和新增 Teams 會議室至會議時會看到的名稱。</span><span class="sxs-lookup"><span data-stu-id="ab700-161">These are the names that users will see when searching for and adding Teams Rooms to meetings.</span></span> <span data-ttu-id="ab700-162">您可以使用網站會議室名稱 (最大會議室容量) 等慣例，例如倫敦 4 人會議室的 Curie，其顯示名稱為 - \*\* LON-CURIE (4) 。 </span><span class="sxs-lookup"><span data-stu-id="ab700-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ab700-164">決策點</span><span class="sxs-lookup"><span data-stu-id="ab700-164">Decision points</span></span>|<ul><li><span data-ttu-id="ab700-165">決定專屬資源帳戶的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="ab700-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="ab700-166">決定是否要建立個別帳戶或使用大量置備腳本。</span><span class="sxs-lookup"><span data-stu-id="ab700-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ab700-168">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ab700-168">Next steps</span></span>|<ul><li><span data-ttu-id="ab700-169">開始規劃您的裝置部署。</span><span class="sxs-lookup"><span data-stu-id="ab700-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="ab700-170">裝置部署</span><span class="sxs-lookup"><span data-stu-id="ab700-170">Device deployment</span></span>

<span data-ttu-id="ab700-171">接下來，您需要建立方案，將裝置及其指派的周邊裝置傳送至您的會議室，然後繼續進行安裝和安裝。</span><span class="sxs-lookup"><span data-stu-id="ab700-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ab700-173">決策點</span><span class="sxs-lookup"><span data-stu-id="ab700-173">Decision points</span></span>|<ul><li><span data-ttu-id="ab700-174">決定誰將管理網站部署。</span><span class="sxs-lookup"><span data-stu-id="ab700-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="ab700-175">找出將現場安裝 Teams 會議室的資源，並負責進行組組和測試。</span><span class="sxs-lookup"><span data-stu-id="ab700-175">Identify the resources who will install Teams Rooms on site and undertake the configuration and testing.</span></span></li></ul>|
| ![描述下一個步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ab700-177">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ab700-177">Next steps</span></span>|<ul><li><span data-ttu-id="ab700-178">開始裝置測試。</span><span class="sxs-lookup"><span data-stu-id="ab700-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="ab700-179">測試</span><span class="sxs-lookup"><span data-stu-id="ab700-179">Testing</span></span>

<span data-ttu-id="ab700-180">部署 Teams 會議室之後，您應該測試它們。</span><span class="sxs-lookup"><span data-stu-id="ab700-180">After you have deployed Teams Rooms, you should test them.</span></span> <span data-ttu-id="ab700-181">請登錄 Teams 會議室，並檢查預期功能是否正常。</span><span class="sxs-lookup"><span data-stu-id="ab700-181">Sign in to Teams Rooms and check that the expected capabilities are working.</span></span> <span data-ttu-id="ab700-182">我們強烈建議您確認它們會顯示在 Microsoft Teams 系統管理中心的裝置標籤下的共同合作列區段。</span><span class="sxs-lookup"><span data-stu-id="ab700-182">We highly recommend that you verify that they are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="ab700-183">您還必須進行數次測試通話和會議，以檢查品質與績效。</span><span class="sxs-lookup"><span data-stu-id="ab700-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="ab700-184">我們建議您在 Microsoft Teams 的一般推出中，設定通話品質儀表板 (CQD) 的建建檔案、監控品質趨勢，以及參與體驗品質檢閱程式。</span><span class="sxs-lookup"><span data-stu-id="ab700-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="ab700-185">詳細資訊，請參閱體驗 [品質檢閱指南](https://aka.ms/qerguide)。</span><span class="sxs-lookup"><span data-stu-id="ab700-185">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="ab700-186">資產管理</span><span class="sxs-lookup"><span data-stu-id="ab700-186">Asset management</span></span>

<span data-ttu-id="ab700-187">在部署中，您想要使用會議室名稱、已登錄的資源帳戶和指派的周邊裝置來更新資產註冊。</span><span class="sxs-lookup"><span data-stu-id="ab700-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab700-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab700-188">Related topics</span></span>

[<span data-ttu-id="ab700-189">使用 Microsoft Teams 系統管理中心設定 Microsoft Teams 會議室的帳戶</span><span class="sxs-lookup"><span data-stu-id="ab700-189">Configure accounts for Microsoft Teams Rooms using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
