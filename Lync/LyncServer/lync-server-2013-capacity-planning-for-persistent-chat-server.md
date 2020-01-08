---
title: Lync Server 2013：持久聊天伺服器的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d6038-102">Lync Server 2013 中持續聊天伺服器的容量規劃</span><span class="sxs-lookup"><span data-stu-id="d6038-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6038-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d6038-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d6038-104">持續聊天伺服器可以執行多使用者即時聊天，以供日後檢索和搜尋。</span><span class="sxs-lookup"><span data-stu-id="d6038-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="d6038-105">與儲存在使用者信箱中的群組立即訊息（IM），如果已設定交談歷程記錄，持續聊天伺服器會話會保持開啟，且內容會儲存在伺服器上，以及郵件、檔案、Url 及其他屬於該部分的資料正在進行中的交談。</span><span class="sxs-lookup"><span data-stu-id="d6038-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="d6038-106">容量規劃是準備部署持久聊天伺服器的重要部分。</span><span class="sxs-lookup"><span data-stu-id="d6038-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="d6038-107">本主題提供支援的持續聊天伺服器拓撲和容量規劃資料表的詳細資料，您可以使用這些表格來判斷部署的最佳配置。</span><span class="sxs-lookup"><span data-stu-id="d6038-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="d6038-108">它也說明如何最好地管理在高峰時間需要較大容量的持久聊天伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="d6038-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="d6038-109">若要下載持續聊天伺服器，請參閱「Microsoft Lync Server 13 永久聊天伺服器[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)」。</span><span class="sxs-lookup"><span data-stu-id="d6038-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="d6038-110">如需安裝持久聊天伺服器的詳細資訊，請參閱在[Lync server 2013 中安裝永久性聊天伺服器](lync-server-2013-installing-persistent-chat-server.md)，以及在部署檔中的[lync server 2013 中設定持續聊天伺服器](lync-server-2013-configuring-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d6038-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="d6038-111">支援工具（例如 Lync Server 規劃工具）可以進一步協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="d6038-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="d6038-112">如需規劃工具的詳細資訊，請參閱在規劃檔中[開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md)。</span><span class="sxs-lookup"><span data-stu-id="d6038-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="d6038-113">持續聊天伺服器支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="d6038-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="d6038-114">您可以在單一伺服器或多重伺服器池中部署持久聊天伺服器，以及使用單一池或多池拓撲。</span><span class="sxs-lookup"><span data-stu-id="d6038-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="d6038-115">我們現在還支援適用于新 Lync Server 2013 部署的標準版 server 上的持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6038-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="d6038-116">不過，效能和規模會受到影響，而且由於這項新的部署沒有高可用性選項，因此我們希望您主要使用這個方法來進行概念驗證、評估等。</span><span class="sxs-lookup"><span data-stu-id="d6038-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6038-117">如需這兩個拓朴的其他詳細資料，請參閱本檔中的 [在<A href="lync-server-2013-planning-for-persistent-chat-server.md">lync server 2013 中規劃持久聊天伺服器</A>]，並在 [部署] 檔中設定<A href="lync-server-2013-deploying-persistent-chat-server.md">lync server 2013 中的持續聊天伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="d6038-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="d6038-118">單伺服器拓朴</span><span class="sxs-lookup"><span data-stu-id="d6038-118">Single-Server Topology</span></span>

<span data-ttu-id="d6038-119">持續聊天伺服器的最小設定和最簡單的部署是單一持續式聊天伺服器前端伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="d6038-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="d6038-120">此部署需要單一伺服器來執行持續聊天伺服器（如果相容性已啟用，也可選擇執行合規性服務）、託管 SQL Server 資料庫的伺服器，以及如果需要合規性，則是 SQL Server 資料庫來儲存合規性資料。</span><span class="sxs-lookup"><span data-stu-id="d6038-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6038-121">您無法將其他伺服器新增至永久聊天伺服器池中，該池是在拓撲建立器中以單一伺服器部署的形式啟動。</span><span class="sxs-lookup"><span data-stu-id="d6038-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="d6038-122">我們建議您使用多重伺服器池拓撲結構，即使您使用的是單一伺服器也一樣。</span><span class="sxs-lookup"><span data-stu-id="d6038-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="d6038-123">如此一來，您稍後就可以新增更多伺服器（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="d6038-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="d6038-124">下圖顯示單一持續聊天伺服器前端伺服器（符合合規性）的所有必要和選用元件。</span><span class="sxs-lookup"><span data-stu-id="d6038-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="d6038-125">**單一持久聊天伺服器**</span><span class="sxs-lookup"><span data-stu-id="d6038-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="d6038-126">![單一伺服器拓朴與合規性服務](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "單一伺服器拓撲（含合規性服務")）</span><span class="sxs-lookup"><span data-stu-id="d6038-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="d6038-127">多重伺服器拓朴</span><span class="sxs-lookup"><span data-stu-id="d6038-127">Multiple-Server Topology</span></span>

<span data-ttu-id="d6038-128">若要提供更大的容量及可靠性，您可以部署多伺服器拓朴，如在[Lync server 2013 規劃持續聊天伺服器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="d6038-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="d6038-129">多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦（高可用性和災害復原設定允許最多八個，但只有四個作用中的4個作用中，還有四個作用中的四個）。</span><span class="sxs-lookup"><span data-stu-id="d6038-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="d6038-130">每個伺服器可支援多達20000並行的使用者，總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="d6038-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="d6038-131">多重伺服器拓朴與單一伺服器拓朴一樣，只是多個伺服器主機持久的聊天伺服器，而且可以擴大規模。</span><span class="sxs-lookup"><span data-stu-id="d6038-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="d6038-132">多台執行持續聊天伺服器的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="d6038-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="d6038-133">下圖顯示多伺服器拓朴中的所有元件，其中多台電腦執行持續聊天伺服器、選用規範服務，以及個別的合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="d6038-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="d6038-134">**多個持續聊天伺服器**</span><span class="sxs-lookup"><span data-stu-id="d6038-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="d6038-135">![多個伺服器拓撲]結構(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多個伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="d6038-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="d6038-136">在四伺服器持續式聊天伺服器部署中，80000使用者可以同時登入並使用持續聊天，在每個伺服器上，都會將負載平均分佈在20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="d6038-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="d6038-137">如果一個伺服器無法使用，則連接至該伺服器的使用者將無法存取永久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6038-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="d6038-138">已中斷連線的使用者會自動轉移到其餘的伺服器，直到無法還原無法使用的伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="d6038-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="d6038-139">根據網路上持久聊天流量的數量，此傳輸可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="d6038-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="d6038-140">因為其餘的每個伺服器都可能會裝載許多30000的使用者，所以建議您儘快還原無法使用的伺服器，以免發生效能問題。</span><span class="sxs-lookup"><span data-stu-id="d6038-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="d6038-141">否則，您可以使用 [拓撲建立器] 或 [Windows PowerShell Cmdlet]，將另一個持久聊天伺服器設為可用，請**CsPersistentChatActiveServer**。</span><span class="sxs-lookup"><span data-stu-id="d6038-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="d6038-142">持續聊天伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="d6038-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="d6038-143">下清單格可協助您使用持續式聊天伺服器的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="d6038-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="d6038-144">其模型變更各種持續聊天伺服器設定對容量功能有何影響。</span><span class="sxs-lookup"><span data-stu-id="d6038-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="d6038-145">規劃持久聊天伺服器的最大容量</span><span class="sxs-lookup"><span data-stu-id="d6038-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="d6038-146">使用下列範例表格來判斷您將能支援的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="d6038-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="d6038-147">持續聊天伺服器池最大容量範例</span><span class="sxs-lookup"><span data-stu-id="d6038-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6038-148">活躍持續聊天服務實例</span><span class="sxs-lookup"><span data-stu-id="d6038-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="d6038-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="d6038-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-150">持續聊天服務實例</span><span class="sxs-lookup"><span data-stu-id="d6038-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="d6038-151"><em>8（4必須是非使用中，最多隻能啟用4個）</em></span><span class="sxs-lookup"><span data-stu-id="d6038-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-152">已連線的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="d6038-153"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="d6038-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-154">已置備的使用者總數</span><span class="sxs-lookup"><span data-stu-id="d6038-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="d6038-155">150000</span><span class="sxs-lookup"><span data-stu-id="d6038-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-156">端點的數目</span><span class="sxs-lookup"><span data-stu-id="d6038-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="d6038-157">120000</span><span class="sxs-lookup"><span data-stu-id="d6038-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6038-158">在前面的範例中，方案是支援持續聊天伺服器允許的使用者數目上限：四個伺服器/每個版本的持續聊天服務（可以有四個待命伺服器執行持久聊天伺服器，以提供高可用性和災難復原），以及每個伺服器的20000使用者（共80000個作用中的使用者）。</span><span class="sxs-lookup"><span data-stu-id="d6038-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="d6038-159">管理持續聊天室存取的容量規劃</span><span class="sxs-lookup"><span data-stu-id="d6038-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="d6038-160">下列範例表格可協助您規劃如何在持續聊天伺服器池中管理持續性聊天室存取。</span><span class="sxs-lookup"><span data-stu-id="d6038-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="d6038-161">管理聊天室存取範例</span><span class="sxs-lookup"><span data-stu-id="d6038-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="d6038-162">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-163">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-164">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-165">總額</span><span class="sxs-lookup"><span data-stu-id="d6038-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6038-166">聊天室的大小（已連接的使用者數目）</span><span class="sxs-lookup"><span data-stu-id="d6038-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="d6038-167">每個房間30個</span><span class="sxs-lookup"><span data-stu-id="d6038-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="d6038-168">每個房間150</span><span class="sxs-lookup"><span data-stu-id="d6038-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="d6038-169">每個房間16000</span><span class="sxs-lookup"><span data-stu-id="d6038-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-170">聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-171">32000</span><span class="sxs-lookup"><span data-stu-id="d6038-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-172">1067</span><span class="sxs-lookup"><span data-stu-id="d6038-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="d6038-173">第</span><span class="sxs-lookup"><span data-stu-id="d6038-173">10</span></span></p></td>
<td><p><span data-ttu-id="d6038-174">33077</span><span class="sxs-lookup"><span data-stu-id="d6038-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-175">auditorium 的會議室%</span><span class="sxs-lookup"><span data-stu-id="d6038-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="d6038-176">sr-1</span><span class="sxs-lookup"><span data-stu-id="d6038-176">1%</span></span></p></td>
<td><p><span data-ttu-id="d6038-177">sr-1</span><span class="sxs-lookup"><span data-stu-id="d6038-177">1%</span></span></p></td>
<td><p><span data-ttu-id="d6038-178">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-179">開啟的會議室%</span><span class="sxs-lookup"><span data-stu-id="d6038-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="d6038-180">3</span><span class="sxs-lookup"><span data-stu-id="d6038-180">3%</span></span></p></td>
<td><p><span data-ttu-id="d6038-181">3</span><span class="sxs-lookup"><span data-stu-id="d6038-181">3%</span></span></p></td>
<td><p><span data-ttu-id="d6038-182">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-183">開啟會議室（無明確成員資格）</span><span class="sxs-lookup"><span data-stu-id="d6038-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="d6038-184">960</span><span class="sxs-lookup"><span data-stu-id="d6038-184">960</span></span></p></td>
<td><p><span data-ttu-id="d6038-185">32</span><span class="sxs-lookup"><span data-stu-id="d6038-185">32</span></span></p></td>
<td><p><span data-ttu-id="d6038-186">500</span><span class="sxs-lookup"><span data-stu-id="d6038-186">5</span></span></p></td>
<td><p><span data-ttu-id="d6038-187">997</span><span class="sxs-lookup"><span data-stu-id="d6038-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-188">未開啟的會議室（具有明確成員資格的一般聊天室）</span><span class="sxs-lookup"><span data-stu-id="d6038-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="d6038-189">31040</span><span class="sxs-lookup"><span data-stu-id="d6038-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="d6038-190">1.035</span><span class="sxs-lookup"><span data-stu-id="d6038-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="d6038-191">500</span><span class="sxs-lookup"><span data-stu-id="d6038-191">5</span></span></p></td>
<td><p><span data-ttu-id="d6038-192">32080</span><span class="sxs-lookup"><span data-stu-id="d6038-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-193">Auditorium 會議室（其他簡報者專案）</span><span class="sxs-lookup"><span data-stu-id="d6038-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="d6038-194">0</span><span class="sxs-lookup"><span data-stu-id="d6038-194">0</span></span></p></td>
<td><p><span data-ttu-id="d6038-195">32</span><span class="sxs-lookup"><span data-stu-id="d6038-195">32</span></span></p></td>
<td><p><span data-ttu-id="d6038-196">500</span><span class="sxs-lookup"><span data-stu-id="d6038-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-197">由直接成員資格管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="d6038-198">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-198">50%</span></span></p></td>
<td><p><span data-ttu-id="d6038-199">第</span><span class="sxs-lookup"><span data-stu-id="d6038-199">10%</span></span></p></td>
<td><p><span data-ttu-id="d6038-200">0</span><span class="sxs-lookup"><span data-stu-id="d6038-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-201">由使用者群組管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="d6038-202">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-202">50%</span></span></p></td>
<td><p><span data-ttu-id="d6038-203">90%</span><span class="sxs-lookup"><span data-stu-id="d6038-203">90%</span></span></p></td>
<td><p><span data-ttu-id="d6038-204">100%</span><span class="sxs-lookup"><span data-stu-id="d6038-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-205">每個聊天室的成員清單中的使用者群組（未明確指定）</span><span class="sxs-lookup"><span data-stu-id="d6038-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="d6038-206">0</span><span class="sxs-lookup"><span data-stu-id="d6038-206">0</span></span></p></td>
<td><p><span data-ttu-id="d6038-207">0</span><span class="sxs-lookup"><span data-stu-id="d6038-207">0</span></span></p></td>
<td><p><span data-ttu-id="d6038-208">0</span><span class="sxs-lookup"><span data-stu-id="d6038-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-209">每個聊天室的每個聊天室的成員資格清單中的使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-210">為期</span><span class="sxs-lookup"><span data-stu-id="d6038-210">30</span></span></p></td>
<td><p><span data-ttu-id="d6038-211">150</span><span class="sxs-lookup"><span data-stu-id="d6038-211">150</span></span></p></td>
<td><p><span data-ttu-id="d6038-212">16000</span><span class="sxs-lookup"><span data-stu-id="d6038-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-213">每個聊天室的每個聊天室成員資格清單中的使用者群組（適用于未開啟的會議室）</span><span class="sxs-lookup"><span data-stu-id="d6038-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-214">3</span><span class="sxs-lookup"><span data-stu-id="d6038-214">3</span></span></p></td>
<td><p><span data-ttu-id="d6038-215">500</span><span class="sxs-lookup"><span data-stu-id="d6038-215">5</span></span></p></td>
<td><p><span data-ttu-id="d6038-216">第</span><span class="sxs-lookup"><span data-stu-id="d6038-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-217">每個聊天室的管理員清單中的使用者和使用者群組（適用于開放和未開啟的會議室）</span><span class="sxs-lookup"><span data-stu-id="d6038-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="d6038-218">6</span><span class="sxs-lookup"><span data-stu-id="d6038-218">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-219">6</span><span class="sxs-lookup"><span data-stu-id="d6038-219">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-220">6</span><span class="sxs-lookup"><span data-stu-id="d6038-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-221">每個 auditorium 聊天室的簡報者清單中的使用者和使用者群組（適用于開放與未開啟的會議室）</span><span class="sxs-lookup"><span data-stu-id="d6038-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="d6038-222">6</span><span class="sxs-lookup"><span data-stu-id="d6038-222">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-223">6</span><span class="sxs-lookup"><span data-stu-id="d6038-223">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-224">6</span><span class="sxs-lookup"><span data-stu-id="d6038-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-225">跨所有非開啟會議室的使用者級成員資格實體</span><span class="sxs-lookup"><span data-stu-id="d6038-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-226">465600</span><span class="sxs-lookup"><span data-stu-id="d6038-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="d6038-227">15520</span><span class="sxs-lookup"><span data-stu-id="d6038-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-228">跨所有非開啟會議室的使用者群組成員資格實體</span><span class="sxs-lookup"><span data-stu-id="d6038-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-229">46560</span><span class="sxs-lookup"><span data-stu-id="d6038-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="d6038-230">4656</span><span class="sxs-lookup"><span data-stu-id="d6038-230">4656</span></span></p></td>
<td><p><span data-ttu-id="d6038-231">50</span><span class="sxs-lookup"><span data-stu-id="d6038-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-232">跨所有 auditorium 聊天室的使用者和使用者群組實體實體</span><span class="sxs-lookup"><span data-stu-id="d6038-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-233">0</span><span class="sxs-lookup"><span data-stu-id="d6038-233">0</span></span></p></td>
<td><p><span data-ttu-id="d6038-234">192</span><span class="sxs-lookup"><span data-stu-id="d6038-234">192</span></span></p></td>
<td><p><span data-ttu-id="d6038-235">50</span><span class="sxs-lookup"><span data-stu-id="d6038-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-236">在所有聊天室管理員清單中的使用者和使用者群組（以小組為基礎）管理員實體</span><span class="sxs-lookup"><span data-stu-id="d6038-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="d6038-237">192000</span><span class="sxs-lookup"><span data-stu-id="d6038-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-238">6400</span><span class="sxs-lookup"><span data-stu-id="d6038-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="d6038-239">60</span><span class="sxs-lookup"><span data-stu-id="d6038-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-240">每個聊天室的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="d6038-241"><em>為期</em></span><span class="sxs-lookup"><span data-stu-id="d6038-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="d6038-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="d6038-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-244">每位使用者的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-245"><em>之間</em></span><span class="sxs-lookup"><span data-stu-id="d6038-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="d6038-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="d6038-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-248"><em>位</em></span><span class="sxs-lookup"><span data-stu-id="d6038-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-249">每個聊天室的成員資格清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="d6038-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="d6038-250"><em>第</em></span><span class="sxs-lookup"><span data-stu-id="d6038-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-251"><em>第</em></span><span class="sxs-lookup"><span data-stu-id="d6038-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-252"><em>工資</em></span><span class="sxs-lookup"><span data-stu-id="d6038-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-253">由使用者群組管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="d6038-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d6038-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d6038-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="d6038-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-257">跨所有聊天室的使用者群組成員資格實體</span><span class="sxs-lookup"><span data-stu-id="d6038-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-258">155200</span><span class="sxs-lookup"><span data-stu-id="d6038-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="d6038-259">5173</span><span class="sxs-lookup"><span data-stu-id="d6038-259">5173</span></span></p></td>
<td><p><span data-ttu-id="d6038-260">68</span><span class="sxs-lookup"><span data-stu-id="d6038-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-261">跨所有聊天室的使用者級成員資格實體</span><span class="sxs-lookup"><span data-stu-id="d6038-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-262">465600</span><span class="sxs-lookup"><span data-stu-id="d6038-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="d6038-263">77600</span><span class="sxs-lookup"><span data-stu-id="d6038-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="d6038-264">72000</span><span class="sxs-lookup"><span data-stu-id="d6038-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-265">每個聊天室的管理員、簡報者及範圍清單中的使用者和使用者群組</span><span class="sxs-lookup"><span data-stu-id="d6038-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="d6038-266">6</span><span class="sxs-lookup"><span data-stu-id="d6038-266">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-267">6</span><span class="sxs-lookup"><span data-stu-id="d6038-267">6</span></span></p></td>
<td><p><span data-ttu-id="d6038-268">6</span><span class="sxs-lookup"><span data-stu-id="d6038-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-269">所有聊天室的管理員、簡報者和範圍清單間的使用者和使用者群組</span><span class="sxs-lookup"><span data-stu-id="d6038-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="d6038-270">192000</span><span class="sxs-lookup"><span data-stu-id="d6038-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-271">6400</span><span class="sxs-lookup"><span data-stu-id="d6038-271">6400</span></span></p></td>
<td><p><span data-ttu-id="d6038-272">60</span><span class="sxs-lookup"><span data-stu-id="d6038-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-273">存取控制專案</span><span class="sxs-lookup"><span data-stu-id="d6038-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="d6038-274">704160</span><span class="sxs-lookup"><span data-stu-id="d6038-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="d6038-275">26768</span><span class="sxs-lookup"><span data-stu-id="d6038-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="d6038-276">160</span><span class="sxs-lookup"><span data-stu-id="d6038-276">160</span></span></p></td>
<td><p><span data-ttu-id="d6038-277">731088</span><span class="sxs-lookup"><span data-stu-id="d6038-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-278">最大存取控制專案</span><span class="sxs-lookup"><span data-stu-id="d6038-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d6038-279">2000000</span><span class="sxs-lookup"><span data-stu-id="d6038-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6038-280">在上述範例中，當您根據建議的準則部署持久聊天伺服器時，他們可以在啟用合規性的四個伺服器池中處理最多80000個作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="d6038-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="d6038-281">此範例顯示分類為小（任何指定時間為30個作用中的使用者）、中型（150作用中使用者）及大型（16000作用中使用者）的聊天室。</span><span class="sxs-lookup"><span data-stu-id="d6038-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="d6038-282">根據下列其中一個大小的聊天室數來計算：</span><span class="sxs-lookup"><span data-stu-id="d6038-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="d6038-283">系統中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-283">Active users in the system</span></span>

  - <span data-ttu-id="d6038-284">指定大小的聊天室中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="d6038-285">單一使用者所連接之指定大小的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="d6038-286">針對每個聊天室，先前的容量規劃表格會指定與聊天室相關聯的存取控制專案數目，包括直接指派至聊天室的專案。</span><span class="sxs-lookup"><span data-stu-id="d6038-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="d6038-287">您可以使用存取控制清單（Acl）來控制個別聊天室的存取權。</span><span class="sxs-lookup"><span data-stu-id="d6038-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="d6038-288">您也可以在類別層級控制存取權。</span><span class="sxs-lookup"><span data-stu-id="d6038-288">You can also control access at the category level.</span></span> <span data-ttu-id="d6038-289">在 ACL 中，個別的存取控制專案可以是使用者群組，例如安全群組、通訊群組清單或單一使用者。</span><span class="sxs-lookup"><span data-stu-id="d6038-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="d6038-290">您可以為聊天室管理員、簡報者和成員定義存取控制專案。</span><span class="sxs-lookup"><span data-stu-id="d6038-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6038-291">在規劃管理聊天室的策略時，請記住，允許存取控制專案的總數為2000000。</span><span class="sxs-lookup"><span data-stu-id="d6038-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="d6038-292">如果計算出的存取控制專案超過2000000，伺服器效能可能會顯著下降。</span><span class="sxs-lookup"><span data-stu-id="d6038-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="d6038-293">若要避免此問題，請確定您的存取控制專案是使用者群組，而不是個別使用者。</span><span class="sxs-lookup"><span data-stu-id="d6038-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="d6038-294">透過邀請管理聊天室存取能力的容量規劃</span><span class="sxs-lookup"><span data-stu-id="d6038-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="d6038-295">您可以使用下列容量規劃表格，瞭解當它設定為傳送邀請時，持續聊天伺服器在永久聊天資料庫中建立並儲存的邀請數目。</span><span class="sxs-lookup"><span data-stu-id="d6038-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="d6038-296">您可以使用 Lync Server [控制台] 中的 [**聊天室類別設定**] 頁面，或使用 Windows PowerShell Cmdlet**設定 csPersistentChatCategory**，來管理類別上的邀請。</span><span class="sxs-lookup"><span data-stu-id="d6038-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="d6038-297">您可以使用從 Lync 用戶端啟動的 [**聊天室管理**]**頁面，或**使用 Windows PowerShell Cmdlet，在聊天室（與類別允許的方式）中管理邀請。</span><span class="sxs-lookup"><span data-stu-id="d6038-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="d6038-298">下表中的範例資料假設，在 [**聊天室設定**] 頁面上，有50% 的所有聊天室，[**邀請**] 選項會設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d6038-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6038-299">如果伺服器產生的邀請函數計算值超過1000000，伺服器效能可能會顯著下降。</span><span class="sxs-lookup"><span data-stu-id="d6038-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="d6038-300">若要避免此問題，請確定您將已設定傳送邀請的聊天室數量減至最少，或限制可以加入已設定傳送邀請之聊天室的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="d6038-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="d6038-301">[透過邀請的聊天室存取] 範例</span><span class="sxs-lookup"><span data-stu-id="d6038-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="d6038-302">小型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-303">中型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-304">大型聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="d6038-305">總額</span><span class="sxs-lookup"><span data-stu-id="d6038-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6038-306">可存取聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="d6038-307">每個房間30個</span><span class="sxs-lookup"><span data-stu-id="d6038-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="d6038-308">每個房間150</span><span class="sxs-lookup"><span data-stu-id="d6038-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="d6038-309">每個房間16000</span><span class="sxs-lookup"><span data-stu-id="d6038-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-310">有邀請的會議室百分比</span><span class="sxs-lookup"><span data-stu-id="d6038-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="d6038-311">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-311">50%</span></span></p></td>
<td><p><span data-ttu-id="d6038-312">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-312">50%</span></span></p></td>
<td><p><span data-ttu-id="d6038-313">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-314">已設定傳送邀請的聊天室</span><span class="sxs-lookup"><span data-stu-id="d6038-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="d6038-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="d6038-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="d6038-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-317"><em>500</em></span><span class="sxs-lookup"><span data-stu-id="d6038-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-318">可存取聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="d6038-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="d6038-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="d6038-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="d6038-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="d6038-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-322">持續聊天伺服器產生的邀請</span><span class="sxs-lookup"><span data-stu-id="d6038-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="d6038-323">960000</span><span class="sxs-lookup"><span data-stu-id="d6038-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-324">120000</span><span class="sxs-lookup"><span data-stu-id="d6038-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-325">80000</span><span class="sxs-lookup"><span data-stu-id="d6038-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="d6038-326">1160000</span><span class="sxs-lookup"><span data-stu-id="d6038-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-327">允許的邀請數目上限</span><span class="sxs-lookup"><span data-stu-id="d6038-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="d6038-328">2000000</span><span class="sxs-lookup"><span data-stu-id="d6038-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-329">模型 1-從每個工作日的每個房間取得預期的郵件數目</span><span class="sxs-lookup"><span data-stu-id="d6038-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-330">每個會議室的聊天費率（每天）</span><span class="sxs-lookup"><span data-stu-id="d6038-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="d6038-331">50</span><span class="sxs-lookup"><span data-stu-id="d6038-331">50</span></span></p></td>
<td><p><span data-ttu-id="d6038-332">500</span><span class="sxs-lookup"><span data-stu-id="d6038-332">500</span></span></p></td>
<td><p><span data-ttu-id="d6038-333">100</span><span class="sxs-lookup"><span data-stu-id="d6038-333">100</span></span></p></td>
<td><p><span data-ttu-id="d6038-334">650</span><span class="sxs-lookup"><span data-stu-id="d6038-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-335">所有聊天室的聊天比率（每秒）</span><span class="sxs-lookup"><span data-stu-id="d6038-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-336">55.56</span><span class="sxs-lookup"><span data-stu-id="d6038-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="d6038-337">18.52</span><span class="sxs-lookup"><span data-stu-id="d6038-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="d6038-338">0.03</span><span class="sxs-lookup"><span data-stu-id="d6038-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="d6038-339">74</span><span class="sxs-lookup"><span data-stu-id="d6038-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-340">模型 2-從每個使用者每天張貼的訊息數目開始</span><span class="sxs-lookup"><span data-stu-id="d6038-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-341">每個使用者每天的聊天費率</span><span class="sxs-lookup"><span data-stu-id="d6038-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="d6038-342">工資</span><span class="sxs-lookup"><span data-stu-id="d6038-342">15</span></span></p></td>
<td><p><span data-ttu-id="d6038-343">500</span><span class="sxs-lookup"><span data-stu-id="d6038-343">5</span></span></p></td>
<td><p><span data-ttu-id="d6038-344">0.1</span><span class="sxs-lookup"><span data-stu-id="d6038-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="d6038-345">20</span><span class="sxs-lookup"><span data-stu-id="d6038-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-346">每個會議室的聊天費率（每天）</span><span class="sxs-lookup"><span data-stu-id="d6038-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="d6038-347">38</span><span class="sxs-lookup"><span data-stu-id="d6038-347">38</span></span></p></td>
<td><p><span data-ttu-id="d6038-348">375</span><span class="sxs-lookup"><span data-stu-id="d6038-348">375</span></span></p></td>
<td><p><span data-ttu-id="d6038-349">800</span><span class="sxs-lookup"><span data-stu-id="d6038-349">800</span></span></p></td>
<td><p><span data-ttu-id="d6038-350">1213</span><span class="sxs-lookup"><span data-stu-id="d6038-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-351">所有聊天室的聊天比率（每秒）</span><span class="sxs-lookup"><span data-stu-id="d6038-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-352">41.67</span><span class="sxs-lookup"><span data-stu-id="d6038-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="d6038-353">13.89</span><span class="sxs-lookup"><span data-stu-id="d6038-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="d6038-354">0.28</span><span class="sxs-lookup"><span data-stu-id="d6038-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="d6038-355">56</span><span class="sxs-lookup"><span data-stu-id="d6038-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="d6038-356">持久聊天伺服器效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="d6038-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="d6038-357">下表說明持久聊天伺服器的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="d6038-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="d6038-358">它提供容量規劃需求的基礎，並代表在四個伺服器上有80000併發使用者的一般組織。</span><span class="sxs-lookup"><span data-stu-id="d6038-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="d6038-359">持久聊天伺服器效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="d6038-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6038-360">已連接的活動使用者數量</span><span class="sxs-lookup"><span data-stu-id="d6038-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="d6038-361">80000</span><span class="sxs-lookup"><span data-stu-id="d6038-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-362">持久聊天伺服器服務實例數</span><span class="sxs-lookup"><span data-stu-id="d6038-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="d6038-363">4</span><span class="sxs-lookup"><span data-stu-id="d6038-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-364">小型聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="d6038-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-365">30個使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-366">中型聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="d6038-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-367">150使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-368">大型聊天室的大小</span><span class="sxs-lookup"><span data-stu-id="d6038-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-369">16000使用者</span><span class="sxs-lookup"><span data-stu-id="d6038-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-370">聊天室的總數量</span><span class="sxs-lookup"><span data-stu-id="d6038-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-371">33077</span><span class="sxs-lookup"><span data-stu-id="d6038-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-372">小型聊天室的數目</span><span class="sxs-lookup"><span data-stu-id="d6038-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-373">32000</span><span class="sxs-lookup"><span data-stu-id="d6038-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-374">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="d6038-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-375">1067</span><span class="sxs-lookup"><span data-stu-id="d6038-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-376">大型聊天室數量</span><span class="sxs-lookup"><span data-stu-id="d6038-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-377">第</span><span class="sxs-lookup"><span data-stu-id="d6038-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-378">每個使用者的聊天室總數</span><span class="sxs-lookup"><span data-stu-id="d6038-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-379">位</span><span class="sxs-lookup"><span data-stu-id="d6038-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-380">每位使用者的小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="d6038-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-381">之間</span><span class="sxs-lookup"><span data-stu-id="d6038-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-382">每位使用者的中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="d6038-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-383">pplx-2</span><span class="sxs-lookup"><span data-stu-id="d6038-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-384">每個使用者的大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="d6038-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-385">pplx-2</span><span class="sxs-lookup"><span data-stu-id="d6038-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-386">每位使用者加入的房間數</span><span class="sxs-lookup"><span data-stu-id="d6038-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-387">24</span><span class="sxs-lookup"><span data-stu-id="d6038-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-388">峰值連接速率</span><span class="sxs-lookup"><span data-stu-id="d6038-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="d6038-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="d6038-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-390">研討總匯率</span><span class="sxs-lookup"><span data-stu-id="d6038-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="d6038-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="d6038-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-392">小型聊天室的聊天速度</span><span class="sxs-lookup"><span data-stu-id="d6038-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-393">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="d6038-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-394">中型聊天室的聊天費率</span><span class="sxs-lookup"><span data-stu-id="d6038-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-395">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="d6038-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-396">大型聊天室的聊天速度</span><span class="sxs-lookup"><span data-stu-id="d6038-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="d6038-397">~ 0.15/秒</span><span class="sxs-lookup"><span data-stu-id="d6038-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-398">為邀請設定的聊天室百分比</span><span class="sxs-lookup"><span data-stu-id="d6038-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="d6038-399">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-400">直接成員資格百分比</span><span class="sxs-lookup"><span data-stu-id="d6038-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="d6038-401">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-402">群組成員資格百分比</span><span class="sxs-lookup"><span data-stu-id="d6038-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="d6038-403">50%</span><span class="sxs-lookup"><span data-stu-id="d6038-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-404">Active Directory 網域服務中祖先隸屬關係的平均數目</span><span class="sxs-lookup"><span data-stu-id="d6038-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="d6038-405">100-200</span><span class="sxs-lookup"><span data-stu-id="d6038-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-406">每位使用者的已訂閱連絡人數量</span><span class="sxs-lookup"><span data-stu-id="d6038-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-407">80</span><span class="sxs-lookup"><span data-stu-id="d6038-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-408">每個使用者的平均端點數</span><span class="sxs-lookup"><span data-stu-id="d6038-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-409">1.5</span><span class="sxs-lookup"><span data-stu-id="d6038-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-410">每個端點的可見聊天室的平均數目</span><span class="sxs-lookup"><span data-stu-id="d6038-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="d6038-411">1.5</span><span class="sxs-lookup"><span data-stu-id="d6038-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-412">每位使用者可見聊天室的平均數量</span><span class="sxs-lookup"><span data-stu-id="d6038-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-413">2.25 （50%），共1個房間和50% （共2個房間）;開啟6個會議室，每個監視器一個</span><span class="sxs-lookup"><span data-stu-id="d6038-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-414">每個間隔所輪詢的參與者人數</span><span class="sxs-lookup"><span data-stu-id="d6038-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="d6038-415">每個可見聊天室25個</span><span class="sxs-lookup"><span data-stu-id="d6038-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-416">巡迴檢測間隔長度</span><span class="sxs-lookup"><span data-stu-id="d6038-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="d6038-417">5分鐘</span><span class="sxs-lookup"><span data-stu-id="d6038-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-418">每秒輪詢的參與者人數</span><span class="sxs-lookup"><span data-stu-id="d6038-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="d6038-419">15000</span><span class="sxs-lookup"><span data-stu-id="d6038-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6038-420">每個使用者每小時的狀態變更數量</span><span class="sxs-lookup"><span data-stu-id="d6038-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="d6038-421">6</span><span class="sxs-lookup"><span data-stu-id="d6038-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6038-422">每秒的狀態變更數量</span><span class="sxs-lookup"><span data-stu-id="d6038-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="d6038-423">133.33</span><span class="sxs-lookup"><span data-stu-id="d6038-423">133.33</span></span></p></td>
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

