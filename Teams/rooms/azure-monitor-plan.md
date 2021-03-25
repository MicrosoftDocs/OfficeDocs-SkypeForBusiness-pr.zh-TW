---
title: 使用 Azure 監視器規劃 Microsoft Teams 會議室管理
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
description: 本文討論在商務用 Skype 或 Teams 中使用 Azure 監視器管理 Microsoft Teams 會議室裝置時，規劃的考慮。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117581"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>使用 Azure 監視器規劃 Microsoft Teams 會議室管理
 
 本文討論在 Microsoft Teams 或商務用 Skype 的實現中使用 Azure 監視器管理 Microsoft Teams 會議室裝置的計畫考慮。
  
[Azure 監視器](/azure/azure-monitor/overview) 是一組從一開始在雲端中設計的管理服務集合。 Azure 監視器元件完全託管在 Azure 中，而不是部署和管理內部部署資源。 組組是最小的，您只需要幾分鐘就可以順利上電。 在一些自訂作業中，它可提供個別會議室系統健康情況或錯誤即時通知，協助管理 Microsoft Teams 會議室會議系統，而且可能會放大管理數千個 Microsoft Teams 會議室會議室。
  
本文提供實管 Microsoft Teams 會議室會議裝置之 Azure 監視器管理所需的需求、設計/架構及實做最佳做法的討論，並提供有關為 Microsoft Teams 會議室實做 Azure 監視器的詳細文章連結，以及持續監控 Microsoft Teams 會議室的重要參考資訊。 
  
## <a name="functional-overview"></a>功能概觀

![使用 Azure 監視器管理 Microsoft Teams 會議室的圖表](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
主機裝置上的 Microsoft Teams 會議室應用程式會將事件寫入其 Windows 事件記錄。 安裝之後，Microsoft 監控代理程式會將資訊傳遞至 Azure Monitor 服務。 
  
正確配置之後，Log Analytics 會剖析事件描述內嵌的 JSON 負載，以描述每個 Microsoft Teams 會議室系統的運作方式，以及偵測到哪些錯誤。 
  
使用 Azure 監視器的系統管理員可以取得離線或遇到 App、連線或硬體故障的 Microsoft Teams 會議室系統通知，以及知道系統是否必須重新開機。 每個系統狀態會經常更新，因此這些通知會接近即時更新。
  
## <a name="azure-monitor-requirements"></a>Azure 監視器需求

您必須擁有有效的 Azure 訂閱，才能使用 Azure 監視器的記錄分析功能。 請參閱 [開始使用記錄分析工作區](/azure/azure-monitor/learn/quick-create-workspace) ，為貴組織建立訂閱。
  
您應該視需要熟悉如何使用記錄分析視圖設計工具。 請參閱 [記錄分析中的查看，](/azure/azure-monitor/platform/view-designer) 瞭解這些詳細資料。
  
### <a name="related-tasks"></a>相關工作

1. 訂閱 Azure 監視器記錄分析之後，請建立自訂欄位 (如地圖 [自訂](azure-monitor-deploy.md#Custom_fields) 欄位) 所述，以剖析從 Microsoft Teams 會議室主控台所送出的資訊。 這包括瞭解在瞭解記錄專案中記載的 [JSON 架構](azure-monitor-manage.md#understand-the-log-entries)。
    
2. 在記錄分析中開發 Microsoft Teams 會議室管理檢視。 您可以使用輸入方法建立 [Microsoft Teams 會議室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) ，或手動建立 [Microsoft Teams 會議室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>個別 Microsoft Teams 會議室主機需求

每個 Microsoft Teams 會議室主控台都是在 Surface Pro 裝置上以資訊站模式執行的應用程式 (通常，它已配置為唯一可在裝置上執行的應用程式) 。 如同任何 Windows App 一樣，Microsoft Teams 會議室應用程式會將啟動和硬體錯誤等事件寫入 Windows 事件記錄。 在 Microsoft Teams 會議室裝置上新增 Microsoft Monitor 代理程式可讓您收集這些事件。  (請參閱 [將 Windows 電腦連接到 Azure](/azure/azure-monitor/platform/agent-windows) 中的記錄分析服務以) 
  
## <a name="ongoing-management"></a>持續管理

使用 Azure 監視器管理 Microsoft Teams 會議室裝置時，您必須瞭解 Azure 監視器使用的事件記錄中包含的資訊。 請參閱 [瞭解這些健康情況訊息](azure-monitor-manage.md#understand-the-log-entries) 的詳細資訊記錄專案。
  
### <a name="related-tasks"></a>相關工作

- 瞭解 Microsoft Teams 會議室產生的通知，以及如何解決 (請參閱瞭解記錄專案) [](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>另請參閱

[使用 Azure 監視器部署 Microsoft Teams 會議室管理](azure-monitor-deploy.md)
  
[使用 Azure 監視器管理 Microsoft Teams 會議室裝置](azure-monitor-manage.md)