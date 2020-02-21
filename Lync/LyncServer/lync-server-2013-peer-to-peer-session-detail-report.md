---
title: Lync Server 2013： 端對端工作階段詳細資料報告
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
ms.openlocfilehash: fe04005d616a97a1fff4c84dbe43a5edb8e3cdba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的端對端工作階段詳細資料報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

端對端工作階段詳細資料報表會傳回對等工作階段的詳細的資訊。 例如，如果您選取 [立即訊息工作階段，報表會告訴您所兩位使用者每個工作階段中傳送的郵件數目。

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>存取對等工作階段詳細資料報告

端對端工作階段詳細資料報告可從任何下列報告 （這些元件可從監視報告首頁）：

  - IP 電話清查報告

  - 使用者活動報告

  - 通話許可控制報告

  - 失敗清單報告

端對端工作階段詳細資料報告中您可以從存取[診斷報告在 Lync Server 2013 中](lync-server-2013-diagnostic-report.md)按一下 [診斷報告 （詳細資料） 計量。 您也可以按一下任一這些兩個評量，以存取最大失敗報告：

  - 回應

  - 診斷識別碼

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>端對端工作階段詳細資料報告的最佳用法

端對端工作階段詳細資料報表包含大量的評量，其中有許多可能不熟悉系統管理員。 大多時候，不過，您可以檢視只要按住滑鼠移到計量標籤提供該計量的簡短描述的工具提示。

請注意，顯示在指定的報表上的實際評量取決於您所選取的端對端工作階段的類型。 音訊/視訊工作階段會報告一組不同的比立即訊息工作階段的計量。

您可以也將滑鼠停留在回應代碼和診斷 ID 計量以取得那些值的描述：

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選端對端工作階段詳細資料報告。

</div>

<div>

## <a name="session-information-metrics"></a>工作階段資訊計量

下表列出每個工作階段端對端工作階段詳細資料報告所提供的資訊。

### <a name="session-information-metrics"></a>工作階段資訊計量

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
<td><p>完整網域名稱 (FQDN) 的登錄器集區或 Edge Server 參與工作階段。</p></td>
</tr>
<tr class="even">
<td><p><strong>邀請時間</strong></p></td>
<td><p>日期和時間工作階段邀請最初發送。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應時間</strong></p></td>
<td><p>日期和時間收到的邀請接受度。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來源使用者代理程式</strong></p></td>
<td><p>起始工作階段之使用者端點所用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>是來源使用者內部</strong></p></td>
<td><p>指出起始工作階段之使用者是否已在內部網路登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>是與電話機整合的來源使用者</strong></p></td>
<td><p>指出起始工作階段之使用者所用的端點是否整合與他或她桌上電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作階段優先順序</strong></p></td>
<td><p>指派給工作階段的優先順序。 有效的優先順序： 未知;非緊急;正常;緊急;和緊急。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>SIP 工作階段失敗時傳送的回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端</strong></p></td>
<td><p>前端伺服器在會議中使用的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>擷取時間</strong></p></td>
<td><p>日期和時間的資訊記錄在工作階段。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>日期與時間工作階段結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者</strong></p></td>
<td><p>獲邀加入工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>目標使用者代理程式</strong></p></td>
<td><p>獲邀加入工作階段之使用者端點所用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>是目標使用者內部</strong></p></td>
<td><p>指出獲邀加入工作階段的使用者是否已在內部網路登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>是與電話機整合的目標使用者</strong></p></td>
<td><p>指出獲邀加入工作階段之使用者所使用的端點是否整合與他或她桌上電話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>重試工作階段</strong></p></td>
<td><p>會指出是否工作階段 」 會嘗試重試先前失敗的工作階段。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。 滑鼠停留的識別碼，若要檢視該識別碼的其他資訊</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>形式的計量

下表列出每個工作階段形式端對端工作階段詳細資料報告所提供的資訊。

### <a name="metrics-for-modalities"></a>形式的計量

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>形式</strong></p></td>
<td><p>否</p></td>
<td><p>工作階段中所使用的形式。 例如，可以立即訊息 (IM) 後或檔案傳輸。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者訊息</strong></p></td>
<td><p>否</p></td>
<td><p>起始工作階段之使用者所傳送的訊息數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者訊息</strong></p></td>
<td><p>否</p></td>
<td><p>獲邀加入工作階段之使用者所傳送的訊息數。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>診斷報告的計量

下表列出每份診斷報告端對端工作階段詳細資料報告所提供的資訊。

### <a name="metrics-for-diagnostic-reports"></a>診斷報告的計量

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Detail</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目時，報告就會顯示 [診斷報告工作階段。</p></td>
</tr>
<tr class="even">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>日期和時間報告的記錄。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 要求的類型。 例如，邀請或 BYE。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>會議中使用的媒體內容類型。 例如，常見的內容類型是應用程式/sdp。 工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。</p></td>
</tr>
<tr class="even">
<td><p><strong>由報告</strong></p></td>
<td><p>否</p></td>
<td><p>電腦 （亦即，用戶端或伺服器），回報的問題。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

