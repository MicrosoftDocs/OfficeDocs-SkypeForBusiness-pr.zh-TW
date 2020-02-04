---
title: Lync Server 2013：FileTransfers 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Lync Server 2013 中的 FileTransfers 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

每個記錄代表一個檔案傳輸會話。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話要求的時間。 與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>檔案名</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td></td>
<td><p>檔案的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>唯一識別碼，區分涉及相同檔案名的檔案傳輸。</p></td>
</tr>
<tr class="odd">
<td><p><strong>C</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>首選</p></td>
<td><p>用來識別與此郵件相關聯的每一封後續訊息。</p></td>
</tr>
<tr class="even">
<td><p><strong>接受</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</p></td>
</tr>
<tr class="odd">
<td><p><strong>否決</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

