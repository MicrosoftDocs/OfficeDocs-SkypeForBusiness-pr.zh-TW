---
title: Lync Server 2013： UCWA 事件
description: Lync Server 2013： UCWA 事件。
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
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548849"
---
# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013 中的 UCWA 事件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 使用整合通訊 Web API (UCWA) 出於許多目的，從存取 Microsoft Exchange 以進行連絡人搜尋，以更新行動用戶端的狀態。

UCWA 會將操作行為記錄撰寫成事件種類的資訊、警告和錯誤。 下表說明 UCWA 元件可寫入的事件。


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
<td><p>資訊</p></td>
<td><p>UCWA 初始化</p></td>
<td><p>不適用</p>
<p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>錯誤</p></td>
<td><p>UCWA 在初始化期間遇到意外的例外狀況</p></td>
<td><p>初始化時發生未預期的錯誤</p>
<p>檢查相關事件記錄檔專案中的例外狀況詳細資料，以判斷可能的原因</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>錯誤</p></td>
<td><p>UCWA 發生未處理的例外狀況</p></td>
<td><p>發生未處理的例外狀況</p>
<p>重新啟動伺服器。 如果問題仍然存在，請與產品支援人員聯繫</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>錯誤</p></td>
<td><p>無法存取 HD 相片的 Exchange</p></td>
<td><p>無法使用 Exchange 連線</p>
<p>確定可使用 Exchange 連線</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>資訊</p></td>
<td><p>從無法存取 HD 相片的 Exchange 復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>錯誤</p></td>
<td><p>無法存取連絡人搜尋的 Exchange</p></td>
<td><p>無法使用 Exchange 連線</p>
<p>確定可使用 Exchange 連線</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>資訊</p></td>
<td><p>從 Exchange 中的搜尋連絡人復原失敗</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</p></td>
<td><p>嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</p>
<p>檢查用戶端是否有不必要的訂閱</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>嘗試訂閱每批次允許的目前狀態訂閱</p></td>
<td><p>嘗試訂閱每批次允許的目前狀態訂閱</p>
<p>檢查用戶端是否有不必要的訂閱</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>錯誤</p></td>
<td><p>無法取得 inband 資料</p></td>
<td><p>無法取得 inband 資料</p>
<p>如果問題仍然存在，請與產品支援人員聯繫</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>錯誤</p></td>
<td><p>無法訂閱目前狀態</p></td>
<td><p>無法訂閱目前狀態</p>
<p>如果問題仍然存在，請與產品支援人員聯繫</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>錯誤</p></td>
<td><p>無法註冊端點</p></td>
<td><p>無法註冊端點</p>
<p>如果問題仍然存在，請與產品支援人員聯繫</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>錯誤</p></td>
<td><p>IM MCU 無法使用</p></td>
<td><p>IM MCU 無法使用</p>
<p>查看 IM MCU 是否正在執行中</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>資訊</p></td>
<td><p>從無法連線至 IM MCU 的失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>錯誤</p></td>
<td><p>無法使用 AV MCU</p></td>
<td><p>無法使用 AV MCU</p>
<p>查看 AV MCU 是否正在執行中</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>資訊</p></td>
<td><p>從無法連線至 AV MCU 的失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>錯誤</p></td>
<td><p>無法使用 MCU</p></td>
<td><p>無法使用 MCU</p>
<p>查看是否正在執行 MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>資訊</p></td>
<td><p>從無法以 MCU 形式連線的方式復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>錯誤</p></td>
<td><p>資料 MCU 無法使用</p></td>
<td><p>資料 MCU 無法使用</p>
<p>查看資料 MCU 是否正在執行中</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>資訊</p></td>
<td><p>從無法連線至資料 MCU 的失敗復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>錯誤</p></td>
<td><p>無法加入 IM MCU</p></td>
<td><p>無法加入 IM MCU</p>
<p>查看 IM MCU 是否正在執行中</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>錯誤</p></td>
<td><p>無法加入 AV MCU</p></td>
<td><p>無法加入 AV MCU</p>
<p>查看 AV MCU 是否正在執行中</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>錯誤</p></td>
<td><p>無法以 MCU 形式加入</p></td>
<td><p>無法以 MCU 形式加入</p>
<p>查看是否正在執行 MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>錯誤</p></td>
<td><p>無法加入資料 MCU</p></td>
<td><p>無法加入資料 MCU</p>
<p>查看資料 MCU 是否正在執行中</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>錯誤</p></td>
<td><p>無法存取相片的 active directory</p></td>
<td><p>無法使用 active directory 的連線</p>
<p>確定可以使用 active directory 的連線</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>資訊</p></td>
<td><p>從無法存取相片的 active directory 復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>無法反序列化</p></td>
<td><p>無法反序列化</p>
<p>如果問題仍然存在，請與產品支援人員聯繫</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

