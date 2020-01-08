---
title: Lync Server 2013：對等語音及視頻報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Lync Server 2013 中的對等語音及視頻報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

對等語音及視頻報告提供在指定的一段時間內進行語音與視頻通話的詳細說明（例如，每小時通話數或每天通話數）。 報告也提供查看所進行的所有語音和視頻通話，或只查看成功或失敗的通話的選項。 報告顯示在下列群組中細分的通話資訊：

  - 每個池的通話

  - 每個通話類型的呼叫（例如，Lync to Lync 通話，以及在 PSTN 網路上將 Lync 呼叫給某個人）

  - 每個存取類型的通話（已登入內部網路的使用者，與已登入外部網路的使用者）

  - 每個轉送伺服器的通話

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>存取對等語音及視頻報告

您只能開啟對等活動摘要報告，然後按一下下列任何一個度量，即可存取對等語音及視頻報告：

  - 對等音訊會話總數

  - 對等音訊通話總時間

  - 對等影片會話總數

  - 對等影片總分鐘數

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>若要充分利用對等的語音及視頻報告

您可以透過多種方式來篩選對等語音及視頻報告。 不過，預設不會顯示這些篩選選項。 若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [**顯示/隱藏參數**] 按鈕。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看資料。 下表列出您可以搭配對等語音及視頻報告使用的篩選。

### <a name="peer-to-peer-voice-and-video-report-filters"></a>對等語音及視頻報表篩選

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
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期和時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列其中一項：</p>
<ul>
<li><p>每小時（最多可顯示25小時）</p></li>
<li><p>每天（最多可以顯示31天）</p></li>
<li><p>每週（最多可以顯示12周）</p></li>
<li><p>每月（最多可以顯示12個月）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>媒體類型</strong></p></td>
<td><p>指出會話中使用的媒體類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>音訊</p></li>
<li><p>顯示器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>通話處置</strong></p></td>
<td><p>表示會話的成功或失敗。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>成功通話</p></li>
<li><p>失敗的通話</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>報告依據</strong></p></td>
<td><p>指出要在報表中使用的值。 選取下列其中一項：</p>
<ul>
<li><p>會話計數</p></li>
<li><p>通話分鐘數</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>依泳池進行對等語音及影片活動的度量單位

下表列出每個池的對等語音及視頻報告中提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>依泳池進行對等語音及影片活動的度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>否</p></td>
<td><p>用於通話的註冊機構池或邊緣伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話發生的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音及影片活動（依呼叫類型）的度量單位

下表列出針對每種通話類型進行對等語音及視頻報告所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>對等語音及影片活動（依呼叫類型）的度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>通話類型</strong></p></td>
<td><p>否</p></td>
<td><p>指出所撥打的通話類型。 [值] 是下列其中一項：</p>
<ul>
<li><p>UC 對 UC</p></li>
<li><p>UC 對 PSTN</p></li>
<li><p>PSTN 到 UC</p></li>
<li><p>PSTN 到 PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話發生的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>依存取類型的對等語音及影片活動指標

下表列出針對每種網路存取類型的對等語音及視頻報告所提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>依存取類型的對等語音及影片活動指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>活動類型</strong></p></td>
<td><p>否</p></td>
<td><p>指出在撥打電話時，用戶端是否已登入內部網路或外部網路。 值通常是下列其中一項：</p>
<ul>
<li><p>內部</p></li>
<li><p>外來</p></li>
<li><p>混淆</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話發生的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>透過中繼伺服器進行對等語音及影片活動的度量標準

下表列出每個中繼伺服器的對等語音及視頻報告中提供的資訊。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>透過中繼伺服器進行對等語音及影片活動的度量標準

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>中繼伺服器</strong></p></td>
<td><p>否</p></td>
<td><p>中繼伺服器的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話發生的日期和時間週期。</p></td>
</tr>
<tr class="odd">
<td><p><strong>總額</strong></p></td>
<td><p>否</p></td>
<td><p>[會話總數] 或 [總郵件數]。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

