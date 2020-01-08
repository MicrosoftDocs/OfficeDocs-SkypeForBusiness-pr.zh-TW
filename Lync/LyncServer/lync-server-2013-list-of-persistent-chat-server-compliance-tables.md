---
title: Lync Server 2013：常設聊天室伺服器規範表的清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="5450d-102">Lync Server 2013 中常設聊天室伺服器規範表的清單</span><span class="sxs-lookup"><span data-stu-id="5450d-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5450d-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5450d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5450d-104">持續性聊天規範資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="5450d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="5450d-105">持續聊天伺服器合規性資料表清單</span><span class="sxs-lookup"><span data-stu-id="5450d-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5450d-106">表格</span><span class="sxs-lookup"><span data-stu-id="5450d-106">Table</span></span></th>
<th><span data-ttu-id="5450d-107">描述</span><span class="sxs-lookup"><span data-stu-id="5450d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5450d-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 中的 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="5450d-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5450d-109">包含已設定的配接器尚未處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="5450d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="5450d-110">此表格包含持續與聊天相關的事件，例如聊天訊息和檔案下載。</span><span class="sxs-lookup"><span data-stu-id="5450d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="5450d-111">（TblComplianceParticipant 資料表會追蹤參與者事件）。</span><span class="sxs-lookup"><span data-stu-id="5450d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="5450d-112">（在此資料表中處理事件的伺服器會列于 [tblComplianceFanout] 資料表中）。</span><span class="sxs-lookup"><span data-stu-id="5450d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5450d-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 中的 tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="5450d-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5450d-114">包含已處理合規性事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="5450d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="5450d-115">此表格與 tblComplianceData 資料表緊密結合。</span><span class="sxs-lookup"><span data-stu-id="5450d-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5450d-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 中的 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="5450d-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5450d-117">包含每個聊天服務和每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="5450d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="5450d-118">它會根據從持久性聊天服務接收到的聯結和元件相容性事件來維護。</span><span class="sxs-lookup"><span data-stu-id="5450d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5450d-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 中的 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="5450d-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5450d-120">包含全池相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="5450d-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

