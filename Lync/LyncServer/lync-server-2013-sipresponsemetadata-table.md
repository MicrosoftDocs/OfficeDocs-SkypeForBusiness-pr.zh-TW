---
title: Lync Server 2013： SIPResponseMetaData 表格
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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 中的 SIPResponseMetaData 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。 系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。

此表格是在 Microsoft Lync Server 2013 中推出。


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>代表 SIP 回應代碼的數值。</p></td>
</tr>
<tr class="even">
<td><p><strong>靜態類</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>回應代碼的一般分類。 分類包括：</p>
<ul>
<li><p>1–資訊回應</p></li>
<li><p>2–成功回應</p></li>
<li><p>3–重新導向回應</p></li>
<li><p>4–用戶端失敗回應</p></li>
<li><p>5--伺服器失敗回應</p></li>
<li><p>6-全域失敗回應</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>說明</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td></td>
<td><p>SIP 回應代碼的描述。 例如，回應代碼181具有下列描述：</p>
<p>呼叫正在轉寄</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

