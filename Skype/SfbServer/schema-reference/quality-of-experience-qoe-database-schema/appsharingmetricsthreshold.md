---
title: AppSharingMetricsThreshold 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 表格包含可與應用程式共用搭配使用之經驗品質計量適用的最佳值與可接受值。這些閾值可用來判斷應用程式共用經驗是否應該分類為不良。
ms.openlocfilehash: 624016a7c98a32859edbdd849b8f1a85f76e8abb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628535"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 表格
 
AppSharingMetricsThreshold 表格包含可與應用程式共用搭配使用之經驗品質計量適用的最佳值與可接受值。這些閾值可用來判斷應用程式共用經驗是否應該分類為不良。
  
此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |主要  <br/> |撥打的通話類型。  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||適用於應用程式共用的最佳頻寬限制。預設值為 1000000。  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||適用於應用程式共用且可接受的頻寬限制。預設值為 500000。  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |十進位 (5，2)   <br/> ||用於分類應用程式共用品質的「spoiled」磚的最佳百分比速率。 此值是來自未送達檢視者之共用者的內容百分比。 當共用者從圖表來源中捨棄並排顯示或 ASMCU 並排顯示個別捨棄來自共用者的並排顯示時，內容可能會被捨棄 (或毀損)。 預設值為 11 個百分比。  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |十進位 (5，2)   <br/> ||適用于分類應用程式共用品質的 "spoiled" 圖塊的可接受百分比率。 此值是來自未送達檢視者之共用者的內容百分比。 當共用者從圖表來源中捨棄並排顯示或 ASMCU 並排顯示個別捨棄來自共用者的並排顯示時，內容可能會被捨棄 (或毀損)。 預設值為 36 個百分比。  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Microsoft Lync Server 2013 中不會使用此欄。  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||應用程式共用中所含之兩個媒體端點間適用於相對單向延遲的最佳值。此為單一躍點延遲措施。預設值為 1.0 秒。  <br/> 欄已引進 Microsoft Lync Server 2013。  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||應用程式共用中所含之兩個媒體端點間適用於相對單向延遲的最佳值。此為單一躍點延遲措施。預設值為 1.75 秒。  <br/> 欄已引進 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||在檢視工作階段期間，AS 會議伺服器中平均 RDP 並排顯示處理延遲的最佳值。 延遲是指當伺服器 (共用或 MCU 上的開始幀進行編碼時，取決於案例) 和在檢視器中解碼相同開始幀的時間差。  <br/> 高平均會反映檢視經驗中較長的延遲。負載過重的會議伺服器可能會發生較高的平均延遲。預設值為 200ms。  <br/> 欄已引進 Microsoft Lync Server 2013。  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||在檢視工作階段期間，AS 會議伺服器中平均 RDP 並排顯示處理延遲的可接受值。 延遲是指當伺服器 (共用或 MCU 上的開始幀進行編碼時，取決於案例) 和在檢視器中解碼相同開始幀的時間差。  <br/> 高平均會反映檢視經驗中較長的延遲。負載過重的會議伺服器可能會發生較高的平均延遲。預設值為 200ms。  <br/> 欄已引進 Microsoft Lync Server 2013。  <br/> |
   

