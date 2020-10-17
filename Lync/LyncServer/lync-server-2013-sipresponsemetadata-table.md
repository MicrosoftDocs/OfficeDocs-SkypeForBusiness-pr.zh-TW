---
title: Lync Server 2013： SIPResponseMetaData 表格
description: Lync Server 2013： SIPResponseMetaData 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558979"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 中的 SIPResponseMetaData 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。 這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。

此表格已引進 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>代表 SIP 回應碼的數值。</p></td>
</tr>
<tr class="even">
<td><p><strong>Class</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>回應碼的一般分類。 分類包括：</p>
<ul>
<li><p>1–資訊性回應</p></li>
<li><p>2–成功的回應</p></li>
<li><p>3–重新導向回應</p></li>
<li><p>4-用戶端失敗回應</p></li>
<li><p>5--伺服器失敗回應</p></li>
<li><p>6–全域失敗回應</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>描述</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td></td>
<td><p>SIP 回應碼的描述。 例如，回應碼181的描述如下：</p>
<p>轉接來電</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

