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
ms.openlocfilehash: df50c94fcf40761247fc647ac8f98ac2d5d4b355
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="f3db0-102">Lync Server 2013 中的常設聊天室伺服器規範表格清單</span><span class="sxs-lookup"><span data-stu-id="f3db0-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3db0-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="f3db0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f3db0-104">常設聊天室規範資料庫結構描述是由下列表格所組成。</span><span class="sxs-lookup"><span data-stu-id="f3db0-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="f3db0-105">常設聊天室伺服器規範表的清單</span><span class="sxs-lookup"><span data-stu-id="f3db0-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3db0-106">資料表</span><span class="sxs-lookup"><span data-stu-id="f3db0-106">Table</span></span></th>
<th><span data-ttu-id="f3db0-107">描述</span><span class="sxs-lookup"><span data-stu-id="f3db0-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3db0-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="f3db0-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3db0-109">包含設定的介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="f3db0-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="f3db0-110">此表格包含常設聊天室相關的事件，例如聊天訊息及下載檔案。</span><span class="sxs-lookup"><span data-stu-id="f3db0-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="f3db0-111">（參與者事件追蹤 tblComplianceParticipant 表所列）。</span><span class="sxs-lookup"><span data-stu-id="f3db0-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="f3db0-112">（處理事件。 此表格中的伺服器會列在 tblComplianceFanout 表格）。</span><span class="sxs-lookup"><span data-stu-id="f3db0-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3db0-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblcompliancefanout 表格</a></span><span class="sxs-lookup"><span data-stu-id="f3db0-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3db0-114">包含處理規範事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f3db0-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="f3db0-115">此表格緊密結合 tblComplianceData 資料表中。</span><span class="sxs-lookup"><span data-stu-id="f3db0-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3db0-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="f3db0-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3db0-117">會包含每個聊天室服務，而每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="f3db0-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="f3db0-118">它會維護根據加入和組件從的常設聊天室服務接收到的規範事件。</span><span class="sxs-lookup"><span data-stu-id="f3db0-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3db0-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="f3db0-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f3db0-120">會包含整個集區的規範狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="f3db0-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

