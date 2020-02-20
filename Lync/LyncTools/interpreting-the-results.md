---
title: 解譯結果
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
ms.openlocfilehash: 484f10757dcbd1463b54cf70ac8d725402decb44
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>解譯結果

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe) 具有您可以使用來了解用戶端所做的動作，以及是否發生問題的許多計數器。

<div>

## <a name="client-counters"></a>用戶端計數器

每個執行個體正在執行的 LyncPerfTool.exe 有獨立的執行個體的計數器。 每個執行個體是名為其處理程序識別碼。

如果用戶端屬於多載，可以發生問題。 若要避免這些問題，執行下列動作：

1.  監視 CPU 及記憶體使用量的用戶端電腦上。 如果 CPU 持續超過百分之 90，降低使用者的數目。

2.  如果記憶體耗用量為高，您可能會遇到問題如果分頁檔不是夠大。 確認認可費用未達到次之電腦上的限制。 如果您執行到記憶體限制，請考慮增加分頁檔案大小或降低的使用者數目

下表列出的索引鍵的 LyncPerfTool 效能計數器。

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
<td><p>以分鐘為單位所花費的時間</p></td>
<td><p>啟動程序後，所需時間。</p></td>
</tr>
<tr class="even">
<td><p>作用中的端點</p></td>
<td><p>目前連接至伺服器的端點數目。</p></td>
</tr>
<tr class="odd">
<td><p>登入失敗</p></td>
<td><p>端點登入失敗總數。</p></td>
</tr>
<tr class="even">
<td><p>登入嘗試次數</p></td>
<td><p>嘗試登入的端點總數。</p></td>
</tr>
<tr class="odd">
<td><p>中斷連線的端點</p></td>
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
<td><p>總數的目前狀態變更次數。 對於不同類型的目前狀態變更，請參閱 < SetPresence （目前狀態類型） 的呼叫] 效能計數器。</p></td>
</tr>
<tr class="even">
<td><p>NNN 回應的 SetPresence</p></td>
<td><p>從伺服器收到 nnn 回應碼的總數。</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 通話</p></td>
<td><p>取得目前狀態要求嘗試的總次數。</p></td>
</tr>
<tr class="even">
<td><p>NNN 回應的 GetPresence</p></td>
<td><p>從伺服器收到 nnn 回應碼的總數。</p></td>
</tr>
</tbody>
</table>


**通訊錄服務資訊**

此類別包含用來監視下載通訊錄服務 (ABS) 檔案和通訊錄 Web 查詢服務要求的計數器。


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
<td><p>嘗試 ABS 完整/差異檔案下載</p></td>
<td><p>嘗試的完整] 或 [差異檔案下載要求總數。</p></td>
</tr>
<tr class="even">
<td><p>ABS 完整/差異檔案下載成功</p></td>
<td><p>嘗試的完整] 或 [差異檔案下載要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>通訊錄 Web 查詢服務相關計數器</p></td>
<td><p>通訊錄檔案下載相關的計數器。</p></td>
</tr>
<tr class="even">
<td><p>嘗試 ABS WS 通話</p></td>
<td><p>嘗試的通訊錄 Web 查詢服務要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 通話成功</p></td>
<td><p>傳回成功回應程式碼的通訊錄 Web 查詢服務要求總數。</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 通話失敗</p></td>
<td><p>傳回的錯誤回應程式碼的通訊錄 Web 查詢服務要求總數。</p></td>
</tr>
</tbody>
</table>


**通訊清單 (DL) 的資訊**


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
<td><p>嘗試的通話</p></td>
<td><p>通訊群組清單擴充 (DLX) web 服務要求嘗試總數。</p></td>
</tr>
<tr class="even">
<td><p>成功的通話</p></td>
<td><p>傳回成功回應程式碼的 DLX web 服務要求總數。</p></td>
</tr>
<tr class="odd">
<td><p>失敗的通話</p></td>
<td><p>傳回的錯誤回應程式碼的 DLX web 服務要求總數。</p></td>
</tr>
</tbody>
</table>


**VoIP Basic 資訊**

效能計數器下面列出報表號碼所有 voice over IP (VoIP) 通話，包括中繼伺服器的呼叫 / V 會議伺服器、 Edge Server，回應群組應用程式，以及會議自動語音應答，當啟用這些案例。


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
<td><p>呼叫使用中</p></td>
<td><p>總數的傳出連入讀的語音呼叫目前進行中。</p></td>
</tr>
<tr class="even">
<td><p>終止前所需的通話</p></td>
<td><p>已終止的內送/撥出語音通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>拒絕的來電</p></td>
<td><p>拒絕的傳入語音呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試的傳入/撥出通話</p></td>
<td><p>嘗試傳入/撥出語音通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>建立內送/撥出通話</p></td>
<td><p>建立內送/撥出語音通話總數。</p></td>
</tr>
<tr class="even">
<td><p>呼叫接收的 NNN</p></td>
<td><p>從伺服器收到 nnn 回應碼的總數。</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 複雜率 （%）</p></td>
<td><p>建立/總通話嘗試來電總數。</p></td>
</tr>
</tbody>
</table>


**回應群組服務呼叫的資訊**


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
<td><p>呼叫使用中</p></td>
<td><p>回應群組應用程式的作用中呼叫總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試的通話</p></td>
<td><p>嘗試的通話總數。</p></td>
</tr>
</tbody>
</table>


**立即訊息 (IM) 通話資訊**


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
<td><p>呼叫使用中</p></td>
<td><p>持續傳入/傳出立即訊息的通話總數。</p></td>
</tr>
<tr class="even">
<td><p>終止前所需的通話</p></td>
<td><p>已終止傳入/傳出立即訊息的來電總數。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫接收的 NNN</p></td>
<td><p>從伺服器收到 nnn 回應碼的總數。</p></td>
</tr>
<tr class="even">
<td><p>接收/傳送 IM 訊息</p></td>
<td><p>訊息總數接收或傳送的所有工作階段。</p></td>
</tr>
<tr class="odd">
<td><p>嘗試的傳入/撥出通話</p></td>
<td><p>傳入/傳出立即訊息呼叫嘗試總數。</p></td>
</tr>
<tr class="even">
<td><p>建立內送/撥出通話</p></td>
<td><p>建立內送/傳出立即訊息通話總數。</p></td>
</tr>
</tbody>
</table>


**應用程式共用通話資訊**


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
<td><p>呼叫使用中</p></td>
<td><p>進行中的內送/傳出的應用程式共用通話總數。</p></td>
</tr>
<tr class="even">
<td><p>終止前所需的通話</p></td>
<td><p>總數傳入/傳出的應用程式共用通話已終止。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫接收的 NNN</p></td>
<td><p>從伺服器收到 nnn 回應碼的總數。</p></td>
</tr>
<tr class="even">
<td><p>嘗試的傳入/撥出通話</p></td>
<td><p>傳入/傳出的應用程式共用嘗試的通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>建立內送/撥出通話</p></td>
<td><p>傳入/傳出的應用程式共用建立的通話總數。</p></td>
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
<th><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>呼叫使用中</p></td>
<td><p>總數傳入/傳出公用交換的電話網路 (PSTN) 通話目前進行中。</p></td>
</tr>
<tr class="even">
<td><p>終止前所需的通話</p></td>
<td><p>已終止的內送/傳出 PSTN 通話總數。</p></td>
</tr>
<tr class="odd">
<td><p>嘗試的傳入/撥出通話</p></td>
<td><p>嘗試傳入/傳出 PSTN 通話總數。</p></td>
</tr>
<tr class="even">
<td><p>建立內送/撥出通話</p></td>
<td><p>建立內送/傳出 PSTN 通話總數。</p></td>
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
<td><p>作用中的立即訊息會議</p></td>
<td><p>進行中的立即訊息會議總數。</p></td>
</tr>
<tr class="even">
<td><p>作用中的音訊/視訊會議</p></td>
<td><p>總數的進行中的音訊/視訊 (A / V) 會議。</p></td>
</tr>
<tr class="odd">
<td><p>使用中應用程式共用會議</p></td>
<td><p>進行中的應用程式共用會議總數。</p></td>
</tr>
<tr class="even">
<td><p>參與者的數量</p></td>
<td><p>目前連線至會議的參與者總數。</p></td>
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
<td><p>總數 IMMCU 聯結成功</p></td>
<td><p>加入立即訊息的會議總數。</p></td>
</tr>
<tr class="even">
<td><p>總數 DMCU 聯結成功</p></td>
<td><p>總數的 A / V 會議加入。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

