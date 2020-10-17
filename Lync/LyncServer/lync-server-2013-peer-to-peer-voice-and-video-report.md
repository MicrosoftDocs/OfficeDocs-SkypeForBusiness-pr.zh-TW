---
title: Lync Server 2013：語音和影片報告 Peer-to-Peer
description: Lync Server 2013：語音和影片報告 Peer-to-Peer。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557269"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>在 Lync Server 2013 中 Peer-to-Peer 語音和影片報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

Peer-to-Peer 的語音和影片報告可提供一段 (時間內的語音和影片通話的詳細資訊，例如每小時或每天通話數) 。 該報告也可讓您查看所進行的所有語音和影片通話，或只查看成功或失敗的通話。 報告顯示通話資訊分為下列群組：

  - 每個集區的通話

  - 每個通話類型的通話 (例如，Lync to Lync 通話和對 PSTN 網路上的人員進行 lync 通話) 

  - 每一種存取類型 (使用者登入內部網路和使用者登入外部網路時的呼叫) 

  - 每個轉送伺服器的通話

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>存取對等語音和影片報告

您可以只開啟 Peer-to-Peer 活動摘要報告，然後按一下下列其中一個計量，即可存取 Peer-to-Peer 語音和影片報告：

  - 對等音訊會話總數

  - 對等音訊分鐘總數

  - 對等音訊會話總數

  - 對等影片總分鐘數

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>若要充分利用對等語音和影片報告

您可以使用多種方式來篩選 Peer-to-Peer 語音和影片報告。 不過，根據預設，這些篩選選項會從視圖中隱藏。 若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [ **顯示/隱藏參數** ] 按鈕。

</div>

<div>

## <a name="filters"></a>篩選

篩選為您提供一種方法，讓您可以傳回更精細的目標資料集，或以不同方式查看資料。 下表列出您可以搭配 Peer-to-Peer 語音和影片報告使用的篩選器。

### <a name="peer-to-peer-voice-and-video-report-filters"></a>對等語音和影片報告篩選器

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
<td><p>時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>媒體類型</strong></p></td>
<td><p>會指出會話中所用的媒體類型。 選取下列其中一項：</p>
<ul>
<li><p>兩者都要</p></li>
<li><p>音訊</p></li>
<li><p>影片</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫處置</strong></p></td>
<td><p>表示會話成功或失敗。 請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>成功通話</p></li>
<li><p>通話失敗</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>報告依據</strong></p></td>
<td><p>指定報告中所要使用的值。請選取下列其中一項：</p>
<ul>
<li><p>工作階段計數</p></li>
<li><p>通話分鐘數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>對等語音和影片活動的計量（依集區）

下表列出每個集區 Peer-to-Peer 語音和影片報告中提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>對等語音和影片活動的計量（依集區）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>否</p></td>
<td><p>用於通話的註冊區集區或 Edge Server 的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>進行通話的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音和影片活動的計量（依通話類型）

下表列出每個所撥打的通話類型的 Peer-to-Peer 語音和影片報告中所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音和影片活動的計量（依通話類型）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>通話類型</strong></p></td>
<td><p>否</p></td>
<td><p>會指出所撥打的通話類型。 值為下列其中一項：</p>
<ul>
<li><p>UC 對 UC</p></li>
<li><p>UC 對 PSTN</p></li>
<li><p>PSTN 對 UC</p></li>
<li><p>PSTN 對 PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>進行通話的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>對等語音和影片活動的計量（依存取類型）

下表列出每個網路訪問類型的 Peer-to-Peer 語音和影片報告中提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>對等語音和影片活動的計量（依存取類型）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>活動類型</strong></p></td>
<td><p>否</p></td>
<td><p>會指出撥打通話時，用戶端是否已登入內部網路或外部網路。 一般來說，值都是下列其中之一：</p>
<ul>
<li><p>內部</p></li>
<li><p>外部</p></li>
<li><p>混合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>進行通話的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>依轉送伺服器的對等語音和影片活動計量

下表列出每個轉送伺服器的 Peer-to-Peer 語音和影片報告中提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>依轉送伺服器的對等語音和影片活動計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>中繼伺服器</strong></p></td>
<td><p>否</p></td>
<td><p>轉送伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>進行通話的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段總數或訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

