---
title: 'Lync Server 2013: IPAddress 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 663494ad52fd8351df7a036fd2954dff0497c608
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a>Lync Server 2013 中的 IPAddress 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-17_

IPAddress 表將 IP 位址對應至用在經驗品質資料庫其他地方的唯一 IP 地址識別碼。 Microsoft Lync Server 2013 中已採用此表格。


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>指定的 IP 位址的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar(50)</p></td>
<td><p>Unique</p></td>
<td><p>唯一的 IP 位址 (例如，189.168.1.1)，對應到 IpAddressKey。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

