---
title: Lync Server 2013： 會議加入時間報表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11932d1f63e6d756b0a3a5ba1eb7b33498dac61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Lync Server 2013 中的會議加入時間報表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-04-23_

會議加入時間摘要可讓您判斷您的使用者加入會議所需的時間。 此報告顯示平均加入時間 （以毫秒為單位），而且也提供分解，可讓您知道多少使用者就可以加入會議，在 2 秒或更少，多少使用者需要 2 到 5 秒的時間才能加入會議，依此類推。

<div>

## <a name="accessing-the-conference-join-time-report"></a>存取會議加入時間報表

從監視報告首頁存取會議加入時間報表。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以使用與會議加入時間報表的篩選器。

### <a name="conference-join-time-report-filters"></a>會議加入時間報表篩選

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
<td><p><strong>Pool</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會議工作階段</strong></p></td>
<td><p>工作階段的類型。 允許的值為：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>焦點工作階段 （焦點中央原則和線上會議的狀態管理員以及協調會議的所有層面</p></li>
<li><p>應用程式共用</p></li>
<li><p>A/V 會議</p></li>
</ul>
<p>如果您選取 [全部]，總計的會議加入時間會顯示頂端的報告。 請注意，這些總計僅適用於使用 Microsoft Exchange 或 Microsoft Outlook 已排程的會議。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出會議加入時間報表中所提供的資訊。

### <a name="conference-join-time-report-metrics"></a>會議加入時間報表評量

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
<td><p><strong>Date</strong></p>
<p>此評量的實際標題將視選取的間隔而異。</p></td>
<td><p>否</p></td>
<td><p>執行日期與時間，會議的位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 （毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>平均量與會者加入會議的時間 （以毫秒為單位） 的詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作階段&lt;2 秒，音量]</strong></p></td>
<td><p>否</p></td>
<td><p>能夠在 2 秒內加入會議的參與者數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段&lt;2 秒，百分比]</strong></p></td>
<td><p>否</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>工作階段 2-5 秒，音量]</strong></p></td>
<td><p>否</p></td>
<td><p>能夠在 2-5 秒內加入會議的參與者數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段 2-5 秒，百分比]</strong></p></td>
<td><p>否</p></td>
<td><p>能夠在 2-5 秒內加入會議的總通話與會者百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作階段 5-10 秒，音量]</strong></p></td>
<td><p>否</p></td>
<td><p>能夠在 5-10 秒內加入會議的參與者數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段 5-10 秒，百分比]</strong></p></td>
<td><p>否</p></td>
<td><p>能夠在 5-10 秒內加入會議的總通話與會者百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作階段&gt;10 秒，音量]</strong></p></td>
<td><p>否</p></td>
<td><p>需要超過 10 秒才能加入會議的參與者數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段&gt;10 秒，百分比]</strong></p></td>
<td><p>否</p></td>
<td><p>需要超過 10 秒才能加入會議的總通話與會者百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

