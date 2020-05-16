---
title: 為 Microsoft 團隊部署共同作業橫條圖
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
description: 閱讀本文以瞭解如何針對 Microsoft 團隊部署共同作業條。
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268030"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="057e1-103">為 Microsoft 團隊部署共同作業橫條圖</span><span class="sxs-lookup"><span data-stu-id="057e1-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="057e1-104">Microsoft 團隊的共同作業橫條圖部署可分為下列階段：</span><span class="sxs-lookup"><span data-stu-id="057e1-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="057e1-105">**網站準備**確認您的部署位置（會議室）符合部署需求。</span><span class="sxs-lookup"><span data-stu-id="057e1-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="057e1-106">**服務就緒**性建立資源帳戶並將其指派給裝置（[請參閱使用 Microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)）。</span><span class="sxs-lookup"><span data-stu-id="057e1-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="057e1-107">雖然我們建議使用專用的聊天室授權，但授權的最終使用者帳戶也可以登入共同作業條。</span><span class="sxs-lookup"><span data-stu-id="057e1-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="057e1-108">**配置和部署**在會議室中設定共同作業橫條圖，並連接您所需的週邊裝置（請參閱您的共同作業條的製造商檔）。</span><span class="sxs-lookup"><span data-stu-id="057e1-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="057e1-109">網站準備</span><span class="sxs-lookup"><span data-stu-id="057e1-109">Site readiness</span></span>

<span data-ttu-id="057e1-110">當訂購的裝置傳送給您的組織時，請與您的網路、設施和音訊視覺團隊共同作業，以確保符合部署需求，且每個網站和會議室都已準備好使用 power、網路及顯示器。</span><span class="sxs-lookup"><span data-stu-id="057e1-110">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="057e1-111">我們針對共同作業條網站的建議如下：</span><span class="sxs-lookup"><span data-stu-id="057e1-111">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="057e1-112">最多4個人員的會議室大小</span><span class="sxs-lookup"><span data-stu-id="057e1-112">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="057e1-113">專用資源帳戶</span><span class="sxs-lookup"><span data-stu-id="057e1-113">Dedicated resource accounts</span></span>
- <span data-ttu-id="057e1-114">支援觸控的顯示器</span><span class="sxs-lookup"><span data-stu-id="057e1-114">Touch-enabled displays</span></span>
- <span data-ttu-id="057e1-115">乙太網佈線</span><span class="sxs-lookup"><span data-stu-id="057e1-115">Ethernet cabling</span></span>
- <span data-ttu-id="057e1-116">在網路上為 Microsoft 團隊媒體啟用的服務品質（QoS）</span><span class="sxs-lookup"><span data-stu-id="057e1-116">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="057e1-117">如需實際安裝的考慮，請參閱製造商的檔，如果有的話，請在安裝並安裝螢幕並執行佈線前，先利用音訊視覺小組的體驗。</span><span class="sxs-lookup"><span data-stu-id="057e1-117">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="057e1-118">請務必參閱[準備您的網路供小組](../prepare-network.md)進行頻寬規劃，並評估您的網路對即時流量的適用性。</span><span class="sxs-lookup"><span data-stu-id="057e1-118">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="057e1-119">我們不建議您將 proxy 伺服器放在團隊裝置與網際網路之間。</span><span class="sxs-lookup"><span data-stu-id="057e1-119">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="057e1-120">如需 proxy 伺服器與團隊的詳細資訊，請參閱[小組的 proxy 伺服器](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="057e1-120">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="057e1-122">決策點</span><span class="sxs-lookup"><span data-stu-id="057e1-122">Decision points</span></span>|<ul><li><span data-ttu-id="057e1-123">確認您的網站符合 Microsoft 團隊共同作業列的網站準備情況需求。</span><span class="sxs-lookup"><span data-stu-id="057e1-123">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="057e1-124">確認您已為每個網站提供足夠的頻寬。</span><span class="sxs-lookup"><span data-stu-id="057e1-124">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="057e1-126">後續步驟</span><span class="sxs-lookup"><span data-stu-id="057e1-126">Next steps</span></span>|<ul><li><span data-ttu-id="057e1-127">開始規劃您的共同作業條部署與設定。</span><span class="sxs-lookup"><span data-stu-id="057e1-127">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="057e1-128">服務就緒性</span><span class="sxs-lookup"><span data-stu-id="057e1-128">Service readiness</span></span>

<span data-ttu-id="057e1-129">在您部署共同作業橫條圖前，您必須決定是否要使用 Microsoft 365 資源帳戶、使用者帳戶或兩者的混合。</span><span class="sxs-lookup"><span data-stu-id="057e1-129">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="057e1-130">Microsoft 365 資源帳戶是專門用於特定資源（例如房間、投影機等）的信箱和小群組帳戶。</span><span class="sxs-lookup"><span data-stu-id="057e1-130">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="057e1-131">這些資源帳戶可以使用您在建立規則時所定義的規則，自動回應會議邀請。</span><span class="sxs-lookup"><span data-stu-id="057e1-131">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="057e1-132">除非共同作業列專用於特定個人供其私人使用，否則我們建議您為它設定 Microsoft 365 資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="057e1-132">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="057e1-133">使用資源帳戶</span><span class="sxs-lookup"><span data-stu-id="057e1-133">Using a resource account</span></span>

<span data-ttu-id="057e1-134">如果您決定要設定 Microsoft 365 資源帳戶，您必須為其購買會議室授權。</span><span class="sxs-lookup"><span data-stu-id="057e1-134">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="057e1-135">[會議室授權] 包含的資源信箱可讓貴組織中的人員透過 Outlook 或團隊預訂會議室。</span><span class="sxs-lookup"><span data-stu-id="057e1-135">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="057e1-136">授權也能在會議參與者之間啟用影片和音訊會議以及螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="057e1-136">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="057e1-137">如果您需要接收或撥打電話給外部電話號碼，您也需要 Microsoft 365 手機系統或 Microsoft 365 商務語音授權。</span><span class="sxs-lookup"><span data-stu-id="057e1-137">If you need to receive or make calls to or from an external telephone number, you'll also need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="057e1-138">當您建立資源帳戶時，您可以選擇是否要讓帳戶自動接受或拒絕會議邀請、允許週期性會議，指定提前的人員預訂資源的進度。</span><span class="sxs-lookup"><span data-stu-id="057e1-138">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="057e1-139">如需 Microsoft 365 資源帳戶共同作業列的詳細資訊，請參閱[使用 microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="057e1-139">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="057e1-141">決策點</span><span class="sxs-lookup"><span data-stu-id="057e1-141">Decision points</span></span>|<ul><li><span data-ttu-id="057e1-142">決定您要撥打或接聽外部電話，以及找出您資源帳戶的授權需求。</span><span class="sxs-lookup"><span data-stu-id="057e1-142">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="057e1-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="057e1-144">Next steps</span></span>|<ul><li><span data-ttu-id="057e1-145">準備資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="057e1-145">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="057e1-146">配置和部署</span><span class="sxs-lookup"><span data-stu-id="057e1-146">Configuration and deployment</span></span>

<span data-ttu-id="057e1-147">規劃配置和部署涵蓋下列主要區域：</span><span class="sxs-lookup"><span data-stu-id="057e1-147">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="057e1-148">資源帳戶預配</span><span class="sxs-lookup"><span data-stu-id="057e1-148">Resource account provisioning</span></span>
- <span data-ttu-id="057e1-149">裝置部署</span><span class="sxs-lookup"><span data-stu-id="057e1-149">Device deployment</span></span>
- <span data-ttu-id="057e1-150">Microsoft 團隊應用程式和週邊裝置設定的共同作業條</span><span class="sxs-lookup"><span data-stu-id="057e1-150">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="057e1-151">正在</span><span class="sxs-lookup"><span data-stu-id="057e1-151">Testing</span></span>
- <span data-ttu-id="057e1-152">資產管理</span><span class="sxs-lookup"><span data-stu-id="057e1-152">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="057e1-153">帳戶預配</span><span class="sxs-lookup"><span data-stu-id="057e1-153">Account provisioning</span></span>

<span data-ttu-id="057e1-154">如果您打算使用 Microsoft 365 資源帳戶來讓使用者預訂共同作業列，請依照[使用 microsoft 365 系統管理中心建立資源帳戶](resource-account-ui.md)中的指示，為每一個需要的共同作業列建立 Microsoft 365 資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="057e1-154">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="057e1-155">您也可以將會議室授權新增至資源帳戶，如果您想要撥打或接聽外部電話號碼（電話系統或商務語音授權）撥打電話或接聽電話。</span><span class="sxs-lookup"><span data-stu-id="057e1-155">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Phone System or Business Voice license.</span></span>

<span data-ttu-id="057e1-156">如果您想要將共同作業條指派給個別的使用者，您不需要設定任何其他帳戶。</span><span class="sxs-lookup"><span data-stu-id="057e1-156">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="057e1-157">使用者可以使用個人帳戶登入共同作業列。</span><span class="sxs-lookup"><span data-stu-id="057e1-157">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="057e1-158">讓您的 Microsoft 365 資源帳戶顯示名稱具描述性且易於理解。</span><span class="sxs-lookup"><span data-stu-id="057e1-158">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="057e1-159">這些是使用者在搜尋並新增 Microsoft 團隊共同作業橫條圖時所看到的名稱。</span><span class="sxs-lookup"><span data-stu-id="057e1-159">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="057e1-160">您可以使用諸如*網站* - *會議室名稱*（*最大房間容量*）等慣例，例如 Curie，倫敦的4人會議室，可能會有顯示名稱 LON-Curie （4）。</span><span class="sxs-lookup"><span data-stu-id="057e1-160">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="057e1-162">決策點</span><span class="sxs-lookup"><span data-stu-id="057e1-162">Decision points</span></span>|<ul><li><span data-ttu-id="057e1-163">針對您的專用資源帳戶決定命名慣例。</span><span class="sxs-lookup"><span data-stu-id="057e1-163">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="057e1-164">決定您要建立個別帳戶或使用大量提供腳本。</span><span class="sxs-lookup"><span data-stu-id="057e1-164">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="057e1-166">後續步驟</span><span class="sxs-lookup"><span data-stu-id="057e1-166">Next steps</span></span>|<ul><li><span data-ttu-id="057e1-167">開始規劃您的裝置部署。</span><span class="sxs-lookup"><span data-stu-id="057e1-167">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="057e1-168">裝置部署</span><span class="sxs-lookup"><span data-stu-id="057e1-168">Device deployment</span></span>

<span data-ttu-id="057e1-169">接著，您需要建立您的方案，以將裝置及其指派的週邊裝置傳送到您的聊天室，然後繼續進行安裝與設定。</span><span class="sxs-lookup"><span data-stu-id="057e1-169">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![描繪決策點的圖示](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="057e1-171">決策點</span><span class="sxs-lookup"><span data-stu-id="057e1-171">Decision points</span></span>|<ul><li><span data-ttu-id="057e1-172">決定誰能管理網站的網站部署。</span><span class="sxs-lookup"><span data-stu-id="057e1-172">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="057e1-173">找出將針對網站上的 Microsoft 團隊安裝共同作業橫條圖的資源，並執行設定及測試。</span><span class="sxs-lookup"><span data-stu-id="057e1-173">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![描述後續步驟的圖示](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="057e1-175">後續步驟</span><span class="sxs-lookup"><span data-stu-id="057e1-175">Next steps</span></span>|<ul><li><span data-ttu-id="057e1-176">啟動裝置測試。</span><span class="sxs-lookup"><span data-stu-id="057e1-176">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="057e1-177">正在</span><span class="sxs-lookup"><span data-stu-id="057e1-177">Testing</span></span>

<span data-ttu-id="057e1-178">在已部署 Microsoft 團隊的共同作業條之後，您應該測試它們。</span><span class="sxs-lookup"><span data-stu-id="057e1-178">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="057e1-179">登入裝置，並檢查所需的功能是否在已部署的裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="057e1-179">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="057e1-180">我們強烈建議您確認裝置出現在 Microsoft 團隊系統管理中心的 [**裝置**] 索引標籤底下的 [共同作業**條**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="057e1-180">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="057e1-181">您也必須進行一些測試通話和會議，才能檢查品質與效能。</span><span class="sxs-lookup"><span data-stu-id="057e1-181">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="057e1-182">我們建議您做為 [一般 Microsoft 團隊推出] 的一部分，您可以設定為通話品質儀表板（CQD）建立檔案、監控品質趨勢，以及參與經驗審查程式的品質。</span><span class="sxs-lookup"><span data-stu-id="057e1-182">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="057e1-183">如需詳細資訊，請參閱[體驗檢查指南的品質](https://aka.ms/qerguide)。</span><span class="sxs-lookup"><span data-stu-id="057e1-183">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="057e1-184">資產管理</span><span class="sxs-lookup"><span data-stu-id="057e1-184">Asset management</span></span>

<span data-ttu-id="057e1-185">在部署過程中，您會想要使用房間名稱、登入資源帳戶和指派的週邊裝置來更新資產登記簿。</span><span class="sxs-lookup"><span data-stu-id="057e1-185">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="057e1-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="057e1-186">Related topics</span></span>

[<span data-ttu-id="057e1-187">使用 Microsoft 團隊系統管理中心針對 Microsoft 團隊設定共同作業橫條圖的帳戶</span><span class="sxs-lookup"><span data-stu-id="057e1-187">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
