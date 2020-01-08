---
title: Lync Server 2013：持久聊天伺服器的元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c59c3-102">Lync Server 2013 中持續聊天伺服器的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="c59c3-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c59c3-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c59c3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c59c3-104">持續聊天伺服器支援單伺服器設定和多重伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="c59c3-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="c59c3-105">永久聊天伺服器也可以在 Lync Server 2013 標準版伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c59c3-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="c59c3-106">這些設定包含下列持續性聊天伺服器元件與拓撲。</span><span class="sxs-lookup"><span data-stu-id="c59c3-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="c59c3-107">持續聊天伺服器元件</span><span class="sxs-lookup"><span data-stu-id="c59c3-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="c59c3-108">安裝最新版本的持久性聊天伺服器需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="c59c3-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="c59c3-109">一或多台執行持續聊天伺服器且提供下列服務的電腦：</span><span class="sxs-lookup"><span data-stu-id="c59c3-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="c59c3-110">持續聊天服務</span><span class="sxs-lookup"><span data-stu-id="c59c3-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="c59c3-111">相容性服務，在啟用合規性時開啟</span><span class="sxs-lookup"><span data-stu-id="c59c3-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c59c3-112">在 Lync Server 2013 中，[檔案上傳/下載] 的持續聊天 Web 服務現在已 collocated Lync&nbsp;server 2013 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c59c3-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="c59c3-113">Lync Server 2013&nbsp;前端伺服器也會 Collocated 聊天室管理的持續聊天 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c59c3-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="c59c3-114">伺服器（如果使用的是多個伺服器的話），該主機會主持 SQL Server 後端資料庫，以託管 [聊天室內容]、[會議室] 和 [類別] 的 [永久聊天] 內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c59c3-115">後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c59c3-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="c59c3-116">如果已啟用合規性，就會儲存一個伺服器（如果使用鏡像的話的話），宿主 SQL Server 後端資料庫以託管持續聊天相容性資料庫，且會儲存合規性事件和聊天內容。</span><span class="sxs-lookup"><span data-stu-id="c59c3-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="c59c3-117">若要從個別的電腦（例如系統管理主控台）管理持久聊天伺服器，請使用電腦上的 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c59c3-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="c59c3-118">這個電腦必須接著部署在 Active Directory 網域服務網域中，在林根中至少有一個通用類別目錄伺服器。</span><span class="sxs-lookup"><span data-stu-id="c59c3-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="c59c3-119">如需持續性聊天伺服器的硬體和軟體需求的詳細資訊，請參閱在支援檔中的 lync server [2013 支援的永久性聊天伺服器技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、 [lync server 2013 支援的硬體](lync-server-2013-supported-hardware.md)，以及[Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c59c3-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="c59c3-120">支援的 Collocation</span><span class="sxs-lookup"><span data-stu-id="c59c3-120">Supported Collocation</span></span>

<span data-ttu-id="c59c3-121">Lync Server 2013 支援各種不同的 collocation 案例，可讓您靈活地在一部伺服器（如果您有小型組織）上執行多個元件，或在不同的伺服器上執行個別元件（如果您有需要可伸縮性和效能的較大型組織。</span><span class="sxs-lookup"><span data-stu-id="c59c3-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="c59c3-122">在您決定是否要 collocate 元件之前，請務必先考慮伸縮性因素。</span><span class="sxs-lookup"><span data-stu-id="c59c3-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="c59c3-123">如果相容性已啟用，則持久聊天合規性服務會與 Lync Server 2013 前端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="c59c3-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="c59c3-124">永久聊天伺服器可以部署在標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="c59c3-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="c59c3-125">在本機 SQL Server Express 後端伺服器的標準版伺服器上，持續式聊天伺服器後端伺服器和持續式聊天合規性資料庫可以 collocated。</span><span class="sxs-lookup"><span data-stu-id="c59c3-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="c59c3-126">如需可在該處 collocated 之元件的詳細資訊，請參閱支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="c59c3-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c59c3-127">在 Lync Server 2013 企業版中，不能在企業版伺服器上 collocated 持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="c59c3-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="c59c3-128">持久聊天伺服器的 SQL Server 資料庫可以與企業版前端池的後端伺服器資料庫 collocated。</span><span class="sxs-lookup"><span data-stu-id="c59c3-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="c59c3-129">您也可以使用企業版池的後端伺服器資料庫，collocated 適用于持續聊天合規性的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c59c3-130">主持持久聊天資料庫的伺服器可以裝載其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="c59c3-131">不過，當您考慮將持續聊天資料庫與其他資料庫 collocating 時，請注意，如果您要儲存的訊息超過幾個使用者，持久聊天資料庫所需的磁碟空間可能會變得很大。</span><span class="sxs-lookup"><span data-stu-id="c59c3-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="c59c3-132">基於這個原因，我們不建議您 collocating 與後端資料庫的持續聊天資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="c59c3-133">如果您 collocate 與後端資料庫的持續聊天資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，或者，您也可以針對每個資料庫使用單獨的 sql Server 實例，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="c59c3-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="c59c3-134">每個 SQL Server 實例都只能包含一個後端資料庫及單一持久聊天資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="c59c3-135">如需 collocation 所有伺服器角色和資料庫的詳細資料，請參閱可支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="c59c3-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="c59c3-136">持續聊天伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="c59c3-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="c59c3-137">持續聊天伺服器支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="c59c3-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="c59c3-138">Lync Server 2013 企業版單一伺服器持久聊天伺服器前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c59c3-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="c59c3-139">Lync Server 2013 企業版多個伺服器持續聊天伺服器前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c59c3-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="c59c3-140">使用 SQL Server Express 的 Lync Server 2013 標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="c59c3-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="c59c3-141">Lync Server 2013 標準版伺服器以及在個別伺服器上使用標準版伺服器作為下一個躍點伺服器的持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="c59c3-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="c59c3-142">您可以使用 [拓撲建立器]，將持續性聊天伺服器新增到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="c59c3-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="c59c3-143">您可以將單一伺服器或多個伺服器持續聊天伺服器池新增到您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="c59c3-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c59c3-144">使用 [拓撲建立器] 建立單一伺服器的持續聊天伺服器池之後，您就無法將其他伺服器新增到該池中。</span><span class="sxs-lookup"><span data-stu-id="c59c3-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="c59c3-145">單伺服器拓朴</span><span class="sxs-lookup"><span data-stu-id="c59c3-145">Single-Server Topology</span></span>

<span data-ttu-id="c59c3-146">持續聊天伺服器的最小設定和最簡單的部署是單一持續式聊天伺服器前端伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="c59c3-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="c59c3-147">此部署需要單一伺服器來執行持續聊天伺服器（如果相容性已啟用，也可選擇執行合規性服務）、託管 SQL Server 資料庫的伺服器，以及如果需要合規性，則是 SQL Server 資料庫來儲存合規性資料。</span><span class="sxs-lookup"><span data-stu-id="c59c3-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c59c3-148">您無法將其他伺服器新增至永久聊天伺服器池中，該池是在拓撲建立器中以單一伺服器部署的形式啟動。</span><span class="sxs-lookup"><span data-stu-id="c59c3-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="c59c3-149">我們建議您使用多重伺服器池拓撲結構，即使您使用的是單一伺服器，您也可以在日後新增更多伺服器（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="c59c3-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="c59c3-150">下圖顯示單一持續聊天伺服器前端伺服器（符合合規性）的所有必要和選用元件。</span><span class="sxs-lookup"><span data-stu-id="c59c3-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="c59c3-151">**單一持久聊天伺服器**</span><span class="sxs-lookup"><span data-stu-id="c59c3-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="c59c3-152">![單一伺服器拓朴與合規性服務](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "單一伺服器拓撲（含合規性服務")）</span><span class="sxs-lookup"><span data-stu-id="c59c3-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="c59c3-153">多重伺服器拓朴</span><span class="sxs-lookup"><span data-stu-id="c59c3-153">Multiple-Server Topology</span></span>

<span data-ttu-id="c59c3-154">若要提供更大的容量及可靠性，您可以部署多伺服器拓朴，如在[Lync server 2013 規劃持續聊天伺服器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="c59c3-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="c59c3-155">多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦（高可用性和災害復原設定允許最多八個，但只有四個作用中的4個作用中，還有四個作用中的四個）。</span><span class="sxs-lookup"><span data-stu-id="c59c3-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="c59c3-156">每個伺服器可支援多達20000並行的使用者，總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="c59c3-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="c59c3-157">多重伺服器拓朴與單一伺服器拓朴一樣，只是多個伺服器主機持久的聊天伺服器，而且可以擴大規模。</span><span class="sxs-lookup"><span data-stu-id="c59c3-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="c59c3-158">多台執行持續聊天伺服器的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="c59c3-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="c59c3-159">下圖顯示多伺服器拓朴中的所有元件，其中多台電腦執行持續聊天伺服器、選用規範服務，以及個別的合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="c59c3-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="c59c3-160">**多個持續聊天伺服器**</span><span class="sxs-lookup"><span data-stu-id="c59c3-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="c59c3-161">![多個伺服器拓撲]結構(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多個伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="c59c3-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="c59c3-162">多伺服器拓朴提供伺服器功能的彙集。</span><span class="sxs-lookup"><span data-stu-id="c59c3-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="c59c3-163">在伺服器池中，持續聊天服務會與資料進行通訊和共用。</span><span class="sxs-lookup"><span data-stu-id="c59c3-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="c59c3-164">例如，您可以從系統中的任何持續聊天服務取得最初張貼到一個持續聊天服務的聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="c59c3-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="c59c3-165">透過一個持久聊天服務上傳的檔案，可透過任何持續聊天服務存取。</span><span class="sxs-lookup"><span data-stu-id="c59c3-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="c59c3-166">使用者可以連線至不同的持續聊天伺服器前端伺服器，而且可以彼此聊天和通訊。</span><span class="sxs-lookup"><span data-stu-id="c59c3-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="c59c3-167">TCP 8011 的預設埠會將伺服器連線到伺服器池中，且持續聊天服務會使用它來溝通本身，或用於管理目的。</span><span class="sxs-lookup"><span data-stu-id="c59c3-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

