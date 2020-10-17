---
title: Lync Server 2013：通話診斷摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f70c4fc0987b75cc8c5a8831eb8ad76493fea9b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526320"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的通話診斷摘要報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

通話診斷摘要報告提供失敗的對等和會議會話的整體外觀。 報告顯示這兩種類型的會話的整體失敗率，並以會話形式的形式進一步打破失敗資訊：

  - 立即訊息

  - 應用程式共用

  - 檔案傳輸

  - 音訊

  - 影片

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>存取通話診斷摘要報告

通話診斷摘要報告可從監控報告的首頁進行存取。 在 [通話診斷摘要報告] 中，您可以按一下報告的 [Peer-to-Peer 會話摘要] 區段下的 [失敗率]，即可 [在 [Lync Server 2013] 中存取 Peer-to-Peer 活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 。 您也可以按一下下列任一會議計量， [以在 Lync Server 2013 中存取會議診斷報告](lync-server-2013-conference-diagnostic-report.md) ：

  - 整體工作階段失敗率

  - 焦點失敗率

  - MCU 失敗率

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>通話診斷摘要報告的最佳用法

通話診斷摘要報告包含的圖形會比較 Microsoft Lync Server 2013 中使用的各種形式的失敗率。 這些圖形中的資料行實際上是 hotlinks 的;例如，如果按一下點對點工作階段的 [立即訊息] 欄，您會向下流覽 [Lync Server 2013 中 Peer-to-Peer 活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)的實例，該報告提供 [通話診斷摘要報告] 中所包含之所有立即訊息會話的其他詳細資料。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，[通話診斷摘要] 報告可讓您篩選諸如會話中所使用的註冊區集區或 Edge Server 等事項。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配通話診斷摘要報告使用的篩選器。

### <a name="call-diagnostic-summary-report-filters"></a>通話診斷摘要報告篩選器

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
<td><p><strong>集區</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Peer-to-Peer 會話的計量

下表列出點對點工作階段的通話診斷摘要報告所提供的資訊 (也就是說，只涉及兩位參與者) 。

### <a name="metrics-for-peer-to-peer-sessions"></a>Peer-to-Peer 會話的計量

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
<td><p><strong>工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>進行中的點對點工作階段總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的點對點工作階段百分比。 當您按一下此專案時，報告會顯示 Peer-to-Peer 活動診斷報告，其中會顯示失敗的點對點工作階段詳細資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議會話的計量

下表列出會議會話的通話診斷報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。

### <a name="metrics-for-conferencing-sessions"></a>會議會話的計量

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
<td><p><strong>會議總數</strong></p></td>
<td><p>否</p></td>
<td><p>已執行的會議總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>會議工作階段總數</strong></p></td>
<td><p>否</p></td>
<td><p>已執行的會議會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>整體工作階段失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗之會議會話總數所占的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦點工作階段</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的專注型會議會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦點失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>失敗之專注于會議會話的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 會話</strong></p></td>
<td><p>否</p></td>
<td><p>會議服務器型 (的總數（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 失敗率</strong></p></td>
<td><p>否</p></td>
<td><p>會議服務器型 (（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

