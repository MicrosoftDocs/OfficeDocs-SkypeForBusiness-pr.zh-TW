---
title: Lync Server 2013：點對點工作階段詳細資料包告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73febb248a8b61979c0aad2df6977c9feccb91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的點對點工作階段詳細資料包表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

點對點工作階段詳細資料包告會傳回點對點工作階段的詳細資訊。 例如，如果您選取 [立即訊息] 會話，報告就會告訴您會話中兩位使用者傳送的訊息數目。

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>存取點對點工作階段詳細資料包告

您可以從下列任何報告存取點對點工作階段詳細資料包告（所有這些報告都可以從 [監控報告] 首頁存取）：

  - IP 電話清查報告

  - 使用者活動報告

  - 通話許可控制報告

  - 失敗清單報告

從點對點工作階段詳細資料包告中，按一下 [診斷報告（詳細資料）] 度量，即可存取[Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md)。 您也可以按一下以下兩個指標中的任何一個，以存取 [熱門失敗] 報告：

  - 應對

  - 診斷識別碼

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>充分運用點對點工作階段詳細資料包告

點對點工作階段詳細資料包告包含大量的度量單位，而系統管理員可能不熟悉其中許多規格。 不過，通常只要將滑鼠放在公制標籤上，就可以查看工具提示，以提供該標準的簡短描述。

請注意，指定報告上顯示的實際度量單位將取決於您所選取的點對點工作階段類型。 音訊/視頻會話會報告一組不同的度量值，而不是立即訊息會話。

您也可以將滑鼠放在回應程式碼和診斷 ID 指標中，以取得這些值的描述：

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法篩選點對點工作階段詳細資料包告。

</div>

<div>

## <a name="session-information-metrics"></a>會話資訊度量單位

下表列出每個會話的點對點工作階段詳細資料包告中提供的資訊。

### <a name="session-information-metrics"></a>會話資訊度量單位

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
<td><p><strong>池 FQDN</strong></p></td>
<td><p>會話中所涉及的註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</p></td>
</tr>
<tr class="even">
<td><p><strong>邀請時間</strong></p></td>
<td><p>最初傳送會話邀請的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應時間</strong></p></td>
<td><p>收到邀請接受的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者</strong></p></td>
<td><p>啟動會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>啟動會話之使用者的端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>是來自使用者內部</strong></p></td>
<td><p>指出啟動會話的使用者是否已登入內部網路。</p></td>
</tr>
<tr class="odd">
<td><p><strong>是來自與手機整合的使用者</strong></p></td>
<td><p>指出啟動會話的使用者所使用的端點是否與他或她的桌面電話整合。</p></td>
</tr>
<tr class="even">
<td><p><strong>會話優先順序</strong></p></td>
<td><p>指派給會話的優先順序。 有效的優先順序為：未知;非緊急;標準非常以及緊急情況。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應代碼</strong></p></td>
<td><p>在會話失敗時傳送 SIP 回應代碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端</strong></p></td>
<td><p>在會議中使用的前端伺服器名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>捕獲時間</strong></p></td>
<td><p>記錄會話資訊的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>會話結束的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>給使用者</strong></p></td>
<td><p>受邀者加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>給使用者代理程式</strong></p></td>
<td><p>受邀者參與會話之使用者的端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>是對使用者內部</strong></p></td>
<td><p>指出受邀加入會話的使用者是否已登入內部網路。</p></td>
</tr>
<tr class="even">
<td><p><strong>是與手機整合的使用者</strong></p></td>
<td><p>表示受邀者加入會話的使用者所使用的端點是否與他或她的桌面電話整合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>[重試] 會話</strong></p></td>
<td><p>指出會話是否嘗試重試先前失敗的會話。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 將滑鼠停留在識別碼編號上方，即可查看該識別碼的其他相關資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>形式的度量單位

下表列出每個會話模態的點對點工作階段詳細資料包告中提供的資訊。

### <a name="metrics-for-modalities"></a>形式的度量單位

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
<td><p><strong>形式</strong></p></td>
<td><p>否</p></td>
<td><p>在會話中使用的形式。 例如，立即訊息（IM）或檔案傳輸。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者郵件</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話的使用者所傳送的訊息數目。</p></td>
</tr>
<tr class="odd">
<td><p><strong>給使用者訊息</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入會話的使用者所傳送的訊息數目。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>診斷報告的度量單位

下表列出每個診斷報告的點對點工作階段詳細資料包告中提供的資訊。

### <a name="metrics-for-diagnostic-reports"></a>診斷報告的度量單位

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
<td><p><strong>具體</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示該會話的診斷報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>記錄報告的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>徵求</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 要求類型。 例如，[邀請] 或 [再見]。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>在會議中使用的媒體內容類型。 例如，常見的內容類型是 Application/sdp。 會話描述通訊協定（SDP）是一種標準的網際網路通訊協定，用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告者</strong></p></td>
<td><p>否</p></td>
<td><p>報告問題的電腦（即用戶端或伺服器）。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

