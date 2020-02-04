---
title: 解釋結果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>解釋結果

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 應力和效能工具（LyncPerfTool）有許多計數器，您可以用來瞭解用戶端正在執行的動作，以及是否遇到問題。

<div>

## <a name="client-counters"></a>用戶端計數器

每個執行中的 LyncPerfTool 實例都有一個單獨的計數器實例。 每個實例都是以其進程識別碼命名。

如果用戶端超載，可能會發生問題。 若要避免這些問題，請執行下列動作：

1.  監視用戶端電腦上的 CPU 和記憶體使用量。 如果 CPU 持續超過90%，請減少使用者數目。

2.  如果記憶體需求量較高，您可能會在頁面檔案不夠大時遇到問題。 確認確認費用未超出電腦的限制。 如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數量

下表列出重要的 LyncPerfTool 效能計數器。

**一般資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>花費的時間（以分鐘為單位）</p></td>
<td><p>進程開始之後所花費的時間。</p></td>
</tr>
<tr class="even">
<td><p>作用中端點</p></td>
<td><p>目前連線到伺服器的端點數目。</p></td>
</tr>
<tr class="odd">
<td><p>失敗的登錄</p></td>
<td><p>端點登入失敗的總數。</p></td>
</tr>
<tr class="even">
<td><p>登入嘗試</p></td>
<td><p>端點登入嘗試的總數。</p></td>
</tr>
<tr class="odd">
<td><p>端點已中斷連接</p></td>
<td><p>已中斷連線的端點總數。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**目前狀態資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 通話</p></td>
<td><p>目前狀態變更嘗試的總數。 針對不同類型的目前狀態變更，請參閱 SetPresence （目前狀態類型）通話效能計數器。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence 的 NNN 回應</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數目。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 通話</p></td>
<td><p>[取得目前狀態] 要求嘗試的總數。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence 的 NNN 回應</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數目。</p></td>
</tr>
</tbody>
</table>


**通訊錄服務資訊**

此類別包含用來監視通訊錄服務（ABS）檔案下載和通訊錄網頁查詢服務要求的計數器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>嘗試的 ABS 完整/增量檔案下載</p></td>
<td><p>已嘗試完整或增量檔案下載要求的總數目。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完整/Delta 檔案下載成功</p></td>
<td><p>已嘗試完整或增量檔案下載要求的總數目。</p></td>
</tr>
<tr class="odd">
<td><p>通訊錄 Web 查詢服務相關計數器</p></td>
<td><p>通訊錄檔案下載相關計數器。</p></td>
</tr>
<tr class="even">
<td><p>嘗試 ABS 通話</p></td>
<td><p>嘗試的通訊錄 Web 查詢服務要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 通話成功</p></td>
<td><p>傳回成功回應代碼之通訊錄 Web 查詢服務要求的總數。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 通話失敗</p></td>
<td><p>傳回錯誤回應代碼之通訊錄 Web 查詢服務要求的總數。</p></td>
</tr>
</tbody>
</table>


**通訊群組清單（DL）資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已嘗試來電</p></td>
<td><p>嘗試的通訊群組清單展開（DLX） web 服務要求總數。</p></td>
</tr>
<tr class="even">
<td><p>通話成功</p></td>
<td><p>傳回成功回應代碼之 DLX web 服務要求的總數目。</p></td>
</tr>
<tr class="odd">
<td><p>通話失敗</p></td>
<td><p>傳回錯誤回應代碼之 DLX web 服務要求的總數。</p></td>
</tr>
</tbody>
</table>


**VoIP 基本資訊**

在啟用這些案例時，以下所列的效能計數器會列示在所有的語音 IP （VoIP）通話中，包括對轉送伺服器、A/V 會議伺服器、邊緣伺服器、回應群組應用程式，以及會議自動語音應答。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用中的通話</p></td>
<td><p>目前正在進行的傳入/傳出語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫終止</p></td>
<td><p>已終止的傳入/傳出語音通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>拒絕通話</p></td>
<td><p>已拒絕的來電通話總數。</p></td>
</tr>
<tr class="even">
<td><p>已嘗試來電/撥出通話</p></td>
<td><p>已嘗試輸入/撥出語音通話的總數。</p></td>
</tr>
<tr class="odd">
<td><p>已建立來電/撥出通話</p></td>
<td><p>已建立的傳入/傳出語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已收到 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數目。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 傳遞率（%）</p></td>
<td><p>已建立的通話總數/嘗試的通話總數。</p></td>
</tr>
</tbody>
</table>


**回應群組服務通話資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用中的通話</p></td>
<td><p>回應群組應用程式的使用中通話總次數。</p></td>
</tr>
<tr class="even">
<td><p>已嘗試來電</p></td>
<td><p>嘗試的通話總次數。</p></td>
</tr>
</tbody>
</table>


**立即訊息（IM）通話資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用中的通話</p></td>
<td><p>正在進行內傳/撥出的立即訊息通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫終止</p></td>
<td><p>已終止傳入/傳出立即訊息通話的總數。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫已收到 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數目。</p></td>
</tr>
<tr class="even">
<td><p>接收/傳送的 IM 訊息</p></td>
<td><p>所有會話接收或傳送的訊息總數。</p></td>
</tr>
<tr class="odd">
<td><p>已嘗試來電/撥出通話</p></td>
<td><p>嘗試的傳入/傳出立即訊息呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p>已建立來電/撥出通話</p></td>
<td><p>已建立的傳入/傳出立即訊息通話總數。</p></td>
</tr>
</tbody>
</table>


**App 共用呼叫資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用中的通話</p></td>
<td><p>正在進行中傳入/傳出應用程式共用通話的總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫終止</p></td>
<td><p>已終止的傳入/傳出應用程式共用通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫已收到 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數目。</p></td>
</tr>
<tr class="even">
<td><p>已嘗試來電/撥出通話</p></td>
<td><p>嘗試的傳入/傳出應用程式共用呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p>已建立來電/撥出通話</p></td>
<td><p>已建立的傳入/傳出應用程式共用通話總數。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA 通話資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用中的通話</p></td>
<td><p>目前正在進行中的內送/出局公用電話網絡（PSTN）通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫終止</p></td>
<td><p>已終止的傳入/傳出 PSTN 通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>已嘗試來電/撥出通話</p></td>
<td><p>嘗試的傳入/傳出 PSTN 呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p>已建立來電/撥出通話</p></td>
<td><p>已建立的傳入/傳出 PSTN 通話總數。</p></td>
</tr>
</tbody>
</table>


**會議資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>即時立即訊息會議</p></td>
<td><p>即時立即訊息會議的總數。</p></td>
</tr>
<tr class="even">
<td><p>活動音訊/視訊會議</p></td>
<td><p>正在進行的音訊/視頻（A/V）會議總數。</p></td>
</tr>
<tr class="odd">
<td><p>使用中的應用程式共用會議</p></td>
<td><p>正在進行的應用程式共用會議總數。</p></td>
</tr>
<tr class="even">
<td><p>參與者人數</p></td>
<td><p>目前與會議連接的參與者總數。</p></td>
</tr>
<tr class="odd">
<td><p>會議排程失敗</p></td>
<td><p>嘗試排程會議時失敗的總數。</p></td>
</tr>
<tr class="even">
<td><p>加入會議失敗</p></td>
<td><p>嘗試連線到會議時失敗的總數。</p></td>
</tr>
</tbody>
</table>


**UCWA 用戶端計數器**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>說明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>成功的 IMMCU 連接總數</p></td>
<td><p>已加入之立即訊息會議的總數。</p></td>
</tr>
<tr class="even">
<td><p>成功的 DMCU 連接總數</p></td>
<td><p>已加入/V 會議的總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

