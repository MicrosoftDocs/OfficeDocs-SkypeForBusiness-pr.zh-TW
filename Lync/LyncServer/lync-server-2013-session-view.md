---
title: Lync Server 2013：會話視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30183ffde7380b5029ac458f102eaf81ecee914b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510090"
---
# <a name="session-view-in-lync-server-2013"></a>Lync Server 2013 中的會話視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>參考來源為 MediaLine 表格。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>如果是會議則為會議 URI，如果是對等工作階段則為 DialogID。</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>Varchar (max) </p></td>
<td><p>工作階段的關聯 ID。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>位</p></td>
<td><p>對話方塊類別;0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>位</p></td>
<td><p>指出通話是否經旁路處理。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。 對於 Lync Server，只會定義一個值：</p>
<p>0x0001 – 預設網路介面卡未知的旁路識別碼</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>通話開始時間。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>通話結束時間。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者集區 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>受話者集區 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>發話者的 P 聲稱的識別 URI 。</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>受話者的 P 聲稱的識別 URI 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者的端點名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者的端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者的使用者代理程式字串。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>發話者的使用者代理程式類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>發話者的使用者代理程式類別。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>受話者的使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>受話者的使用者代理程式類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>受話者的使用者代理程式類別。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>來電者的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>Nvarchar (450) </p></td>
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

