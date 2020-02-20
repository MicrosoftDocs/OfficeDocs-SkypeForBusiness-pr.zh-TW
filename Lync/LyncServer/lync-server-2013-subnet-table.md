---
title: 'Lync Server 2013: Subnet 表格'
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
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a>Lync Server 2013 中的子網路表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>主索引鍵 /</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>子網路 IP 的整數表示。</p></td>
</tr>
<tr class="even">
<td><p><strong>子網路遮罩</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>子網路遮罩。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>參考來源<a href="lync-server-2013-usersite-table.md">: UserSite table Lync Server 2013 中</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SubnetDescription</strong></p></td>
<td><p>nvarchar(512)</p></td>
<td></td>
<td><p>子網路的描述。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

