---
title: Lync Server 2013： Peer-to-Peer 會話詳細資料包告
description: Lync Server 2013： Peer-to-Peer 會話詳細資料包告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557279"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的 Peer-to-Peer 會話詳細資料包告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

Peer-to-Peer 會話詳細資料包告會傳回點對點工作階段的詳細資訊。 例如，如果您選取立即訊息會話，該報告將會告訴您會話中的兩位使用者所傳送的郵件數目。

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>存取 Peer-to-Peer 會話詳細資料包告

您可以從下列任何報告中存取 Peer-to-Peer 會話詳細資料包告 (所有可從監控報告首頁存取的報告) ：

  - IP 電話清查報告

  - 使用者活動報告

  - 通話許可控制報告

  - 失敗清單報告

在 [Peer-to-Peer 會話詳細資料包告] 中，按一下 [診斷報告 (詳細資料]) 指標，即可存取 [Lync Server 2013 中的診斷報告](lync-server-2013-diagnostic-report.md) 。 您也可以按一下下列兩個度量，以存取最上層失敗報告：

  - 回應

  - 診斷識別碼

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Peer-to-Peer 會話詳細資料包告的最佳用法

「Peer-to-Peer 會話詳細資料包告」包括大量的計量，許多系統管理員可能都不熟悉。 不過，您通常可以查看工具提示，只要將滑鼠放在「規格」標籤上方，就能提供該度量的簡短描述。

請注意，顯示在特定報告上的實際度量值將取決於您所選取的點對點工作階段類型。 音訊/視頻會話會報告一組不同于立即訊息會話的計量。

您也可以將滑鼠停留在回應程式碼和診斷識別碼計量中，以取得這些值的描述：

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選 Peer-to-Peer 會話詳細資料包告。

</div>

<div>

## <a name="session-information-metrics"></a>會話資訊計量

下表列出每個會話的 Peer-to-Peer 會話詳細資料包告中提供的資訊。

### <a name="session-information-metrics"></a>會話資訊計量

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
<td><p><strong>集區 FQDN</strong></p></td>
<td><p>與會話有關之註冊區集區或 Edge Server 的完整功能變數名稱 (FQDN) 。</p></td>
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
<td><p><strong>來源使用者</strong></p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>啟動會話之使用者端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>來自使用者內部</strong></p></td>
<td><p>會指出起始會話的使用者是否登入內部網路。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來源於與電話機整合的使用者</strong></p></td>
<td><p>會指出起始會話之使用者所使用的端點是否與他或她的桌面電話整合。</p></td>
</tr>
<tr class="even">
<td><p><strong>會話優先順序</strong></p></td>
<td><p>指派給會話的優先順序。 有效的優先順序如下： Unknown;非緊急;一般緊迫和緊急。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>會話失敗時傳送的 SIP 回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端</strong></p></td>
<td><p>會議中所使用的前端伺服器名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拍攝時間</strong></p></td>
<td><p>記錄會話資訊的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>會話結束的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者</strong></p></td>
<td><p>獲邀加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>至使用者代理程式</strong></p></td>
<td><p>受邀加入會話之使用者的端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>是使用者內部使用者</strong></p></td>
<td><p>會指出被邀加入會話的使用者是否登入內部網路。</p></td>
</tr>
<tr class="even">
<td><p><strong>是與電話機整合的使用者</strong></p></td>
<td><p>會指出受邀加入會話之使用者所使用的端點是否與他或她的桌面電話整合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會重試會話</strong></p></td>
<td><p>會指出會話是否嘗試重試先前失敗的會話。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。 將滑鼠停留在識別碼號碼上方，以查看有關該識別碼的其他資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>形式的計量

下表列出每個會話模態的 Peer-to-Peer 會話詳細資料包告中提供的資訊。

### <a name="metrics-for-modalities"></a>形式的計量

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
<td><p><strong>方式</strong></p></td>
<td><p>否</p></td>
<td><p>會話中使用的形式。 例如，立即訊息 (IM) 或檔案傳輸。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者郵件</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話之使用者所傳送的訊息數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用者訊息</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入會話之使用者所傳送的郵件數目。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>診斷報告的計量

下表列出每個診斷報告的 Peer-to-Peer 會話詳細資料包告中提供的資訊。

### <a name="metrics-for-diagnostic-reports"></a>診斷報告的計量

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
<td><p>當您按一下此專案時，報告會顯示會話的診斷報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>報告的記錄日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>請求</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 要求類型。 例如，INVITE 或再見。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</p></td>
</tr>
<tr class="odd">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>會議中所使用的媒體內容類型。 例如，常見的內容類型為 Application/sdp。 Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告者</strong></p></td>
<td><p>否</p></td>
<td><p>電腦 (，也就是報告問題的用戶端或伺服器) 。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

