---
title: 規劃通話資料連線器 |通話品質儀表板監控混合式分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 使用商務用 Skype Online 遙測工具，以監視混合式案例中的內部部署實施。
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221313"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="6f9c9-103">規劃通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="6f9c9-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="6f9c9-104">概觀</span><span class="sxs-lookup"><span data-stu-id="6f9c9-104">Overview</span></span>

<span data-ttu-id="6f9c9-105">本主題說明實現商務用 Skype Server 呼叫資料連線器的優點、規劃考慮和需求。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="6f9c9-106">如需設定呼叫資料連線器的詳細資訊，請參閱[設定呼叫資料連線器](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="6f9c9-107">呼叫資料連線器大幅簡化混合式環境中的呼叫監控，因為您不再需要使用不同的內部部署和線上工具來監視所有使用者的通話品質。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="6f9c9-108">不論您的使用者是位於內部部署或線上，您可以選擇線上查看整個組織的通話品質。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="6f9c9-109">使用「呼叫資料連線器」，您可以使用單一工具集來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="6f9c9-110">在 Microsoft 團隊、商務用 Skype Online 和商務用 Skype Server 上監視您的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="6f9c9-111">查看並疑難排解整個網路的問題。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="6f9c9-112">指派呼叫分析的「服務台」和「系統管理員」角色，讓輔助技術人員能夠查看及疑難排解其職責範圍。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="6f9c9-113">使用「呼叫資料連線器」時，商務用 Skype 伺服器會將資料推送至雲端服務，以利用商務用 Skype Online 通話分析（CA）和通話品質儀表板（CQD）工具，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="6f9c9-115">伺服器將經驗品質（QoE）和詳細通話記錄（CDR）資料，都推入線上服務。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="6f9c9-116">通話分析和 CQD 工具可讓您監視通話的品質，並以 Microsoft 團隊和商務用 Skype 服務的連線問題進行疑難排解，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="6f9c9-117">呼叫分析著重于特定通話的品質問題。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="6f9c9-118">它會顯示商務用 Skype 帳戶中每位使用者之通話和會議的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="6f9c9-119">使用呼叫分析，您可以將許可權指派給服務台操作員，這樣就能在未存取其他商務用 Skype 系統管理中心的情況下，監控來電。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="6f9c9-120">通話品質儀表板側重于整個組織的網路效能和問題。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="6f9c9-121">商務用 Skype 管理員和網路工程師使用此工具來疑難排解及優化網路效能。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="6f9c9-122">如需詳細資訊，請參閱[Call Analytics 和通話品質儀表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="6f9c9-123">當然，您可能想要在內部部署中保留一些通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="6f9c9-124">例如，如果您要使用協力廠商的解決方案與自訂的報表和工作流程，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="6f9c9-125">呼叫資料連線器可讓您設定將資料傳送到線上服務，同時在內部部署伺服器上保留資料的複本，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="6f9c9-127">需求</span><span class="sxs-lookup"><span data-stu-id="6f9c9-127">Requirements</span></span>

<span data-ttu-id="6f9c9-128">下列需求假設您已在支援的拓撲中部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="6f9c9-129">如需部署商務用 Skype Server 和支援的拓撲的詳細資訊，請參閱[拓撲基礎](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="6f9c9-130">若要設定呼叫資料連線器，您必須：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="6f9c9-131">啟用混合連接。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="6f9c9-132">如果您已部署商務用 Skype Server，而且想要啟用呼叫資料連線器，則必須確定您的內部部署與線上環境之間已設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="6f9c9-133">這有時稱為分割網域設定。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="6f9c9-134">如需詳細資訊，請參閱[規劃商務用 Skype server 與 microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md)式連線，以及[設定商務用 Skype server 與 Microsoft 365 或 office 365 的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="6f9c9-135">驗證您的 Microsoft 365 或 Office 365 組織，並確定已啟用下列角色：</span><span class="sxs-lookup"><span data-stu-id="6f9c9-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="6f9c9-136">商務用 Skype Server 管理員</span><span class="sxs-lookup"><span data-stu-id="6f9c9-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="6f9c9-137">Microsoft 365 或 Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="6f9c9-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="6f9c9-138">若尚未這麼做，請依[開啟和使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述，開啟通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="6f9c9-139">使用本機 LCSCdr 和 QoEMetrics 資料庫，啟用監視的前端集區。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="6f9c9-140">若未這麼做，則通話資料連線器沒有可使用的計量資料。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f9c9-141">如果前端集區上未啟用監視，則通話資料連線器將無法運作。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="6f9c9-142">正確設定[伺服器對伺服器驗證](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)。</span><span class="sxs-lookup"><span data-stu-id="6f9c9-142">Properly configured [server-to-server authentication](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="6f9c9-143">內部部署和線上通話品質儀表板（CQD）報告的比較</span><span class="sxs-lookup"><span data-stu-id="6f9c9-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="6f9c9-144">功能報告</span><span class="sxs-lookup"><span data-stu-id="6f9c9-144">Feature reports</span></span> | <span data-ttu-id="6f9c9-145">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6f9c9-145">Skype for Business Online</span></span> | <span data-ttu-id="6f9c9-146">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="6f9c9-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="6f9c9-147">應用程式共用度量</span><span class="sxs-lookup"><span data-stu-id="6f9c9-147">Application sharing metric</span></span> |<span data-ttu-id="6f9c9-148">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-148">Yes</span></span> | <span data-ttu-id="6f9c9-149">有限</span><span class="sxs-lookup"><span data-stu-id="6f9c9-149">Limited</span></span> |
| <span data-ttu-id="6f9c9-150">客戶組建資訊</span><span class="sxs-lookup"><span data-stu-id="6f9c9-150">Customer building information</span></span>| <span data-ttu-id="6f9c9-151">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-151">Yes</span></span> | <span data-ttu-id="6f9c9-152">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-152">Yes</span></span> |
| <span data-ttu-id="6f9c9-153">深入分析</span><span class="sxs-lookup"><span data-stu-id="6f9c9-153">Drill-down analytics</span></span> | <span data-ttu-id="6f9c9-154">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-154">Yes</span></span> | <span data-ttu-id="6f9c9-155">否</span><span class="sxs-lookup"><span data-stu-id="6f9c9-155">No</span></span> |
| <span data-ttu-id="6f9c9-156">媒體可靠性度量</span><span class="sxs-lookup"><span data-stu-id="6f9c9-156">Media reliability metrics</span></span> | <span data-ttu-id="6f9c9-157">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-157">Yes</span></span> | <span data-ttu-id="6f9c9-158">有限</span><span class="sxs-lookup"><span data-stu-id="6f9c9-158">Limited</span></span> |
| <span data-ttu-id="6f9c9-159">現成的報表</span><span class="sxs-lookup"><span data-stu-id="6f9c9-159">Out-of-the-box reports</span></span> | <span data-ttu-id="6f9c9-160">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-160">Yes</span></span> | <span data-ttu-id="6f9c9-161">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-161">Yes</span></span> |
| <span data-ttu-id="6f9c9-162">總覽報表</span><span class="sxs-lookup"><span data-stu-id="6f9c9-162">Overview reports</span></span> | <span data-ttu-id="6f9c9-163">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-163">Yes</span></span> | <span data-ttu-id="6f9c9-164">否</span><span class="sxs-lookup"><span data-stu-id="6f9c9-164">No</span></span> |
| <span data-ttu-id="6f9c9-165">每個使用者報告</span><span class="sxs-lookup"><span data-stu-id="6f9c9-165">Per user reports</span></span> | <span data-ttu-id="6f9c9-166">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-166">Yes</span></span> | <span data-ttu-id="6f9c9-167">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-167">Yes</span></span> |
| <span data-ttu-id="6f9c9-168">報表集合自訂</span><span class="sxs-lookup"><span data-stu-id="6f9c9-168">Report set customization</span></span> <br> <span data-ttu-id="6f9c9-169">（新增、刪除、修改報告）</span><span class="sxs-lookup"><span data-stu-id="6f9c9-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="6f9c9-170">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-170">Yes</span></span> | <span data-ttu-id="6f9c9-171">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-171">Yes</span></span> |
| <span data-ttu-id="6f9c9-172">以影片為基礎的螢幕共用計量</span><span class="sxs-lookup"><span data-stu-id="6f9c9-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="6f9c9-173">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-173">Yes</span></span> | <span data-ttu-id="6f9c9-174">否</span><span class="sxs-lookup"><span data-stu-id="6f9c9-174">No</span></span> |
| <span data-ttu-id="6f9c9-175">以程式設計方式存取的資料 APIs</span><span class="sxs-lookup"><span data-stu-id="6f9c9-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="6f9c9-176">若要 CQD</span><span class="sxs-lookup"><span data-stu-id="6f9c9-176">to CQD</span></span> | <span data-ttu-id="6f9c9-177">否</span><span class="sxs-lookup"><span data-stu-id="6f9c9-177">No</span></span> | <span data-ttu-id="6f9c9-178">是</span><span class="sxs-lookup"><span data-stu-id="6f9c9-178">Yes</span></span> |
||||
