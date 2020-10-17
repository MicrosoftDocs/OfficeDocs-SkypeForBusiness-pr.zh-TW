---
title: Lync Server 2013： Persistent Chat Server 的容量規劃
description: Lync Server 2013： Persistent Chat Server 的容量規劃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f78f9f3666fb272b808ef36da2d3010f451d0079
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544489"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bada9-103">Lync Server 2013 中的持久聊天伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="bada9-103">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bada9-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="bada9-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="bada9-105">Persistent Chat Server 可以執行多使用者即時聊天，可保留以供未來檢索及搜尋。</span><span class="sxs-lookup"><span data-stu-id="bada9-105">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="bada9-106">與群組立即訊息 (IM) 會儲存在使用者的信箱中如果已設定交談記錄，則 Persistent Chat Server 會話會保持開啟的狀態，而且內容會儲存在伺服器上，以及郵件、檔案、URLs 和其他屬於進行中交談的資料。</span><span class="sxs-lookup"><span data-stu-id="bada9-106">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="bada9-107">容量規劃是準備部署 Persistent Chat Server 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="bada9-107">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="bada9-108">本主題提供支援的持續性聊天伺服器拓撲及容量規劃表格的詳細資料，您可以用來判斷部署的最佳設定。</span><span class="sxs-lookup"><span data-stu-id="bada9-108">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="bada9-109">此外，本文也說明如何在高峰時進行需要較高容量的持久聊天伺服器部署的最佳管理。</span><span class="sxs-lookup"><span data-stu-id="bada9-109">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="bada9-110">若要下載 Persistent Chat Server，請參閱《 Microsoft Lync Server 13 Persistent Chat Server 》，網址為 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。</span><span class="sxs-lookup"><span data-stu-id="bada9-110">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="bada9-111">如需安裝 Persistent Chat Server 的詳細資訊，請參閱部署檔中的在 lync server [2013 中安裝 Persistent Chat server](lync-server-2013-installing-persistent-chat-server.md) 和設定 [persistent chat server 2013](lync-server-2013-configuring-persistent-chat-server.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="bada9-111">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bada9-112">支援工具（例如 Lync Server 規劃工具）可進一步協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="bada9-112">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="bada9-113">如需規劃工具的詳細資訊，請參閱規劃檔中的 [開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md) 。</span><span class="sxs-lookup"><span data-stu-id="bada9-113">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="bada9-114">Persistent Chat Server 支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="bada9-114">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="bada9-115">您可以在單一伺服器或多部伺服器集區中部署 Persistent Chat Server，並使用單一集區或多集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="bada9-115">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="bada9-116">現在，我們也會在 Standard Edition server 上為新的 Lync Server 2013 部署支援 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="bada9-116">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="bada9-117">不過，效能及規模會受到影響，而且由於這項新的部署沒有高可用性選項，因此我們預計您主要是用來進行概念證明、評估等等的目的。</span><span class="sxs-lookup"><span data-stu-id="bada9-117">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bada9-118">如需這兩種拓撲的詳細資訊，請參閱部署檔中的 [在 lync Server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 中規劃 Persistent Chat server</A> ] 和 [在 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 中部署 persistent chat server</A> ]。</span><span class="sxs-lookup"><span data-stu-id="bada9-118">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="bada9-119">單一伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="bada9-119">Single-Server Topology</span></span>

<span data-ttu-id="bada9-120">Persistent Chat Server 的最小設定和最簡單部署是單一持久聊天伺服器前端伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="bada9-120">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="bada9-121">此部署需要執行 Persistent Chat Server (的單一伺服器，如果符合性已啟用) 、主控 SQL Server 資料庫的伺服器及相容性（若有必要），則會執行該程式，以儲存相容性資料。</span><span class="sxs-lookup"><span data-stu-id="bada9-121">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bada9-122">您無法將其他伺服器新增至 Persistent Chat Server 集區，此集區在拓撲產生器中以單一伺服器部署的方式啟動。</span><span class="sxs-lookup"><span data-stu-id="bada9-122">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="bada9-123">我們建議使用多伺服器集區拓撲，即使您使用單一伺服器也是一樣。</span><span class="sxs-lookup"><span data-stu-id="bada9-123">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="bada9-124">如此一來，您就可以在必要時新增更多的伺服器。</span><span class="sxs-lookup"><span data-stu-id="bada9-124">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="bada9-125">下圖顯示單一 Persistent Chat Server 前端伺服器及規範的拓撲的所有必要和選用元件。</span><span class="sxs-lookup"><span data-stu-id="bada9-125">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="bada9-126">**單一常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="bada9-126">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="bada9-127">![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="bada9-127">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="bada9-128">多部伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="bada9-128">Multiple-Server Topology</span></span>

<span data-ttu-id="bada9-129">若要提供更大的容量與可靠性，您可以部署多伺服器拓撲，如在 [Lync server 2013 中規劃 Persistent Chat server](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="bada9-129">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="bada9-130">多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。</span><span class="sxs-lookup"><span data-stu-id="bada9-130">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="bada9-131">每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。</span><span class="sxs-lookup"><span data-stu-id="bada9-131">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="bada9-132">多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。</span><span class="sxs-lookup"><span data-stu-id="bada9-132">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="bada9-133">多部執行 Persistent Chat Server 的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="bada9-133">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="bada9-134">下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="bada9-134">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="bada9-135">**多部常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="bada9-135">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="bada9-136">![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="bada9-136">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="bada9-137">在四部伺服器的持續聊天伺服器部署中，80000使用者可以同時登入和使用持續性聊天，在每個伺服器的20000使用者之間平均分配負載。</span><span class="sxs-lookup"><span data-stu-id="bada9-137">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="bada9-138">如果一部伺服器無法使用，連接至該伺服器的使用者將無法存取其 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="bada9-138">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="bada9-139">連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。</span><span class="sxs-lookup"><span data-stu-id="bada9-139">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="bada9-140">根據網路上的持續性聊天流量數量，此傳輸可能需要數分鐘或更長的時間。</span><span class="sxs-lookup"><span data-stu-id="bada9-140">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="bada9-141">因為剩下的每一部伺服器都可能裝載為30000個使用者，所以建議您儘快還原無法使用的伺服器，以避免效能問題。</span><span class="sxs-lookup"><span data-stu-id="bada9-141">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="bada9-142">否則，您可以使用拓撲產生器或 Windows PowerShell Cmdlet，將另一部 Persistent 聊天伺服器設定為可用， **CsPersistentChatActiveServer**。</span><span class="sxs-lookup"><span data-stu-id="bada9-142">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="bada9-143">持久聊天伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="bada9-143">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="bada9-144">下表可協助您使用 Persistent Chat Server 的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="bada9-144">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="bada9-145">其模型變更各種持久聊天伺服器設定對容量功能的影響。</span><span class="sxs-lookup"><span data-stu-id="bada9-145">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="bada9-146">規劃 Persistent Chat Server 的最大容量</span><span class="sxs-lookup"><span data-stu-id="bada9-146">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="bada9-147">使用下列範例表格，來判斷您可以支援的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="bada9-147">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="bada9-148">Persistent Chat Server 集區的最大容量範例</span><span class="sxs-lookup"><span data-stu-id="bada9-148">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bada9-149">主動 Persistent Chat service 實例</span><span class="sxs-lookup"><span data-stu-id="bada9-149">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="bada9-150"><em>dmx-4</em></span><span class="sxs-lookup"><span data-stu-id="bada9-150"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-151">Persistent Chat service 實例</span><span class="sxs-lookup"><span data-stu-id="bada9-151">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="bada9-152"><em>8 (4 必須是非使用中的;最多隻能使用4個作用中) </em></span><span class="sxs-lookup"><span data-stu-id="bada9-152"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-153">已連線的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-153">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="bada9-154"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="bada9-154"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-155">布建使用者總數</span><span class="sxs-lookup"><span data-stu-id="bada9-155">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="bada9-156">150000</span><span class="sxs-lookup"><span data-stu-id="bada9-156">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-157">端點數目</span><span class="sxs-lookup"><span data-stu-id="bada9-157">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="bada9-158">120000</span><span class="sxs-lookup"><span data-stu-id="bada9-158">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bada9-159">在上述範例中，方案是支援 Persistent Chat Server 所允許的最大使用者數目：「持久聊天」服務 (四個伺服器/實例可以有四個以上的被動式伺服器執行 Persistent Chat Server，以進行高可用性) 和嚴重損壞復原，以及每一部伺服器的20000使用者，共80000個作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="bada9-159">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="bada9-160">管理持續聊天室存取的容量規劃</span><span class="sxs-lookup"><span data-stu-id="bada9-160">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="bada9-161">下列範例表可協助您規劃如何在 Persistent Chat Server 集區中管理持續性聊天室存取。</span><span class="sxs-lookup"><span data-stu-id="bada9-161">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="bada9-162">聊天室存取管理範例</span><span class="sxs-lookup"><span data-stu-id="bada9-162">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bada9-163">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-163">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-164">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-164">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-165">大聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-165">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-166">總計</span><span class="sxs-lookup"><span data-stu-id="bada9-166">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bada9-167">聊天室大小 (連接的使用者人數) </span><span class="sxs-lookup"><span data-stu-id="bada9-167">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="bada9-168">每個會議室30個</span><span class="sxs-lookup"><span data-stu-id="bada9-168">30 per room</span></span></p></td>
<td><p><span data-ttu-id="bada9-169">每個會議室150</span><span class="sxs-lookup"><span data-stu-id="bada9-169">150 per room</span></span></p></td>
<td><p><span data-ttu-id="bada9-170">每個會議室16000</span><span class="sxs-lookup"><span data-stu-id="bada9-170">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-171">聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-171">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-172">32000</span><span class="sxs-lookup"><span data-stu-id="bada9-172">32,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-173">1067</span><span class="sxs-lookup"><span data-stu-id="bada9-173">1,067</span></span></p></td>
<td><p><span data-ttu-id="bada9-174">10 </span><span class="sxs-lookup"><span data-stu-id="bada9-174">10</span></span></p></td>
<td><p><span data-ttu-id="bada9-175">33077</span><span class="sxs-lookup"><span data-stu-id="bada9-175">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-176">視聽中心的會議室%</span><span class="sxs-lookup"><span data-stu-id="bada9-176">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="bada9-177">1</span><span class="sxs-lookup"><span data-stu-id="bada9-177">1%</span></span></p></td>
<td><p><span data-ttu-id="bada9-178">1</span><span class="sxs-lookup"><span data-stu-id="bada9-178">1%</span></span></p></td>
<td><p><span data-ttu-id="bada9-179">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-179">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-180">開啟的會議室%</span><span class="sxs-lookup"><span data-stu-id="bada9-180">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="bada9-181">個</span><span class="sxs-lookup"><span data-stu-id="bada9-181">3%</span></span></p></td>
<td><p><span data-ttu-id="bada9-182">個</span><span class="sxs-lookup"><span data-stu-id="bada9-182">3%</span></span></p></td>
<td><p><span data-ttu-id="bada9-183">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-183">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-184">開啟會議室 (沒有明確的成員資格) </span><span class="sxs-lookup"><span data-stu-id="bada9-184">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="bada9-185">960</span><span class="sxs-lookup"><span data-stu-id="bada9-185">960</span></span></p></td>
<td><p><span data-ttu-id="bada9-186">32</span><span class="sxs-lookup"><span data-stu-id="bada9-186">32</span></span></p></td>
<td><p><span data-ttu-id="bada9-187">5 </span><span class="sxs-lookup"><span data-stu-id="bada9-187">5</span></span></p></td>
<td><p><span data-ttu-id="bada9-188">997</span><span class="sxs-lookup"><span data-stu-id="bada9-188">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-189">使用明確成員資格的非開啟聊天室 (一般會議室) </span><span class="sxs-lookup"><span data-stu-id="bada9-189">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="bada9-190">31040</span><span class="sxs-lookup"><span data-stu-id="bada9-190">31,040</span></span></p></td>
<td><p><span data-ttu-id="bada9-191">1.035</span><span class="sxs-lookup"><span data-stu-id="bada9-191">1.035</span></span></p></td>
<td><p><span data-ttu-id="bada9-192">5 </span><span class="sxs-lookup"><span data-stu-id="bada9-192">5</span></span></p></td>
<td><p><span data-ttu-id="bada9-193">32080</span><span class="sxs-lookup"><span data-stu-id="bada9-193">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-194">視聽中心聊天室 (其他簡報者專案) </span><span class="sxs-lookup"><span data-stu-id="bada9-194">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="bada9-195">0</span><span class="sxs-lookup"><span data-stu-id="bada9-195">0</span></span></p></td>
<td><p><span data-ttu-id="bada9-196">32</span><span class="sxs-lookup"><span data-stu-id="bada9-196">32</span></span></p></td>
<td><p><span data-ttu-id="bada9-197">5 </span><span class="sxs-lookup"><span data-stu-id="bada9-197">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-198">由直接成員資格管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-198">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="bada9-199">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-199">50%</span></span></p></td>
<td><p><span data-ttu-id="bada9-200">十進位</span><span class="sxs-lookup"><span data-stu-id="bada9-200">10%</span></span></p></td>
<td><p><span data-ttu-id="bada9-201">0</span><span class="sxs-lookup"><span data-stu-id="bada9-201">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-202">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-202">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="bada9-203">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-203">50%</span></span></p></td>
<td><p><span data-ttu-id="bada9-204">90%</span><span class="sxs-lookup"><span data-stu-id="bada9-204">90%</span></span></p></td>
<td><p><span data-ttu-id="bada9-205">100%</span><span class="sxs-lookup"><span data-stu-id="bada9-205">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-206">開啟之聊天室之每個聊天室的成員資格清單中的使用者群組 (未明確指定) </span><span class="sxs-lookup"><span data-stu-id="bada9-206">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="bada9-207">0</span><span class="sxs-lookup"><span data-stu-id="bada9-207">0</span></span></p></td>
<td><p><span data-ttu-id="bada9-208">0</span><span class="sxs-lookup"><span data-stu-id="bada9-208">0</span></span></p></td>
<td><p><span data-ttu-id="bada9-209">0</span><span class="sxs-lookup"><span data-stu-id="bada9-209">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-210">非開啟會議室之每個聊天室成員資格清單中的使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-210">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-211">大約</span><span class="sxs-lookup"><span data-stu-id="bada9-211">30</span></span></p></td>
<td><p><span data-ttu-id="bada9-212">150</span><span class="sxs-lookup"><span data-stu-id="bada9-212">150</span></span></p></td>
<td><p><span data-ttu-id="bada9-213">16000</span><span class="sxs-lookup"><span data-stu-id="bada9-213">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-214">非開啟會議室之每個聊天室成員資格清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="bada9-214">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-215">個</span><span class="sxs-lookup"><span data-stu-id="bada9-215">3</span></span></p></td>
<td><p><span data-ttu-id="bada9-216">5 </span><span class="sxs-lookup"><span data-stu-id="bada9-216">5</span></span></p></td>
<td><p><span data-ttu-id="bada9-217">10 </span><span class="sxs-lookup"><span data-stu-id="bada9-217">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-218">每個聊天室的管理員清單中的使用者與使用者群組 (開放和非開啟的會議室) </span><span class="sxs-lookup"><span data-stu-id="bada9-218">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="bada9-219">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-219">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-220">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-220">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-221">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-221">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-222">每個視聽中心聊天室的簡報者清單中的使用者與使用者群組 (開啟和非開啟的會議室) </span><span class="sxs-lookup"><span data-stu-id="bada9-222">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="bada9-223">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-223">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-224">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-224">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-225">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-225">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-226">跨所有非開啟聊天室的使用者型成員資格實體</span><span class="sxs-lookup"><span data-stu-id="bada9-226">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-227">465600</span><span class="sxs-lookup"><span data-stu-id="bada9-227">465,600</span></span></p></td>
<td><p><span data-ttu-id="bada9-228">15520</span><span class="sxs-lookup"><span data-stu-id="bada9-228">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-229">跨所有非開啟會議室的使用者群組型成員資格實體</span><span class="sxs-lookup"><span data-stu-id="bada9-229">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-230">46560</span><span class="sxs-lookup"><span data-stu-id="bada9-230">46,560</span></span></p></td>
<td><p><span data-ttu-id="bada9-231">4656</span><span class="sxs-lookup"><span data-stu-id="bada9-231">4656</span></span></p></td>
<td><p><span data-ttu-id="bada9-232">50</span><span class="sxs-lookup"><span data-stu-id="bada9-232">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-233">所有視聽中心聊天室中的使用者和使用者群組基礎實體</span><span class="sxs-lookup"><span data-stu-id="bada9-233">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-234">0</span><span class="sxs-lookup"><span data-stu-id="bada9-234">0</span></span></p></td>
<td><p><span data-ttu-id="bada9-235">192</span><span class="sxs-lookup"><span data-stu-id="bada9-235">192</span></span></p></td>
<td><p><span data-ttu-id="bada9-236">50</span><span class="sxs-lookup"><span data-stu-id="bada9-236">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-237">所有聊天室管理員清單中的使用者與使用者群組管理員實體</span><span class="sxs-lookup"><span data-stu-id="bada9-237">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="bada9-238">192000</span><span class="sxs-lookup"><span data-stu-id="bada9-238">192,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-239">6400</span><span class="sxs-lookup"><span data-stu-id="bada9-239">6,400</span></span></p></td>
<td><p><span data-ttu-id="bada9-240">60</span><span class="sxs-lookup"><span data-stu-id="bada9-240">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-241">每個聊天室的作用中使用者數</span><span class="sxs-lookup"><span data-stu-id="bada9-241">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="bada9-242"><em>大約</em></span><span class="sxs-lookup"><span data-stu-id="bada9-242"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-243"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="bada9-243"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-244"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="bada9-244"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-245">每位使用者的聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-245">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-246"><em>英寸</em></span><span class="sxs-lookup"><span data-stu-id="bada9-246"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="bada9-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-248"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="bada9-248"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-249"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="bada9-249"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-250">每個聊天室之成員資格清單中的使用者群組數</span><span class="sxs-lookup"><span data-stu-id="bada9-250">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="bada9-251"><em>十進位</em></span><span class="sxs-lookup"><span data-stu-id="bada9-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-252"><em>十進位</em></span><span class="sxs-lookup"><span data-stu-id="bada9-252"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-253"><em>8</em></span><span class="sxs-lookup"><span data-stu-id="bada9-253"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-254">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-254">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="bada9-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="bada9-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="bada9-256"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-257"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="bada9-257"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-258">所有聊天室的使用者群組型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="bada9-258">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-259">155200</span><span class="sxs-lookup"><span data-stu-id="bada9-259">155,200</span></span></p></td>
<td><p><span data-ttu-id="bada9-260">5173</span><span class="sxs-lookup"><span data-stu-id="bada9-260">5173</span></span></p></td>
<td><p><span data-ttu-id="bada9-261">68</span><span class="sxs-lookup"><span data-stu-id="bada9-261">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-262">所有聊天室的使用者型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="bada9-262">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-263">465600</span><span class="sxs-lookup"><span data-stu-id="bada9-263">465,600</span></span></p></td>
<td><p><span data-ttu-id="bada9-264">77600</span><span class="sxs-lookup"><span data-stu-id="bada9-264">77,600</span></span></p></td>
<td><p><span data-ttu-id="bada9-265">72000</span><span class="sxs-lookup"><span data-stu-id="bada9-265">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-266">每個聊天室的管理員、簡報者和範圍清單中的使用者與使用者群組數</span><span class="sxs-lookup"><span data-stu-id="bada9-266">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="bada9-267">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-267">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-268">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-268">6</span></span></p></td>
<td><p><span data-ttu-id="bada9-269">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-269">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-270">所有聊天室的管理員、簡報者和範圍清單之間的使用者和使用者群組</span><span class="sxs-lookup"><span data-stu-id="bada9-270">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="bada9-271">192000</span><span class="sxs-lookup"><span data-stu-id="bada9-271">192,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-272">6400</span><span class="sxs-lookup"><span data-stu-id="bada9-272">6400</span></span></p></td>
<td><p><span data-ttu-id="bada9-273">60</span><span class="sxs-lookup"><span data-stu-id="bada9-273">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-274">存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="bada9-274">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="bada9-275">704160</span><span class="sxs-lookup"><span data-stu-id="bada9-275">704,160</span></span></p></td>
<td><p><span data-ttu-id="bada9-276">26768</span><span class="sxs-lookup"><span data-stu-id="bada9-276">26,768</span></span></p></td>
<td><p><span data-ttu-id="bada9-277">160</span><span class="sxs-lookup"><span data-stu-id="bada9-277">160</span></span></p></td>
<td><p><span data-ttu-id="bada9-278">731088</span><span class="sxs-lookup"><span data-stu-id="bada9-278">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-279">最大存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="bada9-279">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="bada9-280">2000000</span><span class="sxs-lookup"><span data-stu-id="bada9-280">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bada9-281">在上述範例中，當您根據建議的指導方針來部署 Persistent Chat server 時，可在啟用規範的情況下，處理跨越四個伺服器集區的最多80000個活躍使用者。</span><span class="sxs-lookup"><span data-stu-id="bada9-281">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="bada9-282">這個範例會顯示在任何指定時間) 、中型 (150 作用中使用者) 及大型 (16000 作用中使用者) ，歸類為小型 (30 作用中使用者的聊天室。</span><span class="sxs-lookup"><span data-stu-id="bada9-282">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="bada9-283">特定大小聊天室的數目是依下列項目的總數計算而來：</span><span class="sxs-lookup"><span data-stu-id="bada9-283">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="bada9-284">系統中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-284">Active users in the system</span></span>

  - <span data-ttu-id="bada9-285">特定大小聊天室中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-285">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="bada9-286">單一使用者加入的特定大小聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-286">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="bada9-287">針對每個聊天室，先前的容量規劃表格會指定與聊天室相關聯的存取控制專案數目（包括直接指派給聊天室的專案）。</span><span class="sxs-lookup"><span data-stu-id="bada9-287">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="bada9-288">您可以使用存取控制清單 (ACL)，控制對個別聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="bada9-288">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="bada9-289">您也可以在類別層級控制存取。</span><span class="sxs-lookup"><span data-stu-id="bada9-289">You can also control access at the category level.</span></span> <span data-ttu-id="bada9-290">在 ACL 中，個別的存取控制專案可以是使用者群組（例如，安全性群組、通訊群組清單或單一使用者）。</span><span class="sxs-lookup"><span data-stu-id="bada9-290">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="bada9-291">您可以定義聊天室管理員、簡報者和成員的存取控制項目。</span><span class="sxs-lookup"><span data-stu-id="bada9-291">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bada9-292">在規劃管理聊天室的策略時，請記住允許的存取控制專案總數為2000000。</span><span class="sxs-lookup"><span data-stu-id="bada9-292">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="bada9-293">如果計算出的存取控制專案超過2000000，伺服器效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="bada9-293">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="bada9-294">若要避免此問題，請盡可能確定您的存取控制專案是使用者群組，而非個別使用者。</span><span class="sxs-lookup"><span data-stu-id="bada9-294">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="bada9-295">邀請式聊天室存取的容量管理規劃</span><span class="sxs-lookup"><span data-stu-id="bada9-295">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="bada9-296">您可以使用下列容量規劃表格來瞭解 Persistent Chat Server 在設定成傳送邀請時，在 Persistent Chat 資料庫中建立及儲存的邀請數目。</span><span class="sxs-lookup"><span data-stu-id="bada9-296">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="bada9-297">您可以使用 Lync Server 控制台中的 **聊天室類別設定** 頁面或使用 Windows PowerShell Cmdlet **CsPersistentChatCategory**，管理類別上的邀請。</span><span class="sxs-lookup"><span data-stu-id="bada9-297">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="bada9-298">您可以使用 Lync 用戶端（或使用 Windows PowerShell Cmdlet）從 Lync 用戶端（ **clear-cspersistentchatroom**）中所) 提供的「**會議室管理**」頁面來管理聊天室上的邀請函 (線上。</span><span class="sxs-lookup"><span data-stu-id="bada9-298">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="bada9-299">下表中的範例資料假設，在 [ **聊天室設定** ] 頁面上的50% 的所有聊天室中，[ **邀請** ] 選項會設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="bada9-299">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bada9-300">如果伺服器所產生之邀請數目的計算值超過1000000，伺服器效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="bada9-300">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="bada9-301">若要避免此問題，請確定您將設定為傳送邀請的聊天室數目降至最低，或限制可加入已設定為傳送邀請之聊天室的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="bada9-301">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="bada9-302">邀請式聊天室存取範例</span><span class="sxs-lookup"><span data-stu-id="bada9-302">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bada9-303">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-303">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-304">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-304">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-305">大聊天室</span><span class="sxs-lookup"><span data-stu-id="bada9-305">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="bada9-306">總計</span><span class="sxs-lookup"><span data-stu-id="bada9-306">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bada9-307">可以存取聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-307">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="bada9-308">每個會議室30個</span><span class="sxs-lookup"><span data-stu-id="bada9-308">30 per room</span></span></p></td>
<td><p><span data-ttu-id="bada9-309">每個會議室150</span><span class="sxs-lookup"><span data-stu-id="bada9-309">150 per room</span></span></p></td>
<td><p><span data-ttu-id="bada9-310">每個會議室16000</span><span class="sxs-lookup"><span data-stu-id="bada9-310">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-311">具有邀請的會議室百分比</span><span class="sxs-lookup"><span data-stu-id="bada9-311">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="bada9-312">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-312">50%</span></span></p></td>
<td><p><span data-ttu-id="bada9-313">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-313">50%</span></span></p></td>
<td><p><span data-ttu-id="bada9-314">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-314">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-315">設成傳送邀請的聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-315">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="bada9-316"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="bada9-316"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-317"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="bada9-317"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-318"><em>位</em></span><span class="sxs-lookup"><span data-stu-id="bada9-318"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-319">可以存取該聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-319">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="bada9-320"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="bada9-320"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-321"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="bada9-321"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="bada9-322"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="bada9-322"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-323">Persistent Chat Server 產生的邀請</span><span class="sxs-lookup"><span data-stu-id="bada9-323">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="bada9-324">960000</span><span class="sxs-lookup"><span data-stu-id="bada9-324">960,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-325">120000</span><span class="sxs-lookup"><span data-stu-id="bada9-325">120,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-326">80000</span><span class="sxs-lookup"><span data-stu-id="bada9-326">80,000</span></span></p></td>
<td><p><span data-ttu-id="bada9-327">1160000</span><span class="sxs-lookup"><span data-stu-id="bada9-327">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-328">最大允許的邀請數</span><span class="sxs-lookup"><span data-stu-id="bada9-328">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="bada9-329">2000000</span><span class="sxs-lookup"><span data-stu-id="bada9-329">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-330">模型 1-以預期的每天每個會議室的郵件數目為起始單位</span><span class="sxs-lookup"><span data-stu-id="bada9-330">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-331">每個會議室 (每日聊天速度) </span><span class="sxs-lookup"><span data-stu-id="bada9-331">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="bada9-332">50</span><span class="sxs-lookup"><span data-stu-id="bada9-332">50</span></span></p></td>
<td><p><span data-ttu-id="bada9-333">500</span><span class="sxs-lookup"><span data-stu-id="bada9-333">500</span></span></p></td>
<td><p><span data-ttu-id="bada9-334">100</span><span class="sxs-lookup"><span data-stu-id="bada9-334">100</span></span></p></td>
<td><p><span data-ttu-id="bada9-335">650</span><span class="sxs-lookup"><span data-stu-id="bada9-335">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-336">所有會議室每秒 (的交談率) </span><span class="sxs-lookup"><span data-stu-id="bada9-336">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-337">55.56</span><span class="sxs-lookup"><span data-stu-id="bada9-337">55.56</span></span></p></td>
<td><p><span data-ttu-id="bada9-338">18.52</span><span class="sxs-lookup"><span data-stu-id="bada9-338">18.52</span></span></p></td>
<td><p><span data-ttu-id="bada9-339">0.03</span><span class="sxs-lookup"><span data-stu-id="bada9-339">0.03</span></span></p></td>
<td><p><span data-ttu-id="bada9-340">74</span><span class="sxs-lookup"><span data-stu-id="bada9-340">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-341">模型 2-從每位使用者每天發佈的郵件數目開始</span><span class="sxs-lookup"><span data-stu-id="bada9-341">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-342">每天每位使用者的聊天室速度</span><span class="sxs-lookup"><span data-stu-id="bada9-342">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="bada9-343">15 </span><span class="sxs-lookup"><span data-stu-id="bada9-343">15</span></span></p></td>
<td><p><span data-ttu-id="bada9-344">5 </span><span class="sxs-lookup"><span data-stu-id="bada9-344">5</span></span></p></td>
<td><p><span data-ttu-id="bada9-345">0.1</span><span class="sxs-lookup"><span data-stu-id="bada9-345">0.1</span></span></p></td>
<td><p><span data-ttu-id="bada9-346">共</span><span class="sxs-lookup"><span data-stu-id="bada9-346">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-347">每個會議室 (每日聊天速度) </span><span class="sxs-lookup"><span data-stu-id="bada9-347">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="bada9-348">38</span><span class="sxs-lookup"><span data-stu-id="bada9-348">38</span></span></p></td>
<td><p><span data-ttu-id="bada9-349">375</span><span class="sxs-lookup"><span data-stu-id="bada9-349">375</span></span></p></td>
<td><p><span data-ttu-id="bada9-350">800</span><span class="sxs-lookup"><span data-stu-id="bada9-350">800</span></span></p></td>
<td><p><span data-ttu-id="bada9-351">1213</span><span class="sxs-lookup"><span data-stu-id="bada9-351">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-352">所有會議室每秒 (的交談率) </span><span class="sxs-lookup"><span data-stu-id="bada9-352">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-353">41.67</span><span class="sxs-lookup"><span data-stu-id="bada9-353">41.67</span></span></p></td>
<td><p><span data-ttu-id="bada9-354">13.89</span><span class="sxs-lookup"><span data-stu-id="bada9-354">13.89</span></span></p></td>
<td><p><span data-ttu-id="bada9-355">0.28</span><span class="sxs-lookup"><span data-stu-id="bada9-355">0.28</span></span></p></td>
<td><p><span data-ttu-id="bada9-356">56</span><span class="sxs-lookup"><span data-stu-id="bada9-356">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="bada9-357">Persistent Chat Server 效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="bada9-357">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="bada9-358">下表說明 Persistent Chat Server 的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="bada9-358">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="bada9-359">它會提供容量規劃需求的基礎，並代表四部伺服器上具有80000並行使用者的一般組織。</span><span class="sxs-lookup"><span data-stu-id="bada9-359">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="bada9-360">Persistent Chat Server 效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="bada9-360">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bada9-361">連接的使用中使用者數目</span><span class="sxs-lookup"><span data-stu-id="bada9-361">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="bada9-362">80000</span><span class="sxs-lookup"><span data-stu-id="bada9-362">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-363">Persistent Chat Server 服務實例數目</span><span class="sxs-lookup"><span data-stu-id="bada9-363">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="bada9-364">4 </span><span class="sxs-lookup"><span data-stu-id="bada9-364">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-365">小型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="bada9-365">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-366">30 位使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-366">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-367">中型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="bada9-367">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-368">150 位使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-368">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-369">大型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="bada9-369">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-370">16000使用者</span><span class="sxs-lookup"><span data-stu-id="bada9-370">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-371">聊天室總數</span><span class="sxs-lookup"><span data-stu-id="bada9-371">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-372">33077</span><span class="sxs-lookup"><span data-stu-id="bada9-372">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-373">小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-373">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-374">32000</span><span class="sxs-lookup"><span data-stu-id="bada9-374">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-375">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-375">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-376">1067</span><span class="sxs-lookup"><span data-stu-id="bada9-376">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-377">大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-377">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-378">10 </span><span class="sxs-lookup"><span data-stu-id="bada9-378">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-379">每位使用者的聊天室總數</span><span class="sxs-lookup"><span data-stu-id="bada9-379">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-380">16 </span><span class="sxs-lookup"><span data-stu-id="bada9-380">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-381">每位使用者的小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-381">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-382">12 </span><span class="sxs-lookup"><span data-stu-id="bada9-382">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-383">每位使用者的中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-383">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-384">第</span><span class="sxs-lookup"><span data-stu-id="bada9-384">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-385">每位使用者的大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="bada9-385">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-386">第</span><span class="sxs-lookup"><span data-stu-id="bada9-386">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-387">每位使用者加入的會議室數目</span><span class="sxs-lookup"><span data-stu-id="bada9-387">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-388">24</span><span class="sxs-lookup"><span data-stu-id="bada9-388">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-389">尖峰加入速率</span><span class="sxs-lookup"><span data-stu-id="bada9-389">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="bada9-390">10/秒</span><span class="sxs-lookup"><span data-stu-id="bada9-390">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-391">總聊天速率</span><span class="sxs-lookup"><span data-stu-id="bada9-391">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="bada9-392">24/秒</span><span class="sxs-lookup"><span data-stu-id="bada9-392">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-393">小型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="bada9-393">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-394">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="bada9-394">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-395">中型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="bada9-395">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-396">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="bada9-396">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-397">大型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="bada9-397">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="bada9-398">大約 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="bada9-398">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-399">設成傳送邀請的聊天室百分比</span><span class="sxs-lookup"><span data-stu-id="bada9-399">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="bada9-400">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-400">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-401">直接成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="bada9-401">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="bada9-402">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-402">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-403">群組成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="bada9-403">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="bada9-404">50%</span><span class="sxs-lookup"><span data-stu-id="bada9-404">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-405">Active Directory 網域服務中的平均祖先隸屬關係數目</span><span class="sxs-lookup"><span data-stu-id="bada9-405">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="bada9-406">100 - 200</span><span class="sxs-lookup"><span data-stu-id="bada9-406">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-407">每位使用者的已訂閱連絡人數</span><span class="sxs-lookup"><span data-stu-id="bada9-407">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-408">80</span><span class="sxs-lookup"><span data-stu-id="bada9-408">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-409">每位使用者的平均端點數目</span><span class="sxs-lookup"><span data-stu-id="bada9-409">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-410">1.5</span><span class="sxs-lookup"><span data-stu-id="bada9-410">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-411">每個端點的可見聊天室平均數目</span><span class="sxs-lookup"><span data-stu-id="bada9-411">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="bada9-412">1.5</span><span class="sxs-lookup"><span data-stu-id="bada9-412">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-413">每位使用者的可見聊天室平均數目</span><span class="sxs-lookup"><span data-stu-id="bada9-413">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-414">2.25 (50% 的1個會議室和50% 的2個會議室) ;開啟6個會議室，每個監視器一個</span><span class="sxs-lookup"><span data-stu-id="bada9-414">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-415">每段間隔輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="bada9-415">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="bada9-416">每個可見聊天室25個</span><span class="sxs-lookup"><span data-stu-id="bada9-416">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-417">輪詢間隔的長度</span><span class="sxs-lookup"><span data-stu-id="bada9-417">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="bada9-418">5 分鐘</span><span class="sxs-lookup"><span data-stu-id="bada9-418">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-419">每秒輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="bada9-419">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="bada9-420">15,000</span><span class="sxs-lookup"><span data-stu-id="bada9-420">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bada9-421">每位使用者每小時的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="bada9-421">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="bada9-422">6 </span><span class="sxs-lookup"><span data-stu-id="bada9-422">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bada9-423">每秒的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="bada9-423">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="bada9-424">133.33</span><span class="sxs-lookup"><span data-stu-id="bada9-424">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

