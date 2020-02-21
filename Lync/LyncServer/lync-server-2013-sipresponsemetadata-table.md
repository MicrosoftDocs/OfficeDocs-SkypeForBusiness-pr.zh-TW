---
title: 'Lync Server 2013: SIPResponseMetaData 資料表'
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
ms.openlocfilehash: 0143bdd74b955f2cba5f68540be7c969f748aa47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013 中的 SIPResponseMetaData 資料表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

SIPResponseMetaDataTable 包含 SIP 回應碼的分類和定義每個這些代碼的清單。 這些代碼而產生的影響 SIP 裝置的事件回應及的 SIP 通訊工作階段;例如，SIP 裝置提出要求，但伺服器拒絕以受限於該要求時，都會產生回應碼 403。

Microsoft Lync Server 2013 中已採用此表格。


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
<th>主索引鍵 /</th>
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
<td><p><strong>類別</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>一般的回應碼的分類。 分類包括：</p>
<ul>
<li><p>1 – 資訊回應</p></li>
<li><p>2 – 成功回應</p></li>
<li><p>3 – 重新導向回應</p></li>
<li><p>4 – 用戶端失敗回應</p></li>
<li><p>5 – 伺服器失敗回應</p></li>
<li><p>6 – 全域失敗回應</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>描述</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>SIP 回應碼的描述。 例如，回應碼 181 有下列描述：</p>
<p>已轉接通話</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

