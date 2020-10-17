---
title: Lync Server 2013：封存的元件和拓撲
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
ms.openlocfilehash: ec153b237df086f3622acc70c104bddc64fef28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502610"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="a3779-102">Lync Server 2013 中封存的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="a3779-102">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3779-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a3779-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a3779-104">如果您想要封存 Lync Server 2013 IM 和會議內容，您可以在 Lync Server 中執行封存。</span><span class="sxs-lookup"><span data-stu-id="a3779-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="a3779-105">封存元件</span><span class="sxs-lookup"><span data-stu-id="a3779-105">Archiving Components</span></span>

<span data-ttu-id="a3779-106">封存功能包括下列元件：</span><span class="sxs-lookup"><span data-stu-id="a3779-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="a3779-p101">**封存代理程式**。封存代理程式 (亦稱為整合資料收集代理程式) 會自動安裝在每個前端集區和 Standard Edition Server 上並啟動。儘管封存代理程式會自動啟動，但在啟用封存並進行適當設定之前，還是不會實際擷取任何訊息。</span><span class="sxs-lookup"><span data-stu-id="a3779-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="a3779-110">**封存資料存放區**。</span><span class="sxs-lookup"><span data-stu-id="a3779-110">**Archiving data storage**.</span></span> <span data-ttu-id="a3779-111">Lync Server 2013 的資料儲存區可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a3779-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="a3779-112">Exchange 2013 儲存體。</span><span class="sxs-lookup"><span data-stu-id="a3779-112">Exchange 2013 storage.</span></span> <span data-ttu-id="a3779-113">如果您啟用 Microsoft Exchange 整合選項，則在 Exchange 2013 伺服器上的使用者信箱會將 Exchange 2013 儲存區用於封存的資料，但只有在信箱已放在 In-Place 保留中時。</span><span class="sxs-lookup"><span data-stu-id="a3779-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="a3779-114">SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="a3779-114">SQL Server storage.</span></span> <span data-ttu-id="a3779-115">如果您的部署中有使用者在 Lync Server 2013 上，您可以設定執行支援的 SQL Server 版本的封存資料庫，以啟用這些使用者的封存功能。</span><span class="sxs-lookup"><span data-stu-id="a3779-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="a3779-116">封存也會要求檔案存放區，但封存會使用與前端伺服器或 Standard Edition Server 相同的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="a3779-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="a3779-117">如需封存的硬體和軟體需求清單，請參閱支援檔中的 lync server 2013 和[伺服器軟體和基礎結構2013支援](lync-server-2013-server-software-and-infrastructure-support.md)的[支援硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="a3779-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="a3779-118">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="a3779-118">Supported Topologies</span></span>

<span data-ttu-id="a3779-119">您在每個使用者要求支援封存的集區中部署封存。</span><span class="sxs-lookup"><span data-stu-id="a3779-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="a3779-120">封存會在 Enterprise Edition pool 和 Standard Edition server 上的前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="a3779-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="a3779-121">封存資料存放區可以是下列項目：</span><span class="sxs-lookup"><span data-stu-id="a3779-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="a3779-122">與 Exchange 2013 儲存整合</span><span class="sxs-lookup"><span data-stu-id="a3779-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="a3779-123">使用不同的 SQL Server 資料庫部署</span><span class="sxs-lookup"><span data-stu-id="a3779-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="a3779-124">如果您的 Exchange 2013 部署不包括 Lync Server 部署中的所有使用者，您必須針對其信箱在 Exchange 2013 伺服器上的使用者，使用 Microsoft Exchange 整合，而且您必須為所有其他 Lync 使用者部署個別的 SQL Server 資料庫，以供封存使用。</span><span class="sxs-lookup"><span data-stu-id="a3779-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="a3779-125">支援的組合</span><span class="sxs-lookup"><span data-stu-id="a3779-125">Supported Collocation</span></span>

<span data-ttu-id="a3779-126">Lync Server 2013 支援各種組合案例，可讓您靈活地在一部 (伺服器上執行多個元件，以節省硬體成本，如果您有) 小型組織，或是在不同的伺服器上執行個別元件 (如果您有較大的組織需要可擴充性和效能) 。</span><span class="sxs-lookup"><span data-stu-id="a3779-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="a3779-127">在您決定是否組合元件之前，務必考量延展性因素。</span><span class="sxs-lookup"><span data-stu-id="a3779-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="a3779-128">封存部署于集區或 Standard Edition server 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a3779-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="a3779-129">如需可在該處組合之元件的詳細資訊，請參閱支援檔中的 [支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。</span><span class="sxs-lookup"><span data-stu-id="a3779-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a3779-130">如果您使用個別的 SQL Server 資料庫進行封存，而不是或除了整合 Exchange 2013 儲存的儲存體，您可以使用下列任何一種方式來組合封存資料庫：</span><span class="sxs-lookup"><span data-stu-id="a3779-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="a3779-131">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="a3779-131">Monitoring database</span></span>

  - <span data-ttu-id="a3779-132">Enterprise Edition 前端集區的後端資料庫</span><span class="sxs-lookup"><span data-stu-id="a3779-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3779-p108">裝載封存資料庫的伺服器可以裝載其他資料庫。不過，當您考慮將封存資料庫與其他資料庫組合時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。基於這項因素，建議您不要將封存資料庫與後端資料庫整合。</span><span class="sxs-lookup"><span data-stu-id="a3779-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="a3779-136">如果您將封存資料庫與監控資料庫、後端資料庫 (或兩者) 組合在一起，即可將單一 SQL 執行個體使用於任一或所有資料庫；或者，您可以將個別 SQL 執行個體使用於每一個資料庫，但具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="a3779-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="a3779-137">每個 SQL 執行個體僅能包含單一後端資料庫、單一監控資料庫和單一封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="a3779-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="a3779-138">如需組合的所有伺服器角色及資料庫的詳細資訊，請參閱支援檔中的 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="a3779-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

