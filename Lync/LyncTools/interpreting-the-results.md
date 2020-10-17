---
title: 解讀結果
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499910"
---
# <a name="interpreting-the-results"></a>解讀結果

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

Lync Server 2013 應力和效能工具 ( # A0) 有許多計數器可供您用來瞭解用戶端的執行狀況及是否發生問題。

<div>

## <a name="client-counters"></a>用戶端計數器

每個執行的 LyncPerfTool.exe 實例都有個別的計數器實例。 每個實例都會以其進程識別碼命名。

如果用戶端超載，可能會發生問題。 若要避免這些問題，請執行下列操作：

1.  監視用戶端電腦上的 CPU 和記憶體使用量。 如果 CPU 持續超過90%，請減少使用者數目。

2.  如果記憶體佔用量高，您可能會遇到問題，如果頁面檔案不夠大。 確認認可費用未超出電腦上的限制。 如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數目

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
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>花費的時間（分鐘）</p></td>
<td><p>自處理常式開始所花費的時間。</p></td>
</tr>
<tr class="even">
<td><p>作用中端點</p></td>
<td><p>目前連線至伺服器的端點數目。</p></td>
</tr>
<tr class="odd">
<td><p>失敗登入</p></td>
<td><p>端點登入失敗總數。</p></td>
</tr>
<tr class="even">
<td><p>登入嘗試</p></td>
<td><p>嘗試登入嘗試次數的總數。</p></td>
</tr>
<tr class="odd">
<td><p>中斷連線端點</p></td>
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
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 通話</p></td>
<td><p>目前狀態變更嘗試的總數。 針對不同類型的狀態變更，請參閱 SetPresence (目前狀態類型) 通話效能計數器。</p></td>
</tr>
<tr class="even">
<td><p>SetPresence 的 NNN 回應</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 通話</p></td>
<td><p>Get 顯示狀態要求嘗試總數。</p></td>
</tr>
<tr class="even">
<td><p>GetPresence 的 NNN 回應</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數。</p></td>
</tr>
</tbody>
</table>


**通訊錄服務資訊**

此類別包含用於監視通訊錄服務 (ABS) 檔案下載和通訊錄 Web 查詢服務要求的計數器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>嘗試實際的完整/Delta 檔案下載</p></td>
<td><p>所嘗試的完整或增量檔案下載要求總數。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完整/Delta 檔案下載成功</p></td>
<td><p>所嘗試的完整或增量檔案下載要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>通訊錄 Web 查詢服務相關的計數器</p></td>
<td><p>通訊錄檔案下載相關的計數器。</p></td>
</tr>
<tr class="even">
<td><p>嘗試的 ABS WS 通話</p></td>
<td><p>嘗試的通訊錄 Web 查詢服務要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 通話成功</p></td>
<td><p>傳回成功回應碼之通訊錄 Web 查詢服務要求的總數。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 通話失敗</p></td>
<td><p>傳回錯誤回應碼之通訊錄 Web 查詢服務要求的總數。</p></td>
</tr>
</tbody>
</table>


**通訊群組清單 (DL) 資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>嘗試的來電</p></td>
<td><p>嘗試之通訊群組清單擴充 (DLX) web 服務要求的總數。</p></td>
</tr>
<tr class="even">
<td><p>通話成功</p></td>
<td><p>傳回成功回應碼之 DLX web 服務要求的總數。</p></td>
</tr>
<tr class="odd">
<td><p>通話失敗</p></td>
<td><p>傳回錯誤回應碼之 DLX web 服務要求的總數。</p></td>
</tr>
</tbody>
</table>


**VoIP 基本資訊**

在啟用這些案例時，所有 Voice over IP (VoIP) 通話（包括對轉送伺服器的呼叫、A/V 會議伺服器、Edge Server、回應群組應用程式和會議自動語音應答）的報告編號，均會列出下列效能計數器。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動通話</p></td>
<td><p>目前正在進行的傳入/傳出語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>來電終止</p></td>
<td><p>已終止傳入/傳出語音通話的總數。</p></td>
</tr>
<tr class="odd">
<td><p>拒絕通話</p></td>
<td><p>拒絕的傳入語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試傳入/撥出電話</p></td>
<td><p>嘗試傳入/傳出語音通話的總數。</p></td>
</tr>
<tr class="odd">
<td><p>已建立傳入/撥出電話</p></td>
<td><p>已建立的傳入/傳出語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫已接收的 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 通率 (% ) </p></td>
<td><p>已建立的通話總數/嘗試的總通話數。</p></td>
</tr>
</tbody>
</table>


**回應群組服務呼叫資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動通話</p></td>
<td><p>回應群組應用程式的作用中呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試的來電</p></td>
<td><p>嘗試的呼叫總數。</p></td>
</tr>
</tbody>
</table>


**立即訊息 (IM) 呼叫資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動通話</p></td>
<td><p>進行中傳入/傳出立即訊息通話的總數。</p></td>
</tr>
<tr class="even">
<td><p>來電終止</p></td>
<td><p>已終止的傳入/傳出立即訊息通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫已接收的 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數。</p></td>
</tr>
<tr class="even">
<td><p>接收/傳送的 IM 訊息</p></td>
<td><p>所有會話中已接收或已傳送的郵件總數。</p></td>
</tr>
<tr class="odd">
<td><p>嘗試傳入/撥出電話</p></td>
<td><p>嘗試傳入/傳出立即訊息通話的總數。</p></td>
</tr>
<tr class="even">
<td><p>已建立傳入/撥出電話</p></td>
<td><p>已建立的傳入/傳出立即訊息通話總數。</p></td>
</tr>
</tbody>
</table>


**應用程式共用呼叫資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動通話</p></td>
<td><p>進行中傳入/傳出應用程式共用呼叫的總數。</p></td>
</tr>
<tr class="even">
<td><p>來電終止</p></td>
<td><p>已終止的傳入/傳出應用程式共用呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫已接收的 NNN</p></td>
<td><p>從伺服器接收的 nnn 回應碼總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試傳入/撥出電話</p></td>
<td><p>嘗試的傳入/傳出應用程式共用呼叫總數。</p></td>
</tr>
<tr class="odd">
<td><p>已建立傳入/撥出電話</p></td>
<td><p>已建立的傳入/傳出應用程式共用通話總數。</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA 呼叫資訊**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>效能計數器</strong></th>
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動通話</p></td>
<td><p>目前 (PSTN) 通話的內送/撥出公用交換電話網路 PSTN 總數。</p></td>
</tr>
<tr class="even">
<td><p>來電終止</p></td>
<td><p>已終止的傳入/傳出 PSTN 通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>嘗試傳入/撥出電話</p></td>
<td><p>嘗試傳入/傳出 PSTN 通話的總數。</p></td>
</tr>
<tr class="even">
<td><p>已建立傳入/撥出電話</p></td>
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
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>主動立即訊息會議</p></td>
<td><p>進行中的立即訊息會議總數。</p></td>
</tr>
<tr class="even">
<td><p>活躍 Audio/Video 會議</p></td>
<td><p>A/V) 會議的日常音訊/視頻 (總數。</p></td>
</tr>
<tr class="odd">
<td><p>Active Application 共用會議</p></td>
<td><p>進行中的應用程式共用會議總數。</p></td>
</tr>
<tr class="even">
<td><p>參與者人數</p></td>
<td><p>目前連接至會議的參與者總數。</p></td>
</tr>
<tr class="odd">
<td><p>會議排程失敗</p></td>
<td><p>嘗試排程會議時的失敗總數。</p></td>
</tr>
<tr class="even">
<td><p>加入會議失敗</p></td>
<td><p>嘗試連線至會議時的失敗總數。</p></td>
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
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已成功聯結的 IMMCU 聯接總數</p></td>
<td><p>加入的立即訊息會議總數。</p></td>
</tr>
<tr class="even">
<td><p>已成功聯結的 DMCU 聯接總數</p></td>
<td><p>加入的 A/V 會議總數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

