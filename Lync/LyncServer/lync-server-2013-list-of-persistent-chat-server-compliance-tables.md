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
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="43163-102">Lync Server 2013 中的 Persistent Chat Server 相容性資料表清單</span><span class="sxs-lookup"><span data-stu-id="43163-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43163-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="43163-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="43163-104">Persistent Chat 規範資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="43163-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="43163-105">Persistent Chat Server 相容性表格清單</span><span class="sxs-lookup"><span data-stu-id="43163-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43163-106">資料表</span><span class="sxs-lookup"><span data-stu-id="43163-106">Table</span></span></th>
<th><span data-ttu-id="43163-107">描述</span><span class="sxs-lookup"><span data-stu-id="43163-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43163-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="43163-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43163-109">包含已設定之介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="43163-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="43163-110">此表格包含持續聊天相關的事件，例如聊天訊息和檔案下載。</span><span class="sxs-lookup"><span data-stu-id="43163-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="43163-111"> (參與者事件會由 tblComplianceParticipant 表追蹤。 ) </span><span class="sxs-lookup"><span data-stu-id="43163-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="43163-112"> (處理此表中之事件的伺服器會列在 tblComplianceFanout 表格中。 ) </span><span class="sxs-lookup"><span data-stu-id="43163-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43163-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="43163-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43163-114">包含處理規範事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="43163-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="43163-115">此表格與 tblComplianceData 表格緊密結合。</span><span class="sxs-lookup"><span data-stu-id="43163-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43163-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="43163-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43163-117">包含每個聊天服務和每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="43163-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="43163-118">它會根據從 Persistent Chat service 接收的 join 和 part 相容性事件來維護。</span><span class="sxs-lookup"><span data-stu-id="43163-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43163-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="43163-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="43163-120">包含集區範圍的相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="43163-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

