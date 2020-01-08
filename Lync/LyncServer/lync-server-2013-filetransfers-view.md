---
title: Lync Server 2013： FileTransfers view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013 中的 [FileTransfers] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。

<div>


> [!NOTE]  
> [FileTransfers] 視圖會包含 [ <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013</A> ] 的 [SessionDetails] 視圖中的所有資料行，以及下列所列的欄。



</div>


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
<td><p><strong>副檔名</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已傳輸檔案的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>C</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>用來識別與此郵件相關聯的每一封後續訊息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>唯一識別碼，區分涉及相同檔案名的檔案傳輸。</p></td>
</tr>
<tr class="even">
<td><p><strong>接受</strong></p></td>
<td><p>稍微</p></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</p></td>
</tr>
<tr class="odd">
<td><p><strong>否決</strong></p></td>
<td><p>稍微</p></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>稍微</p></td>
<td><p>可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

