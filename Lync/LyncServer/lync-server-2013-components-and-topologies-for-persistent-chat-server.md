---
title: Lync Server 2013： Persistent Chat Server 的元件和拓撲
description: Lync Server 2013： Persistent Chat Server 的元件和拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576809"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="a4775-103">Lync Server 2013 中持久聊天伺服器的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="a4775-103">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4775-104">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a4775-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a4775-105">Persistent Chat Server 同時支援單一伺服器設定和多部伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="a4775-105">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="a4775-106">Persistent Chat Server 也可以在 Lync Server 2013 Standard Edition Server 上執行。</span><span class="sxs-lookup"><span data-stu-id="a4775-106">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="a4775-107">這些設定包含下列 Persistent Chat Server 元件和拓撲。</span><span class="sxs-lookup"><span data-stu-id="a4775-107">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="a4775-108">Persistent Chat Server 元件</span><span class="sxs-lookup"><span data-stu-id="a4775-108">Persistent Chat Server Components</span></span>

<span data-ttu-id="a4775-109">安裝最新版本的 Persistent Chat Server 需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="a4775-109">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="a4775-110">一或多部執行 Persistent Chat Server 的電腦，並提供下列服務：</span><span class="sxs-lookup"><span data-stu-id="a4775-110">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="a4775-111">Persistent Chat service</span><span class="sxs-lookup"><span data-stu-id="a4775-111">Persistent Chat service</span></span>
    
      - <span data-ttu-id="a4775-112">規範服務，會在啟用規範時開啟</span><span class="sxs-lookup"><span data-stu-id="a4775-112">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a4775-113">在 Lync Server 2013 中，檔案上傳/下載的 Persistent Chat Web 服務現在已與 Lync Server 2013 &nbsp; 前端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="a4775-113">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="a4775-114">聊天室管理的 Persistent Chat Web 服務也會與 Lync Server 2013 &nbsp; 前端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="a4775-114">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="a4775-115">如果) 使用鏡像，則伺服器 (s) 會 (多部伺服器，該主機會主控 SQL Server 後端資料庫，以裝載存放聊天室內容、會議室和類別的持久聊天內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-115">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a4775-116">後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的資訊。</span><span class="sxs-lookup"><span data-stu-id="a4775-116">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="a4775-117">如果已啟用相容性，則伺服器 (s) 會 (多部伺服器。如果) 使用鏡像，則會主控 SQL Server 後端資料庫，以主控持久的聊天室規範資料庫，以儲存相容性事件和聊天內容的目的。</span><span class="sxs-lookup"><span data-stu-id="a4775-117">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="a4775-118">若要從不同的電腦管理 Persistent Chat Server (例如管理主控台) ，請使用電腦上的 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a4775-118">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="a4775-119">這部電腦必須部署在 Active Directory 網域服務網域中，至少要有一個樹系根中的通用類別目錄伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4775-119">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="a4775-120">如需有關 Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱支援檔中的 lync server [2013 中的 [Persistent Chat server] 的技術需求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)（lync server [2013 支援的硬體](lync-server-2013-supported-hardware.md)，以及 [Lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="a4775-120">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="a4775-121">支援的組合</span><span class="sxs-lookup"><span data-stu-id="a4775-121">Supported Collocation</span></span>

<span data-ttu-id="a4775-122">Lync Server 2013 支援各種組合案例，可讓您靈活地在一部伺服器 (上執行多個元件，以節省硬體成本，如果您有小型組織) ，或是在不同的伺服器上執行個別元件 (如果您有較大的組織需要可擴充性和效能) 。</span><span class="sxs-lookup"><span data-stu-id="a4775-122">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="a4775-123">在您決定是否組合元件之前，務必考量延展性因素。</span><span class="sxs-lookup"><span data-stu-id="a4775-123">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="a4775-124">如果啟用規範，則 Persistent Chat 合規性服務會與 Lync Server 2013 前端伺服器進行組合。</span><span class="sxs-lookup"><span data-stu-id="a4775-124">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="a4775-125">Persistent Chat Server 可以部署在 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="a4775-125">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="a4775-126">在本機 SQL Server Express 後端伺服器上的 Standard Edition server 上，可以組合持久的 Chat Server 後端伺服器和 Persistent 聊天室規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-126">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="a4775-127">如需可在該處組合之元件的詳細資訊，請參閱支援檔中的 [支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。</span><span class="sxs-lookup"><span data-stu-id="a4775-127">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a4775-128">對於 Lync Server 2013 Enterprise Edition，無法在 Enterprise Edition Server 上組合 Persistent Chat server。</span><span class="sxs-lookup"><span data-stu-id="a4775-128">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="a4775-129">Persistent Chat Server 的 SQL Server 資料庫可與 Enterprise Edition 前端集區的後端伺服器資料庫組合。</span><span class="sxs-lookup"><span data-stu-id="a4775-129">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="a4775-130">使用 Enterprise Edition 集區的後端伺服器資料庫也可以組合適用于持續性聊天規範的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-130">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4775-131">主控 Persistent Chat 資料庫的伺服器可以主控其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-131">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="a4775-132">不過，當您考慮將 Persistent Chat 資料庫與其他資料庫組合時，請注意，如果您儲存的是少數幾個使用者的郵件，則 Persistent Chat 資料庫所需的磁碟空間會變得非常大。</span><span class="sxs-lookup"><span data-stu-id="a4775-132">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="a4775-133">基於這個理由，我們不建議組合 Persistent Chat 資料庫與後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-133">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="a4775-134">如果您使用後端資料庫組合 Persistent Chat 資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，也可以針對每個資料庫使用不同的 SQL Server 實例，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="a4775-134">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="a4775-135">每個 SQL Server 實例只能包含單一後端資料庫和單一持久聊天資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-135">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="a4775-136">如需組合的所有伺服器角色及資料庫的詳細資訊，請參閱支援檔中的 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="a4775-136">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="a4775-137">Persistent Chat Server 拓撲</span><span class="sxs-lookup"><span data-stu-id="a4775-137">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="a4775-138">Persistent Chat Server 支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="a4775-138">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="a4775-139">Lync Server 2013 Enterprise Edition single server Persistent Chat server 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="a4775-139">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="a4775-140">Lync Server 2013 Enterprise Edition 多部伺服器 Persistent Chat Server 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="a4775-140">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="a4775-141">使用 SQL Server Express 的 Lync Server 2013 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="a4775-141">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="a4775-142">使用 Standard Edition server 做為下一個躍點伺服器的不同伺服器上的 Lync Server 2013 Standard Edition server 和 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="a4775-142">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="a4775-143">您可以使用拓撲產生器，將 Persistent Chat Server 新增至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="a4775-143">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="a4775-144">您可以將單一伺服器或多部伺服器的持久聊天伺服器集區新增至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="a4775-144">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4775-145">使用拓撲產生器建立持久聊天伺服器集區和單一伺服器之後，就無法將其他伺服器新增至集區。</span><span class="sxs-lookup"><span data-stu-id="a4775-145">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="a4775-146">單一伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="a4775-146">Single-Server Topology</span></span>

<span data-ttu-id="a4775-147">Persistent Chat Server 的最小設定和最簡單部署是單一持久聊天伺服器前端伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="a4775-147">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="a4775-148">此部署需要執行 Persistent Chat Server (的單一伺服器，如果符合性已啟用) 、主控 SQL Server 資料庫的伺服器及相容性（若有必要），則會執行該程式，以儲存相容性資料。</span><span class="sxs-lookup"><span data-stu-id="a4775-148">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4775-149">您無法將其他伺服器新增至 Persistent Chat Server 集區，此集區在拓撲產生器中以單一伺服器部署的方式啟動。</span><span class="sxs-lookup"><span data-stu-id="a4775-149">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="a4775-150">即使您正在使用單一伺服器，我們仍建議您使用多伺服器集區拓撲，這樣您就可以在日後視需要新增更多的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a4775-150">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="a4775-151">下圖顯示單一 Persistent Chat Server 前端伺服器及規範的拓撲的所有必要和選用元件。</span><span class="sxs-lookup"><span data-stu-id="a4775-151">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="a4775-152">**單一常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="a4775-152">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="a4775-153">![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="a4775-153">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="a4775-154">多部伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="a4775-154">Multiple-Server Topology</span></span>

<span data-ttu-id="a4775-155">若要提供更大的容量與可靠性，您可以部署多伺服器拓撲，如在 [Lync server 2013 中規劃 Persistent Chat server](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="a4775-155">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="a4775-156">多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。</span><span class="sxs-lookup"><span data-stu-id="a4775-156">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="a4775-157">每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。</span><span class="sxs-lookup"><span data-stu-id="a4775-157">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="a4775-158">多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。</span><span class="sxs-lookup"><span data-stu-id="a4775-158">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="a4775-159">多部執行 Persistent Chat Server 的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。</span><span class="sxs-lookup"><span data-stu-id="a4775-159">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="a4775-160">下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4775-160">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="a4775-161">**多部常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="a4775-161">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="a4775-162">![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="a4775-162">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="a4775-163">多伺服器拓撲提供伺服器功能的集區。</span><span class="sxs-lookup"><span data-stu-id="a4775-163">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="a4775-164">在伺服器集區中，Persistent Chat service 會通訊和共用資料。</span><span class="sxs-lookup"><span data-stu-id="a4775-164">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="a4775-165">例如，您可以從系統中的任何 Persistent Chat service 取得最初發佈到某項 Persistent Chat service 的聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="a4775-165">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="a4775-166">任何 Persistent chat service 都可以存取透過某項 Persistent Chat service 上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="a4775-166">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="a4775-167">使用者可以連線至不同的持久聊天伺服器前端伺服器，也可以相互聊天和通訊。</span><span class="sxs-lookup"><span data-stu-id="a4775-167">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="a4775-168">TCP 8011 的預設埠會將伺服器連線至伺服器集區，而 Persistent Chat service 會使用該埠自行進行通訊，或用於管理目的。</span><span class="sxs-lookup"><span data-stu-id="a4775-168">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

