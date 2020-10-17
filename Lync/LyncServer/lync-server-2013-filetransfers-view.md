---
title: Lync Server 2013： FileTransfers view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500870"
---
# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013 中的 FileTransfers 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

FileTransfer view 會儲存對等檔案傳輸會話的資訊。 此視圖已引進于 Microsoft Lync Server 2013。

<div>


> [!NOTE]  
> FileTransfers view 包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。



</div>


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
<td><p><strong>FileName</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已傳輸的檔案名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>可用來識別與此訊息相關聯的每則後續訊息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>唯一</p></td>
<td><p>唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>位</p></td>
<td><p>可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>位</p></td>
<td><p>可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>位</p></td>
<td><p>可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

