---
title: Lync Server 2013：行動性效能計數器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013 中的行動效能計數器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊 Web API （UCWA）和 Lync Server 2013 Mcx 行動服務的伺服器。

UCWA 資料表中計數器的類別名稱是**LS： WEB – UCWA**。

Mcx 行動服務資料表中計數器的類別名稱是**LS： WEB Mobile 通訊服務**。

<div>

## <a name="performance-counters-for-ucwa"></a>UCWA 的效能計數器


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>反</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>作用中的應用程式計數</p></td>
<td><p>目前的應用程式數</p></td>
</tr>
<tr class="even">
<td><p>使用中的應用程式共用模態計數</p></td>
<td><p>應用程式共用模態的目前數量</p></td>
</tr>
<tr class="odd">
<td><p>使用中的音訊模態計數</p></td>
<td><p>目前的音訊模態數量</p></td>
</tr>
<tr class="even">
<td><p>活動資料共同作業計數</p></td>
<td><p>目前的資料共同作業數</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 相片取得延遲（毫秒）</p></td>
<td><p>這個計數器顯示從 active directory 中檢索相片的平均時間（以毫秒為單位）</p></td>
</tr>
<tr class="even">
<td><p>使用中的訊息模態計數</p></td>
<td><p>目前的訊息模態數量</p></td>
</tr>
<tr class="odd">
<td><p>使用中全景視頻的狀態計數</p></td>
<td><p>目前的全景視頻模態數量</p></td>
</tr>
<tr class="even">
<td><p>作用中未決取得計數</p></td>
<td><p>目前處於作用中未決的取得次數;在伺服器上保留較長的連線連接</p></td>
</tr>
<tr class="odd">
<td><p>活動會話計數</p></td>
<td><p>每個應用程式在 UCWA 中註冊的端點數目及總計</p></td>
</tr>
<tr class="even">
<td><p>作用中使用者實例計數</p></td>
<td><p>目前的使用者實例數</p></td>
</tr>
<tr class="odd">
<td><p>不含應用程式的作用中使用者實例</p></td>
<td><p>目前不含應用程式的使用者實例數</p></td>
</tr>
<tr class="even">
<td><p>使用中的視頻模態統計</p></td>
<td><p>目前的視頻模態數量</p></td>
</tr>
<tr class="odd">
<td><p>收到的應用程式建立要求/秒</p></td>
<td><p>每秒收到應用程式建立要求的速率</p></td>
</tr>
<tr class="even">
<td><p>作為 MCU 連接失敗</p></td>
<td><p>MCU 連接失敗的次數</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 聯接失敗</p></td>
<td><p>AV MCU 連接失敗次數</p></td>
</tr>
<tr class="even">
<td><p>應用程式的平均啟動時間（毫秒）</p></td>
<td><p>應用程式的平均啟動時間（以毫秒為單位）</p></td>
</tr>
<tr class="odd">
<td><p>會話的平均存留期（毫秒）</p></td>
<td><p>會話的平均存留期（以毫秒為單位）</p></td>
</tr>
<tr class="even">
<td><p>資料 MCU 連接失敗</p></td>
<td><p>資料 MCU 連接失敗次數</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 連絡人搜尋延遲時間（毫秒）</p></td>
<td><p>這個計數器顯示在 Exchange 中搜尋連絡人的平均時間（以毫秒為單位）</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 相片取得延遲（毫秒）</p></td>
<td><p>這個計數器顯示從 Exchange 中檢索相片的平均時間（以毫秒為單位）</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 回應/秒</p></td>
<td><p>每秒回應與 HTTP 4xx 代碼的回應速率</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 回應/秒</p></td>
<td><p>每秒回應與 HTTP 5xx 代碼的回應速率</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU 連接失敗</p></td>
<td><p>IM MCU 連接失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 相片取得失敗的次數</p></td>
<td><p>從 Active Directory 中檢索相片的失敗總次數</p></td>
</tr>
<tr class="odd">
<td><p>連絡人搜尋失敗的次數</p></td>
<td><p>在 Exchange 中搜尋連絡人的失敗總次數</p></td>
</tr>
<tr class="even">
<td><p>反序列化失敗次數</p></td>
<td><p>反序列化失敗的總次數</p></td>
</tr>
<tr class="odd">
<td><p>HD 相片取得失敗的次數</p></td>
<td><p>從 Exchange 中取得 HD 相片的失敗總次數</p></td>
</tr>
<tr class="even">
<td><p>針對每個應用程式的最大訂閱數</p></td>
<td><p>每個應用程式允許的訂閱要求數目上限</p></td>
</tr>
<tr class="odd">
<td><p>針對每個批次的最大訂閱數</p></td>
<td><p>每個批次允許的訂閱要求數目上限</p></td>
</tr>
<tr class="even">
<td><p>目前狀態訂閱失敗</p></td>
<td><p>訂閱目前狀態失敗的次數</p></td>
</tr>
<tr class="odd">
<td><p>註冊端點失敗</p></td>
<td><p>要註冊端點的失敗次數</p></td>
</tr>
<tr class="even">
<td><p>收到的要求/秒</p></td>
<td><p>每秒收到要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>成功的要求/秒</p></td>
<td><p>每秒成功要求的速度（HTTP 2xx/3xx 回應碼）</p></td>
</tr>
<tr class="even">
<td><p>已成功建立應用程式要求/秒</p></td>
<td><p>成功應用程式建立要求的每秒匯率</p></td>
</tr>
<tr class="odd">
<td><p>已超時擱置中的 [取得計數]</p></td>
<td><p>超時的未決取得數</p></td>
</tr>
<tr class="even">
<td><p>收到的應用程式建立要求總計</p></td>
<td><p>在服務啟動後收到的應用程式建立要求總數量</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 回應總數</p></td>
<td><p>HTTP 4xx 回應總數目</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 回應總數</p></td>
<td><p>HTTP 5xx 回應總次數</p></td>
</tr>
<tr class="odd">
<td><p>在命令通道上接收到的總請求數</p></td>
<td><p>在命令通道上接收到的總請求數</p></td>
</tr>
<tr class="even">
<td><p>成功總請求數</p></td>
<td><p>成功的要求總數量</p></td>
</tr>
<tr class="odd">
<td><p>啟動的會話總數</p></td>
<td><p>啟動服務之後所啟動的會話總數</p></td>
</tr>
<tr class="even">
<td><p>因空閒超時而終止的總會話數</p></td>
<td><p>因使用者空閒超時而終止的會話總數</p></td>
</tr>
<tr class="odd">
<td><p>已限制的應用程式總計</p></td>
<td><p>受限制的應用程式數目</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx 行動服務的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>反</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>會話的平均存留期（以毫秒為單位）</p></td>
<td><p>會話的平均存留期（以毫秒為單位）</p></td>
</tr>
<tr class="even">
<td><p>目前的推播通知訂閱</p></td>
<td><p>推播通知訂閱的目前數目。 這個數位與目前的活動會話計數，代表已針對 Windows Mobile 或 iPhone 裝置註冊的目前活動會話子集。</p></td>
</tr>
<tr class="odd">
<td><p>目前使用中的網路超時輪詢計數</p></td>
<td><p>超時的網路輪詢數</p></td>
</tr>
<tr class="even">
<td><p>目前使用中的輪詢計數</p></td>
<td><p>目前使用中的輪詢數（與伺服器的長時間連接）</p></td>
</tr>
<tr class="odd">
<td><p>目前的活動會話計數</p></td>
<td><p>行動服務中的目前已註冊端點數目</p></td>
</tr>
<tr class="even">
<td><p>目前處於作用中狀態訂閱的目前活動會話計數</p></td>
<td><p>目前處於作用中狀態訂閱的目前活動會話數</p></td>
</tr>
<tr class="odd">
<td><p>失敗/秒的推播通知要求</p></td>
<td><p>每秒失敗推播通知的速率</p></td>
</tr>
<tr class="even">
<td><p>成功/秒的推播通知要求</p></td>
<td><p>每秒成功推播通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>每秒限制的推播通知要求</p></td>
<td><p>每秒限制推播通知的速率</p></td>
</tr>
<tr class="even">
<td><p>推播通知要求/秒</p></td>
<td><p>每秒傳送推播通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>失敗/秒的要求</p></td>
<td><p>每秒失敗要求的速率</p></td>
</tr>
<tr class="even">
<td><p>收到的要求/秒</p></td>
<td><p>每秒收到要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>拒絕的要求/秒</p></td>
<td><p>拒絕的要求每秒的工資率</p></td>
</tr>
<tr class="even">
<td><p>成功的要求/秒</p></td>
<td><p>成功要求的每秒匯率</p></td>
</tr>
<tr class="odd">
<td><p>已成功啟動會話要求/秒</p></td>
<td><p>成功取得位置要求的每秒利率。 啟動會話的要求會佔用伺服器上的大多數 CPU。 支援的負載峰值為 12/秒。 可持續性是由伺服器上的其他負載所決定。 啟動會話通常代表已登入長時間時段之使用者的登入。</p></td>
</tr>
<tr class="even">
<td><p>已拒絕的撥入語音通話總數</p></td>
<td><p>已拒絕的輸入通話總次數</p></td>
</tr>
<tr class="odd">
<td><p>失敗的入站語音通話總數</p></td>
<td><p>失敗的入站語音通話總數</p></td>
</tr>
<tr class="even">
<td><p>失敗的傳出語音通話總計</p></td>
<td><p>失敗的出站語音通話總數</p></td>
</tr>
<tr class="odd">
<td><p>使用者終止的會話總數</p></td>
<td><p>使用者終止的會話總數</p></td>
</tr>
<tr class="even">
<td><p>推播通知要求總數</p></td>
<td><p>推播通知要求的總數量</p></td>
</tr>
<tr class="odd">
<td><p>[推播通知] 要求總失敗</p></td>
<td><p>失敗的推播通知請求總數</p></td>
</tr>
<tr class="even">
<td><p>成功的推播通知請求總數</p></td>
<td><p>成功的推播通知請求總數</p></td>
</tr>
<tr class="odd">
<td><p>限制的推播通知總要求</p></td>
<td><p>已中止的推播通知請求總數</p></td>
</tr>
<tr class="even">
<td><p>失敗的總請求數</p></td>
<td><p>失敗的總請求數</p></td>
</tr>
<tr class="odd">
<td><p>在命令通道上接收到的總請求數</p></td>
<td><p>在命令通道上接收到的總請求數</p></td>
</tr>
<tr class="even">
<td><p>拒絕的總請求數</p></td>
<td><p>拒絕的要求總數</p></td>
</tr>
<tr class="odd">
<td><p>成功總請求數</p></td>
<td><p>已成功完成行動服務的總請求數</p></td>
</tr>
<tr class="even">
<td><p>會話啟動總計數</p></td>
<td><p>行動服務啟動後啟動的會話總數</p></td>
</tr>
<tr class="odd">
<td><p>因使用者空閒超時而終止的會話總數</p></td>
<td><p>因使用者空閒超時而終止的會話總數</p></td>
</tr>
<tr class="even">
<td><p>成功輸入語音通話總計</p></td>
<td><p>成功的輸入通話總次數</p></td>
</tr>
<tr class="odd">
<td><p>成功的傳出語音通話總數</p></td>
<td><p>成功的出站通話總次數</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

