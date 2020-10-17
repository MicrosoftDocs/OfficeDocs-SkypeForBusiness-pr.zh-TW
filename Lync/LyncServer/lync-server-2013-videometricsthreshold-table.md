---
title: Lync Server 2013： VideoMetricsThreshold 表格
description: Lync Server 2013： VideoMetricsThreshold 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567999"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoMetricsThreshold 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>被指定的電話類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 0.05。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 0.10。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 10.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td></td>
<td><p>預設值為 12.0000。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>十進位 (9，4) </p></td>
<td></td>
<td><p>預設值為 7.0000。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 10.0/。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 5.0。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 10.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>foat</p></td>
<td></td>
<td><p>預設值為 0.05。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>預設值為 0.10。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>預設值為 12。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>預設值為 7。</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 5.00。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>十進位 (5，2) </p></td>
<td></td>
<td><p>預設值為 10.00。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

