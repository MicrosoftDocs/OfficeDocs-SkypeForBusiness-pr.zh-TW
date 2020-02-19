---
title: Lync Server 2013： 會議活動報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93113f3167cf16733f5c7ab51247dcb57f1a118c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的會議活動報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

「會議活動報告」可讓您輕鬆回答下列問題：每天舉行了幾場會議？ 這些會議的舉行時間為何？ 這類資訊不只具備本質的意義，也是非常實用的疑難排解工具。 快速檢視會議活動報告可能建議可能的原因之一： 遠會議排定之間的上午 10:00 的時間，然後在任何其他階段 2:00 PM。

若網路太慢導致了問題，您就可以鼓勵使用者將部分會議重新排程在較為離峰流量的時段。

<div>

## <a name="accessing-the-conference-activity-report"></a>存取會議活動報告

從[Lync Server 2013 中的會議摘要報告](lync-server-2013-conference-summary-report.md)存取會議活動報告按一下下列計量之一：

  - 會議總數

  - 參與者總數

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>善加利用會議活動報告

會議活動報告預設會顯示特定時間範圍內的會議總數 (例如，每天的會議總數，或當天某一小時的會議總數)。不過，您也可以選擇要顯示該時段的參與者總數或參與者總分鐘數。要進行這項作業，您可按一下 [顯示/隱藏參數] 按鈕，以顯示篩選選項，然後從下拉式清單的報告中選取其中一個項目：

  - 參與者計數

  - 參與者分鐘數

  - 會議計數

</div>

<div>

## <a name="filters"></a>篩選

篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。下表列出您可以搭配會議活動報告的篩選。

### <a name="conference-activity-report-filters"></a>會議活動報告篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列任何一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告依據</strong></p></td>
<td><p>指定報告中所要使用的值。您可選擇下列其中一項：</p>
<ul>
<li><p>參與者計數</p></li>
<li><p>參與者分鐘數</p></li>
<li><p>會議計數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>會議計量 (依集區)

下表列出會議活動報告針對每個集區提供的資訊。

### <a name="metrics-for-conferences-by-pool"></a>會議計量 (依集區)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>否</p></td>
<td><p>會議中所使用的登錄器集區或 Edge Server 名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>會議的舉行日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>參與者總數、參與者的總分鐘數或會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>會議計量 (依伺服器類型)

下表列出會議活動報告針對每種伺服器類型提供的資訊。

### <a name="metrics-for-conferences-by-server-type"></a>會議計量 (依伺服器類型)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>會議伺服器類型</strong></p></td>
<td><p>否</p></td>
<td><p>會議中所使用的伺服器類型一般為下列其中一種：</p>
<ul>
<li><p>Web 會議伺服器</p></li>
<li><p>IM 會議伺服器</p></li>
<li><p>電話會議伺服器</p></li>
<li><p>音訊/視訊會議伺服器</p></li>
<li><p>應用程式共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>會議的舉行日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>參與者總數、參與者的總分鐘數或會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

