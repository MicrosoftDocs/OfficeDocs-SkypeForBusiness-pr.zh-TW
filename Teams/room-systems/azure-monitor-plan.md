---
title: 使用 Azure 監視器規劃 Microsoft 團隊聊天室管理
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: 本文將討論使用 Azure 監視器來管理商務用 Skype 或團隊實現中的 Microsoft 團隊會議室裝置的規劃考慮。
ms.openlocfilehash: 6536ee07ef64119d3529c7b9f279df3a7bbbdaed
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184335"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>使用 Azure 監視器規劃 Microsoft 團隊聊天室管理
 
 本文將討論使用 Azure 監視器來管理 Microsoft 團隊或商務用 Skype 實現中的 Microsoft 團隊會議室裝置的規劃考慮。
  
[Azure 監視器](https://docs.microsoft.com/azure/azure-monitor/overview)是從開始就在雲端中設計的管理服務集合。 Azure 監視器元件完全託管于 Azure 中, 而不是部署和管理內部部署資源。 配置最小, 在幾分鐘內您就可以依原義地啟動並執行。 有了一些自訂作業, it 能協助您管理 Microsoft 團隊會議室會議系統, 方法是提供即時通知給個別房間系統的系統健康情況或故障, 而且可能會擴大以管理成千上萬個 Microsoft 團隊會議室會議室。
  
本文將討論針對 Microsoft 團隊聊天室會議裝置的 Azure 監視器管理所需執行的需求、設計/架構和實施最佳做法, 並提供詳細文章的連結針對 Microsoft 團隊聊天室和對 Microsoft 團隊會議室進行即時監視的重要參考資訊, 實施 Azure 監視器。 
  
## <a name="functional-overview"></a>功能概覽

![使用 Azure 監視器的 Microsoft 團隊聊天室管理圖表](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
主機裝置上的 Microsoft [小組聊天室] app 會將事件寫入其 Windows 事件記錄檔。 安裝 Microsoft Monitoring agent 之後, 就會將資訊傳送到 Azure 監視器服務。 
  
設定正確之後, Log Analytics 會分析事件描述中內嵌的 JSON 負載, 說明每個 Microsoft 團隊聊天室系統如何運作, 以及偵測到哪些故障。 
  
使用 Azure 監視器的管理員可以取得離線或遇到 app、連線或硬體故障的 Microsoft 團隊聊天室系統通知, 以及瞭解是否需要重新開機系統。 每個系統狀態都會經常更新, 因此這些通知會接近即時更新。
  
## <a name="azure-monitor-requirements"></a>Azure 監視器需求

您必須具備有效的 Azure 監視器 Azure 訂閱才能使用 Log Analytics 功能。 請參閱[開始使用 Log Analytics 工作區](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace), 為您的組織建立訂閱。
  
您應該熟悉如何使用 Log Analytics 視圖設計工具。 如需詳細資訊, 請參閱[記錄分析中的視圖](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。
  
### <a name="related-tasks"></a>相關任務

1. 訂閱 Azure 監視器記錄分析之後, 請建立自訂欄位 (如[對應自訂欄位](azure-monitor-deploy.md#Custom_fields)所述), 以分析將從 Microsoft 團隊聊天室主控台傳送的資訊。 這包括瞭解在[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)中記錄的 JSON 架構。
    
2. 在 Log Analytics 中開發 Microsoft 團隊聊天室管理檢視。 您可以使用 import 方法或[手動建立 Microsoft 團隊聊天室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually), 來[建立 microsoft 團隊聊天室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>個別 Microsoft 團隊會議室的需求

每個 Microsoft [團隊聊天室] 主控台都是在 kiosk 模式 (通常是設定為可以在裝置上執行) 的 Surface Pro 裝置上執行的 app。 就像任何 Windows app 一樣, Microsoft 團隊聊天室 app 會將啟動和硬體故障等事件寫入 Windows 事件記錄檔。 在 Microsoft 團隊聊天室裝置上新增 Microsoft 監視器代理程式後, 就能收集這些事件。 (如需詳細資訊, 請參閱[將 Windows 電腦連線至 Azure 中的 Log Analytics 服務](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。)
  
## <a name="ongoing-management"></a>持續管理

使用 Azure 監視器來管理 Microsoft 團隊聊天室裝置時, 您必須瞭解 Azure 監視器所使用的事件記錄中所包含的資訊。 如需這些狀況訊息的詳細資料, 請參閱[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)。
  
### <a name="related-tasks"></a>相關任務

- 瞭解 Microsoft 團隊聊天室所產生的通知, 以及如何解決這些警報 (請參閱標題為[瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)的章節)
    
## <a name="see-also"></a>另請參閱

[使用 Azure 監視器部署 Microsoft 團隊聊天室管理](azure-monitor-deploy.md)
  
[使用 Azure 監視器管理 Microsoft 團隊聊天室裝置](azure-monitor-manage.md)