---
title: Lync Server 2013：失敗的發佈報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5250b03aef3fb77de2cbeefa4688a150c9b4a302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Lync Server 2013 中的發佈報告失敗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

失敗的發佈報告在下列類別中排名失敗的會話：

  - 常見的診斷原因

  - 上方形式

  - 頂層池

  - 熱門來源

  - 上方元件

  - 使用者頂端

  - 使用者頂端

  - 從使用者代理程式頂端

您可以使用這些類別來判斷問題發生的確切位置，在某些情況下，也會發生問題的原因。 例如，假設您在指定的一天期間記錄了242失敗的音訊/視頻會話。 如果您看到失敗的發佈報告，可能會顯示您的都柏林池中發生了這些失敗會話的237。 這可讓您在追蹤及診斷這些失敗背後的原因時提供良好的開始位置。 如果您在 [**頂層池**] 類別底下按一下 [都柏林]，就會看到該群組的 [分發報告] 只出現失敗。 然後，您就可以開始分析都柏林池為什麼會遇到這麼多問題。

<div>

## <a name="viewing-the-failure-distribution-report"></a>查看失敗發佈報告

您可以按一下**預期的失敗量**或**意外的失敗體積**指標，從下列任何報告存取失敗的發佈報告：

  - [Lync Server 2013 中的 [熱門失敗] 報告](lync-server-2013-top-failures-report.md)

  - [Lync Server 2013 中的會議診斷報告](lync-server-2013-conference-diagnostic-report.md)

  - [Lync Server 2013 中的對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

從失敗的發佈報告中，您可以按一下下列任何一項測量，以[在 Lync Server 2013 中查看失敗清單報告](lync-server-2013-failure-list-report.md)：

  - 常見的診斷原因（會話）

  - 熱門形式（會話）

  - 頂層池（會話）

  - 熱門來源（會話）

  - Top 元件（會話）

  - 使用者的最上層（會話）

  - 使用者的最上層（會話）

  - 使用者代理程式（會話）的頂端

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>使用失敗發佈報告

視您的監視器大小和螢幕解析度而定，當您在螢幕上查看失敗的發佈報告時，可能會有一些顯示的資料會被截斷。 特別是對於使用者代理程式（例如使用者代理程式）而言，可能會有非常長的標籤。 例如，名為「UCCAPI/4.0.7400.0 OC/4.0.7400.0 （Microsoft Lync 2013）」的使用者代理程式可能只會部分出現在螢幕上：

UCCAPI/4.0.7400.0 OC/4.0.7400.0 （Microsoft Ly .。。

幸運的是，您只需將滑鼠放在截斷的值上，就能看到整張標籤。

您可以使用「失敗發佈」報告篩選的一個有趣的度量單位是 [診斷 ID]。 如果您在其他報告中看到相同的診斷識別碼，您可以在失敗的發佈報告中篩選該識別碼，並在失敗的會話期間，獲得非常詳細的資訊，以及該識別碼已報告的頻率。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，失敗的發佈報告可讓您篩選諸如活動類型（點對點工作階段或會議會話）或隨附每個失敗會話的診斷 ID 等專案。

下表列出您可與失敗發佈報告搭配使用的篩選。

### <a name="failure-distribution-report-filters"></a>失敗的發佈報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
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
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
<tr class="even">
<td><p><strong>活動類型</strong></p></td>
<td><p>要篩選的活動類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>對等</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>會話類別</strong></p></td>
<td><p>指出問題中的活動是否已成功或失敗。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>成功案例</p></li>
<li><p>預期失敗</p></li>
<li><p>意外失敗</p></li>
</ul>
<p>&quot;預期的失敗&quot;是預期發生的失敗。 例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。 發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。 例如，如果來電者停留在 [保留] 上，就不應該終止通話。 如果發生這種情況，就會將它標記為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>常見診斷原因的度量單位

下表列出以最常報告的診斷 ID 為基礎的失敗發佈報告所提供的資訊。

### <a name="metrics-for-top-diagnostic-reasons"></a>常見診斷原因的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據診斷識別碼，失敗會話的相對排名。 診斷識別碼是附加至 SIP 訊息的唯一識別碼（以 ms 診斷標頭形式），它通常會在疑難排解錯誤中提供有用的資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>常見的診斷原因</strong></p></td>
<td><p>否</p></td>
<td><p>在會話中產生的診斷 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>產生指定診斷 ID 的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Top 形式的度量單位

下表列出根據遇到最多失敗的會話形式，在失敗發佈報告中提供的資訊。

### <a name="metrics-for-top-modalities"></a>Top 形式的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據會話類型（例如音訊/視訊會議或對等檔案傳輸會話），以失敗的會話為基礎的相對排名。</p></td>
</tr>
<tr class="even">
<td><p><strong>上方形式</strong></p></td>
<td><p>否</p></td>
<td><p>會話類型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>涉及指定模態的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>頂層池的度量單位

下表列出根據遇到最多失敗的池，在失敗發佈報告中提供的資訊。

### <a name="metrics-for-top-pools"></a>頂層池的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據執行會話的註冊機構池或邊緣伺服器來找出失敗會話的相對等級。</p></td>
</tr>
<tr class="even">
<td><p><strong>頂層池</strong></p></td>
<td><p>否</p></td>
<td><p>註冊機構池或邊緣伺服器的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個註冊機構池或邊緣伺服器的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>熱門來源的度量單位

下表列出根據遇到最多失敗的電腦，在失敗發佈報告中提供的資訊。

### <a name="metrics-for-top-sources"></a>熱門來源的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>每個電腦的相對排名失敗的會話。</p></td>
</tr>
<tr class="even">
<td><p><strong>熱門來源</strong></p></td>
<td><p>否</p></td>
<td><p>失敗會話中所涉及的電腦名稱稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個電腦的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>Top 元件的度量單位

下表列出根據遇到最多失敗的 Microsoft Lync Server 2010 元件，在失敗發佈報告中提供的資訊。

### <a name="metrics-for-top-components"></a>Top 元件的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據 Lync Server 2010 元件（例如 ExumRouting、GroupChat 或 MediationServer）而失敗的會話相對排名。</p></td>
</tr>
<tr class="even">
<td><p><strong>上方元件</strong></p></td>
<td><p>否</p></td>
<td><p>失敗會話中所涉及元件的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個元件的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>使用者的最高指標

下表列出失敗發佈報告中提供的資訊，這些資訊是根據在嘗試呼叫其他人（稱為「寄件者」使用者）時遇到最多失敗的使用者。

### <a name="metrics-for-top-from-users"></a>使用者的最高指標

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據受邀加入會話的使用者，對失敗的會話進行相對等級。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者頂端</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入會話的使用者 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個使用者的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>最上層使用者的度量單位

下表列出失敗發佈報告所提供的資訊，這些資訊是根據在其他使用者嘗試呼叫它們（稱為「收件者」使用者）時遇到最多失敗的使用者所提供。


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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據啟動會話的使用者，失敗會話的相對等級。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者頂端</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個使用者的失敗會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>主要使用者代理程式的度量單位

下表列出根據遇到最多失敗的端點軟體，在失敗發佈報告中提供的資訊。

### <a name="metrics-for-top-user-agents"></a>主要使用者代理程式的度量單位

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>排名</strong></p></td>
<td><p>否</p></td>
<td><p>根據會話中所涉及的使用者代理程式（軟體），在失敗的會話中相對排名的依據。 例如： RTCC/4.0.0.0 入站路由/4.0.0.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>最上層的使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>失敗會話中所涉及之使用者代理程式的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時段</strong></p></td>
<td><p>否</p></td>
<td><p>每個使用者代理程式失敗的會話總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

