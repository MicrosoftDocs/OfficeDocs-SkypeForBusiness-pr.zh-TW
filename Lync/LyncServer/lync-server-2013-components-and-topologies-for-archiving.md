---
title: Lync Server 2013： 的元件和拓撲封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea07370fc0ccaebb5e89cfea958067b3d6373bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="0d4fa-102">Lync Server 2013 中的封存的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="0d4fa-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d4fa-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="0d4fa-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0d4fa-104">如果您想要封存的 Lync Server 2013 IM 和會議內容，您可以在 Lync Server 中實作封存。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="0d4fa-105">封存元件</span><span class="sxs-lookup"><span data-stu-id="0d4fa-105">Archiving Components</span></span>

<span data-ttu-id="0d4fa-106">封存功能包括下列元件：</span><span class="sxs-lookup"><span data-stu-id="0d4fa-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="0d4fa-p101">**封存代理程式**。封存代理程式 (亦稱為整合資料收集代理程式) 會自動安裝在每個前端集區和 Standard Edition Server 上並啟動。儘管封存代理程式會自動啟動，但在啟用封存並進行適當設定之前，還是不會實際擷取任何訊息。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="0d4fa-110">**封存資料存放區**。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-110">**Archiving data storage**.</span></span> <span data-ttu-id="0d4fa-111">Lync Server 2013 的資料儲存區可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0d4fa-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="0d4fa-112">Exchange 2013 儲存體。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-112">Exchange 2013 storage.</span></span> <span data-ttu-id="0d4fa-113">如果您啟用 [Microsoft Exchange 整合選項，使用者信箱位於 Exchange 2013 伺服器使用封存的資料，但僅限如果信箱已處於就地保留中的 Exchange 2013 儲存體。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="0d4fa-114">SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-114">SQL Server storage.</span></span> <span data-ttu-id="0d4fa-115">如果您有部署中，位於 Lync Server 2013 的使用者，您可以設定封存執行支援的版本的 SQL Server，以對那些使用者啟用封存的資料庫。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="0d4fa-116">封存也會要求檔案存放區，但封存會使用與前端伺服器或 Standard Edition Server 相同的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="0d4fa-117">如要封存的硬體和軟體需求清單，請參閱支援文件中的[支援 Lync Server 2013 的](lync-server-2013-supported-hardware.md)軟硬體[的 Server software and Lync Server 2013 中支援的基礎結構](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="0d4fa-118">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="0d4fa-118">Supported Topologies</span></span>

<span data-ttu-id="0d4fa-119">您在每個使用者要求支援封存的集區中部署封存。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="0d4fa-120">封存在 Enterprise Edition 集區中前端伺服器和 Standard Edition server 上執行。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="0d4fa-121">封存資料存放區可以是下列項目：</span><span class="sxs-lookup"><span data-stu-id="0d4fa-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="0d4fa-122">與 Exchange 2013 儲存體整合</span><span class="sxs-lookup"><span data-stu-id="0d4fa-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="0d4fa-123">部署使用不同的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="0d4fa-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="0d4fa-124">如果您的 Exchange 2013 部署 Lync Server 部署中未包含的所有使用者，您必須為其信箱的使用者使用 Microsoft Exchange 整合首頁在 Exchange 2013 伺服器，以及您必須針對所有其他部署不同的 SQL Server 資料庫要用於封存的 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="0d4fa-125">支援的組合</span><span class="sxs-lookup"><span data-stu-id="0d4fa-125">Supported Collocation</span></span>

<span data-ttu-id="0d4fa-126">Lync Server 2013 支援的各種組合案例中，讓您節省硬體成本 （如果您擁有小型組織） 的一部伺服器，執行多個元件，或在不同的伺服器上執行個別元件 （如果您有較大的彈性組織需要延展性和效能）。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="0d4fa-127">在您決定是否組合元件之前，務必考量延展性因素。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="0d4fa-128">封存部署的集區前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="0d4fa-129">如需可以那里組合的元件的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="0d4fa-130">如果您使用個別的 SQL Server 資料庫的封存，而不是或除了整合存放裝置與 Exchange 2013 儲存體，您可以組合封存資料庫與下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0d4fa-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="0d4fa-131">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="0d4fa-131">Monitoring database</span></span>

  - <span data-ttu-id="0d4fa-132">Enterprise Edition 前端集區的後端資料庫</span><span class="sxs-lookup"><span data-stu-id="0d4fa-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d4fa-p108">裝載封存資料庫的伺服器可以裝載其他資料庫。不過，當您考慮將封存資料庫與其他資料庫組合時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。基於這項因素，建議您不要將封存資料庫與後端資料庫整合。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="0d4fa-136">如果您將封存資料庫與監控資料庫、後端資料庫 (或兩者) 組合在一起，即可將單一 SQL 執行個體使用於任一或所有資料庫；或者，您可以將個別 SQL 執行個體使用於每一個資料庫，但具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="0d4fa-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="0d4fa-137">每個 SQL 執行個體僅能包含單一後端資料庫、單一監控資料庫和單一封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="0d4fa-138">如需所有伺服器角色和資料庫組合的詳細資訊，請參閱支援文件中的[Lync Server 2013 中的支援伺服器共同配置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

