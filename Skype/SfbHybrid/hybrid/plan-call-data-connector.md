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
description: 使用商務用 Skype 線上遙測工具來監視混合式案例中的內部部署實施，以瞭解如何使用線上遙測工具。
ms.openlocfilehash: 7b6076224280446b7fc52c505fe5fc3ab8d41be4
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856352"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="cecfa-103">規劃通話資料連接器</span><span class="sxs-lookup"><span data-stu-id="cecfa-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="cecfa-104">概觀</span><span class="sxs-lookup"><span data-stu-id="cecfa-104">Overview</span></span>

<span data-ttu-id="cecfa-105">本主題說明執行商務用 Skype Server 呼叫資料連線器的優點、規劃考慮和需求。</span><span class="sxs-lookup"><span data-stu-id="cecfa-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="cecfa-106">如需設定呼叫資料連線器的詳細資訊，請參閱 [設定呼叫資料連線器](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="cecfa-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="cecfa-107">呼叫資料連線器大幅簡化混合式環境中的呼叫監控，因為您不再需要使用不同的內部部署和線上工具來監視所有使用者的通話品質。</span><span class="sxs-lookup"><span data-stu-id="cecfa-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="cecfa-108">不論您的使用者是位於內部部署或線上，您可以選擇線上查看整個組織的通話品質。</span><span class="sxs-lookup"><span data-stu-id="cecfa-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="cecfa-109">使用「呼叫資料連線器」，您可以使用單一工具集來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="cecfa-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="cecfa-110">監控使用者對 Microsoft Teams、商務用 Skype 線上及商務用 Skype Server 的體驗。</span><span class="sxs-lookup"><span data-stu-id="cecfa-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="cecfa-111">查看並疑難排解整個網路的問題。</span><span class="sxs-lookup"><span data-stu-id="cecfa-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="cecfa-112">指派呼叫分析的「服務台」和「系統管理員」角色，讓輔助技術人員能夠查看及疑難排解其職責範圍。</span><span class="sxs-lookup"><span data-stu-id="cecfa-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="cecfa-113">使用呼叫資料連線器時，商務用 Skype Server 會將資料推送至雲端服務，以便您可以利用商務用 Skype 線上呼叫分析 (CA) 及通話品質儀表板 (CQD) 工具，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="cecfa-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="cecfa-115">伺服器會將經驗品質 (QoE) 和詳細通話記錄 (CDR) 資料到線上服務。</span><span class="sxs-lookup"><span data-stu-id="cecfa-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="cecfa-116">通話分析和 CQD 工具可讓您監視通話的品質，並使用 Microsoft Teams 和商務用 Skype 服務來疑難排解連線問題，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cecfa-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="cecfa-117">呼叫分析著重于特定通話的品質問題。</span><span class="sxs-lookup"><span data-stu-id="cecfa-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="cecfa-118">它會顯示商務用 Skype 帳戶中每位使用者之通話和會議的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cecfa-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="cecfa-119">使用呼叫分析，您可以將許可權指派給服務台操作員，這樣就能在未存取商務用 Skype 系統管理中心的其餘部分的情況下監視通話。</span><span class="sxs-lookup"><span data-stu-id="cecfa-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="cecfa-120">通話品質儀表板側重于整個組織的網路效能和問題。</span><span class="sxs-lookup"><span data-stu-id="cecfa-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="cecfa-121">商務用 Skype 系統管理員和網路工程師使用此工具來疑難排解及優化網路效能。</span><span class="sxs-lookup"><span data-stu-id="cecfa-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="cecfa-122">如需詳細資訊，請參閱 [Call Analytics 和通話品質儀表板](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="cecfa-122">For more information, see [Call Analytics and Call Quality Dashboard](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="cecfa-123">當然，您可能想要在內部部署中保留一些通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="cecfa-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="cecfa-124">例如，如果您要使用協力廠商的解決方案與自訂的報表和工作流程，便會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="cecfa-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="cecfa-125">呼叫資料連線器可讓您設定將資料傳送到線上服務，同時在內部部署伺服器上保留資料的複本，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="cecfa-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="cecfa-127">需求</span><span class="sxs-lookup"><span data-stu-id="cecfa-127">Requirements</span></span>

<span data-ttu-id="cecfa-128">下列需求假設您已在支援的拓撲中部署商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="cecfa-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="cecfa-129">如需部署商務用 Skype Server 和支援的拓撲的詳細資訊，請參閱[拓撲基礎](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="cecfa-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md).</span></span> <span data-ttu-id="cecfa-130">若要設定呼叫資料連線器，您必須：</span><span class="sxs-lookup"><span data-stu-id="cecfa-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="cecfa-131">啟用混合連接。</span><span class="sxs-lookup"><span data-stu-id="cecfa-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="cecfa-132">如果您已部署商務用 Skype Server 而且想要啟用呼叫資料連線器，則必須確定您的內部部署與線上環境之間已設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="cecfa-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="cecfa-133">這有時稱為分割網域設定。</span><span class="sxs-lookup"><span data-stu-id="cecfa-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="cecfa-134">如需詳細資訊，請參閱[Plan 商務用 Skype Server 和 Microsoft 365 之間的混合](plan-hybrid-connectivity.md)式連線，或 Office 365 和[設定商務用 Skype Server 及 Microsoft 365 或 Office 365 之間的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="cecfa-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="cecfa-135">驗證您的 Microsoft 365 或 Office 365 組織，並確認您已啟用下列角色：</span><span class="sxs-lookup"><span data-stu-id="cecfa-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="cecfa-136">商務用 Skype Server管理員</span><span class="sxs-lookup"><span data-stu-id="cecfa-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="cecfa-137">Microsoft 365 或 Office 365 全域管理員</span><span class="sxs-lookup"><span data-stu-id="cecfa-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="cecfa-138">如果您還沒有這麼做，請依[開啟和使用通話品質儀表板中的 Microsoft Teams 和商務用 Skype 線上](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述，開啟通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="cecfa-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="cecfa-139">使用本機 LCSCdr 和 QoEMetrics 資料庫，啟用監視的前端集區。</span><span class="sxs-lookup"><span data-stu-id="cecfa-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="cecfa-140">若未這麼做，則通話資料連線器沒有可使用的計量資料。</span><span class="sxs-lookup"><span data-stu-id="cecfa-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cecfa-141">如果前端集區上未啟用監視，則通話資料連線器將無法運作。</span><span class="sxs-lookup"><span data-stu-id="cecfa-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="cecfa-142">正確設定 [伺服器對伺服器驗證](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="cecfa-142">Properly configured [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="cecfa-143">內部部署和線上通話品質儀表板的比較 (CQD) 報告</span><span class="sxs-lookup"><span data-stu-id="cecfa-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="cecfa-144">功能報告</span><span class="sxs-lookup"><span data-stu-id="cecfa-144">Feature reports</span></span> | <span data-ttu-id="cecfa-145">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="cecfa-145">Skype for Business Online</span></span> | <span data-ttu-id="cecfa-146">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="cecfa-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="cecfa-147">應用程式共用度量</span><span class="sxs-lookup"><span data-stu-id="cecfa-147">Application sharing metric</span></span> |<span data-ttu-id="cecfa-148">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-148">Yes</span></span> | <span data-ttu-id="cecfa-149">有限</span><span class="sxs-lookup"><span data-stu-id="cecfa-149">Limited</span></span> |
| <span data-ttu-id="cecfa-150">客戶組建資訊</span><span class="sxs-lookup"><span data-stu-id="cecfa-150">Customer building information</span></span>| <span data-ttu-id="cecfa-151">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-151">Yes</span></span> | <span data-ttu-id="cecfa-152">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-152">Yes</span></span> |
| <span data-ttu-id="cecfa-153">深入分析</span><span class="sxs-lookup"><span data-stu-id="cecfa-153">Drill-down analytics</span></span> | <span data-ttu-id="cecfa-154">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-154">Yes</span></span> | <span data-ttu-id="cecfa-155">否</span><span class="sxs-lookup"><span data-stu-id="cecfa-155">No</span></span> |
| <span data-ttu-id="cecfa-156">媒體可靠性度量</span><span class="sxs-lookup"><span data-stu-id="cecfa-156">Media reliability metrics</span></span> | <span data-ttu-id="cecfa-157">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-157">Yes</span></span> | <span data-ttu-id="cecfa-158">有限</span><span class="sxs-lookup"><span data-stu-id="cecfa-158">Limited</span></span> |
| <span data-ttu-id="cecfa-159">現成的報表</span><span class="sxs-lookup"><span data-stu-id="cecfa-159">Out-of-the-box reports</span></span> | <span data-ttu-id="cecfa-160">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-160">Yes</span></span> | <span data-ttu-id="cecfa-161">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-161">Yes</span></span> |
| <span data-ttu-id="cecfa-162">總覽報表</span><span class="sxs-lookup"><span data-stu-id="cecfa-162">Overview reports</span></span> | <span data-ttu-id="cecfa-163">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-163">Yes</span></span> | <span data-ttu-id="cecfa-164">否</span><span class="sxs-lookup"><span data-stu-id="cecfa-164">No</span></span> |
| <span data-ttu-id="cecfa-165">每個使用者報告</span><span class="sxs-lookup"><span data-stu-id="cecfa-165">Per user reports</span></span> | <span data-ttu-id="cecfa-166">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-166">Yes</span></span> | <span data-ttu-id="cecfa-167">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-167">Yes</span></span> |
| <span data-ttu-id="cecfa-168">報表集合自訂</span><span class="sxs-lookup"><span data-stu-id="cecfa-168">Report set customization</span></span> <br> <span data-ttu-id="cecfa-169"> (新增、刪除、修改報告) </span><span class="sxs-lookup"><span data-stu-id="cecfa-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="cecfa-170">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-170">Yes</span></span> | <span data-ttu-id="cecfa-171">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-171">Yes</span></span> |
| <span data-ttu-id="cecfa-172">以影片為基礎的螢幕共用計量</span><span class="sxs-lookup"><span data-stu-id="cecfa-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="cecfa-173">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-173">Yes</span></span> | <span data-ttu-id="cecfa-174">否</span><span class="sxs-lookup"><span data-stu-id="cecfa-174">No</span></span> |
| <span data-ttu-id="cecfa-175">以程式設計方式存取的資料 APIs</span><span class="sxs-lookup"><span data-stu-id="cecfa-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="cecfa-176">若要 CQD</span><span class="sxs-lookup"><span data-stu-id="cecfa-176">to CQD</span></span> | <span data-ttu-id="cecfa-177">否</span><span class="sxs-lookup"><span data-stu-id="cecfa-177">No</span></span> | <span data-ttu-id="cecfa-178">是</span><span class="sxs-lookup"><span data-stu-id="cecfa-178">Yes</span></span> |
||||