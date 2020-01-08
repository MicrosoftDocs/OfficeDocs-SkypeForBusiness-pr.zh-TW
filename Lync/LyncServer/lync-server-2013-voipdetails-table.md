---
title: Lync Server 2013：VoipDetails 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013 中的 VoipDetails 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

每個記錄代表 1 2 方通話，其中至少有一個使用者是 VoIP 使用者。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>會話要求的時間。 與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的<strong>PhoneId</strong> 。 如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。 如果 not Null 且<strong>FromGatewayId</strong>不是 null，則呼叫者是 PSTN 使用者。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器的<strong>PhoneId</strong> 。 如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。 如果 not Null 且<strong>ToGatewayId</strong>不是 null，則呼叫接收器是 PSTN 使用者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫來源的中繼伺服器。 如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的中繼伺服器將要移至。 如需詳細資訊，請參閱<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中</a>的 [MediationServers] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>通話來源的閘道。 如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>通話的閘道。 如需詳細資訊，請參閱<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 [閘道] 資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>中斷通話的使用者 URI （如果使用者有 URI）。 如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>中斷通話的電話的識別碼已從手機中斷連線。 如需詳細資訊，請參閱<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 [電話] 資料表。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

