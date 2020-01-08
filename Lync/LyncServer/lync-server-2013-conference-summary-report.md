---
title: Lync Server 2013：會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 [會議摘要] 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-03_

[會議摘要] 報告提供您的線上會議會話的整體視圖。 會議通常會涉及超過2個使用者，且需要使用 Microsoft Lync Server 2013 會議服務。 相比之下，點對點工作階段通常只涉及2個使用者，不需要使用 Lync Server 的會議服務。 對等活動會報告在[Lync Server 2013 的對等活動摘要報告](lync-server-2013-peer-to-peer-activity-summary-report.md)上。

[會議摘要報告] 不僅告訴您在指定時間內所舉行的會議數量（每小時、每天、每週、每月），也會告知您參與這些會議的人員總數，以及唯一會議的總人數組織.

「唯一」召集人是指至少安排一個會議的人。 例如，如果 Pilar 方排程一個會議，她將其計算為一個唯一的召集人。 如果 Ken Myer 排程148會議給他，太多是一個唯一的召集人。 例如，下表顯示已排程8個會議，但只有三個唯一的召集人（Ken Myer、Pilar 方和 David Ahs）。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>會議召集人</th>
<th>會議日期</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


[會議摘要] 報告也會指出包括音訊和/或影片在內的會議數。

<div>

## <a name="accessing-the-conference-summary-report"></a>存取會議摘要報告

[會議摘要] 報告是從 [監控報告] 首頁存取。 您可以按一下下列其中一個度量來向下切入會議活動報告：

  - 會議總數

  - 參與者總數

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>充分利用會議摘要報告

[會議摘要] 報告中所使用之大部分標準的總值，可以在報表底部找到;向下滾動以查看值，例如在指定的時段內所保留的會議總數，以及參與這些會議的人員總數。 在報表底部沒有匯總的一個度量單位是唯一的會議召集人總數。 為什麼不呢？ 以下是其中一個原因。 假設您要查看一個月的資料。 在第1天，您有34唯一的會議召集人;在第2天，您有27個唯一的會議召集人。 這是否表示您有61唯一的會議召集人來執行這兩天？ 不一定。 畢竟，在第2天組織會議的所有27人，都可能是在第1天共同進行會議的34人員。 例如，在這份簡單的報表中，請注意，在7/7/2012 和7/2/2012 上，Ken Myer 與 Pilar 方排程的會議：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>會議召集人</th>
<th>會議日期</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar 方</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


若要進一步瞭解組織會議的唯一使用者總數，請變更您的時間間隔;例如，依月份查看資料，而不是依日期查看。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[會議摘要] 報告可讓您選擇資料的分組方式。 在這種情況下，會議會依小時、日、周或月進行分組。

下表列出可與會議摘要報告搭配使用的篩選。

### <a name="conference-summary-report-filters"></a>會議摘要報表篩選

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
<td><p>時間範圍的開始日期/時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
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
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數目，則只會顯示最大值數（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表是會議摘要報告所提供的資訊。

### <a name="conference-summary-report-metrics"></a>會議摘要報表度量單位

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
<td><p>指出您在 [篩選] 工具列上選取的時間間隔。 在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>已保留的會議總數（無論會議類型為何）。 當您按一下此專案時，報告會顯示所選時段的會議活動報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>參與者總數</strong></p></td>
<td><p>否</p></td>
<td><p>參與會議的人員總數。 當您按一下此專案時，報告會顯示所選時段的會議活動報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>每個會議的平均參與者</strong></p></td>
<td><p>否</p></td>
<td><p>參與特定會議的平均人數。 由由總參與者數除會議數來決定。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>包含音訊或影片的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 會議紀要總計</strong></p></td>
<td><p>否</p></td>
<td><p>專用於音訊/視訊會議的總分鐘數。</p>
<p>總計 A/V 會議分鐘數的度量會總結所有音訊/視覺會議類型，包括： A/V 會議;IM 會議;app 共用會議;資料會議;和 PSTN 會議。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 會議參與者紀要總計</strong></p></td>
<td><p>否</p></td>
<td><p>專用於音訊/視訊會議的參與者總分鐘數。 例如，假設一個使用者在音訊/視訊會議中花費5分鐘，而另一個使用者在該會議中花3分鐘的時間。 這會產生總共8個參與者的分鐘數：5分鐘再加上3分鐘。</p></td>
</tr>
<tr class="even">
<td><p><strong>平均/V 會議分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>每個音訊/視訊會議的平均分鐘數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會議唯一召集人總數</strong></p></td>
<td><p>否</p></td>
<td><p>至少組織一次會議的使用者總數。 組織多個會議的使用者會算作一個唯一的召集人，就像只組織單一會議的使用者。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議訊息總計</strong></p></td>
<td><p>否</p></td>
<td><p>在會議期間傳送的立即訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

