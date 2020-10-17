---
title: Lync Server 2013： tblPreference
description: Lync Server 2013： tblPreference。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547509"
---
# <a name="tblpreference-in-lync-server-2013"></a>Lync Server 2013 中的 tblPreference

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-24_

tblPreference 包含使用者的用戶端喜好設定。 這通常是 Lync 2013 之前的用戶端使用。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prefLabel</p></td>
<td><p>nvarchar (255)，非 null</p></td>
<td><p>標籤，格式如下： &lt; user sip uri &gt; | username。 &lt;喜好設定 &gt; 。</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int，非 null</p></td>
<td><p>每個標籤的序數位 (，供版本設定之用) 。</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>編碼內容。</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>更新首選項的主體識別碼。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>索引鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

