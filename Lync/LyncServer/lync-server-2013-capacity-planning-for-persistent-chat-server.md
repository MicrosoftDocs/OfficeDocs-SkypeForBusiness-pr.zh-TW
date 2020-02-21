---
title: 'Lync Server 2013: Capacity planning for Persistent Chat Server'
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
ms.openlocfilehash: 18f24d99a8b22c78acd32efdb5867c92a5621fe8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="493f5-102">Persistent Chat Server in Lync Server 2013 的容量規劃</span><span class="sxs-lookup"><span data-stu-id="493f5-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="493f5-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="493f5-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="493f5-104">Persistent Chat Server 可以執行多個使用者可以保存的即時聊天室未來擷取與搜尋。</span><span class="sxs-lookup"><span data-stu-id="493f5-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="493f5-105">不同於群組立即訊息 (IM)，會儲存在使用者的信箱如果交談歷程記錄設定，Persistent Chat Server 的工作階段保持開啟更久，且內容儲存在伺服器上，以及郵件、 檔案、 Url 和屬於其他資料進行中的交談。</span><span class="sxs-lookup"><span data-stu-id="493f5-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="493f5-106">容量規劃是準備部署 Persistent Chat Server 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="493f5-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="493f5-107">本主題提供有關支援的常設聊天室伺服器拓撲和容量規劃表格可用來判斷您的部署的最佳組態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="493f5-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="493f5-108">它也說明如何以最佳管理 Persistent Chat Server 部署在尖峰時間需要更多的容量。</span><span class="sxs-lookup"><span data-stu-id="493f5-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="493f5-109">若要下載 Persistent Chat Server，請參閱 「 Microsoft Lync Server 13 Persistent Chat Server" [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)。</span><span class="sxs-lookup"><span data-stu-id="493f5-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="493f5-110">如需安裝 Persistent Chat Server 的詳細資訊，請參閱部署文件中的[安裝 Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)和[Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="493f5-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="493f5-111">支援的工具，例如 [Lync Server 規劃工具，可進一步協助您進行容量規劃。</span><span class="sxs-lookup"><span data-stu-id="493f5-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="493f5-112">如需規劃工具的詳細資訊，請參閱規劃文件的[開頭 Lync Server 2013 的規劃程序](lync-server-2013-beginning-the-planning-process.md)。</span><span class="sxs-lookup"><span data-stu-id="493f5-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="493f5-113">常設聊天室伺服器支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="493f5-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="493f5-114">您可以部署 Persistent Chat Server 在單一伺服器或多部伺服器集區，並與集區的單一或多個集區的拓撲。</span><span class="sxs-lookup"><span data-stu-id="493f5-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="493f5-115">我們現在也支援 Persistent Chat Server 的新的 Lync Server 2013 部署的 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="493f5-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="493f5-116">不過，會影響效能和規模，並沒有這個新部署的高可用性選項，因為我們希望您可以使用此功能主要是基於證明概念、 評估，依此類推。</span><span class="sxs-lookup"><span data-stu-id="493f5-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="493f5-117">如需這兩種拓撲的詳細資訊，請參閱<A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A>中此文件組與<A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="493f5-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="493f5-118">單一伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="493f5-118">Single-Server Topology</span></span>

<span data-ttu-id="493f5-119">最小的設定資料庫和 for Persistent Chat Server 的最簡單部署是單一常設聊天室伺服器前端伺服器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="493f5-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="493f5-120">此部署需要執行常設聊天室伺服器 （如果啟用規範，選擇性地執行規範服務，）、 主控這兩個 SQL Server 資料庫伺服器的單一伺服器和合規性是否有需要，要儲存的 SQL Server 資料庫規範資料。</span><span class="sxs-lookup"><span data-stu-id="493f5-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="493f5-121">您無法新增其他伺服器至已啟動拓撲產生器中的單一伺服器部署為 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="493f5-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="493f5-122">我們建議使用多部伺服器集區的拓撲，即使您使用單一伺服器。</span><span class="sxs-lookup"><span data-stu-id="493f5-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="493f5-123">這是這樣您就可以新增更多伺服器更新版本中，視需要。</span><span class="sxs-lookup"><span data-stu-id="493f5-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="493f5-124">下圖顯示內含規範單一常設聊天室伺服器前端伺服器拓撲的所有必要與選用元件。</span><span class="sxs-lookup"><span data-stu-id="493f5-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="493f5-125">**單一常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="493f5-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="493f5-126">![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="493f5-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="493f5-127">多部伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="493f5-127">Multiple-Server Topology</span></span>

<span data-ttu-id="493f5-128">若要提供更大的容量及可靠性，您可以部署多部伺服器拓撲，[規劃 Persistent Chat Server in Lync Server 2013 ](lync-server-2013-planning-for-persistent-chat-server.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="493f5-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="493f5-129">多部伺服器拓撲可以包含多達四個作用中的電腦執行 Persistent Chat Server （高可用性和災害復原設定會允許最多第八個，但只有四個可以是作用中，其餘四處於待命狀態）。</span><span class="sxs-lookup"><span data-stu-id="493f5-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="493f5-130">每個伺服器可支援多達 20000 位並行使用者，總共為 80000 位並行使用者連線到具有 4 部伺服器 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="493f5-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="493f5-131">在多部伺服器拓撲是單一伺服器拓撲相同之處在於多部伺服器主控 Persistent Chat Server，並可將其調整更高版本。</span><span class="sxs-lookup"><span data-stu-id="493f5-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="493f5-132">執行 Persistent Chat Server 的多部電腦應該位於相同的 Active Directory 網域服務網域 Lync 伺服器和規範服務。</span><span class="sxs-lookup"><span data-stu-id="493f5-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="493f5-133">下圖顯示所有的元件的多部伺服器拓撲與執行 Persistent Chat Server、 選用的 Compliance service 和獨立的規範資料庫的多部電腦。</span><span class="sxs-lookup"><span data-stu-id="493f5-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="493f5-134">**多部常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="493f5-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="493f5-135">![多伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="493f5-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="493f5-136">在有四部伺服器 Persistent Chat Server 部署中，可以 80000 位使用者同時登入，並使用常設聊天室，負載平均分配在每個伺服器 20000 位使用者。</span><span class="sxs-lookup"><span data-stu-id="493f5-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="493f5-137">如果一部伺服器變成無法使用，連線至該伺服器的使用者都將遺失其存取至 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="493f5-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="493f5-138">連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。</span><span class="sxs-lookup"><span data-stu-id="493f5-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="493f5-139">在網路上的常設聊天室傳輸量，根據此傳輸可能需要數分鐘或更久。</span><span class="sxs-lookup"><span data-stu-id="493f5-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="493f5-140">因為每個剩餘伺服器可能會主控多達 30000 位使用者，我們建議您以避免發生效能問題儘速還原無法使用的伺服器。</span><span class="sxs-lookup"><span data-stu-id="493f5-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="493f5-141">否則，您可以提供另一部常設聊天室伺服器使用拓撲產生器或 Windows PowerShell cmdlet， **Set-cspersistentchatactiveserver**。</span><span class="sxs-lookup"><span data-stu-id="493f5-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="493f5-142">常設聊天室伺服器容量規劃</span><span class="sxs-lookup"><span data-stu-id="493f5-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="493f5-143">下表可協助您使用的容量規劃 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="493f5-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="493f5-144">他們建立模型如何變更各種 Persistent Chat Server 設定會影響容量功能。</span><span class="sxs-lookup"><span data-stu-id="493f5-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="493f5-145">規劃常設聊天室伺服器的最大容量</span><span class="sxs-lookup"><span data-stu-id="493f5-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="493f5-146">使用下列範例表格，來判斷您可以支援的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="493f5-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="493f5-147">Persistent Chat Server 集區最大容量範例</span><span class="sxs-lookup"><span data-stu-id="493f5-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="493f5-148">作用中的常設聊天室服務執行個體</span><span class="sxs-lookup"><span data-stu-id="493f5-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="493f5-149"><em>4</em></span><span class="sxs-lookup"><span data-stu-id="493f5-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-150">常設聊天室服務執行個體</span><span class="sxs-lookup"><span data-stu-id="493f5-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="493f5-151"><em>8 （4 必須是不在作用中; 只有最大值為 4，可在作用中）</em></span><span class="sxs-lookup"><span data-stu-id="493f5-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-152">作用中的使用者連線</span><span class="sxs-lookup"><span data-stu-id="493f5-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="493f5-153"><em>80000</em></span><span class="sxs-lookup"><span data-stu-id="493f5-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-154">已佈建的使用者總數</span><span class="sxs-lookup"><span data-stu-id="493f5-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="493f5-155">150000</span><span class="sxs-lookup"><span data-stu-id="493f5-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-156">端點數目</span><span class="sxs-lookup"><span data-stu-id="493f5-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="493f5-157">120000</span><span class="sxs-lookup"><span data-stu-id="493f5-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="493f5-158">在上述範例中，該計劃是要支援，Persistent Chat Server 可讓使用者的數目上限: （可以有四部執行 Persistent Chat Server 的高可用性和災害復原的多個被動伺服器） 的常設聊天室的服務和 20000 位使用者每個伺服器，80000 位作用中的使用者，總共四個伺服器/執行個體。</span><span class="sxs-lookup"><span data-stu-id="493f5-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="493f5-159">管理常設聊天室存取的容量規劃</span><span class="sxs-lookup"><span data-stu-id="493f5-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="493f5-160">下列範例表格可協助您管理常設聊天室 Persistent Chat Server 集區中的聊天室存取的計劃。</span><span class="sxs-lookup"><span data-stu-id="493f5-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="493f5-161">聊天室存取管理範例</span><span class="sxs-lookup"><span data-stu-id="493f5-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="493f5-162">小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-163">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-164">大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-165">總計</span><span class="sxs-lookup"><span data-stu-id="493f5-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="493f5-166">大小的聊天室 （已連線的使用者數目）</span><span class="sxs-lookup"><span data-stu-id="493f5-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="493f5-167">每個聊天室 30</span><span class="sxs-lookup"><span data-stu-id="493f5-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="493f5-168">每個聊天室 150</span><span class="sxs-lookup"><span data-stu-id="493f5-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="493f5-169">每個聊天室 16000</span><span class="sxs-lookup"><span data-stu-id="493f5-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-170">聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-171">32000</span><span class="sxs-lookup"><span data-stu-id="493f5-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-172">1,067</span><span class="sxs-lookup"><span data-stu-id="493f5-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="493f5-173">10 </span><span class="sxs-lookup"><span data-stu-id="493f5-173">10</span></span></p></td>
<td><p><span data-ttu-id="493f5-174">33,077</span><span class="sxs-lookup"><span data-stu-id="493f5-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-175">%of 所視聽中心聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="493f5-176">1%</span><span class="sxs-lookup"><span data-stu-id="493f5-176">1%</span></span></p></td>
<td><p><span data-ttu-id="493f5-177">1%</span><span class="sxs-lookup"><span data-stu-id="493f5-177">1%</span></span></p></td>
<td><p><span data-ttu-id="493f5-178">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-179">%的已開啟的聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="493f5-180">3%</span><span class="sxs-lookup"><span data-stu-id="493f5-180">3%</span></span></p></td>
<td><p><span data-ttu-id="493f5-181">3%</span><span class="sxs-lookup"><span data-stu-id="493f5-181">3%</span></span></p></td>
<td><p><span data-ttu-id="493f5-182">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-183">開啟的聊天室 （沒有明確的成員資格）</span><span class="sxs-lookup"><span data-stu-id="493f5-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="493f5-184">960</span><span class="sxs-lookup"><span data-stu-id="493f5-184">960</span></span></p></td>
<td><p><span data-ttu-id="493f5-185">32</span><span class="sxs-lookup"><span data-stu-id="493f5-185">32</span></span></p></td>
<td><p><span data-ttu-id="493f5-186">5</span><span class="sxs-lookup"><span data-stu-id="493f5-186">5</span></span></p></td>
<td><p><span data-ttu-id="493f5-187">997</span><span class="sxs-lookup"><span data-stu-id="493f5-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-188">非開啟聊天室 （使用明確的成員資格的一般聊天室）</span><span class="sxs-lookup"><span data-stu-id="493f5-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="493f5-189">31,040</span><span class="sxs-lookup"><span data-stu-id="493f5-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="493f5-190">1.035</span><span class="sxs-lookup"><span data-stu-id="493f5-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="493f5-191">5</span><span class="sxs-lookup"><span data-stu-id="493f5-191">5</span></span></p></td>
<td><p><span data-ttu-id="493f5-192">32,080</span><span class="sxs-lookup"><span data-stu-id="493f5-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-193">視聽中心聊天室 （其他簡報者項目）</span><span class="sxs-lookup"><span data-stu-id="493f5-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="493f5-194">0</span><span class="sxs-lookup"><span data-stu-id="493f5-194">0</span></span></p></td>
<td><p><span data-ttu-id="493f5-195">32</span><span class="sxs-lookup"><span data-stu-id="493f5-195">32</span></span></p></td>
<td><p><span data-ttu-id="493f5-196">5</span><span class="sxs-lookup"><span data-stu-id="493f5-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-197">直接成員資格所管理的聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="493f5-198">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-198">50%</span></span></p></td>
<td><p><span data-ttu-id="493f5-199">10%</span><span class="sxs-lookup"><span data-stu-id="493f5-199">10%</span></span></p></td>
<td><p><span data-ttu-id="493f5-200">0%</span><span class="sxs-lookup"><span data-stu-id="493f5-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-201">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="493f5-202">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-202">50%</span></span></p></td>
<td><p><span data-ttu-id="493f5-203">90%</span><span class="sxs-lookup"><span data-stu-id="493f5-203">90%</span></span></p></td>
<td><p><span data-ttu-id="493f5-204">100%</span><span class="sxs-lookup"><span data-stu-id="493f5-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-205">開啟的聊天室 （未明確指定） 的每個聊天室的成員資格清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="493f5-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="493f5-206">0</span><span class="sxs-lookup"><span data-stu-id="493f5-206">0</span></span></p></td>
<td><p><span data-ttu-id="493f5-207">0</span><span class="sxs-lookup"><span data-stu-id="493f5-207">0</span></span></p></td>
<td><p><span data-ttu-id="493f5-208">0</span><span class="sxs-lookup"><span data-stu-id="493f5-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-209">非開啟會議室的每個聊天室的成員資格清單中的使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-210">30</span><span class="sxs-lookup"><span data-stu-id="493f5-210">30</span></span></p></td>
<td><p><span data-ttu-id="493f5-211">150</span><span class="sxs-lookup"><span data-stu-id="493f5-211">150</span></span></p></td>
<td><p><span data-ttu-id="493f5-212">16000</span><span class="sxs-lookup"><span data-stu-id="493f5-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-213">非開啟會議室的每個聊天室的成員資格清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="493f5-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-214">3</span><span class="sxs-lookup"><span data-stu-id="493f5-214">3</span></span></p></td>
<td><p><span data-ttu-id="493f5-215">5</span><span class="sxs-lookup"><span data-stu-id="493f5-215">5</span></span></p></td>
<td><p><span data-ttu-id="493f5-216">10 </span><span class="sxs-lookup"><span data-stu-id="493f5-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-217">使用者與 （適用於開啟和非開啟的聊天室） 的每個聊天室的管理員清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="493f5-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="493f5-218">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-218">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-219">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-219">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-220">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-221">使用者和 （適用於開啟和非開啟會議室） 每個視聽中心聊天室的 [主持人] 清單中的使用者群組</span><span class="sxs-lookup"><span data-stu-id="493f5-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="493f5-222">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-222">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-223">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-223">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-224">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-225">使用者型成員資格實體數所有非開啟會議室</span><span class="sxs-lookup"><span data-stu-id="493f5-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-226">465,600</span><span class="sxs-lookup"><span data-stu-id="493f5-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="493f5-227">15,520</span><span class="sxs-lookup"><span data-stu-id="493f5-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-228">使用者群組型成員資格實體數所有非開啟會議室</span><span class="sxs-lookup"><span data-stu-id="493f5-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-229">46,560</span><span class="sxs-lookup"><span data-stu-id="493f5-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="493f5-230">4656</span><span class="sxs-lookup"><span data-stu-id="493f5-230">4656</span></span></p></td>
<td><p><span data-ttu-id="493f5-231">50</span><span class="sxs-lookup"><span data-stu-id="493f5-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-232">使用者與使用者群組型實體之間所有視聽中心聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-233">0</span><span class="sxs-lookup"><span data-stu-id="493f5-233">0</span></span></p></td>
<td><p><span data-ttu-id="493f5-234">192</span><span class="sxs-lookup"><span data-stu-id="493f5-234">192</span></span></p></td>
<td><p><span data-ttu-id="493f5-235">50</span><span class="sxs-lookup"><span data-stu-id="493f5-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-236">使用者和使用者群組為主管理員實體的跨所有聊天室管理員清單</span><span class="sxs-lookup"><span data-stu-id="493f5-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="493f5-237">192,000</span><span class="sxs-lookup"><span data-stu-id="493f5-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-238">6400</span><span class="sxs-lookup"><span data-stu-id="493f5-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="493f5-239">60</span><span class="sxs-lookup"><span data-stu-id="493f5-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-240">每個聊天室的作用中使用者數</span><span class="sxs-lookup"><span data-stu-id="493f5-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="493f5-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="493f5-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="493f5-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="493f5-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-244">每位使用者的聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="493f5-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="493f5-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="493f5-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="493f5-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-249">每個聊天室之成員資格清單中的使用者群組數</span><span class="sxs-lookup"><span data-stu-id="493f5-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="493f5-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="493f5-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="493f5-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-252"><em>15</em></span><span class="sxs-lookup"><span data-stu-id="493f5-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-253">以使用者群組管理的聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="493f5-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="493f5-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="493f5-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="493f5-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-257">所有聊天室的使用者群組型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="493f5-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-258">155,200</span><span class="sxs-lookup"><span data-stu-id="493f5-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="493f5-259">5173</span><span class="sxs-lookup"><span data-stu-id="493f5-259">5173</span></span></p></td>
<td><p><span data-ttu-id="493f5-260">68</span><span class="sxs-lookup"><span data-stu-id="493f5-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-261">所有聊天室的使用者型成員資格實體數</span><span class="sxs-lookup"><span data-stu-id="493f5-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-262">465,600</span><span class="sxs-lookup"><span data-stu-id="493f5-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="493f5-263">77,600</span><span class="sxs-lookup"><span data-stu-id="493f5-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="493f5-264">72,000</span><span class="sxs-lookup"><span data-stu-id="493f5-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-265">每個聊天室的管理員、簡報者和範圍清單中的使用者與使用者群組數</span><span class="sxs-lookup"><span data-stu-id="493f5-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="493f5-266">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-266">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-267">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-267">6</span></span></p></td>
<td><p><span data-ttu-id="493f5-268">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-269">使用者與使用者群組，跨所有聊天室的管理員、 簡報者和範圍清單</span><span class="sxs-lookup"><span data-stu-id="493f5-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="493f5-270">192,000</span><span class="sxs-lookup"><span data-stu-id="493f5-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-271">6400</span><span class="sxs-lookup"><span data-stu-id="493f5-271">6400</span></span></p></td>
<td><p><span data-ttu-id="493f5-272">60</span><span class="sxs-lookup"><span data-stu-id="493f5-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-273">存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="493f5-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="493f5-274">704,160</span><span class="sxs-lookup"><span data-stu-id="493f5-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="493f5-275">26,768</span><span class="sxs-lookup"><span data-stu-id="493f5-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="493f5-276">160</span><span class="sxs-lookup"><span data-stu-id="493f5-276">160</span></span></p></td>
<td><p><span data-ttu-id="493f5-277">731,088</span><span class="sxs-lookup"><span data-stu-id="493f5-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-278">最大存取控制項目數</span><span class="sxs-lookup"><span data-stu-id="493f5-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="493f5-279">每 2000000 個</span><span class="sxs-lookup"><span data-stu-id="493f5-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="493f5-280">在上述範例中，當您部署的建議準則，根據常設聊天室伺服器時所能處理最多 80000 位作用中使用者之間有四部伺服器集區與已啟用的規範。</span><span class="sxs-lookup"><span data-stu-id="493f5-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="493f5-281">此範例會示範聊天室分類為 「 小 （30 作用中的使用者在任何指定時間），中型 （150 主動使用者），以及大型 （16000 活躍的使用者）。</span><span class="sxs-lookup"><span data-stu-id="493f5-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="493f5-282">特定大小聊天室的數目是依下列項目的總數計算而來：</span><span class="sxs-lookup"><span data-stu-id="493f5-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="493f5-283">系統中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-283">Active users in the system</span></span>

  - <span data-ttu-id="493f5-284">特定大小聊天室中的作用中使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="493f5-285">單一使用者加入的特定大小聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="493f5-286">針對每個聊天室，上述的容量規劃的表格會指定與聊天室，包括直接指派給該聊天室的項目相關聯的存取控制項目數目。</span><span class="sxs-lookup"><span data-stu-id="493f5-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="493f5-287">您可以使用存取控制清單 (ACL)，控制對個別聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="493f5-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="493f5-288">您也可以在類別層級控制存取。</span><span class="sxs-lookup"><span data-stu-id="493f5-288">You can also control access at the category level.</span></span> <span data-ttu-id="493f5-289">在 ACL 中的個別存取控制項目可以是使用者群組 — 例如，[安全性] 群組、 通訊群組清單或單一使用者。</span><span class="sxs-lookup"><span data-stu-id="493f5-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="493f5-290">您可以定義聊天室管理員、簡報者和成員的存取控制項目。</span><span class="sxs-lookup"><span data-stu-id="493f5-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="493f5-291">規劃策略管理聊天室，請記住，允許的存取控制項目總數是 2 百萬。</span><span class="sxs-lookup"><span data-stu-id="493f5-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="493f5-292">如果計算的存取控制項目超過 2 百萬個，伺服器的效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="493f5-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="493f5-293">若要避免此問題，可能的話，請務必您存取控制項目會而不是個別使用者的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="493f5-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="493f5-294">邀請式聊天室存取的容量管理規劃</span><span class="sxs-lookup"><span data-stu-id="493f5-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="493f5-295">您可以使用下列的容量規劃的表格以了解邀請 Persistent Chat Server 建立，並將儲存在常設聊天室資料庫時就會設成傳送邀請的數目。</span><span class="sxs-lookup"><span data-stu-id="493f5-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="493f5-296">使用 Lync Server 控制台] 中的**聊天室類別設定**] 頁面上或使用 Windows PowerShell cmdlet，**設定 csPersistentChatCategory**，您可以管理類別上的邀請。</span><span class="sxs-lookup"><span data-stu-id="493f5-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="493f5-297">使用 Lync 用戶端上，從啟動 「**聊天室管理**」 頁面或使用 Windows PowerShell cmdlet，**設定 csPersistentChatRoom**，您可以管理聊天室時亦可 （內嵌類別的讓） 上的邀請。</span><span class="sxs-lookup"><span data-stu-id="493f5-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="493f5-298">下表中的範例資料假設，在所有聊天室的 50%的**聊天室設定**] 頁面上，[**邀請**] 選項設為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="493f5-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="493f5-299">如果伺服器所產生的邀請數的計算的值超過 1 千萬個，伺服器的效能可能會大幅降低。</span><span class="sxs-lookup"><span data-stu-id="493f5-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="493f5-300">若要避免此問題，請務必您最小化設定為傳送邀請] 或 [限制可以加入已設成傳送邀請的聊天室的使用者數目的聊天室數。</span><span class="sxs-lookup"><span data-stu-id="493f5-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="493f5-301">邀請式聊天室存取範例</span><span class="sxs-lookup"><span data-stu-id="493f5-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="493f5-302">小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-303">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-304">大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="493f5-305">總計</span><span class="sxs-lookup"><span data-stu-id="493f5-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="493f5-306">使用者可以存取聊天室</span><span class="sxs-lookup"><span data-stu-id="493f5-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="493f5-307">每個聊天室 30</span><span class="sxs-lookup"><span data-stu-id="493f5-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="493f5-308">每個聊天室 150</span><span class="sxs-lookup"><span data-stu-id="493f5-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="493f5-309">每個聊天室 16000</span><span class="sxs-lookup"><span data-stu-id="493f5-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-310">具有邀請的聊天室的百分比</span><span class="sxs-lookup"><span data-stu-id="493f5-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="493f5-311">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-311">50%</span></span></p></td>
<td><p><span data-ttu-id="493f5-312">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-312">50%</span></span></p></td>
<td><p><span data-ttu-id="493f5-313">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-314">設成傳送邀請的聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="493f5-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="493f5-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="493f5-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-317"><em>5</em></span><span class="sxs-lookup"><span data-stu-id="493f5-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-318">可以存取該聊天室的使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="493f5-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="493f5-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="493f5-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="493f5-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="493f5-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-322">Persistent Chat Server 所產生的邀請</span><span class="sxs-lookup"><span data-stu-id="493f5-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="493f5-323">960,000</span><span class="sxs-lookup"><span data-stu-id="493f5-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-324">120000</span><span class="sxs-lookup"><span data-stu-id="493f5-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-325">80000</span><span class="sxs-lookup"><span data-stu-id="493f5-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="493f5-326">1,160,000</span><span class="sxs-lookup"><span data-stu-id="493f5-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-327">最大允許的邀請數</span><span class="sxs-lookup"><span data-stu-id="493f5-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="493f5-328">每 2000000 個</span><span class="sxs-lookup"><span data-stu-id="493f5-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-329">模型 1-預期的每個聊天室每日的郵件數目的開頭</span><span class="sxs-lookup"><span data-stu-id="493f5-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-330">速率每個聊天室 （每日）</span><span class="sxs-lookup"><span data-stu-id="493f5-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="493f5-331">50</span><span class="sxs-lookup"><span data-stu-id="493f5-331">50</span></span></p></td>
<td><p><span data-ttu-id="493f5-332">500</span><span class="sxs-lookup"><span data-stu-id="493f5-332">500</span></span></p></td>
<td><p><span data-ttu-id="493f5-333">100</span><span class="sxs-lookup"><span data-stu-id="493f5-333">100</span></span></p></td>
<td><p><span data-ttu-id="493f5-334">650</span><span class="sxs-lookup"><span data-stu-id="493f5-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-335">跨所有聊天室的聊天速率 （每秒）</span><span class="sxs-lookup"><span data-stu-id="493f5-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-336">55.56</span><span class="sxs-lookup"><span data-stu-id="493f5-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="493f5-337">18.52</span><span class="sxs-lookup"><span data-stu-id="493f5-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="493f5-338">0.03</span><span class="sxs-lookup"><span data-stu-id="493f5-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="493f5-339">74</span><span class="sxs-lookup"><span data-stu-id="493f5-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-340">模型 2-開頭的每位使用者每天張貼的訊息數目</span><span class="sxs-lookup"><span data-stu-id="493f5-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-341">每位使用者每天的聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="493f5-342">15 </span><span class="sxs-lookup"><span data-stu-id="493f5-342">15</span></span></p></td>
<td><p><span data-ttu-id="493f5-343">5</span><span class="sxs-lookup"><span data-stu-id="493f5-343">5</span></span></p></td>
<td><p><span data-ttu-id="493f5-344">0.1</span><span class="sxs-lookup"><span data-stu-id="493f5-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="493f5-345">20</span><span class="sxs-lookup"><span data-stu-id="493f5-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-346">每個 （每日） 的聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="493f5-347">38</span><span class="sxs-lookup"><span data-stu-id="493f5-347">38</span></span></p></td>
<td><p><span data-ttu-id="493f5-348">375</span><span class="sxs-lookup"><span data-stu-id="493f5-348">375</span></span></p></td>
<td><p><span data-ttu-id="493f5-349">800</span><span class="sxs-lookup"><span data-stu-id="493f5-349">800</span></span></p></td>
<td><p><span data-ttu-id="493f5-350">1,213</span><span class="sxs-lookup"><span data-stu-id="493f5-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-351">跨所有聊天室的聊天速率 （每秒）</span><span class="sxs-lookup"><span data-stu-id="493f5-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-352">41.67</span><span class="sxs-lookup"><span data-stu-id="493f5-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="493f5-353">13.89</span><span class="sxs-lookup"><span data-stu-id="493f5-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="493f5-354">0.28</span><span class="sxs-lookup"><span data-stu-id="493f5-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="493f5-355">56</span><span class="sxs-lookup"><span data-stu-id="493f5-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="493f5-356">常設聊天室伺服器效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="493f5-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="493f5-357">下表說明 for Persistent Chat Server 的使用者模型。</span><span class="sxs-lookup"><span data-stu-id="493f5-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="493f5-358">它提供的容量規劃需求之基礎，代表含有四部伺服器上的 80000 位並行使用者的典型組織。</span><span class="sxs-lookup"><span data-stu-id="493f5-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="493f5-359">常設聊天室伺服器效能使用者模型</span><span class="sxs-lookup"><span data-stu-id="493f5-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="493f5-360">連線的作用中使用者數</span><span class="sxs-lookup"><span data-stu-id="493f5-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="493f5-361">80000</span><span class="sxs-lookup"><span data-stu-id="493f5-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-362">Persistent Chat Server 服務執行個體數</span><span class="sxs-lookup"><span data-stu-id="493f5-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="493f5-363">4</span><span class="sxs-lookup"><span data-stu-id="493f5-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-364">小型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="493f5-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-365">30 位使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-366">中型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="493f5-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-367">150 位使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-368">大型聊天室大小</span><span class="sxs-lookup"><span data-stu-id="493f5-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-369">16000 名使用者</span><span class="sxs-lookup"><span data-stu-id="493f5-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-370">聊天室總數</span><span class="sxs-lookup"><span data-stu-id="493f5-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-371">33,077</span><span class="sxs-lookup"><span data-stu-id="493f5-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-372">小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-373">32000</span><span class="sxs-lookup"><span data-stu-id="493f5-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-374">中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-375">1,067</span><span class="sxs-lookup"><span data-stu-id="493f5-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-376">大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-377">10 </span><span class="sxs-lookup"><span data-stu-id="493f5-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-378">每位使用者的聊天室總數</span><span class="sxs-lookup"><span data-stu-id="493f5-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-379">16 </span><span class="sxs-lookup"><span data-stu-id="493f5-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-380">每位使用者的小型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-381">12</span><span class="sxs-lookup"><span data-stu-id="493f5-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-382">每位使用者的中型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-383">2</span><span class="sxs-lookup"><span data-stu-id="493f5-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-384">每位使用者的大型聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-385">2</span><span class="sxs-lookup"><span data-stu-id="493f5-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-386">每個使用者加入的聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-387">24</span><span class="sxs-lookup"><span data-stu-id="493f5-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-388">尖峰加入速率</span><span class="sxs-lookup"><span data-stu-id="493f5-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="493f5-389">10/秒</span><span class="sxs-lookup"><span data-stu-id="493f5-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-390">總聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="493f5-391">24/秒</span><span class="sxs-lookup"><span data-stu-id="493f5-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-392">小型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-393">22.22/秒</span><span class="sxs-lookup"><span data-stu-id="493f5-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-394">中型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-395">1.67/秒</span><span class="sxs-lookup"><span data-stu-id="493f5-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-396">大型聊天室的聊天速率</span><span class="sxs-lookup"><span data-stu-id="493f5-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="493f5-397">~0.15/second</span><span class="sxs-lookup"><span data-stu-id="493f5-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-398">設成傳送邀請的聊天室百分比</span><span class="sxs-lookup"><span data-stu-id="493f5-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="493f5-399">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-400">直接成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="493f5-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="493f5-401">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-402">群組成員資格的百分比</span><span class="sxs-lookup"><span data-stu-id="493f5-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="493f5-403">50%</span><span class="sxs-lookup"><span data-stu-id="493f5-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-404">在 Active Directory 網域服務中的上階聯盟的平均數目</span><span class="sxs-lookup"><span data-stu-id="493f5-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="493f5-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="493f5-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-406">每位使用者的已訂閱連絡人數</span><span class="sxs-lookup"><span data-stu-id="493f5-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-407">80</span><span class="sxs-lookup"><span data-stu-id="493f5-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-408">平均每位使用者的端點數目</span><span class="sxs-lookup"><span data-stu-id="493f5-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-409">1.5</span><span class="sxs-lookup"><span data-stu-id="493f5-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-410">每個端點的可見聊天室的平均數目</span><span class="sxs-lookup"><span data-stu-id="493f5-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="493f5-411">1.5</span><span class="sxs-lookup"><span data-stu-id="493f5-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-412">平均每位使用者的可見聊天室數</span><span class="sxs-lookup"><span data-stu-id="493f5-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-413">2.25 （50 %1 的會議室而 50%為 2 的聊天室）;最多 6 個聊天室開啟時，監視每一個</span><span class="sxs-lookup"><span data-stu-id="493f5-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-414">每段間隔輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="493f5-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="493f5-415">每個可見聊天室 25</span><span class="sxs-lookup"><span data-stu-id="493f5-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-416">輪詢間隔的長度</span><span class="sxs-lookup"><span data-stu-id="493f5-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="493f5-417">5 分鐘</span><span class="sxs-lookup"><span data-stu-id="493f5-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-418">每秒輪詢的參與者數</span><span class="sxs-lookup"><span data-stu-id="493f5-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="493f5-419">15,000</span><span class="sxs-lookup"><span data-stu-id="493f5-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="493f5-420">每位使用者每小時的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="493f5-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="493f5-421">6 </span><span class="sxs-lookup"><span data-stu-id="493f5-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="493f5-422">每秒的目前狀態變更次數</span><span class="sxs-lookup"><span data-stu-id="493f5-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="493f5-423">133.33</span><span class="sxs-lookup"><span data-stu-id="493f5-423">133.33</span></span></p></td>
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

