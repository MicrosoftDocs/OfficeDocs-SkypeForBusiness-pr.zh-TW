---
title: Lync Server 2013： 行動效能計數器
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
ms.openlocfilehash: 56454e4ea4fa1498dc73056d5b5f01193b007352
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013 中的行動效能計數器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

下表列出的名稱和描述的效能計數器可監視執行 Unified Communications Web API (UCWA) 及 Lync Server 2013 Mcx Mobility Service 的伺服器。

UCWA 表格中的計數器的類別名稱是**LS:WEB – ucwa 的參考**。

Mcx Mobility Service 表格中的計數器的類別名稱是**LS:WEB-行動通訊服務**。

<div>

## <a name="performance-counters-for-ucwa"></a>UCWA 的效能計數器


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>計數器</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>作用中的應用程式計數</p></td>
<td><p>目前的應用程式數目</p></td>
</tr>
<tr class="even">
<td><p>使用中應用程式共用形式計數</p></td>
<td><p>目前應用程式共用形式的數目</p></td>
</tr>
<tr class="odd">
<td><p>主動音訊形式計數</p></td>
<td><p>目前音訊形式的數目</p></td>
</tr>
<tr class="even">
<td><p>作用中資料共同作業形式計數</p></td>
<td><p>目前的資料共同作業形式數目</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 相片取得延遲 （毫秒）</p></td>
<td><p>此計數器會顯示平均時間 （以毫秒為單位） 來擷取將相片從 active directory</p></td>
</tr>
<tr class="even">
<td><p>作用中郵件的形式計數</p></td>
<td><p>目前的通訊形式數目</p></td>
</tr>
<tr class="odd">
<td><p>作用中的全景視訊形式計數</p></td>
<td><p>目前的全景視訊形式數目</p></td>
</tr>
<tr class="even">
<td><p>使用中擱置 Get 計數</p></td>
<td><p>擱置取得; 目前作用中的數字長期保留的伺服器連線</p></td>
</tr>
<tr class="odd">
<td><p>Active Session Count</p></td>
<td><p>目前的每個應用程式及總計 UCWA 中註冊的端點數目</p></td>
</tr>
<tr class="even">
<td><p>作用中使用者執行個體計數</p></td>
<td><p>目前的使用者執行個體數</p></td>
</tr>
<tr class="odd">
<td><p>作用中使用者沒有應用程式的執行個體</p></td>
<td><p>目前的使用者沒有應用程式的執行個體數</p></td>
</tr>
<tr class="even">
<td><p>主動影片形式計數</p></td>
<td><p>目前的影片形式數目</p></td>
</tr>
<tr class="odd">
<td><p>應用程式建立要求接收/秒</p></td>
<td><p>每秒接收應用程式建立要求的速率</p></td>
</tr>
<tr class="even">
<td><p>為 MCU 加入失敗</p></td>
<td><p>AS MCU 加入失敗的次數</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 加入失敗</p></td>
<td><p>AV MCU 加入失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>平均應用程式啟動時間 （毫秒）</p></td>
<td><p>平均應用程式啟動時間 （毫秒）</p></td>
</tr>
<tr class="odd">
<td><p>平均存留期 （毫秒） 的工作階段</p></td>
<td><p>以毫秒為單位的工作階段平均存留期</p></td>
</tr>
<tr class="even">
<td><p>資料 MCU 加入失敗</p></td>
<td><p>資料 MCU 加入失敗的次數</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 連絡人搜尋延遲 （毫秒）</p></td>
<td><p>此計數器會顯示平均時間 （以毫秒為單位） 若要在 Exchange 中搜尋連絡人</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 相片 Get 延遲 （毫秒）</p></td>
<td><p>此計數器會顯示平均時間 （以毫秒為單位） 從 Exchange 擷取相片</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 回應/秒</p></td>
<td><p>每秒的 HTTP 4xx 碼回應的速率</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 回應/秒</p></td>
<td><p>每秒的 HTTP 5xx 碼回應的速率</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU 加入失敗</p></td>
<td><p>IM MCU 加入失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 相片取得失敗的次數</p></td>
<td><p>若要從 Active Directory 擷取相片的失敗總數</p></td>
</tr>
<tr class="odd">
<td><p>連絡人搜尋失敗的次數</p></td>
<td><p>若要在 Exchange 中搜尋連絡人的失敗總數</p></td>
</tr>
<tr class="even">
<td><p>還原序列化失敗的次數</p></td>
<td><p>還原序列化失敗總數</p></td>
</tr>
<tr class="odd">
<td><p>HD 相片取得失敗的次數</p></td>
<td><p>若要從 Exchange 擷取 HD 相片的失敗總數</p></td>
</tr>
<tr class="even">
<td><p>對每個應用程式的最大訂閱</p></td>
<td><p>訂閱要求，透過允許每個應用程式的最大數目</p></td>
</tr>
<tr class="odd">
<td><p>對每個批次的最大訂閱</p></td>
<td><p>透過最大允許每個批次訂閱要求數目</p></td>
</tr>
<tr class="even">
<td><p>目前狀態訂閱失敗</p></td>
<td><p>若要訂閱目前狀態的次數</p></td>
</tr>
<tr class="odd">
<td><p>註冊的端點失敗</p></td>
<td><p>若要註冊端點失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>要求接收/秒</p></td>
<td><p>每秒接收要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>要求成功/秒</p></td>
<td><p>每秒成功的要求 （HTTP 2xx/3xx 回應碼） 的速率</p></td>
</tr>
<tr class="even">
<td><p>成功建立應用程式要求數/秒</p></td>
<td><p>每秒成功的應用程式建立要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>暫止的 Get 計數逾時</p></td>
<td><p>等候逾時取得的數目</p></td>
</tr>
<tr class="even">
<td><p>接收到的總應用程式建立要求</p></td>
<td><p>自從服務啟動以來所收到的應用程式建立要求總數</p></td>
</tr>
<tr class="odd">
<td><p>總 HTTP 4xx 回應</p></td>
<td><p>HTTP 4xx 回應總數</p></td>
</tr>
<tr class="even">
<td><p>總 HTTP 5xx 回應</p></td>
<td><p>HTTP 5xx 回應總數</p></td>
</tr>
<tr class="odd">
<td><p>命令通道上接收的要求總數</p></td>
<td><p>命令通道上接收的要求總數</p></td>
</tr>
<tr class="even">
<td><p>成功的要求總數</p></td>
<td><p>成功的要求總數</p></td>
</tr>
<tr class="odd">
<td><p>起始的工作階段總數</p></td>
<td><p>自服務啟動後已起始的工作階段總數</p></td>
</tr>
<tr class="even">
<td><p>因為閒置逾時終止的工作階段總數</p></td>
<td><p>由於使用者閒置逾時而終止的工作階段總數</p></td>
</tr>
<tr class="odd">
<td><p>總節流應用程式</p></td>
<td><p>節流應用程式數目</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx Mobility Service 的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>計數器</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>以毫秒為單位的工作階段的平均存留期</p></td>
<td><p>以毫秒為單位的工作階段平均存留期</p></td>
</tr>
<tr class="even">
<td><p>目前的推播通知訂閱</p></td>
<td><p>目前的推播通知訂閱數目。 此數字，搭配使用 Currently Active Session Count，代表目前使用中的工作階段並登錄 Windows Mobile 或 iPhone 裝置的子集。</p></td>
</tr>
<tr class="odd">
<td><p>目前使用中網路逾時投票計數</p></td>
<td><p>逾時的網路輪詢數目</p></td>
</tr>
<tr class="even">
<td><p>目前作用中投票計數</p></td>
<td><p>目前使用中的輪詢 （長期保留的伺服器連線） 的數目</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Session Count</p></td>
<td><p>目前在 Mobility Service 中註冊的端點數目</p></td>
</tr>
<tr class="even">
<td><p>目前 Active Session Count with Active 目前狀態訂閱</p></td>
<td><p>目前使用中的工作階段與作用中的目前狀態訂閱數目</p></td>
</tr>
<tr class="odd">
<td><p>失敗的推入通知要求數/秒</p></td>
<td><p>每秒的失敗的推入通知速率</p></td>
</tr>
<tr class="even">
<td><p>成功的推入通知要求數/秒</p></td>
<td><p>每秒成功的推入通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>推入通知要求節流/秒</p></td>
<td><p>每秒的節流的推入通知速率</p></td>
</tr>
<tr class="even">
<td><p>推入通知要求數/秒</p></td>
<td><p>每秒傳送推入通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>要求失敗/秒</p></td>
<td><p>每秒的失敗的要求速率</p></td>
</tr>
<tr class="even">
<td><p>要求接收/秒</p></td>
<td><p>每秒接收要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>要求拒絕/秒</p></td>
<td><p>每秒拒絕要求的速率</p></td>
</tr>
<tr class="even">
<td><p>要求成功/秒</p></td>
<td><p>每秒成功的要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>已成功啟動工作階段要求數/秒</p></td>
<td><p>每秒成功取得位置的速率要求。 若要啟動工作階段要求消耗最多的 cpu 資源，在伺服器上。 支援的尖峰負載是 12/秒。 永續取決於伺服器上的其他負載。 起始工作階段通常表示登入已擴充的一段時間登出使用者。</p></td>
</tr>
<tr class="even">
<td><p>總拒絕撥入的語音通話</p></td>
<td><p>拒絕的撥入的語音通話的總數</p></td>
</tr>
<tr class="odd">
<td><p>失敗的撥入的語音通話總計</p></td>
<td><p>失敗的撥入的語音通話總數</p></td>
</tr>
<tr class="even">
<td><p>總失敗的撥出語音通話</p></td>
<td><p>失敗的撥出語音通話總數</p></td>
</tr>
<tr class="odd">
<td><p>由使用者終止的工作階段總數</p></td>
<td><p>使用者終止的工作階段總數</p></td>
</tr>
<tr class="even">
<td><p>總數的推入通知要求</p></td>
<td><p>推入通知要求總數</p></td>
</tr>
<tr class="odd">
<td><p>總數的推入通知要求失敗</p></td>
<td><p>失敗的推入通知要求總數</p></td>
</tr>
<tr class="even">
<td><p>成功的總數的推入通知要求</p></td>
<td><p>成功的推入通知要求總數</p></td>
</tr>
<tr class="odd">
<td><p>總數的推入通知要求節流</p></td>
<td><p>流速的推入通知要求總數</p></td>
</tr>
<tr class="even">
<td><p>失敗的要求總數</p></td>
<td><p>失敗的要求總數</p></td>
</tr>
<tr class="odd">
<td><p>命令通道上接收的要求總數</p></td>
<td><p>命令通道上接收的要求總數</p></td>
</tr>
<tr class="even">
<td><p>拒絕的要求總數</p></td>
<td><p>拒絕的要求總數</p></td>
</tr>
<tr class="odd">
<td><p>成功的要求總數</p></td>
<td><p>對 Mobility Service 成功的要求總數</p></td>
</tr>
<tr class="even">
<td><p>工作階段總計起始計數</p></td>
<td><p>啟動 Mobility Service 後已起始的工作階段總數</p></td>
</tr>
<tr class="odd">
<td><p>由於使用者閒置逾終止的工作階段總數</p></td>
<td><p>由於使用者閒置逾時而終止的工作階段總數</p></td>
</tr>
<tr class="even">
<td><p>總成功的撥入的語音通話</p></td>
<td><p>撥入的語音通話的成功總數</p></td>
</tr>
<tr class="odd">
<td><p>總成功的撥出語音通話</p></td>
<td><p>撥出語音通話的成功總數</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

