---
title: Lync Server 2013： ErrorReport view
description: Lync Server 2013： ErrorReport view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572039"
---
# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorReport 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-22_

ErrorReport view 會儲存所報告錯誤的相關資訊。 每個記錄是一個錯誤發生。 這兩個錯誤是由前端伺服器上執行的 CDR 代理程式所捕獲，或是從用戶端傳送。 此視圖已引進于 Microsoft Lync Server 2013。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生錯誤的時間。 與 ErrorReportSeq 搭配使用，以唯一識別錯誤。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用以識別錯誤的 ID 號碼。 與 ErrorTime 搭配使用，以唯一識別錯誤。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>錯誤報表的診斷識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>產生錯誤之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>產生錯誤之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>產生錯誤之使用者的租使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>錯誤報表之目標之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>錯誤報表目標使用者的 URI 類型。 如需詳細資訊，請參閱＜UriTypes Table＞。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>目標為錯誤報表之使用者的租使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>錯誤報表目標的會議 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>錯誤報表目標的會議 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發出錯誤報表之會話要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別產生錯誤報表之會話要求的識別碼編號。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775) </p></td>
<td><p>發出錯誤之會話的 SIP 對話方塊識別碼。 格式為：</p>
<p>dialog; 從-標籤; to-標記</p>
<p>您可以使用下列語法將此資料轉換成文字格式：</p>
<p>cast (cast (ExternalId 為 Varbinary (max) # A4 做為 Varchar (最大) # A7</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.rule</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>產生錯誤之使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>產生錯誤之使用者所使用的用戶端。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>產生錯誤之使用者所使用的用戶端類別名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>應用程式</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>包含錯誤報表之 SIP 郵件會話的 SIP 回應碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>Varchar (max) </p></td>
<td><p>失敗的要求類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>Varchar (max) </p></td>
<td><p>失敗之要求的內容類型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>會話類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>唯一</p></td>
<td><p>與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定元件加入會議所需的時間 (（毫秒）) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>位</p></td>
<td><p>會指出是否是由前端伺服器上執行的 CDR 代理程式所捕獲，或是由用戶端所傳送的錯誤報表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>Smallint</p></td>
<td><p>保留供日後使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>Varchar (max) </p></td>
<td><p>有關錯誤的其他資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>提交報告之前端伺服器的完整功能變數名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>包含提交報告之前端伺服器集區的完整功能變數名稱。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

