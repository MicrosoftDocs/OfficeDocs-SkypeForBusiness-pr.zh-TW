---
title: Lync Server 2013： Persistent Chat Server 相容性資料表清單
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
ms.openlocfilehash: 70d8b61b67b8c6156b3875d2a9c0d5c9b6870459
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513950"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013 中的 Persistent Chat Server 相容性資料表清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

Persistent Chat 規範資料庫架構是由下清單格所組成。

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Persistent Chat Server 相容性表格清單


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>資料表</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></p></td>
<td><p>包含已設定之介面卡尚未處理的規範事件。</p>
<p>此表格包含持續聊天相關的事件，例如聊天訊息和檔案下載。  (參與者事件會由 tblComplianceParticipant 表追蹤。 ) </p>
<p> (處理此表中之事件的伺服器會列在 tblComplianceFanout 表格中。 ) </p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></p></td>
<td><p>包含處理規範事件的伺服器。 此表格與 tblComplianceData 表格緊密結合。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></p></td>
<td><p>包含每個聊天服務和每個伺服器的目前參與者。 它會根據從 Persistent Chat service 接收的 join 和 part 相容性事件來維護。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></p></td>
<td><p>包含集區範圍的相容性狀態資訊。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

