---
title: Lync Server 2013：行動效能計數器
description: Lync Server 2013：行動效能計數器。
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
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550529"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013 中的行動效能計數器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊網頁 API (UCWA) 和 Lync Server 2013 Mcx 行動性服務的伺服器。

UCWA 資料表中的計數器類別名稱是 **LS： WEB – UCWA**。

Mcx 行動性服務表格中的計數器類別名稱是 **LS： WEB Mobile Communication service**。

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
<td><p>使用中應用程式計數</p></td>
<td><p>目前的應用程式數目</p></td>
</tr>
<tr class="even">
<td><p>使用中應用程式共用的形式計數</p></td>
<td><p>目前的應用程式共用形式數目</p></td>
</tr>
<tr class="odd">
<td><p>使用中音訊的模態計數</p></td>
<td><p>目前的音訊模態數目</p></td>
</tr>
<tr class="even">
<td><p>主動資料共同作業模式計數</p></td>
<td><p>目前的資料共同作業數目</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 照片取得延遲 (毫秒) </p></td>
<td><p>此計數器會顯示從 active directory 中取得相片的平均 (（毫秒）) </p></td>
</tr>
<tr class="even">
<td><p>使用中的郵件模式計數</p></td>
<td><p>目前的郵件模態模式數目</p></td>
</tr>
<tr class="odd">
<td><p>使用中全景影片的模式計數</p></td>
<td><p>目前的全景影片形式數目</p></td>
</tr>
<tr class="even">
<td><p>作用中擱置的取得計數</p></td>
<td><p>目前使用中擱置的取得數目;保留伺服器的長時間連接</p></td>
</tr>
<tr class="odd">
<td><p>主動會話計數</p></td>
<td><p>UCWA 中每個應用程式和總數所註冊的端點數目</p></td>
</tr>
<tr class="even">
<td><p>作用中使用者實例計數</p></td>
<td><p>目前的使用者實例數目</p></td>
</tr>
<tr class="odd">
<td><p>不含應用程式的作用中使用者實例</p></td>
<td><p>目前沒有 application 的使用者實例數目</p></td>
</tr>
<tr class="even">
<td><p>使用中影片的模態計數</p></td>
<td><p>目前影片的模態數目</p></td>
</tr>
<tr class="odd">
<td><p>每秒收到的應用程式建立要求</p></td>
<td><p>每秒收到應用程式建立要求的速率</p></td>
</tr>
<tr class="even">
<td><p>作為 MCU 加入失敗</p></td>
<td><p>作為 MCU 加入失敗的數目</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 加入失敗</p></td>
<td><p>AV MCU 加入失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>平均應用程式啟動時間 (毫秒) </p></td>
<td><p>應用程式的平均啟動時間（毫秒）</p></td>
</tr>
<tr class="odd">
<td><p>會話的平均壽命 (毫秒) </p></td>
<td><p>會話的平均生命週期（毫秒）</p></td>
</tr>
<tr class="even">
<td><p>資料 MCU 加入失敗</p></td>
<td><p>資料 MCU 加入失敗次數</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 連絡人搜尋延遲 (毫秒) </p></td>
<td><p>此計數器會顯示在 Exchange 中搜尋連絡人的平均 (毫秒) </p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 相片取得延遲 (毫秒) </p></td>
<td><p>此計數器會顯示從 Exchange 取得相片的平均 (（毫秒）) </p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 回應數/秒</p></td>
<td><p>每秒以 HTTP 4xx 代碼回應的速率</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 回應數/秒</p></td>
<td><p>每秒以 HTTP 5xx 代碼回應的速率</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU 聯接失敗</p></td>
<td><p>IM MCU 加入失敗的次數</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 照片取得失敗的數目</p></td>
<td><p>從 Active Directory 中取得相片的失敗總數</p></td>
</tr>
<tr class="odd">
<td><p>連絡人搜尋失敗次數</p></td>
<td><p>在 Exchange 中搜尋連絡人的失敗總數</p></td>
</tr>
<tr class="even">
<td><p>反序列化失敗次數</p></td>
<td><p>反序列化失敗總數</p></td>
</tr>
<tr class="odd">
<td><p>HD 相片 Get 失敗次數</p></td>
<td><p>從 Exchange 取得 HD 相片的失敗總次數</p></td>
</tr>
<tr class="even">
<td><p>每個應用程式的最大訂閱數</p></td>
<td><p>每個應用程式允許的最大訂閱要求數目</p></td>
</tr>
<tr class="odd">
<td><p>每個批次的最大訂閱數</p></td>
<td><p>每個批次允許的訂閱要求數目上限</p></td>
</tr>
<tr class="even">
<td><p>目前狀態訂閱失敗</p></td>
<td><p>訂閱目前狀態失敗的次數</p></td>
</tr>
<tr class="odd">
<td><p>註冊端點失敗</p></td>
<td><p>註冊端點的失敗次數</p></td>
</tr>
<tr class="even">
<td><p>接收的要求數/秒</p></td>
<td><p>每秒收到要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>每秒成功的要求</p></td>
<td><p>每秒成功要求 (HTTP 2xx/3xx 回應碼的速率) </p></td>
</tr>
<tr class="even">
<td><p>成功建立應用程式 Requests/Second</p></td>
<td><p>每秒成功的應用程式建立要求速率</p></td>
</tr>
<tr class="odd">
<td><p>超時等候中的取得計數</p></td>
<td><p>超時的擱置取得數目</p></td>
</tr>
<tr class="even">
<td><p>已接收的應用程式建立要求總數</p></td>
<td><p>啟動服務後收到的應用程式建立要求總數</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 回應總數</p></td>
<td><p>HTTP 4xx 回應總數</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 回應總數</p></td>
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
<td><p>起始的會話總數</p></td>
<td><p>啟動服務後所初始化的會話總數</p></td>
</tr>
<tr class="even">
<td><p>因空閒超時而終止的會話總數</p></td>
<td><p>因使用者空閒超時而終止的會話總數</p></td>
</tr>
<tr class="odd">
<td><p>限制的應用程式總數</p></td>
<td><p>節流應用程式的數目</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx 行動性服務的效能計數器

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
<td><p>會話的平均生命週期（毫秒）</p></td>
<td><p>會話的平均生命週期（毫秒）</p></td>
</tr>
<tr class="even">
<td><p>目前的推播通知訂閱</p></td>
<td><p>推播通知訂閱的目前數目。 這個數目會與目前作用中的會話計數搭配使用，代表為 Windows Mobile 或 iPhone 裝置註冊的目前作用中會話的子集。</p></td>
</tr>
<tr class="odd">
<td><p>目前使用中的網路超時輪詢計數</p></td>
<td><p>超時的網路輪詢數目</p></td>
</tr>
<tr class="even">
<td><p>目前使用中的輪詢計數</p></td>
<td><p>目前使用中輪詢的數目 (長期保留與伺服器的連線) </p></td>
</tr>
<tr class="odd">
<td><p>目前使用中的會話計數</p></td>
<td><p>目前在行動服務中註冊的端點數目</p></td>
</tr>
<tr class="even">
<td><p>目前使用中的會話計數與使用中狀態訂閱</p></td>
<td><p>目前使用中狀態訂閱的目前活動會話數目</p></td>
</tr>
<tr class="odd">
<td><p>推播通知要求失敗/秒</p></td>
<td><p>每秒失敗推播通知的速率</p></td>
</tr>
<tr class="even">
<td><p>每秒成功的推入通知要求</p></td>
<td><p>每秒成功推播通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>限制的推播通知要求數/秒</p></td>
<td><p>每秒節流推播通知的速率</p></td>
</tr>
<tr class="even">
<td><p>推播通知 Requests/Second</p></td>
<td><p>每秒傳送推播通知的速率</p></td>
</tr>
<tr class="odd">
<td><p>每秒失敗的要求</p></td>
<td><p>每秒失敗要求的速率</p></td>
</tr>
<tr class="even">
<td><p>接收的要求數/秒</p></td>
<td><p>每秒收到要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>拒絕的要求數/秒</p></td>
<td><p>每秒拒絕要求的速率</p></td>
</tr>
<tr class="even">
<td><p>每秒成功的要求</p></td>
<td><p>每秒成功要求的速率</p></td>
</tr>
<tr class="odd">
<td><p>已成功啟動會話 Requests/Second</p></td>
<td><p>每秒成功取得位置要求的速率。 啟動會話的要求會消耗伺服器上的大部分 CPU。 支援的負載峰值為 12/秒。 可持續性取決於伺服器上的其他負載。 [啟動會話] 通常表示登入的使用者已長時間簽入的使用者。</p></td>
</tr>
<tr class="even">
<td><p>拒絕的撥入語音通話總數</p></td>
<td><p>已謝絕的撥入語音通話總數</p></td>
</tr>
<tr class="odd">
<td><p>失敗的撥入語音通話總數</p></td>
<td><p>失敗的撥入語音通話總數</p></td>
</tr>
<tr class="even">
<td><p>失敗的撥出語音通話總數</p></td>
<td><p>失敗的撥出語音通話總數</p></td>
</tr>
<tr class="odd">
<td><p>使用者終止的會話總數</p></td>
<td><p>使用者終止的會話總數</p></td>
</tr>
<tr class="even">
<td><p>推播通知要求總數</p></td>
<td><p>推播通知要求總數</p></td>
</tr>
<tr class="odd">
<td><p>推播通知要求總數失敗</p></td>
<td><p>失敗的推入通知要求總數</p></td>
</tr>
<tr class="even">
<td><p>已成功的推播通知要求總數</p></td>
<td><p>成功的推播通知要求總數</p></td>
</tr>
<tr class="odd">
<td><p>限制的推播通知要求總數</p></td>
<td><p>已節流之推播通知要求的總數</p></td>
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
<td><p>已成功完成行動服務的總要求數</p></td>
</tr>
<tr class="even">
<td><p>會話起始計數總數</p></td>
<td><p>啟動行動服務後所啟動的會話總數</p></td>
</tr>
<tr class="odd">
<td><p>因使用者空閒超時而終止的會話總數</p></td>
<td><p>因使用者空閒超時而終止的會話總數</p></td>
</tr>
<tr class="even">
<td><p>成功輸入語音通話總數</p></td>
<td><p>輸入語音通話的成功總數</p></td>
</tr>
<tr class="odd">
<td><p>成功的撥出語音通話總數</p></td>
<td><p>已成功撥出語音通話的總數</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

