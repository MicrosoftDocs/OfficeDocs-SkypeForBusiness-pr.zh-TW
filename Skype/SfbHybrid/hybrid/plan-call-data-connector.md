---
title: 規劃通話資料連線器 |通話品質儀表板監視混合式分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在混合式案例中使用商務用 Skype Online 遙測工具來監控內部部署實現的概覽。
ms.openlocfilehash: 3300ad17b109ac069c4f7382f610dd0214b30197
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328425"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="6ead6-103">規劃通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="6ead6-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="6ead6-104">概觀</span><span class="sxs-lookup"><span data-stu-id="6ead6-104">Overview</span></span>

<span data-ttu-id="6ead6-105">本主題說明實現商務用 Skype Server 通話資料連線器的優點、規劃考慮及需求。</span><span class="sxs-lookup"><span data-stu-id="6ead6-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="6ead6-106">如需設定呼叫資料連線器的詳細資訊，請參閱[設定呼叫資料連線器](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="6ead6-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="6ead6-107">呼叫資料連線器極大地簡化了混合式環境中的呼叫監視，因為您不再需要使用不同的內部部署和線上工具來監控所有使用者的通話品質。</span><span class="sxs-lookup"><span data-stu-id="6ead6-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="6ead6-108">無論您的使用者是駐留在內部部署還是線上，您都可以選擇在線上查看整個組織的通話品質。</span><span class="sxs-lookup"><span data-stu-id="6ead6-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="6ead6-109">使用 [呼叫資料連線器]，您可以使用單一工具集來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="6ead6-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="6ead6-110">在 Microsoft 團隊、商務用 Skype Online 和商務用 Skype Server 上監控您的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="6ead6-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="6ead6-111">在您的網路上查看問題並進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="6ead6-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="6ead6-112">指派呼叫分析的 [支援人員] 和 [系統管理員] 角色，讓技術支援人員能查看並疑難排解其職責範圍。</span><span class="sxs-lookup"><span data-stu-id="6ead6-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="6ead6-113">使用呼叫資料連線器時，商務用 Skype 伺服器會將資料推入雲端服務，以便您利用商務用 Skype Online 通話分析（CA）和通話品質儀表板（CQD）工具，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6ead6-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="6ead6-115">伺服器會將體驗品質（QoE）推入，並呼叫詳細資料錄製（CDR）資料至線上服務。</span><span class="sxs-lookup"><span data-stu-id="6ead6-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="6ead6-116">[通話分析] 和 [CQD 工具] 可讓您監控通話品質，以及使用 Microsoft 團隊與商務用 Skype 服務的連線問題進行疑難排解，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ead6-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="6ead6-117">呼叫分析重點針對特定通話的品質問題。</span><span class="sxs-lookup"><span data-stu-id="6ead6-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="6ead6-118">它會顯示商務用 Skype 帳戶中每位使用者的通話與會議的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6ead6-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="6ead6-119">有了呼叫分析，您就可以將許可權指派給支援人員的操作員，而不需存取其餘的商務用 Skype 系統管理中心，就可以監視通話。</span><span class="sxs-lookup"><span data-stu-id="6ead6-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="6ead6-120">[通話品質儀表板] 重點說明整個組織的網路效能與問題。</span><span class="sxs-lookup"><span data-stu-id="6ead6-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="6ead6-121">商務用 Skype 系統管理員和網路工程人員使用這個工具來疑難排解及優化網路效能。</span><span class="sxs-lookup"><span data-stu-id="6ead6-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="6ead6-122">如需詳細資訊，請參閱[通話分析和通話品質儀表板](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="6ead6-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="6ead6-123">當然，您可能會想要在內部部署中保留一些通話品質資料。</span><span class="sxs-lookup"><span data-stu-id="6ead6-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="6ead6-124">例如，如果您使用的是協力廠商解決方案，且已自訂報表與工作流程，則可能是這種情況。</span><span class="sxs-lookup"><span data-stu-id="6ead6-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="6ead6-125">[通話資料連線器] 可讓您設定將資料傳送至線上服務，同時也會在您的內部部署伺服器上保留一份資料複本，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="6ead6-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB 雲端語音信箱](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="6ead6-127">需求</span><span class="sxs-lookup"><span data-stu-id="6ead6-127">Requirements</span></span>

<span data-ttu-id="6ead6-128">下列需求假設您已在支援的拓撲中部署商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6ead6-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="6ead6-129">如需有關部署商務用 Skype Server 和支援的拓撲的詳細資訊，請參閱[拓撲結構基礎](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)。</span><span class="sxs-lookup"><span data-stu-id="6ead6-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="6ead6-130">若要設定呼叫資料連線器，您必須：</span><span class="sxs-lookup"><span data-stu-id="6ead6-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="6ead6-131">啟用混合式連接。</span><span class="sxs-lookup"><span data-stu-id="6ead6-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="6ead6-132">如果您已部署商務用 Skype Server 且想要啟用呼叫資料連線器，您必須確保您在內部部署與線上環境之間已設定混合式連接。</span><span class="sxs-lookup"><span data-stu-id="6ead6-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="6ead6-133">這有時稱為分割網域配置。</span><span class="sxs-lookup"><span data-stu-id="6ead6-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="6ead6-134">如需詳細資訊，請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md)，以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="6ead6-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="6ead6-135">驗證您的 Office 365 租使用者，並確認您已啟用下列角色：</span><span class="sxs-lookup"><span data-stu-id="6ead6-135">Authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="6ead6-136">商務用 Skype Server 系統管理員</span><span class="sxs-lookup"><span data-stu-id="6ead6-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="6ead6-137">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="6ead6-137">Office 365 Global Administrator</span></span>

- <span data-ttu-id="6ead6-138">如果您尚未這麼做，請開啟 [通話品質儀表板]，如[開啟並使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板](/microsoftteams/turning-on-and-using-call-quality-dashboard)中所述。</span><span class="sxs-lookup"><span data-stu-id="6ead6-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="6ead6-139">使用 local LCSCdr 和 QoEMetrics 資料庫啟用監視的前端池。</span><span class="sxs-lookup"><span data-stu-id="6ead6-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="6ead6-140">若未這麼做，通話資料連線器將無法使用公制資料。</span><span class="sxs-lookup"><span data-stu-id="6ead6-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ead6-141">如果未在前端池中啟用監視，則呼叫資料連線器將無法運作。</span><span class="sxs-lookup"><span data-stu-id="6ead6-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="6ead6-142">已正確設定[伺服器對伺服器驗證](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)。</span><span class="sxs-lookup"><span data-stu-id="6ead6-142">Properly configured [server-to-server authentication](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="6ead6-143">內部部署與線上通話品質儀表板（CQD）報告的比較</span><span class="sxs-lookup"><span data-stu-id="6ead6-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="6ead6-144">功能報告</span><span class="sxs-lookup"><span data-stu-id="6ead6-144">Feature reports</span></span> | <span data-ttu-id="6ead6-145">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6ead6-145">Skype for Business Online</span></span> | <span data-ttu-id="6ead6-146">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="6ead6-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="6ead6-147">應用程式共用躍點數</span><span class="sxs-lookup"><span data-stu-id="6ead6-147">Application sharing metric</span></span> |<span data-ttu-id="6ead6-148">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-148">Yes</span></span> | <span data-ttu-id="6ead6-149">受</span><span class="sxs-lookup"><span data-stu-id="6ead6-149">Limited</span></span> |
| <span data-ttu-id="6ead6-150">客戶建築物資訊</span><span class="sxs-lookup"><span data-stu-id="6ead6-150">Customer building information</span></span>| <span data-ttu-id="6ead6-151">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-151">Yes</span></span> | <span data-ttu-id="6ead6-152">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-152">Yes</span></span> |
| <span data-ttu-id="6ead6-153">向下切入分析</span><span class="sxs-lookup"><span data-stu-id="6ead6-153">Drill-down analytics</span></span> | <span data-ttu-id="6ead6-154">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-154">Yes</span></span> | <span data-ttu-id="6ead6-155">不</span><span class="sxs-lookup"><span data-stu-id="6ead6-155">No</span></span> |
| <span data-ttu-id="6ead6-156">媒體可靠性度量單位</span><span class="sxs-lookup"><span data-stu-id="6ead6-156">Media reliability metrics</span></span> | <span data-ttu-id="6ead6-157">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-157">Yes</span></span> | <span data-ttu-id="6ead6-158">受</span><span class="sxs-lookup"><span data-stu-id="6ead6-158">Limited</span></span> |
| <span data-ttu-id="6ead6-159">外框報告</span><span class="sxs-lookup"><span data-stu-id="6ead6-159">Out-of-the-box reports</span></span> | <span data-ttu-id="6ead6-160">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-160">Yes</span></span> | <span data-ttu-id="6ead6-161">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-161">Yes</span></span> |
| <span data-ttu-id="6ead6-162">[總覽] 報表</span><span class="sxs-lookup"><span data-stu-id="6ead6-162">Overview reports</span></span> | <span data-ttu-id="6ead6-163">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-163">Yes</span></span> | <span data-ttu-id="6ead6-164">不</span><span class="sxs-lookup"><span data-stu-id="6ead6-164">No</span></span> |
| <span data-ttu-id="6ead6-165">每位使用者報告</span><span class="sxs-lookup"><span data-stu-id="6ead6-165">Per user reports</span></span> | <span data-ttu-id="6ead6-166">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-166">Yes</span></span> | <span data-ttu-id="6ead6-167">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-167">Yes</span></span> |
| <span data-ttu-id="6ead6-168">報表集自訂</span><span class="sxs-lookup"><span data-stu-id="6ead6-168">Report set customization</span></span> <br> <span data-ttu-id="6ead6-169">（[新增]、[刪除]、[修改報告]）</span><span class="sxs-lookup"><span data-stu-id="6ead6-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="6ead6-170">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-170">Yes</span></span> | <span data-ttu-id="6ead6-171">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-171">Yes</span></span> |
| <span data-ttu-id="6ead6-172">以影片為基礎的畫面共用規格</span><span class="sxs-lookup"><span data-stu-id="6ead6-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="6ead6-173">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-173">Yes</span></span> | <span data-ttu-id="6ead6-174">不</span><span class="sxs-lookup"><span data-stu-id="6ead6-174">No</span></span> |
| <span data-ttu-id="6ead6-175">以程式設計方式存取的資料 Api</span><span class="sxs-lookup"><span data-stu-id="6ead6-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="6ead6-176">若要 CQD</span><span class="sxs-lookup"><span data-stu-id="6ead6-176">to CQD</span></span> | <span data-ttu-id="6ead6-177">不</span><span class="sxs-lookup"><span data-stu-id="6ead6-177">No</span></span> | <span data-ttu-id="6ead6-178">是的</span><span class="sxs-lookup"><span data-stu-id="6ead6-178">Yes</span></span> |
||||
