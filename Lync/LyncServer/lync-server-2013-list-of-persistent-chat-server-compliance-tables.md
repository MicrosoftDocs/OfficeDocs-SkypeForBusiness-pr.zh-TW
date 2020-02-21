---
title: Lync Server 2013： 常設聊天室伺服器規範表格清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013 中的常設聊天室伺服器規範表格清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

常設聊天室規範資料庫結構描述是由下列表格所組成。

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設聊天室伺服器規範表的清單


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料表</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></p></td>
<td><p>包含設定的介面卡尚未處理的規範事件。</p>
<p>此表格包含常設聊天室相關的事件，例如聊天訊息及下載檔案。 （參與者事件追蹤 tblComplianceParticipant 表所列）。</p>
<p>（處理事件。 此表格中的伺服器會列在 tblComplianceFanout 表格）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblcompliancefanout 表格</a></p></td>
<td><p>包含處理規範事件的伺服器。 此表格緊密結合 tblComplianceData 資料表中。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></p></td>
<td><p>會包含每個聊天室服務，而每個伺服器的目前參與者。 它會維護根據加入和組件從的常設聊天室服務接收到的規範事件。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></p></td>
<td><p>會包含整個集區的規範狀態資訊。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

