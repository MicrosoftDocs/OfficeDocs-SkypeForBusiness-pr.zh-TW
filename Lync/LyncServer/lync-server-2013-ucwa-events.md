---
title: Lync Server 2013： UCWA 事件
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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>在 Lync Server 2013 中 UCWA 事件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 使用整合通訊 Web API （UCWA）來實現多種用途，從存取 Microsoft Exchange 進行連絡人搜尋，以更新行動用戶端的目前狀態。

UCWA 會將操作行為的記錄寫入為事件種類的資訊、警告和錯誤。 下表說明可由 UCWA 元件所撰寫的事件。


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
<th>事件種類</th>
<th>總結</th>
<th>原因與解決方式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>參考</p></td>
<td><p>UCWA 初始化</p></td>
<td><p>不適用</p>
<p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>出錯</p></td>
<td><p>UCWA 在初始化期間遇到意外的例外狀況</p></td>
<td><p>初始化時發生意外的錯誤</p>
<p>檢查相關聯的事件記錄條目中的例外詳細資料，以判斷可能的原因</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>出錯</p></td>
<td><p>UCWA 遇到未處理的例外狀況</p></td>
<td><p>發生未處理的例外狀況</p>
<p>重新開機伺服器。 如果問題持續發生，請與產品支援人員聯繫</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>出錯</p></td>
<td><p>無法存取 HD 相片的 Exchange</p></td>
<td><p>無法連線到 Exchange</p>
<p>確認已提供與 Exchange 的連線</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>參考</p></td>
<td><p>已從無法存取 HD 相片的 Exchange 復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>出錯</p></td>
<td><p>無法存取連絡人搜尋的 Exchange</p></td>
<td><p>無法連線到 Exchange</p>
<p>確認已提供與 Exchange 的連線</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>參考</p></td>
<td><p>已從 Exchange 中的搜尋連絡人復原失敗</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>嘗試訂閱超過每個應用程式允許的目前狀態訂閱</p></td>
<td><p>嘗試訂閱超過每個應用程式允許的目前狀態訂閱</p>
<p>檢查用戶端是否有不必要的訂閱</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>每批次嘗試訂閱超過允許的目前狀態訂閱</p></td>
<td><p>每批次嘗試訂閱超過允許的目前狀態訂閱</p>
<p>檢查用戶端是否有不必要的訂閱</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>出錯</p></td>
<td><p>無法檢索 inband 資料</p></td>
<td><p>無法檢索 inband 資料</p>
<p>如果問題持續發生，請與產品支援人員聯繫</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>出錯</p></td>
<td><p>無法訂閱目前狀態</p></td>
<td><p>無法訂閱目前狀態</p>
<p>如果問題持續發生，請與產品支援人員聯繫</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>出錯</p></td>
<td><p>無法註冊端點</p></td>
<td><p>無法註冊端點</p>
<p>如果問題持續發生，請與產品支援人員聯繫</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>出錯</p></td>
<td><p>IM MCU 無法使用</p></td>
<td><p>IM MCU 無法使用</p>
<p>查看 IM MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>參考</p></td>
<td><p>已從無法連線至 IM MCU 的故障復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>出錯</p></td>
<td><p>無法使用 AV MCU</p></td>
<td><p>無法使用 AV MCU</p>
<p>查看 AV MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>參考</p></td>
<td><p>從無法連線到 AV MCU 的故障復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>出錯</p></td>
<td><p>無法使用 MCU</p></td>
<td><p>無法使用 MCU</p>
<p>查看是否正在執行 MCU</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>參考</p></td>
<td><p>從無法連線到 MCU 的方式復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>出錯</p></td>
<td><p>資料 MCU 無法使用</p></td>
<td><p>資料 MCU 無法使用</p>
<p>查看資料 MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>參考</p></td>
<td><p>從無法連線到資料 MCU 的情況中復原</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>出錯</p></td>
<td><p>無法加入 IM MCU</p></td>
<td><p>無法加入 IM MCU</p>
<p>查看 IM MCU 是否正在執行</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>出錯</p></td>
<td><p>無法加入 AV MCU</p></td>
<td><p>無法加入 AV MCU</p>
<p>查看 AV MCU 是否正在執行</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>出錯</p></td>
<td><p>無法以 MCU 進行加入</p></td>
<td><p>無法以 MCU 進行加入</p>
<p>查看是否正在執行 MCU</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>出錯</p></td>
<td><p>無法加入資料 MCU</p></td>
<td><p>無法加入資料 MCU</p>
<p>查看資料 MCU 是否正在執行</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>出錯</p></td>
<td><p>無法存取相片的 active directory</p></td>
<td><p>無法使用 active directory 連線</p>
<p>確定有可用的連線至 active directory</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>參考</p></td>
<td><p>已復原無法存取相片的 active directory</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>無法反序列化</p></td>
<td><p>無法反序列化</p>
<p>如果問題持續發生，請與產品支援人員聯繫</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

