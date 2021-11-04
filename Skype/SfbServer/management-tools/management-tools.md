---
title: 商務用 Skype Server 2015 管理工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: 摘要：瞭解商務用 Skype Server 2015 中的服務管理工具。
ms.openlocfilehash: 89adf7ab2ad71441abf765de75537eec43b8ce17
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776173"
---
# <a name="skype-for-business-server-2015-management-tools"></a>商務用 Skype Server 2015 管理工具
 
**摘要：** 深入瞭解商務用 Skype Server 2015 中的服務管理工具。
  
商務用 Skype Server 2015 通訊軟體 (以前的 Lync Server) ，可提供立即訊息 (IM) 、顯示狀態、會議及電話語音解決方案，以支援企業層級的共同作業需求。 管理這些服務的工具既靈活又強大。 
  
## <a name="skype-for-business-server-2015-tools"></a>商務用 Skype Server 2015 工具

|&nbsp;|內容|描述|
|:-----|:-----|:-----|
||[Microsoft 通話品質方法計分卡，v 1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip 下載)  <br/> [商務用 Skype 的 CQM 海報](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013 的 CQM 海報](https://go.microsoft.com/fwlink/p/?LinkId=391841)  |Microsoft 通話品質方法的更新版本 (CQM) Lync Server 和商務用 Skype Server 2015 的計分卡。 您可以使用 CQM 計分卡來執行通話品質方法，這是一種整體方式，可根據《網路指南》中所述的方法，有序定義及斷言通話品質。 CQM 會將 Lync/商務用 Skype 的實施劃分成10個分立的區域，這些區域會影響品質，為每一個人定義目標和修正計畫。 CQM 是一種可解決通話品質問題的架構-您可以修改或擴充它，以解決網路上的特定狀況。  <br/> CQM 海報可協助您瞭解 CQM、lync 和商務用 Skype 的通話品質方法，可協助您找出並消除影響包含企業語音功能之 Lync/商務用 Skype 實施之通話品質和使用者經驗的問題。  <br/>**附注：** 這些工具將不會更新商務用 Skype Server 2019。 |
|![儀表板圖示。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[通話品質儀表板](./call-quality-dashboard/call-quality-dashboard.md)  |通話品質儀表板 (CQD) 是一個網頁入口網站，可根據經驗品質 (QoE) 商務用 Skype 或 Lync 環境中的資料，快速建立及組織報表。 CQD 會部署 SSAS cube，以匯總 QoEMetrics 資料庫中的資料，這可讓使用者建立及修改報告，以及即時查看更新。 此外，CQD 會公開 web APIs，讓使用者以程式設計方式存取 cube 資料，以在自訂儀表板中使用。   |
|![KHI 圖示。](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 資源](https://go.microsoft.com/fwlink/p/?LinkId=534843)  | (KHI) 的主要健康情況指示器是效能計數器，其建議的臨界值是針對可能會影響使用者體驗的問題。 KHI 指南概述維護良好部署的操作過程和修正步驟，並包含用於設定 KHI 資料收集器的範例 PowerShell 腳本，以及可分析 KHI 效能資料的分析和定義活頁簿。   |
|![儀表板圖示。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[商務用 Skype Server 2015 的統計資料管理員](statistics-manager/statistics-manager.md)  |StatsMan 是一種可即時查看 KHI 計算的儀表板解決方案，以及跨您基礎結構匯總的圖形效能計數器。 儀表板可用於找出不斷的效能問題、查看環境中已計畫變更的結果、追蹤中斷的解決方式，以及更多。 現成時，它會使用來自 KHI 資源的 KHI 閥值進行設定，而且可以自訂以符合您的部署的獨特需求。   |
|![儀表板圖示。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[商務用 Skype Server 2015 資源套件工具](https://www.microsoft.com/download/details.aspx?id=52631)  |商務用 Skype Server 2015 資源套件工具，可協助 IT 系統管理員部署及管理商務用 Skype Server 2015，以簡化某些日常工作。   |
|![網狀圖標。](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[網路指南](https://go.microsoft.com/fwlink/p/?LinkID=390677)  |Microsoft Lync Server 2013 和商務用 Skype 2015 通訊軟體，可讓對等音訊和影片 (A/V) 通話、會議及共同作業，並依賴優化、可靠的網路基礎結構，以在用戶端之間提供高品質的媒體會話。 《網路指南》提供用於管理商務用 Skype 和 Lync 之網路基礎結構的模型，包含三個階段：規劃、監控及疑難排解。 您可以將這些階段套用到新的 Lync 或商務用 Skype Server 部署或現有的部署。 透過 Wi-Fi 與設定服務品質原則所涵蓋的《 Lync/Skype 》中的最新變更。   |
|![剪貼簿圖示。](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[商務用 Skype 2015 中的集中式記錄服務](centralized-logging-service/centralized-logging-service.md)  |集中式記錄服務是一種功能強大的疑難排解工具，可讓您從根本原因分析到效能問題進行大規模或小規模的問題。 所有範例都是使用商務用 Skype Server 管理命令介面來顯示。 協助是透過工具本身為命令列工具提供，但是您可以從命令列執行的功能集有限。 透過使用商務用 Skype Server 管理命令介面，您可以存取更大、更具可設定的功能集，因此永遠都應該是第一項選擇。   |
|![SCOM 圖示。](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[使用 SCOM 管理元件管理商務用 Skype Server 2015](use-scom-management-pack/use-scom-management-pack.md)  |透過使用商務用 Skype Server 2015 管理元件，您可以主動識別並處理潛在的問題。 如此一來，商務用 Skype Server 2015 管理元件會擴充 System Center Operations Manager 的功能。   |
|![儀表板圖示。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[商務用 Skype Server 2015 規劃工具](planning-tool/planning-tool.md)  |商務用 Skype 2015 規劃工具提供的指導方針，可讓您開始規劃拓撲。  <br/> **附注：** 將不會更新商務用 Skype Server 2019 的此工具。 |
|![儀表板圖示。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[商務用 Skype Server 2015 容量規劃計算機](capacity-planning-calculator.md)  |商務用 Skype Server 2015 容量規劃計算機可協助您為組織的需求建立拓撲模型。   |
|![網狀圖標。](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[商務用 Skype Server 2015 應力和效能工具](stress-and-performance-tool/stress-and-performance-tool.md)  |此工具可讓您使用商務用 Skype Server 2015 環境的使用者負載來執行各種效能相關的測試。 工具附帶範例腳本，以協助您獨特的環境需求。  <br/>**附注：** 將不會更新商務用 Skype Server 2019 的此工具。 |
   
## <a name="see-also"></a>另請參閱

[Lync Server 2013 工具](/previous-versions/office/lync-server-2013/lync-server-2013-tools)
  
[Lync Server 2010 工具](/previous-versions/office/lync-server-2010-tools/dn145002(v=ocs.14))