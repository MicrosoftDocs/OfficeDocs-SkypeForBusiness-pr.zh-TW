---
title: Lync Server 2013：Session 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013 中的 Session 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-09_

每個記錄代表一個涉及音訊或音訊與影片的會話。 它包含有關會話的整體資訊。 會話是在兩個端點之間定義為音訊或視頻會話初始通訊協定（SIP）對話方塊。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>從<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>從<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>[會議金鑰]。 <a href="lync-server-2013-conference-table.md">在 Lync Server 2013 的 [會議] 表格中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>[關聯金鑰]。 從<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>對話方塊類別;0是 Lync Server 以進行轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>該旗標指出通話是否被略過。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>此欄位（如果有的話）會指出即使繞過的旁路 Id，也不會避開通話。 對於 Lync Server，只會定義一個值。</p>
<p>0x0001 –預設網路介面卡的旁路旁路 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>呼叫開始時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通話結束時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的池子。 從<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 [Pool] 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器的池子。 從<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 [Pool] 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收端點的 SIP p 斷言身分識別（PAI）中的 SIP URI。 從<a href="lync-server-2013-user-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的 URI。 從<a href="lync-server-2013-user-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的端點。 從<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 的端點資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>稍微</p></td>
<td><p>外</p></td>
<td><p>來電者的使用者代理程式。 從<a href="lync-server-2013-useragent-table.md">Lync Server 2013 的 UserAgent 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>此通話的優先順序。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>此欄已棄用，且未在 Microsoft Lync Server 2013 中使用。 相反地，此資訊是在每個媒體的行基底報告。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>P-已斷言-撥打電話之使用者的身分識別。 P 斷言身分識別（PAI）是用來傳達撥打電話之使用者的真實身分識別。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收通話的端點。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>由接收通話的使用者所使用的使用者代理程式。 使用者代理代表用戶端端點裝置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收通話之使用者的 SIP URI。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

