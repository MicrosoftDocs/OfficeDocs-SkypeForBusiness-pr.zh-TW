---
title: Lync Server 2013：ErrorReport 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorReport 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

ErrorReport 資料表儲存所發生錯誤的相關資訊。 每一筆記錄都是一個錯誤發生。 錯誤是由在前端伺服器上執行或從用戶端傳送的 CDR 代理程式所捕獲。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>發生錯誤的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別錯誤報表的識別碼編號。 與<strong>ErrorTime</strong>搭配使用，可唯一識別錯誤報表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>錯誤類型的唯一識別碼。 如需詳細資訊，請參閱<a href="lync-server-2013-errordef-table.md">Lync Server 2013 中</a>的 [ErrorDef] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>產生導致錯誤之要求的使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>導致錯誤之要求的目的地使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>與錯誤相關的會議 URI。 如需詳細資訊，請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中</a>的 [ConferenceUris] 資料表。 通常，如果 ConferenceUriId 不是 null，則 FromUserId 或 ToUserId 將會是 null。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外</p></td>
<td><p>與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。 如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。 如需詳細資訊，請參閱<a href="lync-server-2013-application-table.md">Lync Server 2013 中的 [應用程式] 資料表</a>。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>影像</p></td>
<td><p> </p></td>
<td><p>有關錯誤的詳細資訊。</p>
<p>您可以使用下列語法，將此資料轉換成文字格式：</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>傳送錯誤報表的用戶端版本端點。 如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>是由在前端伺服器上執行的 CDR 代理程式所捕獲，或由用戶端傳送的錯誤報表。</p></td>
</tr>
<tr class="even">
<td><p><strong>標識</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>保留供日後使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定元件加入會議所需的時間（以毫秒為單位）。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>代表產生錯誤報表之伺服器的完整功能變數名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>代表產生錯誤報表之池的完整功能變數名稱。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

