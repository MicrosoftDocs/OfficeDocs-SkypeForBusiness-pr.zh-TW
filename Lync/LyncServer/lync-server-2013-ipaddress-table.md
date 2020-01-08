---
title: Lync Server 2013： IPAddress 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82eef0e1926bc794df7c6a80b28fa68008561315
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a>Lync Server 2013 中的 [IPAddress] 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>指定 IP 位址的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>Varchar （50）</p></td>
<td><p>唯一</p></td>
<td><p>對應至 IpAddressKey 的唯一 IP 位址（例如，189.168.1.1）。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

