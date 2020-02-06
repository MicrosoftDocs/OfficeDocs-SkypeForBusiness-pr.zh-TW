---
title: AppSharingMetricsThreshold 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表格包含與應用程式共用搭配使用之經驗統計之品質最佳且可接受的值。 這些閾值是用來判斷應用程式共用體驗是否應該歸類為較差。
ms.openlocfilehash: 3639d9f2783b6433353f23d15e6ce063fb8ec49f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811381"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 資料表
 
AppSharingMetricsThreshold 表格包含與應用程式共用搭配使用之經驗統計之品質最佳且可接受的值。 這些閾值是用來判斷應用程式共用體驗是否應該歸類為較差。
  
此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |首選  <br/> |所撥打的通話類型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||應用程式共用的最佳頻寬限制。 預設值為1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||應用程式共用的可接受頻寬限制。 預設值為500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal （5，2）  <br/> ||針對應用程式共用品質分類的「spoiled」磚最佳百分比率。 此值是來自共用資源且未到達檢視器的內容百分比。 在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。 預設值為11%。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal （5，2）  <br/> ||針對應用程式共用品質分類的「spoiled」磚可接受的百分比比率。 此值是來自共用資源且未到達檢視器的內容百分比。 在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。 預設值為36%。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |浮  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |浮  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |浮  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |浮  <br/> ||此欄未用於 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |浮  <br/> ||應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。 這是一個單跳躍延遲測量。 預設值為1.0 秒。  <br/> 欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |浮  <br/> ||應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。 這是一個單跳躍延遲測量。 預設值為1.75 秒。  <br/> 欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |浮  <br/> ||在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲時間最佳值。 延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。  <br/> 高平均值會在觀賞體驗中反映較長的延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。 預設值為200ms。  <br/> 欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |浮  <br/> ||在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲值。 延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。  <br/> 高平均值會在觀賞體驗中反映較長的延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。 預設值為200ms。  <br/> 欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

