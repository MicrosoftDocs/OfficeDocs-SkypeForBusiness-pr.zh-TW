---
title: Lync Server 2013： ErrorReport view
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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013 中的 [ErrorReport] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-22_

[ErrorReport] 視圖儲存所報告錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。 此視圖已在 Microsoft Lync Server 2013 中推出。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生錯誤的時間。 與 ErrorReportSeq 搭配使用，可唯一識別錯誤。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別錯誤的識別碼號碼。 與 ErrorTime 搭配使用，可唯一識別錯誤。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>錯誤報表的診斷 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>產生錯誤之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>產生錯誤之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>產生錯誤之使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>錯誤報表目標使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>錯誤報表目標使用者的 URI 類型。 如需詳細資訊，請參閱 UriTypes 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>針對錯誤報表的目標使用者的租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>錯誤報表目標的會議 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>錯誤報表目標會議的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>產生錯誤報表之會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別產生錯誤報表之會話要求的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring （775）</p></td>
<td><p>產生錯誤之會話的 SIP 對話方塊識別碼。 格式為：</p>
<p>對話方塊; 從標籤; 到標籤</p>
<p>您可以使用下列語法，將此資料轉換成文字格式：</p>
<p>cast （轉換（ExternalId 為 Varbinary （max））做為 Varchar （max））</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>產生錯誤的使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>產生錯誤的使用者所使用的用戶端。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>產生錯誤之使用者所使用之用戶端類別的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>從源</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>應用程式</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 回應程式碼加入包含錯誤報表之 SIP 訊息的會話中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>Varchar （max）</p></td>
<td><p>失敗的要求類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>Varchar （max）</p></td>
<td><p>失敗之要求的內容類型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>會話類型。 如需詳細資訊，請參閱<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中</a>的 [CallType] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定元件加入會議所需的時間（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>稍微</p></td>
<td><p>指示錯誤報表是由在前端伺服器上執行的 CDR 代理程式捕獲，還是由用戶端傳送。</p></td>
</tr>
<tr class="odd">
<td><p><strong>標識</strong></p></td>
<td><p>Smallint</p></td>
<td><p>保留供日後使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>Varchar （max）</p></td>
<td><p>錯誤的其他相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>提交報表之前端伺服器的完整功能變數名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>包含提交報表之前端伺服器之池的完整功能變數名稱。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

