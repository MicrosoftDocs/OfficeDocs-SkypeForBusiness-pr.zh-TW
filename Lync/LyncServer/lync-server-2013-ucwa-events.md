---
title: 'Lync Server 2013: UCWA 事件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013 中的 UCWA 事件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 使用數量的目的，以用於行動用戶端更新目前狀態的連絡人搜尋存取 Microsoft Exchange Unified Communications Web API (UCWA)。

UCWA 將提示資訊、 警告及錯誤的事件類型為寫入作業行為的記錄。 下表說明可以由 UCWA 元件所撰寫的事件。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>事件識別碼</th>
<th>事件類型</th>
<th>摘要</th>
<th>原因和解決方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>資訊性</p></td>
<td><p>UCWA 初始化</p></td>
<td><p>不適用</p>
<p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA 發生未預期的例外狀況初始化期間</p></td>
<td><p>初始化期間發生未預期的錯誤</p>
<p>檢查至判斷可能的原因的相關聯的事件日誌項目中的例外狀況詳細資料</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA 發生未處理的例外狀況</p></td>
<td><p>未處理的例外狀況</p>
<p>重新啟動伺服器。 如果問題仍然存在連絡產品支援服務</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>無法存取 Exchange 的 HD 相片</p></td>
<td><p>連線至 Exchange 不提供</p>
<p>請確定沒有可用的連線至 Exchange</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>資訊性</p></td>
<td><p>從失敗的 HD 相片存取 Exchange 復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>無法存取 Exchange 連絡人搜尋</p></td>
<td><p>連線至 Exchange 不提供</p>
<p>請確定沒有可用的連線至 Exchange</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>資訊性</p></td>
<td><p>復原從 Exchange 中搜尋連絡人失敗</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>嘗試將超過每個應用程式的允許的目前狀態訂閱訂閱</p></td>
<td><p>嘗試將超過每個應用程式的允許的目前狀態訂閱訂閱</p>
<p>檢查不必要的訂用帳戶的用戶端</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>嘗試將超過允許的目前狀態訂閱，每個批次訂閱</p></td>
<td><p>嘗試將超過允許的目前狀態訂閱，每個批次訂閱</p>
<p>檢查不必要的訂用帳戶的用戶端</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>無法擷取 inband 資料</p></td>
<td><p>無法擷取 inband 資料</p>
<p>如果問題仍然存在連絡產品支援服務</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>無法訂閱目前狀態</p></td>
<td><p>無法訂閱目前狀態</p>
<p>如果問題仍然存在連絡產品支援服務</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>無法註冊端點</p></td>
<td><p>無法註冊端點</p>
<p>如果問題仍然存在連絡產品支援服務</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>IM MCU 是無法使用</p></td>
<td><p>IM MCU 是無法使用</p>
<p>請參閱 IM MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>資訊性</p></td>
<td><p>從連線至 IM MCU 失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>AV MCU 是無法使用</p></td>
<td><p>AV MCU 是無法使用</p>
<p>請參閱 AV MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>資訊性</p></td>
<td><p>從連線至 AV MCU 失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>無法使用此 MCU 為</p></td>
<td><p>無法使用此 MCU 為</p>
<p>請參閱 AS MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>資訊性</p></td>
<td><p>從連線至 AS MCU 失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>資料 MCU 是無法使用</p></td>
<td><p>資料 MCU 是無法使用</p>
<p>請參閱資料 MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>資訊性</p></td>
<td><p>從連線至資料 MCU 失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>無法加入 IM MCU</p></td>
<td><p>無法加入 IM MCU</p>
<p>請參閱 IM MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>無法加入 AV MCU</p></td>
<td><p>無法加入 AV MCU</p>
<p>請參閱 AV MCU 是否正在執行</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>無法加入 AS MCU</p></td>
<td><p>無法加入 AS MCU</p>
<p>請參閱 AS MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>無法加入資料 MCU</p></td>
<td><p>無法加入資料 MCU</p>
<p>請參閱資料 MCU 是否正在執行</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>無法存取 active directory 中的相片</p></td>
<td><p>Active directory 連線不提供</p>
<p>請確定沒有可用的 active directory 連線</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>資訊性</p></td>
<td><p>復原從失敗的存取 active directory 中的相片</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>無法還原序列化的 labs.core.ilabobject</p></td>
<td><p>無法還原序列化的 labs.core.ilabobject</p>
<p>如果問題仍然存在連絡產品支援服務</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

