---
title: Lync Server 2013： Persistent Chat Server 的容量規劃
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
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512800"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="56ced-102">Lync Server 2013 中的持久聊天伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="56ced-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56ced-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="56ced-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="56ced-104">Persistent Chat Server 可以執行多使用者即時聊天，可保留以供未來檢索及搜尋。</span><span class="sxs-lookup"><span data-stu-id="56ced-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="56ced-105">與群組立即訊息 (IM) 會儲存在使用者的信箱中如果已設定交談記錄，則 Persistent Chat Server 會話會保持開啟的狀態，而且內容會儲存在伺服器上，以及郵件、檔案、URLs 和其他屬於進行中交談的資料。</span><span class="sxs-lookup"><span data-stu-id="56ced-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="56ced-106">容量規劃是準備部署 Persistent Chat Server 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="56ced-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="56ced-107">本主題提供支援的持續性聊天伺服器拓撲及容量規劃表格的詳細資料，您可以用來判斷部署的最佳設定。</span><span class="sxs-lookup"><span data-stu-id="56ced-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="56ced-108">此外，本文也說明如何在高峰時進行需要較高容量的持久聊天伺服器部署的最佳管理。</span><span class="sxs-lookup"><span data-stu-id="56ced-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="56ced-109">若要下載 Persistent Chat Server，請參閱《 Microsoft Lync Server 13 Persistent Chat Server 》，網址為 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。</span><span class="sxs-lookup"><span data-stu-id="56ced-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="56ced-110">如需安裝 Persistent Chat Server 的詳細資訊，請參閱部署檔中的在 lync server [2013 中安裝 Persistent Chat server](lync-server-2013-installing-persistent-chat-server.md) 和設定 [persistent chat server 2013](lync-server-2013-configuring-persistent-chat-server.md) 中的功能。</span><span class="sxs-lookup"><span data-stu-id="56ced-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="56ced-111">支援工具（例如 Lync Server 規劃工具）可進一步協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="56ced-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="56ced-112">如需規劃工具的詳細資訊，請參閱規劃檔中的 [開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md) 。</span><span class="sxs-lookup"><span data-stu-id="56ced-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="56ced-113">Persistent Chat Server 支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="56ced-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="56ced-114">您可以在單一伺服器或多部伺服器集區中部署 Persistent Chat Server，並使用單一集區或多集區拓撲。</span><span class="sxs-lookup"><span data-stu-id="56ced-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="56ced-115">現在，我們也會在 Standard Edition server 上為新的 Lync Server 2013 部署支援 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="56ced-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="56ced-116">不過，效能及規模會受到影響，而且由於這項新的部署沒有高可用性選項，因此我們預計您主要是用來進行概念證明、評估等等的目的。</span><span class="sxs-lookup"><span data-stu-id="56ced-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56ced-117">如需這兩種拓撲的詳細資訊，請參閱部署檔中的 [在 lync Server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 中規劃 Persistent Chat server</A> ] 和 [在 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 中部署 persistent chat server</A> ]。</span><span class="sxs-lookup"><span data-stu-id="56ced-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="56ced-118">單一伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="56ced-118">Single-Server Topology</span></span>

<span data-ttu-id="56ced-119">Persistent Chat Server 的最小設定和最簡單部署是單一持久聊天伺服器前端伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="56ced-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="56ced-120">此部署需要執行 Persistent Chat Server (的單一伺服器，如果符合性已啟用) 、主控 SQL Server 資料庫的伺服器及相容性（若有必要），則會執行該程式，以儲存相容性資料。</span><span class="sxs-lookup"><span data-stu-id="56ced-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56ced-121">您無法將其他伺服器新增至 Persistent Chat Server 集區，此集區在拓撲產生器中以單一伺服器部署的方式啟動。</span><span class="sxs-lookup"><span data-stu-id="56ced-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="56ced-122">我們建議使用多伺服器集區拓撲，即使您使用單一伺服器也是一樣。</span><span class="sxs-lookup"><span data-stu-id="56ced-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="56ced-123">如此一來，您就可以在必要時新增更多的伺服器。</span><span class="sxs-lookup"><span data-stu-id="56ced-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="56ced-124">下圖顯示單一 Persistent Chat Server 前端伺服器及規範的拓撲的所有必要和選用元件。</span><span class="sxs-lookup"><span data-stu-id="56ced-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="56ced-125">**單一常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="56ced-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="56ced-126">![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="56ced-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="56ced-127">多部伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="56ced-127">Multiple-Server Topology</span></span>

<span data-ttu-id="56ced-128">若要提供更大的容量與可靠性，您可以部署多伺服器拓撲，如在 [Lync server 2013 中規劃 Persistent Chat server](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="56ced-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="56ced-129">多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。</span><span class="sxs-lookup"><span data-stu-id="56ced-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="56ced-130">每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。</span><span class="sxs-lookup"><span data-stu-id="56ced-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="56ced-131">多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。</span><span class="sxs-lookup"><span data-stu-id="56ced-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="56ced-132">多部執行 Persistent Chat Server 的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="56ced-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="56ced-133">下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="56ced-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="56ced-134">**多部常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="56ced-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="56ced-135">![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="56ced-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="56ced-136">在四部伺服器的持續聊天伺服器部署中，80000使用者可以同時登入和使用持續性聊天，在每個伺服器的20000使用者之間平均分配負載。</span><span class="sxs-lookup"><span data-stu-id="56ced-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="56ced-137">如果一部伺服器無法使用，連接至該伺服器的使用者將無法存取其 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="56ced-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="56ced-138">連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。</span><span class="sxs-lookup"><span data-stu-id="56ced-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="56ced-139">根據網路上的持續性聊天流量數量，此傳輸可能需要數分鐘或更長的時間。</span><span class="sxs-lookup"><span data-stu-id="56ced-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="56ced-140">因為剩下的每一部伺服器都可能裝載為30000個使用者，所以建議您儘快還原無法使用的伺服器，以避免效能問題。</span><span class="sxs-lookup"><span data-stu-id="56ced-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="56ced-141">否則，您可以使用拓撲產生器或 Windows PowerShell Cmdlet，將另一部 Persistent 聊天伺服器設定為可用， **CsPersistentChatActiveServer**。</span><span class="sxs-lookup"><span data-stu-id="56ced-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="56ced-142">持久聊天伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="56ced-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="56ced-143">下表可協助您使用 Persistent Chat Server 的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="56ced-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="56ced-144">其模型變更各種持久聊天伺服器設定對容量功能的影響。</span><span class="sxs-lookup"><span data-stu-id="56ced-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="56ced-145">規劃 Persistent Chat Server 的最大容量</span><span class="sxs-lookup"><span data-stu-id="56ced-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="56ced-146">使用下列範例表格，來判斷您可以支援的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="56ced-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="56ced-147">Persistent Chat Server 集區的最大容量範例</span><span class="sxs-lookup"><span data-stu-id="56ced-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ced-148">主動 Persistent Chat service 實例</span><span class="sxs-lookup"><span data-stu-id="56ced-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="56ced-149"><em>dmx-4</em></span><span class="sxs-lookup"><span data-stu-id="56ced-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-150">Persistent Chat service 實例</span><span class="sxs-lookup"><span data-stu-id="56ced-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="56ced-151"><em>8 (4 必須是非使用中的;最多隻能使用4個作用中) </em></span><span class="sxs-lookup"><span data-stu-id="56ced-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-152">已連線的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="56ced-153"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="56ced-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-154">布建使用者總數</span><span class="sxs-lookup"><span data-stu-id="56ced-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="56ced-155">150000</span><span class="sxs-lookup"><span data-stu-id="56ced-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-156">端點數目</span><span class="sxs-lookup"><span data-stu-id="56ced-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="56ced-157">120000</span><span class="sxs-lookup"><span data-stu-id="56ced-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="56ced-158">在上述範例中，方案是支援 Persistent Chat Server 所允許的最大使用者數目：「持久聊天」服務 (四個伺服器/實例可以有四個以上的被動式伺服器執行 Persistent Chat Server，以進行高可用性) 和嚴重損壞復原，以及每一部伺服器的20000使用者，共80000個作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="56ced-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="56ced-159">管理持續聊天室存取的容量規劃</span><span class="sxs-lookup"><span data-stu-id="56ced-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="56ced-160">下列範例表可協助您規劃如何在 Persistent Chat Server 集區中管理持續性聊天室存取。</span><span class="sxs-lookup"><span data-stu-id="56ced-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="56ced-161">聊天室存取管理範例</span><span class="sxs-lookup"><span data-stu-id="56ced-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="56ced-162">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-163">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-164">大聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-165">總計</span><span class="sxs-lookup"><span data-stu-id="56ced-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ced-166">聊天室大小 (連接的使用者人數) </span><span class="sxs-lookup"><span data-stu-id="56ced-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="56ced-167">每個會議室30個</span><span class="sxs-lookup"><span data-stu-id="56ced-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="56ced-168">每個會議室150</span><span class="sxs-lookup"><span data-stu-id="56ced-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="56ced-169">每個會議室16000</span><span class="sxs-lookup"><span data-stu-id="56ced-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-170">聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-171">32000</span><span class="sxs-lookup"><span data-stu-id="56ced-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-172">1067</span><span class="sxs-lookup"><span data-stu-id="56ced-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="56ced-173">10 </span><span class="sxs-lookup"><span data-stu-id="56ced-173">10</span></span></p></td>
<td><p><span data-ttu-id="56ced-174">33077</span><span class="sxs-lookup"><span data-stu-id="56ced-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-175">視聽中心的會議室%</span><span class="sxs-lookup"><span data-stu-id="56ced-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="56ced-176">1</span><span class="sxs-lookup"><span data-stu-id="56ced-176">1%</span></span></p></td>
<td><p><span data-ttu-id="56ced-177">1</span><span class="sxs-lookup"><span data-stu-id="56ced-177">1%</span></span></p></td>
<td><p><span data-ttu-id="56ced-178">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-179">開啟的會議室%</span><span class="sxs-lookup"><span data-stu-id="56ced-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="56ced-180">個</span><span class="sxs-lookup"><span data-stu-id="56ced-180">3%</span></span></p></td>
<td><p><span data-ttu-id="56ced-181">個</span><span class="sxs-lookup"><span data-stu-id="56ced-181">3%</span></span></p></td>
<td><p><span data-ttu-id="56ced-182">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-183">開啟會議室 (沒有明確的成員資格) </span><span class="sxs-lookup"><span data-stu-id="56ced-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="56ced-184">960</span><span class="sxs-lookup"><span data-stu-id="56ced-184">960</span></span></p></td>
<td><p><span data-ttu-id="56ced-185">32</span><span class="sxs-lookup"><span data-stu-id="56ced-185">32</span></span></p></td>
<td><p><span data-ttu-id="56ced-186">5 </span><span class="sxs-lookup"><span data-stu-id="56ced-186">5</span></span></p></td>
<td><p><span data-ttu-id="56ced-187">997</span><span class="sxs-lookup"><span data-stu-id="56ced-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-188">使用明確成員資格的非開啟聊天室 (一般會議室) </span><span class="sxs-lookup"><span data-stu-id="56ced-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="56ced-189">31040</span><span class="sxs-lookup"><span data-stu-id="56ced-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="56ced-190">1.035</span><span class="sxs-lookup"><span data-stu-id="56ced-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="56ced-191">5 </span><span class="sxs-lookup"><span data-stu-id="56ced-191">5</span></span></p></td>
<td><p><span data-ttu-id="56ced-192">32080</span><span class="sxs-lookup"><span data-stu-id="56ced-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-193">視聽中心聊天室 (其他簡報者專案) </span><span class="sxs-lookup"><span data-stu-id="56ced-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="56ced-194">0</span><span class="sxs-lookup"><span data-stu-id="56ced-194">0</span></span></p></td>
<td><p><span data-ttu-id="56ced-195">32</span><span class="sxs-lookup"><span data-stu-id="56ced-195">32</span></span></p></td>
<td><p><span data-ttu-id="56ced-196">5 </span><span class="sxs-lookup"><span data-stu-id="56ced-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-197">由直接成員資格管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="56ced-198">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-198">50%</span></span></p></td>
<td><p><span data-ttu-id="56ced-199">十進位</span><span class="sxs-lookup"><span data-stu-id="56ced-199">10%</span></span></p></td>
<td><p><span data-ttu-id="56ced-200">0</span><span class="sxs-lookup"><span data-stu-id="56ced-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-201">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="56ced-202">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-202">50%</span></span></p></td>
<td><p><span data-ttu-id="56ced-203">90%</span><span class="sxs-lookup"><span data-stu-id="56ced-203">90%</span></span></p></td>
<td><p><span data-ttu-id="56ced-204">100%</span><span class="sxs-lookup"><span data-stu-id="56ced-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-205">開啟之聊天室之每個聊天室的成員資格清單中的使用者群組 (未明確指定) </span><span class="sxs-lookup"><span data-stu-id="56ced-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="56ced-206">0</span><span class="sxs-lookup"><span data-stu-id="56ced-206">0</span></span></p></td>
<td><p><span data-ttu-id="56ced-207">0</span><span class="sxs-lookup"><span data-stu-id="56ced-207">0</span></span></p></td>
<td><p><span data-ttu-id="56ced-208">0</span><span class="sxs-lookup"><span data-stu-id="56ced-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-209">非開啟會議室之每個聊天室成員資格清單中的使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-210">大約</span><span class="sxs-lookup"><span data-stu-id="56ced-210">30</span></span></p></td>
<td><p><span data-ttu-id="56ced-211">150</span><span class="sxs-lookup"><span data-stu-id="56ced-211">150</span></span></p></td>
<td><p><span data-ttu-id="56ced-212">16000</span><span class="sxs-lookup"><span data-stu-id="56ced-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-213">非開啟會議室之每個聊天室成員資格清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="56ced-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-214">個</span><span class="sxs-lookup"><span data-stu-id="56ced-214">3</span></span></p></td>
<td><p><span data-ttu-id="56ced-215">5 </span><span class="sxs-lookup"><span data-stu-id="56ced-215">5</span></span></p></td>
<td><p><span data-ttu-id="56ced-216">10 </span><span class="sxs-lookup"><span data-stu-id="56ced-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-217">每個聊天室的管理員清單中的使用者與使用者群組 (開放和非開啟的會議室) </span><span class="sxs-lookup"><span data-stu-id="56ced-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="56ced-218">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-218">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-219">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-219">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-220">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-221">每個視聽中心聊天室的簡報者清單中的使用者與使用者群組 (開啟和非開啟的會議室) </span><span class="sxs-lookup"><span data-stu-id="56ced-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="56ced-222">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-222">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-223">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-223">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-224">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-225">跨所有非開啟聊天室的使用者型成員資格實體</span><span class="sxs-lookup"><span data-stu-id="56ced-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-226">465600</span><span class="sxs-lookup"><span data-stu-id="56ced-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="56ced-227">15520</span><span class="sxs-lookup"><span data-stu-id="56ced-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-228">跨所有非開啟會議室的使用者群組型成員資格實體</span><span class="sxs-lookup"><span data-stu-id="56ced-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-229">46560</span><span class="sxs-lookup"><span data-stu-id="56ced-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="56ced-230">4656</span><span class="sxs-lookup"><span data-stu-id="56ced-230">4656</span></span></p></td>
<td><p><span data-ttu-id="56ced-231">50</span><span class="sxs-lookup"><span data-stu-id="56ced-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-232">所有視聽中心聊天室中的使用者和使用者群組基礎實體</span><span class="sxs-lookup"><span data-stu-id="56ced-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-233">0</span><span class="sxs-lookup"><span data-stu-id="56ced-233">0</span></span></p></td>
<td><p><span data-ttu-id="56ced-234">192</span><span class="sxs-lookup"><span data-stu-id="56ced-234">192</span></span></p></td>
<td><p><span data-ttu-id="56ced-235">50</span><span class="sxs-lookup"><span data-stu-id="56ced-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-236">所有聊天室管理員清單中的使用者與使用者群組管理員實體</span><span class="sxs-lookup"><span data-stu-id="56ced-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="56ced-237">192000</span><span class="sxs-lookup"><span data-stu-id="56ced-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-238">6400</span><span class="sxs-lookup"><span data-stu-id="56ced-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="56ced-239">60</span><span class="sxs-lookup"><span data-stu-id="56ced-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-240">每個聊天室的作用中使用者數</span><span class="sxs-lookup"><span data-stu-id="56ced-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="56ced-241"><em>大約</em></span><span class="sxs-lookup"><span data-stu-id="56ced-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="56ced-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="56ced-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-244">每位使用者的聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-245"><em>英寸</em></span><span class="sxs-lookup"><span data-stu-id="56ced-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="56ced-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="56ced-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="56ced-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-249">每個聊天室之成員資格清單中的使用者群組數</span><span class="sxs-lookup"><span data-stu-id="56ced-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="56ced-250"><em>十進位</em></span><span class="sxs-lookup"><span data-stu-id="56ced-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-251"><em>十進位</em></span><span class="sxs-lookup"><span data-stu-id="56ced-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-252"><em>8</em></span><span class="sxs-lookup"><span data-stu-id="56ced-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-253">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="56ced-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="56ced-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="56ced-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="56ced-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-257">所有聊天室的使用者群組型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="56ced-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-258">155200</span><span class="sxs-lookup"><span data-stu-id="56ced-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="56ced-259">5173</span><span class="sxs-lookup"><span data-stu-id="56ced-259">5173</span></span></p></td>
<td><p><span data-ttu-id="56ced-260">68</span><span class="sxs-lookup"><span data-stu-id="56ced-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-261">所有聊天室的使用者型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="56ced-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-262">465600</span><span class="sxs-lookup"><span data-stu-id="56ced-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="56ced-263">77600</span><span class="sxs-lookup"><span data-stu-id="56ced-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="56ced-264">72000</span><span class="sxs-lookup"><span data-stu-id="56ced-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-265">每個聊天室的管理員、簡報者和範圍清單中的使用者與使用者群組數</span><span class="sxs-lookup"><span data-stu-id="56ced-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="56ced-266">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-266">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-267">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-267">6</span></span></p></td>
<td><p><span data-ttu-id="56ced-268">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-269">所有聊天室的管理員、簡報者和範圍清單之間的使用者和使用者群組</span><span class="sxs-lookup"><span data-stu-id="56ced-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="56ced-270">192000</span><span class="sxs-lookup"><span data-stu-id="56ced-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-271">6400</span><span class="sxs-lookup"><span data-stu-id="56ced-271">6400</span></span></p></td>
<td><p><span data-ttu-id="56ced-272">60</span><span class="sxs-lookup"><span data-stu-id="56ced-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-273">存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="56ced-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="56ced-274">704160</span><span class="sxs-lookup"><span data-stu-id="56ced-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="56ced-275">26768</span><span class="sxs-lookup"><span data-stu-id="56ced-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="56ced-276">160</span><span class="sxs-lookup"><span data-stu-id="56ced-276">160</span></span></p></td>
<td><p><span data-ttu-id="56ced-277">731088</span><span class="sxs-lookup"><span data-stu-id="56ced-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-278">最大存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="56ced-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="56ced-279">2000000</span><span class="sxs-lookup"><span data-stu-id="56ced-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="56ced-280">在上述範例中，當您根據建議的指導方針來部署 Persistent Chat server 時，可在啟用規範的情況下，處理跨越四個伺服器集區的最多80000個活躍使用者。</span><span class="sxs-lookup"><span data-stu-id="56ced-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="56ced-281">這個範例會顯示在任何指定時間) 、中型 (150 作用中使用者) 及大型 (16000 作用中使用者) ，歸類為小型 (30 作用中使用者的聊天室。</span><span class="sxs-lookup"><span data-stu-id="56ced-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="56ced-282">特定大小聊天室的數目是依下列項目的總數計算而來：</span><span class="sxs-lookup"><span data-stu-id="56ced-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="56ced-283">系統中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-283">Active users in the system</span></span>

  - <span data-ttu-id="56ced-284">特定大小聊天室中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="56ced-285">單一使用者加入的特定大小聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="56ced-286">針對每個聊天室，先前的容量規劃表格會指定與聊天室相關聯的存取控制專案數目（包括直接指派給聊天室的專案）。</span><span class="sxs-lookup"><span data-stu-id="56ced-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="56ced-287">您可以使用存取控制清單 (ACL)，控制對個別聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="56ced-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="56ced-288">您也可以在類別層級控制存取。</span><span class="sxs-lookup"><span data-stu-id="56ced-288">You can also control access at the category level.</span></span> <span data-ttu-id="56ced-289">在 ACL 中，個別的存取控制專案可以是使用者群組（例如，安全性群組、通訊群組清單或單一使用者）。</span><span class="sxs-lookup"><span data-stu-id="56ced-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="56ced-290">您可以定義聊天室管理員、簡報者和成員的存取控制項目。</span><span class="sxs-lookup"><span data-stu-id="56ced-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56ced-291">在規劃管理聊天室的策略時，請記住允許的存取控制專案總數為2000000。</span><span class="sxs-lookup"><span data-stu-id="56ced-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="56ced-292">如果計算出的存取控制專案超過2000000，伺服器效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="56ced-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="56ced-293">若要避免此問題，請盡可能確定您的存取控制專案是使用者群組，而非個別使用者。</span><span class="sxs-lookup"><span data-stu-id="56ced-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="56ced-294">邀請式聊天室存取的容量管理規劃</span><span class="sxs-lookup"><span data-stu-id="56ced-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="56ced-295">您可以使用下列容量規劃表格來瞭解 Persistent Chat Server 在設定成傳送邀請時，在 Persistent Chat 資料庫中建立及儲存的邀請數目。</span><span class="sxs-lookup"><span data-stu-id="56ced-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="56ced-296">您可以使用 Lync Server 控制台中的 **聊天室類別設定** 頁面或使用 Windows PowerShell Cmdlet **CsPersistentChatCategory**，管理類別上的邀請。</span><span class="sxs-lookup"><span data-stu-id="56ced-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="56ced-297">您可以使用 Lync 用戶端（或使用 Windows PowerShell Cmdlet）從 Lync 用戶端（ **clear-cspersistentchatroom**）中所) 提供的「**會議室管理**」頁面來管理聊天室上的邀請函 (線上。</span><span class="sxs-lookup"><span data-stu-id="56ced-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="56ced-298">下表中的範例資料假設，在 [ **聊天室設定** ] 頁面上的50% 的所有聊天室中，[ **邀請** ] 選項會設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="56ced-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56ced-299">如果伺服器所產生之邀請數目的計算值超過1000000，伺服器效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="56ced-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="56ced-300">若要避免此問題，請確定您將設定為傳送邀請的聊天室數目降至最低，或限制可加入已設定為傳送邀請之聊天室的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="56ced-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="56ced-301">邀請式聊天室存取範例</span><span class="sxs-lookup"><span data-stu-id="56ced-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="56ced-302">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-303">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-304">大聊天室</span><span class="sxs-lookup"><span data-stu-id="56ced-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="56ced-305">總計</span><span class="sxs-lookup"><span data-stu-id="56ced-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ced-306">可以存取聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="56ced-307">每個會議室30個</span><span class="sxs-lookup"><span data-stu-id="56ced-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="56ced-308">每個會議室150</span><span class="sxs-lookup"><span data-stu-id="56ced-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="56ced-309">每個會議室16000</span><span class="sxs-lookup"><span data-stu-id="56ced-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-310">具有邀請的會議室百分比</span><span class="sxs-lookup"><span data-stu-id="56ced-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="56ced-311">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-311">50%</span></span></p></td>
<td><p><span data-ttu-id="56ced-312">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-312">50%</span></span></p></td>
<td><p><span data-ttu-id="56ced-313">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-314">設成傳送邀請的聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="56ced-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="56ced-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="56ced-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-317"><em>位</em></span><span class="sxs-lookup"><span data-stu-id="56ced-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-318">可以存取該聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="56ced-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="56ced-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="56ced-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="56ced-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="56ced-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-322">Persistent Chat Server 產生的邀請</span><span class="sxs-lookup"><span data-stu-id="56ced-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="56ced-323">960000</span><span class="sxs-lookup"><span data-stu-id="56ced-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-324">120000</span><span class="sxs-lookup"><span data-stu-id="56ced-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-325">80000</span><span class="sxs-lookup"><span data-stu-id="56ced-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="56ced-326">1160000</span><span class="sxs-lookup"><span data-stu-id="56ced-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-327">最大允許的邀請數</span><span class="sxs-lookup"><span data-stu-id="56ced-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="56ced-328">2000000</span><span class="sxs-lookup"><span data-stu-id="56ced-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-329">模型 1-以預期的每天每個會議室的郵件數目為起始單位</span><span class="sxs-lookup"><span data-stu-id="56ced-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-330">每個會議室 (每日聊天速度) </span><span class="sxs-lookup"><span data-stu-id="56ced-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="56ced-331">50</span><span class="sxs-lookup"><span data-stu-id="56ced-331">50</span></span></p></td>
<td><p><span data-ttu-id="56ced-332">500</span><span class="sxs-lookup"><span data-stu-id="56ced-332">500</span></span></p></td>
<td><p><span data-ttu-id="56ced-333">100</span><span class="sxs-lookup"><span data-stu-id="56ced-333">100</span></span></p></td>
<td><p><span data-ttu-id="56ced-334">650</span><span class="sxs-lookup"><span data-stu-id="56ced-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-335">所有會議室每秒 (的交談率) </span><span class="sxs-lookup"><span data-stu-id="56ced-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-336">55.56</span><span class="sxs-lookup"><span data-stu-id="56ced-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="56ced-337">18.52</span><span class="sxs-lookup"><span data-stu-id="56ced-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="56ced-338">0.03</span><span class="sxs-lookup"><span data-stu-id="56ced-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="56ced-339">74</span><span class="sxs-lookup"><span data-stu-id="56ced-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-340">模型 2-從每位使用者每天發佈的郵件數目開始</span><span class="sxs-lookup"><span data-stu-id="56ced-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-341">每天每位使用者的聊天室速度</span><span class="sxs-lookup"><span data-stu-id="56ced-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="56ced-342">15 </span><span class="sxs-lookup"><span data-stu-id="56ced-342">15</span></span></p></td>
<td><p><span data-ttu-id="56ced-343">5 </span><span class="sxs-lookup"><span data-stu-id="56ced-343">5</span></span></p></td>
<td><p><span data-ttu-id="56ced-344">0.1</span><span class="sxs-lookup"><span data-stu-id="56ced-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="56ced-345">共</span><span class="sxs-lookup"><span data-stu-id="56ced-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-346">每個會議室 (每日聊天速度) </span><span class="sxs-lookup"><span data-stu-id="56ced-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="56ced-347">38</span><span class="sxs-lookup"><span data-stu-id="56ced-347">38</span></span></p></td>
<td><p><span data-ttu-id="56ced-348">375</span><span class="sxs-lookup"><span data-stu-id="56ced-348">375</span></span></p></td>
<td><p><span data-ttu-id="56ced-349">800</span><span class="sxs-lookup"><span data-stu-id="56ced-349">800</span></span></p></td>
<td><p><span data-ttu-id="56ced-350">1213</span><span class="sxs-lookup"><span data-stu-id="56ced-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-351">所有會議室每秒 (的交談率) </span><span class="sxs-lookup"><span data-stu-id="56ced-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-352">41.67</span><span class="sxs-lookup"><span data-stu-id="56ced-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="56ced-353">13.89</span><span class="sxs-lookup"><span data-stu-id="56ced-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="56ced-354">0.28</span><span class="sxs-lookup"><span data-stu-id="56ced-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="56ced-355">56</span><span class="sxs-lookup"><span data-stu-id="56ced-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="56ced-356">Persistent Chat Server 效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="56ced-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="56ced-357">下表說明 Persistent Chat Server 的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="56ced-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="56ced-358">它會提供容量規劃需求的基礎，並代表四部伺服器上具有80000並行使用者的一般組織。</span><span class="sxs-lookup"><span data-stu-id="56ced-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="56ced-359">Persistent Chat Server 效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="56ced-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ced-360">連接的使用中使用者數目</span><span class="sxs-lookup"><span data-stu-id="56ced-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="56ced-361">80000</span><span class="sxs-lookup"><span data-stu-id="56ced-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-362">Persistent Chat Server 服務實例數目</span><span class="sxs-lookup"><span data-stu-id="56ced-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="56ced-363">4 </span><span class="sxs-lookup"><span data-stu-id="56ced-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-364">小型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="56ced-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-365">30 位使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-366">中型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="56ced-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-367">150 位使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-368">大型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="56ced-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-369">16000使用者</span><span class="sxs-lookup"><span data-stu-id="56ced-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-370">聊天室總數</span><span class="sxs-lookup"><span data-stu-id="56ced-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-371">33077</span><span class="sxs-lookup"><span data-stu-id="56ced-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-372">小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-373">32000</span><span class="sxs-lookup"><span data-stu-id="56ced-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-374">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-375">1067</span><span class="sxs-lookup"><span data-stu-id="56ced-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-376">大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-377">10 </span><span class="sxs-lookup"><span data-stu-id="56ced-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-378">每位使用者的聊天室總數</span><span class="sxs-lookup"><span data-stu-id="56ced-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-379">16 </span><span class="sxs-lookup"><span data-stu-id="56ced-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-380">每位使用者的小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-381">12 </span><span class="sxs-lookup"><span data-stu-id="56ced-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-382">每位使用者的中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-383">第</span><span class="sxs-lookup"><span data-stu-id="56ced-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-384">每位使用者的大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="56ced-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-385">第</span><span class="sxs-lookup"><span data-stu-id="56ced-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-386">每位使用者加入的會議室數目</span><span class="sxs-lookup"><span data-stu-id="56ced-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-387">24</span><span class="sxs-lookup"><span data-stu-id="56ced-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-388">尖峰加入速率</span><span class="sxs-lookup"><span data-stu-id="56ced-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="56ced-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="56ced-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-390">總聊天速率</span><span class="sxs-lookup"><span data-stu-id="56ced-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="56ced-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="56ced-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-392">小型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="56ced-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-393">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="56ced-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-394">中型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="56ced-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-395">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="56ced-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-396">大型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="56ced-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="56ced-397">大約 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="56ced-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-398">設成傳送邀請的聊天室百分比</span><span class="sxs-lookup"><span data-stu-id="56ced-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="56ced-399">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-400">直接成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="56ced-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="56ced-401">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-402">群組成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="56ced-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="56ced-403">50%</span><span class="sxs-lookup"><span data-stu-id="56ced-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-404">Active Directory 網域服務中的平均祖先隸屬關係數目</span><span class="sxs-lookup"><span data-stu-id="56ced-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="56ced-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="56ced-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-406">每位使用者的已訂閱連絡人數</span><span class="sxs-lookup"><span data-stu-id="56ced-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-407">80</span><span class="sxs-lookup"><span data-stu-id="56ced-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-408">每位使用者的平均端點數目</span><span class="sxs-lookup"><span data-stu-id="56ced-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-409">1.5</span><span class="sxs-lookup"><span data-stu-id="56ced-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-410">每個端點的可見聊天室平均數目</span><span class="sxs-lookup"><span data-stu-id="56ced-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="56ced-411">1.5</span><span class="sxs-lookup"><span data-stu-id="56ced-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-412">每位使用者的可見聊天室平均數目</span><span class="sxs-lookup"><span data-stu-id="56ced-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-413">2.25 (50% 的1個會議室和50% 的2個會議室) ;開啟6個會議室，每個監視器一個</span><span class="sxs-lookup"><span data-stu-id="56ced-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-414">每段間隔輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="56ced-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="56ced-415">每個可見聊天室25個</span><span class="sxs-lookup"><span data-stu-id="56ced-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-416">輪詢間隔的長度</span><span class="sxs-lookup"><span data-stu-id="56ced-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="56ced-417">5 分鐘</span><span class="sxs-lookup"><span data-stu-id="56ced-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-418">每秒輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="56ced-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="56ced-419">15,000</span><span class="sxs-lookup"><span data-stu-id="56ced-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ced-420">每位使用者每小時的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="56ced-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="56ced-421">6 </span><span class="sxs-lookup"><span data-stu-id="56ced-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ced-422">每秒的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="56ced-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="56ced-423">133.33</span><span class="sxs-lookup"><span data-stu-id="56ced-423">133.33</span></span></p></td>
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

