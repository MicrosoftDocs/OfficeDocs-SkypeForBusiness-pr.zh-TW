---
title: Lync Server 2013： 的元件和拓撲 Persistent Chat Server
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
ms.openlocfilehash: be9ab539b652fc1d6ae82883df1f8875a0257614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5a1d3-102">Persistent Chat Server in Lync Server 2013 的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="5a1d3-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a1d3-103">_**主題上次修改日期：** 2012年-10-05_</span><span class="sxs-lookup"><span data-stu-id="5a1d3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5a1d3-104">Persistent Chat Server 支援單一伺服器組態和多部伺服器組態。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="5a1d3-105">Persistent Chat Server 也可以在 Lync Server 2013 Standard Edition server 上執行。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="5a1d3-106">這些設定包括下列 Persistent Chat Server 元件和拓撲。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="5a1d3-107">常設聊天室伺服器元件</span><span class="sxs-lookup"><span data-stu-id="5a1d3-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="5a1d3-108">安裝最新版的 Persistent Chat Server 需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="5a1d3-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="5a1d3-109">一或多個電腦執行 Persistent Chat Server，並提供下列服務：</span><span class="sxs-lookup"><span data-stu-id="5a1d3-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="5a1d3-110">常設聊天服務</span><span class="sxs-lookup"><span data-stu-id="5a1d3-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="5a1d3-111">規範服務，會在啟用規範時開啟</span><span class="sxs-lookup"><span data-stu-id="5a1d3-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5a1d3-112">在 Lync Server 2013 常設聊天室 Web 服務的檔案上傳/下載中現在已組合搭配 Lync Server 2013&nbsp;前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="5a1d3-113">常設聊天室 Web 服務用於聊天室管理也組合搭配 Lync Server 2013&nbsp;前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="5a1d3-114">伺服器 （多部用於一部伺服器如果鏡像） 裝載 SQL Server 後端資料庫，以裝載儲存聊天室內容、 房間和類別的常設聊天室內容資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a1d3-115">後端資料庫可儲存交談記錄資料，包括類別和所建立的常設聊天室的資訊。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="5a1d3-116">如果啟用規範，裝載 SQL Server 後端資料庫，以裝載儲存規範事件與交談內容，基於規範目的常設聊天室規範資料庫伺服器 （多部用如果鏡像的一部伺服器）。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="5a1d3-117">若要管理 Persistent Chat Server 從不同的電腦 （例如系統管理主控台），請在電腦上使用 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="5a1d3-118">這部電腦然後必須部署在 Active Directory 網域服務的網域中,，但會與樹系根中至少一個通用類別目錄伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="5a1d3-119">如需 for Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱支援文件中[的 Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、 [Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)，和[Lync Server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="5a1d3-120">支援的組合</span><span class="sxs-lookup"><span data-stu-id="5a1d3-120">Supported Collocation</span></span>

<span data-ttu-id="5a1d3-121">Lync Server 2013 支援的各種組合案例中，提供的彈性來節省硬體成本 （如果您擁有小型組織） 的一部伺服器，執行多個元件，或在不同的伺服器上執行個別元件 (如果您有大型組織需要延展性和效能）。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="5a1d3-122">在您決定是否組合元件之前，務必考量延展性因素。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="5a1d3-123">常設聊天室規範服務，如果啟用規範，則已組合與 Lync Server 2013 前端伺服器中。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="5a1d3-124">Persistent Chat Server 可以部署在 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="5a1d3-125">常設聊天室伺服器後端伺服器和常設聊天室規範資料庫可以組合在 Standard Edition 伺服器的本機 SQL Server Express 後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="5a1d3-126">如需可以那里組合的元件的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5a1d3-127">針對 Lync Server 2013 Enterprise Edition，常設聊天室伺服器無法配置在一起 Enterprise Edition 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="5a1d3-128">Persistent Chat Server 的 SQL Server 資料庫可以與 Enterprise Edition 前端集區的後端伺服器資料庫組合。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="5a1d3-129">常設聊天室規範 SQL Server 資料庫也可以組合與 Enterprise Edition 集區的後端伺服器資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a1d3-130">常設聊天室資料庫所在的伺服器可以主控其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="5a1d3-131">不過，當您考慮組合常設聊天室資料庫與其他資料庫，請注意，如果您儲存多個使用者的郵件的磁碟空間需要常設聊天室資料庫可以變得非常大。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="5a1d3-132">基於這個理由，我們不建議組合常設聊天室資料庫與後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="5a1d3-133">如果您在組合常設聊天室資料庫與後端資料庫，您也可以使用任何的 SQL Server 的單一執行個體或所有資料庫，或者您都可以使用 SQL Server 個別執行個體的每個資料庫，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="5a1d3-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="5a1d3-134">每個 SQL Server 執行個體可以包含單一後端資料庫和單一常設聊天室資料庫。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="5a1d3-135">如需所有伺服器角色和資料庫組合的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="5a1d3-136">常設聊天室伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="5a1d3-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="5a1d3-137">Persistent Chat Server 支援下列拓撲：</span><span class="sxs-lookup"><span data-stu-id="5a1d3-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="5a1d3-138">Lync Server 2013 Enterprise Edition 單一伺服器 Persistent Chat Server 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5a1d3-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="5a1d3-139">Lync Server 2013 Enterprise Edition 多部伺服器 Persistent Chat Server 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5a1d3-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="5a1d3-140">使用 SQL Server Express 的 Lync Server 2013 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="5a1d3-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="5a1d3-141">Lync Server 2013 Standard Edition server 和使用 Standard Edition server 的下一個躍點伺服器為一部伺服器上的 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="5a1d3-142">您可以使用拓撲產生器，將 Persistent Chat Server 新增至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="5a1d3-143">您可以新增單一或多個伺服器 Persistent Chat Server 集區至您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a1d3-144">您使用拓撲產生器來建立含有單一伺服器 Persistent Chat Server 集區之後，您無法新增其他伺服器至集區。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="5a1d3-145">單一伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="5a1d3-145">Single-Server Topology</span></span>

<span data-ttu-id="5a1d3-146">最小的設定資料庫和 for Persistent Chat Server 的最簡單部署是單一常設聊天室伺服器前端伺服器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="5a1d3-147">此部署需要執行常設聊天室伺服器 （如果啟用規範，選擇性地執行規範服務，）、 主控這兩個 SQL Server 資料庫伺服器的單一伺服器和合規性是否有需要，要儲存的 SQL Server 資料庫規範資料。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a1d3-148">您無法新增其他伺服器至已啟動拓撲產生器中的單一伺服器部署為 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="5a1d3-149">即使您正在使用單一伺服器，我們仍建議您使用多伺服器集區拓撲，這樣您就可以在日後視需要新增更多的伺服器。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="5a1d3-150">下圖顯示內含規範單一常設聊天室伺服器前端伺服器拓撲的所有必要與選用元件。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="5a1d3-151">**單一常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="5a1d3-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="5a1d3-152">![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="5a1d3-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="5a1d3-153">多部伺服器拓撲</span><span class="sxs-lookup"><span data-stu-id="5a1d3-153">Multiple-Server Topology</span></span>

<span data-ttu-id="5a1d3-154">若要提供更大的容量及可靠性，您可以部署多部伺服器拓撲，[規劃 Persistent Chat Server in Lync Server 2013 ](lync-server-2013-planning-for-persistent-chat-server.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="5a1d3-155">多部伺服器拓撲可以包含多達四個作用中的電腦執行 Persistent Chat Server （高可用性和災害復原設定會允許最多第八個，但只有四個可以是作用中，其餘四處於待命狀態）。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="5a1d3-156">每個伺服器可支援多達 20000 位並行使用者，總共為 80000 位並行使用者連線到具有 4 部伺服器 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="5a1d3-157">在多部伺服器拓撲是單一伺服器拓撲相同之處在於多部伺服器主控 Persistent Chat Server，並可將其調整更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="5a1d3-158">執行 Persistent Chat Server 的多部電腦應該位於相同的 Active Directory 網域服務網域 Lync 伺服器和規範服務。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="5a1d3-159">下圖顯示所有的元件的多部伺服器拓撲與執行 Persistent Chat Server、 選用的 Compliance service 和獨立的規範資料庫的多部電腦。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="5a1d3-160">**多部常設聊天室伺服器**</span><span class="sxs-lookup"><span data-stu-id="5a1d3-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="5a1d3-161">![多伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多伺服器拓撲")</span><span class="sxs-lookup"><span data-stu-id="5a1d3-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="5a1d3-162">多伺服器拓撲提供伺服器功能的集區。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="5a1d3-163">伺服器集區中的常設聊天室服務通訊，並共用資料。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="5a1d3-164">例如，原本已張貼到一個常設聊天室服務的聊天歷程記錄系統中是可從任何常設聊天室服務。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="5a1d3-165">任何的常設聊天室服務可透過一個常設聊天室服務上傳的檔案。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="5a1d3-166">使用者可以連線至不同 Persistent Chat Server 前端伺服器和可以聊天並與彼此進行通訊。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="5a1d3-167">預設連接埠 TCP 8011 會將伺服器連接至伺服器集區，並由通訊之間，或系統管理用途的常設聊天室服務。</span><span class="sxs-lookup"><span data-stu-id="5a1d3-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

