---
title: Lync Server 2013： [會話] 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Lync Server 2013 中的 [會話] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

[會話] 視圖儲存在資料庫中有記錄之會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>從 MediaLine 資料表中參照。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。</p></td>
</tr>
<tr class="odd">
<td><p>相關</p></td>
<td><p>Varchar （max）</p></td>
<td><p>會話的相關識別碼。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>稍微</p></td>
<td><p>對話方塊類別;0是 Lync Server 以進行轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>稍微</p></td>
<td><p>指出是否已略過通話。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>此欄位（如果有的話）會指出即使繞過的旁路 Id，也不會避開通話。 對於 Lync Server，只會定義一個值：</p>
<p>0x0001 –預設網路介面卡的旁路旁路 ID</p></td>
</tr>
<tr class="odd">
<td><p>開始</p></td>
<td><p>datetime</p></td>
<td><p>呼叫開始時間。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>通話結束時間。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>呼叫者池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>被呼叫方池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>來電者 p 斷言身分識別 URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>被呼叫者的 p 聲明身分識別 URI。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>來電者的端點名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>來電者的端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>來電者的使用者代理程式字串。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>呼叫者的使用者代理程式類型。 如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>呼叫者的使用者代理類別。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>被呼叫者的使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>被呼叫者的使用者代理程式類型。 如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>被呼叫者的使用者代理類別。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>來電者的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>被呼叫者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>通話的優先順序。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

