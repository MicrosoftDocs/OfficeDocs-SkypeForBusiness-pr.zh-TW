---
title: Lync Server 2013： CodecDescription 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a407d8eeb1ad9e318ff2f960f8cb7d62b1e3a9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a>Lync Server 2013 中的 CodecDescription 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

CodecDescription 表格會將唯一的編解碼器識別碼對應至其相對應的編解碼器。 編解碼器是用來編碼傳輸和廣播的數位信號，然後解碼這些信號以進行播放。 此表格是在 Microsoft Lync Server 2013 中推出


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
<td><p><strong>CodecDescriptionKey</strong></p></td>
<td><p>Smallint</p></td>
<td><p>首選</p></td>
<td><p>指派給編解碼器的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>CodecDescription</strong></p></td>
<td><p>Varchar （256）</p></td>
<td><p>唯一</p></td>
<td><p>對應至 CodecDescriptionKey 的編解碼器的唯一描述。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

