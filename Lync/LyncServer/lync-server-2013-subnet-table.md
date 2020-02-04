---
title: Lync Server 2013：Subnet 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d107889b49ec16c51224b075a8fb7f7a7cec1b00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a>Lync Server 2013 中的 Subnet 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>子網 IP 的整數表示。</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetMask</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>子網路遮罩。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>從<a href="lync-server-2013-usersite-table.md">Lync Server 2013 的 UserSite 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>Nvarchar （512）</p></td>
<td></td>
<td><p>子網的描述。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

