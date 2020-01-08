---
title: Lync Server 2013：熱門失敗報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Lync Server 2013 中的 [熱門失敗] 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[熱門失敗] 報告可讓您查看最常報告的失敗及其隨時間變化的趨勢。 失敗是以下列兩個度量的組合為基礎：

  - **診斷 ID**。 附加至 SIP 訊息的唯一識別碼（以 ms diagnostics 標頭形式）。 診斷識別碼可在疑難排解呼叫相關問題時提供有用的資訊。

  - **回應代碼**。 在 SIP 通訊會話中使用回應代碼來回應 SIP 要求。 例如，如果 Ken 將邀請要求傳送給 Pilar 方（也就是，假設 Ken Myer 呼叫 Pilar 方）。 如果 Pilar 答案，她的手機會傳送回應碼200（確定），讓 Ken 手機知道 Pilar 已回答問題。 [熱門失敗] 報告只包含回應通話失敗時所傳送的回應碼;Lync Server 不會追蹤通話期間發出的所有回應碼。

資訊不只會報告發生失敗的會話總數，以及因失敗而受到影響的使用者總數。

<div>

## <a name="accessing-the-top-failures-report"></a>存取 [熱門失敗] 報告

[熱門失敗] 報告是從 [監控報告] 首頁存取。 按一下報告的會話指標會將您帶到[Lync Server 2013 的失敗發佈報告](lync-server-2013-failure-distribution-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>充分利用 [熱門失敗] 報告

[熱門失敗] 報告在某種情況下是不尋常的：它可讓您一次篩選多達5個診斷 Id。 （通常您只能篩選一個專案，例如一個使用者 SIP 位址（一次）。若要篩選多個診斷識別碼，只要在 [診斷識別碼] 方塊中輸入每個識別碼，即可使用逗號分隔識別碼。 （如果您想要的話，您可以在每個逗號後留一個空格）。例如：

1011、2412、1033、52116、1008

請執行這項作業，而且只會顯示那些五個診斷識別碼中至少有一個報告的失敗通話。

如果您將滑鼠放在回應代碼上，您會看到工具提示，告訴您有問題的回應碼。 例如，如果您將滑鼠放在回應代碼486上，您會看到以下訊息：

在這裡忙碌。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[熱門失敗] 報告可讓您根據活動類型（點對點工作階段或會議會話）或隨附失敗會話的 SIP 回應程式碼，來篩選傳回的資料。 您也可以選擇分組資料的方式。 在這種情況下，使用方式會依小時、日、周或月分組。

下表列出可用於 [熱門失敗] 報告的篩選。

### <a name="top-failures-report-filters"></a>[熱門失敗] 報表篩選

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
<td><p><strong>活動類型</strong></p></td>
<td><p>活動類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>對等</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>模態</strong></p></td>
<td><p>目前唯一可用的選項是<strong>[全部]</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
<tr class="even">
<td><p><strong>類別</strong></p></td>
<td><p>遇到的失敗類型。 選取下列其中一項：</p>
<ul>
<li><p>預期與意外失敗</p></li>
<li><p>意外失敗</p></li>
</ul>
<p>&quot;預期的失敗&quot;是預期發生的失敗。 例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。 發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。 例如，如果來電者停留在 [保留] 上，就不應該終止通話。 如果發生這種情況，就會將它標記為未預期的失敗。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應代碼</strong></p></td>
<td><p>在會議失敗時傳送 SIP 回應代碼。 輸入整個回應代碼（例如：</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 [熱門失敗] 報告中提供的資訊。

### <a name="top-failures-report-metrics"></a>熱門失敗報告度量單位

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
<td><p><strong>排名</strong></p></td>
<td><p>是</p></td>
<td><p>根據所報告的會話數進行相對等級。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告的會話</strong></p></td>
<td><p>是</p></td>
<td><p>根據診斷識別碼和 SIP 回應代碼，失敗的會話總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>受影響的使用者</strong></p></td>
<td><p>是</p></td>
<td><p>受失敗會話影響的使用者總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>失敗資訊</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的詳細資訊，包括診斷識別碼、SIP 回應代碼，以及會話失敗原因的描述。</p></td>
</tr>
<tr class="odd">
<td><p><strong>過去的趨勢</strong></p></td>
<td><p>否</p></td>
<td><p>圖形在一段時間內失敗的會話。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

