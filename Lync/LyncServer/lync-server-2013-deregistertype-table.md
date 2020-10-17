---
title: Lync Server 2013： DeRegisterType 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4aa5ea27cdf86d9c8e0c0cdf7260b20cca4478
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498960"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Lync Server 2013 中的 DeRegisterType 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

DeRegisterType 表格是靜態表格，可儲存使用者取消註冊可能類型的清單 (如「由用戶端起始」、「註冊到期」或「用戶端停止回應」)。


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
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td></td>
<td><p>允許的值：</p>
<ul>
<li><p>0 -- 不明</p></li>
<li><p>1 -- 由用戶端起始取消註冊</p></li>
<li><p>2 -- 註冊到期</p></li>
<li><p>3 – 用戶端損毀</p></li>
<li><p>4 -- 使用者屬性變更</p></li>
<li><p>5 – 慣用的登錄器變更</p></li>
<li><p>6 -- 舊版用戶端處於生存模式</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

