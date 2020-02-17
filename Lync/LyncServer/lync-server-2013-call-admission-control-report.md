---
title: Lync Server 2013： 通話許可控制報告
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
ms.openlocfilehash: ba5b643adf6a8208285aeba66304ddd1657afdfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a>Lync Server 2013 中通話許可控制報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-29_

通話許可控制報告提供的端對端的相關資訊和 [限制] 下所進行的會議工作階段設定中的通話許可控制的地方。 通話許可控制，在 Microsoft Lync Server 2010 中引進，讓系統管理員允許 （或不允許） 的通訊工作階段為基礎的頻寬限制。 例如，管理員可以建立加諸的適用於語音和視訊通話頻寬限制的原則。 如果已達到該頻寬限制，然後沒有新的語音或視訊通話可以放直到下列其中一個目前的呼叫已結束並釋出所需的網路資源。

<div>

## <a name="accessing-the-call-admission-control-report"></a>存取通話許可控制報告

通話許可控制報告是從監視報告首頁存取。 從 [通話許可控制報告中您可以向下其中一個下列報告切入：

  - 會議詳細資料報告： 要存取這份報告，請按一下 [從會議工作階段的詳細資料計量。

  - 端對端工作階段詳細資料報告： 要存取這份報告，請按一下 [詳細資料] 計量的端對端工作階段。

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>通話許可控制報告的最佳用法

若要取得的失敗，因為沒有足夠的頻寬的呼叫清單，選取 [因為呼叫類別下拉式清單中的通話許可控制而拒絕通話]。 大部分的傳回呼叫可能會有 5 的診斷識別碼：

若要建立工作階段的頻寬不足。 嘗試 PSTN 重新路由傳送。

這表示該通話許可控制限制所導致無法從 VoIP 網路上進行呼叫。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，通話許可控制報告可讓您篩選由撥打通話之使用者或已被呼叫使用者的呼叫。 您也可以選擇資料的分組方式。 在這種情況下，通話會按照小時、日、星期或月而加以分組。

下表列出您可以搭配通話許可控制報告的篩選器。

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
<p>2012/7/13</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/13</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>活動類型</strong></p></td>
<td><p>活動的類型。 選取下列其中一個下列活動：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>端對端</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>通話類別</strong></p></td>
<td><p>會指出 CAC 已用於通話的原因。 請選取下列其中一項：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>因通話許可控制而拒絕通話</p></li>
<li><p>因通話許可控制而透過 PSTN 重新路由</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>端對端工作階段的計量

下表列出對等端對端工作階段 （也就是工作階段只有兩個參與者） 通話許可控制報告內所提供的資訊。

### <a name="metrics-for-peer-to-peer-sessions"></a>端對端工作階段的計量

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
<td><p><strong>Detail</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告顯示您對等工作階段詳細資料報告的指定的工作階段。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>是</p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者</strong></p></td>
<td><p>是</p></td>
<td><p>獲邀加入工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>是</p></td>
<td><p>溝通形式 （如音訊或視訊） 工作階段期間所用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀請時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間初始工作階段邀請傳送至 「 從 」 使用者。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間收到的邀請接受度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和工作階段結束的時間。</p></td>
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

## <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

下表列出會議工作階段 （也就是參與者的工作階段三個或多個） 的通話許可控制報告內所提供的資訊。

### <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

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
<td><p><strong>會議 URI</strong></p></td>
<td><p>是</p></td>
<td><p>會議的唯一識別碼。 當您按一下此項目時，「 報告 」 顯示個別參與者。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td><p>是</p></td>
<td><p>召開會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>是</p></td>
<td><p>會議中使用的 edge Server。</p></td>
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

下表列出個別參與者的通話許可控制報告內所提供的資訊。

### <a name="metrics-for-individual-conference-participants"></a>個別會議參與者的計量

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
<td><p><strong>形式</strong></p></td>
<td><p>否</p></td>
<td><p>會議類型 (例如，A / V 會議)。</p></td>
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

