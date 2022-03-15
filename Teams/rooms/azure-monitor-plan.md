---
title: 使用 azure 監視器Microsoft Teams 會議室監控
ms.author: czawideh
author: cazawideh
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
description: 本文討論規劃使用 Azure 監視器監控Microsoft Teams 會議室或商務用 Skype或Teams考慮。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 510f249ea4aef78b898294db0a2c3fbeef8fc283
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504120"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>使用 azure 監視器Microsoft Teams 會議室監控
 
 本文討論規劃使用 Azure 監視器管理Microsoft Teams 會議室或Microsoft Teams裝置商務用 Skype考慮。

> [!NOTE]
> 您也可以使用[系統管理中心設定](../alerts/device-health-status.md)Teams 會議室健康Teams監控。

[Azure 監視器](/azure/azure-monitor/overview) 是一組監控服務，從一開始即是在雲端中設計。 Azure 監視器元件完全託管在 Azure 中，而不是部署和管理內部部署資源。 組組是最小的，您只需要幾分鐘就可以啟動並運作。 有了一些自訂作業，它Microsoft Teams 會議室提供個別會議室系統之系統健康情況或錯誤通知，協助監控Microsoft Teams 會議室。
  
本文將討論實行 Azure Monitor 監控所需的需求、設計/架構及實Microsoft Teams 會議室。 它也提供有關為會議室執行 Azure 監視器的詳細文章Microsoft Teams 會議室以及持續監控會議室的重要Microsoft Teams 會議室資訊。
  
## <a name="functional-overview"></a>功能概觀

![使用 Azure 監視器Microsoft Teams 會議室管理圖表。](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
應用程式Microsoft Teams 會議室事件寫入到 Windows記錄。 安裝之後，Microsoft 監控代理程式會將資訊傳遞至 Azure 監視器服務。
  
正確配置之後，Log Analytics 會剖析事件描述中內嵌的 JSON 負載，Microsoft Teams 會議室功能及偵測到哪些錯誤。
  
使用 Azure 監視器的系統管理員Microsoft Teams 會議室離線或遇到應用程式、連線或硬體故障的通知，以及知道系統是否必須重新開機。 每個系統狀態會經常更新，因此這些通知會接近即時更新。
  
## <a name="azure-monitor-requirements"></a>Azure 監視器需求

您必須擁有 Azure 監視器的有效 Azure 訂閱，才能使用記錄分析功能。 請參閱 [開始使用記錄分析工作區](/azure/azure-monitor/learn/quick-create-workspace) ，為貴組織建立訂閱。
  
您應該熟悉如何使用記錄分析視圖設計工具。 請參閱 [記錄分析中的查看，](/azure/azure-monitor/platform/view-designer) 瞭解這些詳細資料。
  
### <a name="related-tasks"></a>相關工作

1. 訂閱 Azure 監視器記錄分析之後，請建立自訂欄位 (如地圖自訂[欄位) 所述](azure-monitor-deploy.md#Custom_fields)，以剖析從 Microsoft Teams 會議室 中Microsoft Teams 會議室。 這包括瞭解在瞭解記錄專案中記載 [的 JSON 架構](azure-monitor-manage.md#understand-the-log-entries)。
    
2. 在記錄分析Microsoft Teams 會議室建立管理檢視。 您可以手動[建立Microsoft Teams 會議室儀表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>個別Microsoft Teams 會議室需求

Microsoft Teams 會議室是在資訊站模式中在計算裝置上執行的應用程式。 如同任何Windows應用程式一樣，Microsoft Teams 會議室應用程式會將啟動和硬體錯誤等事件寫入 Windows記錄。 新增 Microsoft Monitor 代理程式Microsoft Teams 會議室可收集這些事件。  (請參閱[連線 Windows到 Azure](/azure/azure-monitor/platform/agent-windows)中的記錄分析服務以查看詳細資料。) 
  
## <a name="ongoing-management"></a>持續管理

使用 Azure 監視器監控Microsoft Teams 會議室，您必須瞭解 Azure 監視器使用的事件記錄中包含的資訊。 請參閱 [瞭解這些健康情況訊息](azure-monitor-manage.md#understand-the-log-entries) 的詳細資訊記錄專案。
  
### <a name="related-tasks"></a>相關工作

- 瞭解使用者產生的Microsoft Teams 會議室，以及如何解決 (請參閱瞭解記錄專案) [](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>另請參閱

[使用 azure 監視器Microsoft Teams 會議室部署管理](azure-monitor-deploy.md)
  
[使用 azure 監視器Microsoft Teams 會議室管理裝置](azure-monitor-manage.md)
