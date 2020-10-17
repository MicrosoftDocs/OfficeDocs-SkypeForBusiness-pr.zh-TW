---
title: Lync Server 2013：通話許可控制報告
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
ms.openlocfilehash: d1c1ff2b667c0529dfb7a90291dba7ad5ab154a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517960"
---
# <a name="call-admission-control-report-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-29_

通話許可控制報告可提供對等和會議會話的相關資訊，這些會話是在「通話許可控制」設定的限制下進行的。 Microsoft Lync Server 2010 所引進的通話許可控制可讓系統管理員允許 (或不允許根據頻寬限制進行) 通訊會話。 例如，系統管理員可以建立原則限制可用於語音和影片通話的頻寬量。 如果已達到頻寬限制，則直到其中一個目前的通話結束並釋放必要的網路資源時，才可以放入新的語音或視頻通話。

<div>

## <a name="accessing-the-call-admission-control-report"></a>存取通話許可控制報告

通話許可控制報告可從監控報告的首頁進行存取。 從通話許可控制報告中，您可以深入查看下列任一報告：

  - 會議詳細資料包告–若要存取此報告，請按一下會議會話中的詳細資料度量。

  - Peer-to-Peer 會話詳細資料包告–若要存取此報告，請按一下點對點工作階段的詳細資料度量。

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>充分利用通話許可控制報告

若要取得因頻寬不足而失敗的來電清單，請在 [呼叫類別] 下拉式清單中，選取 [通話許可控制拒絕的來電]。 大多數傳回的呼叫可能會有5個診斷識別碼：

沒有足夠的頻寬來建立會話。 嘗試 PSTN 重新路由傳送。

這表示通話許可控制限制阻礙在 VoIP 網路上進行呼叫。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，通話許可控制報告可讓您篩選撥打通話之使用者的電話，或由呼叫的使用者來篩選來電。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配通話許可控制報告使用的篩選器。

### <a name="call-admission-control-report-filters"></a>通話許可控制報告篩選器

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
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>活動類型</strong></p></td>
<td><p>活動的類型。 選取下列其中一個活動：</p>
<ul>
<li><p>一切</p></li>
<li><p>Peer-to-Peer</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>通話類別</strong></p></td>
<td><p>指出用於通話的 CAC 的原因。 請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>因通話許可控制而拒絕通話</p></li>
<li><p>通話透過 PSTN 重新路由傳送，因為通話許可控制</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Peer-to-Peer 會話的計量

下表列出點對點工作階段的通話許可控制報告中所提供的資訊 (也就是說，只涉及兩位參與者的會話) 。

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
<td><p><strong>Detail</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示指定之會話的 Peer-to-Peer 會話詳細資料包告。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>是</p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者</strong></p></td>
<td><p>是</p></td>
<td><p>獲邀加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>方式</strong></p></td>
<td><p>是</p></td>
<td><p>通訊形式 (例如在會話期間使用的音訊和影片) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀請時間</strong></p></td>
<td><p>是</p></td>
<td><p>初始會話邀請傳送給寄件者的日期和時間。</p></td>
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
<td><p>附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議會話的計量

下表列出會議會話的通話許可控制報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。

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
<td><p><strong>會議 URI</strong></p></td>
<td><p>是</p></td>
<td><p>會議的唯一識別碼。 當您按一下此專案時，報表會顯示個別的會議參與者。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td><p>是</p></td>
<td><p>召開會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>是</p></td>
<td><p>會議中所使用的 Edge Server。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議開始的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議結束的日期與時間。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>個別會議參與者的計量

下表列出個別會議參與者通話許可控制報告中提供的資訊。

### <a name="metrics-for-individual-conference-participants"></a>個別會議參與者的計量

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
<td><p><strong>Role</strong></p></td>
<td><p>否</p></td>
<td><p>會議參與者所扮演的角色 (例如，簡報者)。</p></td>
</tr>
<tr class="even">
<td><p><strong>參與者</strong></p></td>
<td><p>否</p></td>
<td><p>會議參與者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連線能力</strong></p></td>
<td><p>否</p></td>
<td><p>參與者的網路連線 (一般來說是從內部或從外部)。</p></td>
</tr>
<tr class="even">
<td><p><strong>形態</strong></p></td>
<td><p>否</p></td>
<td><p>會議類型 (例如，A/V 會議) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入時間</strong></p></td>
<td><p>否</p></td>
<td><p>參與者加入會議的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>離開時間</strong></p></td>
<td><p>否</p></td>
<td><p>參與者離開會議的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

