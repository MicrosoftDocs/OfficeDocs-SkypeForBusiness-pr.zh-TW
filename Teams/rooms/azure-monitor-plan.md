---
title: 使用 Azure 監視器規劃Microsoft Teams 會議室監控
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 本文討論使用 Azure 監視器監控 商務用 Skype 或 Teams 實作中Microsoft Teams 會議室的規劃考慮。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269568"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>使用 Azure 監視器規劃Microsoft Teams 會議室監控
 
 本文討論使用 Azure 監視器管理 Microsoft Teams 中Microsoft Teams 會議室裝置或商務用 Skype實作的規劃考慮。

> [!NOTE]
> 您也可以使用 Teams 系統管理中心[設定Teams 會議室的健康情況監控](../alerts/device-health-status.md)。

[Azure 監視器](/azure/azure-monitor/overview) 是一組監控服務集合，從一開始就在雲端中設計。 Azure 監視器元件完全裝載于 Azure 中，而不是部署和管理內部部署資源。 設定最小，而且您只要幾分鐘就能啟動並執行。 透過某些自訂工作，它可透過提供個別會議室系統系統系統健康情況或錯誤的通知，協助監控Microsoft Teams 會議室，而且可以放大為管理數千個Microsoft Teams 會議室。
  
本文將探討實作 Azure 監視器以監控Microsoft Teams 會議室所需的需求、設計/架構和實作最佳做法。 它也會提供實作 Azure 監視器的詳細文章連結，以取得Microsoft Teams 會議室以及持續監視Microsoft Teams 會議室會議室的重要參考資訊。
  
## <a name="functional-overview"></a>功能概觀

![使用 Azure 監視器管理Microsoft Teams 會議室圖表。](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Microsoft Teams 會議室應用程式會將事件寫入 Windows 事件記錄檔。 安裝之後，Microsoft 監控專員會將資訊傳遞給 Azure 監視器服務。
  
一旦正確設定後，Log Analytics 會剖析事件描述中內嵌的 JSON 承載，以描述Microsoft Teams 會議室如何運作，以及偵測到哪些錯誤。
  
使用 Azure 監視器的系統管理員可以收到Microsoft Teams 會議室離線或發生應用程式、連線或硬體故障的通知，以及知道系統是否需要重新開機。 每個系統狀態都會經常更新，因此這些通知即將接近即時更新。
  
## <a name="azure-monitor-requirements"></a>Azure 監視器需求

您必須擁有 Azure 監視器的有效 Azure 訂閱，才能使用 Log Analytics 功能。 請參閱 [開始使用記錄分析工作區](/azure/azure-monitor/learn/quick-create-workspace) ，為您的組織建立訂閱。
  
您應該熟悉如何使用記錄分析檢視設計工具。 如需這些詳細資料，請參 [閱記錄分析中的檢視](/azure/azure-monitor/platform/view-designer) 。
  
### <a name="related-tasks"></a>相關工作

1. 訂閱 Azure 監視器記錄分析之後， (建立自訂欄位，如對應[自訂欄位](azure-monitor-deploy.md#Custom_fields)所述，) 剖析要從Microsoft Teams 會議室傳送的資訊。 這包括瞭解在 [瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)中所記錄的 JSON 架構。
    
2. 在 Log Analytics 中開發Microsoft Teams 會議室管理檢視。 您可以[手動建立Microsoft Teams 會議室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>個人Microsoft Teams 會議室需求

Microsoft Teams 會議室是以 kiosk 模式在計算裝置上執行的應用程式。 與任何 Windows 應用程式一樣，Microsoft Teams 會議室應用程式會將啟動和硬體錯誤等事件寫入 Windows 事件記錄檔。 在 Microsoft Teams 會議室 上新增 Microsoft Monitor 代理程式可讓您收集這些事件。  (請參閱 [將 Windows 電腦連線至 Azure 中的 Log Analytics 服務](/azure/azure-monitor/platform/agent-windows) 以取得詳細資料。) 
  
## <a name="ongoing-management"></a>持續管理

使用 Azure 監視器監控Microsoft Teams 會議室時，您必須瞭解 Azure 監視器所使用事件記錄檔中的資訊。 如需這些健康情況訊息的詳細資料，請參閱 [瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries) 。
  
### <a name="related-tasks"></a>相關工作

- 瞭解Microsoft Teams 會議室所產生的通知及其解決方式 (參閱標題為[「瞭解記錄專案](azure-monitor-manage.md#understand-the-log-entries)) 
    
## <a name="see-also"></a>另請參閱

[使用 Azure 監視器部署Microsoft Teams 會議室管理](azure-monitor-deploy.md)
  
[使用 Azure 監視器管理Microsoft Teams 會議室裝置](azure-monitor-manage.md)
