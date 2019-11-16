---
title: 使用 Azure 監視器規劃 Microsoft 團隊聊天室管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 本文將討論使用 Azure 監視器來管理商務用 Skype 或團隊實現中的 Microsoft 團隊會議室裝置的規劃考慮。
ms.openlocfilehash: 1e5c41866b02a74bee06b472623919f955691dd9
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675781"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="84bb5-103">使用 Azure 監視器規劃 Microsoft 團隊聊天室管理</span><span class="sxs-lookup"><span data-stu-id="84bb5-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="84bb5-104">本文將討論使用 Azure 監視器來管理 Microsoft 團隊或商務用 Skype 實現中的 Microsoft 團隊會議室裝置的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="84bb5-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="84bb5-105">[Azure 監視器](https://docs.microsoft.com/azure/azure-monitor/overview)是從開始就在雲端中設計的管理服務集合。</span><span class="sxs-lookup"><span data-stu-id="84bb5-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="84bb5-106">Azure 監視器元件完全託管于 Azure 中，而不是部署和管理內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="84bb5-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="84bb5-107">配置最小，在幾分鐘內您就可以依原義地啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="84bb5-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="84bb5-108">有了一些自訂作業，it 能協助您管理 Microsoft 團隊會議室會議系統，方法是提供即時通知給個別房間系統的系統健康情況或故障，而且可能會擴大以管理成千上萬個 Microsoft 團隊會議室會議室。</span><span class="sxs-lookup"><span data-stu-id="84bb5-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="84bb5-109">本文提供針對 microsoft 團隊會議室會議裝置的 Azure 監視器管理所需執行的需求、設計/架構和實施最佳做法的討論，並提供有關針對 microsoft 團隊會議室進行即時監視的詳細文章的連結。</span><span class="sxs-lookup"><span data-stu-id="84bb5-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="84bb5-110">功能概覽</span><span class="sxs-lookup"><span data-stu-id="84bb5-110">Functional overview</span></span>

![使用 Azure 監視器的 Microsoft 團隊聊天室管理圖表](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="84bb5-112">主機裝置上的 Microsoft [小組聊天室] app 會將事件寫入其 Windows 事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="84bb5-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="84bb5-113">安裝 Microsoft Monitoring agent 之後，就會將資訊傳送到 Azure 監視器服務。</span><span class="sxs-lookup"><span data-stu-id="84bb5-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="84bb5-114">設定正確之後，Log Analytics 會分析事件描述中內嵌的 JSON 負載，說明每個 Microsoft 團隊聊天室系統如何運作，以及偵測到哪些故障。</span><span class="sxs-lookup"><span data-stu-id="84bb5-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="84bb5-115">使用 Azure 監視器的管理員可以取得離線或遇到 app、連線或硬體故障的 Microsoft 團隊聊天室系統通知，以及瞭解是否需要重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="84bb5-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="84bb5-116">每個系統狀態都會經常更新，因此這些通知會接近即時更新。</span><span class="sxs-lookup"><span data-stu-id="84bb5-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="84bb5-117">Azure 監視器需求</span><span class="sxs-lookup"><span data-stu-id="84bb5-117">Azure Monitor requirements</span></span>

<span data-ttu-id="84bb5-118">您必須具備有效的 Azure 監視器 Azure 訂閱才能使用 Log Analytics 功能。</span><span class="sxs-lookup"><span data-stu-id="84bb5-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="84bb5-119">請參閱[開始使用 Log Analytics 工作區](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)，為您的組織建立訂閱。</span><span class="sxs-lookup"><span data-stu-id="84bb5-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="84bb5-120">您應該熟悉如何使用 Log Analytics 視圖設計工具。</span><span class="sxs-lookup"><span data-stu-id="84bb5-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="84bb5-121">如需詳細資訊，請參閱[記錄分析中的視圖](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。</span><span class="sxs-lookup"><span data-stu-id="84bb5-121">See [Views in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="84bb5-122">相關任務</span><span class="sxs-lookup"><span data-stu-id="84bb5-122">Related Tasks</span></span>

1. <span data-ttu-id="84bb5-123">訂閱 Azure 監視器記錄分析之後，請建立自訂欄位（如[對應自訂欄位](azure-monitor-deploy.md#Custom_fields)所述），以分析將從 Microsoft 團隊聊天室主控台傳送的資訊。</span><span class="sxs-lookup"><span data-stu-id="84bb5-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="84bb5-124">這包括瞭解在[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)中記錄的 JSON 架構。</span><span class="sxs-lookup"><span data-stu-id="84bb5-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="84bb5-125">在 Log Analytics 中開發 Microsoft 團隊聊天室管理檢視。</span><span class="sxs-lookup"><span data-stu-id="84bb5-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="84bb5-126">您可以使用 import 方法或[手動建立 Microsoft 團隊聊天室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)，來[建立 microsoft 團隊聊天室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)。</span><span class="sxs-lookup"><span data-stu-id="84bb5-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="84bb5-127">個別 Microsoft 團隊會議室的需求</span><span class="sxs-lookup"><span data-stu-id="84bb5-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="84bb5-128">每個 Microsoft [團隊聊天室] 主控台都是在 kiosk 模式（通常是設定為可以在裝置上執行）的 Surface Pro 裝置上執行的 app。</span><span class="sxs-lookup"><span data-stu-id="84bb5-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="84bb5-129">就像任何 Windows app 一樣，Microsoft 團隊聊天室 app 會將啟動和硬體故障等事件寫入 Windows 事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="84bb5-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="84bb5-130">在 Microsoft 團隊聊天室裝置上新增 Microsoft 監視器代理程式後，就能收集這些事件。</span><span class="sxs-lookup"><span data-stu-id="84bb5-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="84bb5-131">（如需詳細資訊，請參閱[將 Windows 電腦連線至 Azure 中的 Log Analytics 服務](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。）</span><span class="sxs-lookup"><span data-stu-id="84bb5-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="84bb5-132">持續管理</span><span class="sxs-lookup"><span data-stu-id="84bb5-132">Ongoing management</span></span>

<span data-ttu-id="84bb5-133">使用 Azure 監視器來管理 Microsoft 團隊聊天室裝置時，您必須瞭解 Azure 監視器所使用的事件記錄中所包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="84bb5-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="84bb5-134">如需這些狀況訊息的詳細資料，請參閱[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="84bb5-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="84bb5-135">相關任務</span><span class="sxs-lookup"><span data-stu-id="84bb5-135">Related Tasks</span></span>

- <span data-ttu-id="84bb5-136">瞭解 Microsoft 團隊聊天室所產生的通知，以及如何解決這些警報（請參閱標題為[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)的章節）</span><span class="sxs-lookup"><span data-stu-id="84bb5-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="84bb5-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="84bb5-137">See also</span></span>

[<span data-ttu-id="84bb5-138">使用 Azure 監視器部署 Microsoft 團隊聊天室管理</span><span class="sxs-lookup"><span data-stu-id="84bb5-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="84bb5-139">使用 Azure 監視器管理 Microsoft 團隊聊天室裝置</span><span class="sxs-lookup"><span data-stu-id="84bb5-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)