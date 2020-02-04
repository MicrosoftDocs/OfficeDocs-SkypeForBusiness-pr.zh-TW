---
title: Lync Server 2013： AppSharingMetricsThreshold 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 中的 AppSharingMetricsThreshold 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-12-08_

AppSharingMetricsThreshold 表格包含與應用程式共用搭配使用之經驗統計之品質最佳且可接受的值。 這些閾值是用來判斷應用程式共用體驗是否應該歸類為較差。

此表格是在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>所撥打的通話類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>應用程式共用的最佳頻寬限制。 預設值為1000000。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>應用程式共用的可接受頻寬限制。 預設值為500000。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>針對應用程式共用品質分類的「spoiled」磚最佳百分比率。 此值是來自共用資源且未到達檢視器的內容百分比。 在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。 預設值為11%。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>針對應用程式共用品質分類的 "spoiled" 磚的 cceptable 百分比率。 此值是來自共用資源且未到達檢視器的內容百分比。 在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。 預設值為36%。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>此欄未用於 Microsoft Lync Server 2013。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。 這是一個單跳躍延遲測量。 預設值為1.0 秒。</p>
<p>欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。 這是一個單跳躍延遲測量。 預設值為1.75 秒。</p>
<p>欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲時間最佳值。 延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。</p>
<p>高平均值會在觀賞體驗中反映較長的延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。 預設值為200ms。</p>
<p>欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>浮</p></td>
<td></td>
<td><p>在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲值。 延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。</p>
<p>高平均值會在觀賞體驗中反映較長的延遲。 超負荷的會議服務器可能會遇到較高的平均延遲。 預設值為200ms。</p>
<p>欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

