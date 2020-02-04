---
title: Lync Server 2013：呼叫許可控制報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a>Lync Server 2013 中的呼叫許可控制報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-29_

[通話許可控制] 報告會提供對等及會議會話的相關資訊，這些會話是在 [呼叫許可控制] 設定的 [限制] 下進行。 在 Microsoft Lync Server 2010 中引進的呼叫許可控制，提供讓系統管理員允許（或不允許）根據頻寬限制進行通訊會話的方式。 例如，管理員可以建立原則，限制語音和視頻通話可用的頻寬量。 如果已達到頻寬限制，則在其中一個目前的通話結束並釋放所需的網路資源前，不會放置新的語音或視頻通話。

<div>

## <a name="accessing-the-call-admission-control-report"></a>存取 [通話許可控制] 報告

[通話許可控制] 報告可從 [監控報告] 首頁存取。 從 [呼叫許可控制] 報告中，您可以向下切入至下列其中一項報告：

  - 會議詳細資料包告：若要存取此報告，請按一下會議會話中的詳細資料指標。

  - 點對點工作階段詳細資料包告-若要存取此報告，請按一下點對點工作階段的詳細資料規格。

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>充分利用 [呼叫許可控制] 報告

若要取得因頻寬不足而失敗的通話清單，請選取 [呼叫類別] 下拉式清單中的 [呼叫許可控制]。 大多數傳回的通話可能會有5的診斷識別碼：

頻寬不足，無法建立會話。 嘗試 PSTN 重新路由。

這表示呼叫許可控制限制是無法在 VoIP 網路上進行通話。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，[通話許可控制] 報告可讓您依啟動通話的使用者或呼叫的使用者來篩選通話。 您也可以選擇分組資料的方式。 在這種情況下，通話會依小時、日、周或月進行分組。

下表列出可與 [通話許可控制] 報告搭配使用的篩選器。

### <a name="call-admission-control-report-filters"></a>呼叫許可控制報告篩選器

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
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
<tr class="even">
<td><p><strong>活動類型</strong></p></td>
<td><p>活動類型。 選取下列其中一個活動：</p>
<ul>
<li><p>同時</p></li>
<li><p>對等</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>通話類別</strong></p></td>
<td><p>指出此通話使用 CAC 的原因。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>呼叫被拒絕，因為通話許可控制</p></li>
<li><p>呼叫在 PSTN 進行重新路由的呼叫，因為呼叫許可控制</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

下表列出點對點工作階段的呼叫許可控制報告中所提供的資訊（也就是只涉及兩個參與者的會話）。

### <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

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
<td><p><strong>具體</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示指定會話的點對點工作階段詳細資料包告。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者</strong></p></td>
<td><p>是</p></td>
<td><p>啟動會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>給使用者</strong></p></td>
<td><p>是</p></td>
<td><p>受邀加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>是</p></td>
<td><p>在會話期間使用的通訊形式（例如音訊與影片）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀請時間</strong></p></td>
<td><p>是</p></td>
<td><p>將初始會話邀請傳送給 [寄件者] 使用者的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應時間</strong></p></td>
<td><p>是</p></td>
<td><p>收到邀請接受的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>會話結束的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>是</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

下表列出會議會話的通話許可控制報告中所提供的資訊（也就是與三個或更多參與者相關的會話）。

### <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

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
<td><p><strong>會議 URI</strong></p></td>
<td><p>是</p></td>
<td><p>會議的唯一識別碼。 當您按一下此專案時，報告會顯示個別的會議參與者。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td><p>是</p></td>
<td><p>組織會議的使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>是</p></td>
<td><p>在會議中使用的邊緣伺服器。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議開始的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議結束的日期和時間。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>個別會議參與者的度量單位

下表列出個別會議參與者的通話許可控制報告所提供的資訊。

### <a name="metrics-for-individual-conference-participants"></a>個別會議參與者的度量單位

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
<td><p><strong>角色</strong></p></td>
<td><p>否</p></td>
<td><p>會議參與者所扮演的角色（例如，簡報者）。</p></td>
</tr>
<tr class="even">
<td><p><strong>參加</strong></p></td>
<td><p>否</p></td>
<td><p>會議參與者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連通</strong></p></td>
<td><p>否</p></td>
<td><p>參與者的網路連線（通常是內部或外部的網路連線）。</p></td>
</tr>
<tr class="even">
<td><p><strong>模態</strong></p></td>
<td><p>否</p></td>
<td><p>會議類型（例如，A/V 會議）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入時間</strong></p></td>
<td><p>否</p></td>
<td><p>參與者加入會議的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>休假時間</strong></p></td>
<td><p>否</p></td>
<td><p>參與者離開會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

