---
title: Lync Server 2013：對等活動摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的對等活動摘要報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

對等活動摘要報告可提供對等通訊會話的整體視圖。 點對點工作階段通常只涉及兩個使用者，不需要使用 Lync Server 會議服務。 依比較，會議通常會涉及超過兩個使用者，且需要使用 Microsoft Lync Server 2013 會議服務。 會議活動會報告在會議摘要報告上。

對等活動摘要報告可協助您回答如下所示的問題：

  - 我的使用者在一般日期傳送多少對等立即訊息？

  - 我是否有任何使用者確實充分利用 Lync Server 應用程式的共用和檔案傳輸功能？

  - 使用者抱怨，網路在一天的特定時間看起來很慢。 在這些時段內，專門針對對等音訊和影片會議所用的分鐘數為何？

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>存取對等活動摘要報告

您可以從 [監控報告] 首頁存取對等活動摘要報告。 在 Lync Server 2013 中，按一下下列其中一個度量，即可開啟[對等 IM 報告](lync-server-2013-peer-to-peer-im-report.md)：

  - 對等 IM 會話總數

  - 對等 IM 訊息總計

同樣地，您也可以按一下下列任何一個度量來開啟對等語音及視頻報告：

  - 對等音訊會話總數

  - 對等音訊會話總分鐘數

  - 對等音訊會話總數

  - 對等音訊會話總分鐘數

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>充分運用對等活動摘要報告

在對等活動摘要報告的底部，您會發現指標（例如對等與對等 IM 會話以及對等與對等 IM 訊息總計）的合計。 這可讓您快速摘要顯示在報表本文中找到的詳細資訊。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。 例如，對等活動摘要報告可讓您選擇資料的分組方式。 在這種情況下，活動會依小時、日、周或月分組。

下表列出您可以搭配對等活動摘要報告使用的篩選。

### <a name="peer-to-peer-activity-summary-report-filters"></a>對等活動摘要報表篩選

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
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期和時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
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
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。 例如，如果您選取 [開始日期 7/17/12012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/12012 12:00 AM 至 9/7/12012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出對等活動摘要報告中提供的資訊。

### <a name="peer-to-peer-activity-summary-report-metrics"></a>對等活動摘要報表度量單位

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
<td><p><strong>工資</strong></p>
<p><strong>日常</strong></p>
<p><strong>周更新</strong></p>
<p><strong>次</strong></p></td>
<td><p>否</p></td>
<td><p>指出您在 [篩選] 工具列上選取的時間間隔。 在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/17/12012]，就會看到該日期的使用者註冊活動的每小時細目。</p></td>
</tr>
<tr class="even">
<td><p><strong>點對點工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>所進行的點對點工作階段總數（無論會話類型為何）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等 IM 會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等立即訊息（IM）會話的總數。 當您按一下此專案時，報告會顯示所選時段的對等 IM 報表。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等 IM 訊息總計</strong></p></td>
<td><p>否</p></td>
<td><p>在點對點工作階段中傳送的立即訊息總數。 當您按一下此專案時，報告會顯示所選時段的對等 IM 報表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等音訊會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊通話的總數。 當您按一下這個欄位時，報告會顯示所選時間範圍內的對等語音及視頻報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等音訊會話總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊會話所花費的總時間量。 當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均對等音訊會話分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等音訊會話所花費的平均時間長度。 將音訊會話總時間除以音訊會話總數來計算。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等影片會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻通話的總數。 請注意，視頻會話也會計算為音訊會話：每個視頻會話都會計算為一個影片會話和一個音訊會話。 當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等影片會話總分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻會話所花費的總時間量。 當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均對等影片會話分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>對等視頻會話所花費的平均時間長度。 透過將影片總時間除以視頻會話總數來計算。</p></td>
</tr>
<tr class="odd">
<td><p><strong>對等檔案傳輸會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>包含檔案傳輸的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>對等應用程式共用會話總數</strong></p></td>
<td><p>否</p></td>
<td><p>包含應用程式共用的點對點工作階段總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

