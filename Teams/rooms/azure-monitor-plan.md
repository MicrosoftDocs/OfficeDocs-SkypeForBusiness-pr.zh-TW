---
title: 使用 azure 監視器Microsoft Teams 會議室管理計畫
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 本文討論規劃使用 Azure 監視器管理Microsoft Teams 會議室裝置或商務用 Skype或Teams考慮。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117581"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="22d2e-103">使用 azure 監視器Microsoft Teams 會議室管理計畫</span><span class="sxs-lookup"><span data-stu-id="22d2e-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="22d2e-104">本文討論規劃使用 Azure 監視器管理Microsoft Teams 會議室或Microsoft Teams裝置商務用 Skype考慮。</span><span class="sxs-lookup"><span data-stu-id="22d2e-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="22d2e-105">[Azure 監視器](/azure/azure-monitor/overview) 是一組從一開始在雲端中設計的管理服務集合。</span><span class="sxs-lookup"><span data-stu-id="22d2e-105">[Azure Monitor](/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="22d2e-106">Azure 監視器元件完全託管在 Azure 中，而不是部署和管理內部部署資源。</span><span class="sxs-lookup"><span data-stu-id="22d2e-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="22d2e-107">組組是最小的，您只需要幾分鐘就可以完全啟動並運作。</span><span class="sxs-lookup"><span data-stu-id="22d2e-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="22d2e-108">有了一些自訂工作，它可針對個別會議室系統提供系統健康情況或錯誤即時通知，協助管理 Microsoft Teams 會議室 會議系統，而且可以向上擴展以管理數千Microsoft Teams 會議室會議室。</span><span class="sxs-lookup"><span data-stu-id="22d2e-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="22d2e-109">本文提供實行 Microsoft Teams 會議室 會議裝置 Azure 監視器管理所需的需求、設計/架構及實做最佳做法的討論，並提供有關實做 Microsoft Teams 會議室 版 Azure 監視器的詳細文章的連結，以及持續監控 Microsoft Teams 會議室 會議室的重要參考資訊。</span><span class="sxs-lookup"><span data-stu-id="22d2e-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="22d2e-110">功能概觀</span><span class="sxs-lookup"><span data-stu-id="22d2e-110">Functional overview</span></span>

![使用 Azure 監視器Microsoft Teams 會議室管理圖表](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="22d2e-112">主機Microsoft Teams 會議室上的應用程式會將事件寫入其Windows記錄。</span><span class="sxs-lookup"><span data-stu-id="22d2e-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="22d2e-113">安裝之後，Microsoft 監控代理程式會將資訊傳遞至 Azure Monitor 服務。</span><span class="sxs-lookup"><span data-stu-id="22d2e-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="22d2e-114">正確配置之後，Log Analytics 會剖析事件描述中內嵌的 JSON 負載，以描述每個Microsoft Teams 會議室系統的運作方式，以及偵測到哪些錯誤。</span><span class="sxs-lookup"><span data-stu-id="22d2e-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="22d2e-115">使用 Azure 監視器的系統管理員Microsoft Teams 會議室離線或遇到應用程式、連線或硬體失敗之系統的通知，以及知道系統是否必須重新開機。</span><span class="sxs-lookup"><span data-stu-id="22d2e-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="22d2e-116">每個系統狀態會經常更新，因此這些通知會接近即時更新。</span><span class="sxs-lookup"><span data-stu-id="22d2e-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="22d2e-117">Azure 監視器需求</span><span class="sxs-lookup"><span data-stu-id="22d2e-117">Azure Monitor requirements</span></span>

<span data-ttu-id="22d2e-118">您必須擁有有效的 Azure 訂閱，才能使用 Azure 監視器的記錄分析功能。</span><span class="sxs-lookup"><span data-stu-id="22d2e-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="22d2e-119">請參閱 [開始使用記錄分析工作區](/azure/azure-monitor/learn/quick-create-workspace) ，為貴組織建立訂閱。</span><span class="sxs-lookup"><span data-stu-id="22d2e-119">See [Get started with a Log Analytics workspace](/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="22d2e-120">您應該視需要熟悉如何使用記錄分析視圖設計工具。</span><span class="sxs-lookup"><span data-stu-id="22d2e-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="22d2e-121">請參閱 [記錄分析中的查看，](/azure/azure-monitor/platform/view-designer) 瞭解這些詳細資料。</span><span class="sxs-lookup"><span data-stu-id="22d2e-121">See [Views in Log Analytics](/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="22d2e-122">相關工作</span><span class="sxs-lookup"><span data-stu-id="22d2e-122">Related Tasks</span></span>

1. <span data-ttu-id="22d2e-123">訂閱 Azure 監視器記錄分析之後，請建立自訂欄位 (如地圖自訂欄位[) ](azure-monitor-deploy.md#Custom_fields)所述，以剖析從 Microsoft Teams 會議室 主機Microsoft Teams 會議室的資訊。</span><span class="sxs-lookup"><span data-stu-id="22d2e-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="22d2e-124">這包括瞭解在瞭解記錄專案中記載的 [JSON 架構](azure-monitor-manage.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="22d2e-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="22d2e-125">在記錄Microsoft Teams 會議室中建立管理檢視。</span><span class="sxs-lookup"><span data-stu-id="22d2e-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="22d2e-126">您可以使用輸入[方法](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)Microsoft Teams 會議室建立儀表板，或手動建立Microsoft Teams 會議室[儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。</span><span class="sxs-lookup"><span data-stu-id="22d2e-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="22d2e-127">個別Microsoft Teams 會議室主機需求</span><span class="sxs-lookup"><span data-stu-id="22d2e-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="22d2e-128">每個 Microsoft Teams 會議室 主機都是在 Surface Pro 裝置上以資訊站模式執行的應用程式 (通常，它被配置為唯一可在裝置上執行的應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="22d2e-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="22d2e-129">如同任何Windows應用程式一樣，Microsoft Teams 會議室應用程式會將啟動和硬體錯誤等事件寫入 Windows記錄。</span><span class="sxs-lookup"><span data-stu-id="22d2e-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="22d2e-130">在裝置上新增 Microsoft 監視器Microsoft Teams 會議室可讓您收集這些事件。</span><span class="sxs-lookup"><span data-stu-id="22d2e-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="22d2e-131"> (請參閱連線 Windows到[Azure](/azure/azure-monitor/platform/agent-windows)中的記錄分析服務以查看詳細資料。) </span><span class="sxs-lookup"><span data-stu-id="22d2e-131">(See [Connect Windows computers to the Log Analytics service in Azure](/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="22d2e-132">持續管理</span><span class="sxs-lookup"><span data-stu-id="22d2e-132">Ongoing management</span></span>

<span data-ttu-id="22d2e-133">使用 Azure 監視器管理您的Microsoft Teams 會議室裝置時，您必須瞭解 Azure 監視器使用的事件記錄中包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="22d2e-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="22d2e-134">請參閱 [瞭解這些健康情況訊息](azure-monitor-manage.md#understand-the-log-entries) 的詳細資訊記錄專案。</span><span class="sxs-lookup"><span data-stu-id="22d2e-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="22d2e-135">相關工作</span><span class="sxs-lookup"><span data-stu-id="22d2e-135">Related Tasks</span></span>

- <span data-ttu-id="22d2e-136">瞭解使用者產生的Microsoft Teams 會議室，以及如何解決 (請參閱瞭解記錄專案) [](azure-monitor-manage.md#understand-the-log-entries)</span><span class="sxs-lookup"><span data-stu-id="22d2e-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22d2e-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="22d2e-137">See also</span></span>

[<span data-ttu-id="22d2e-138">使用 azure Microsoft Teams 會議室部署管理</span><span class="sxs-lookup"><span data-stu-id="22d2e-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="22d2e-139">使用 azure 監視器Microsoft Teams 會議室管理裝置</span><span class="sxs-lookup"><span data-stu-id="22d2e-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)