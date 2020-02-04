---
title: Lync Server 2013：封存的元件與拓撲
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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="e8f05-102">Lync Server 2013 中封存的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="e8f05-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8f05-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e8f05-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e8f05-104">如果您想要封存 Lync Server 2013 IM 和會議內容，您可以在 Lync Server 中執行封存。</span><span class="sxs-lookup"><span data-stu-id="e8f05-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="e8f05-105">封存元件</span><span class="sxs-lookup"><span data-stu-id="e8f05-105">Archiving Components</span></span>

<span data-ttu-id="e8f05-106">[存檔] 功能包括下列元件：</span><span class="sxs-lookup"><span data-stu-id="e8f05-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="e8f05-107">封存**代理**程式。</span><span class="sxs-lookup"><span data-stu-id="e8f05-107">**Archiving agents**.</span></span> <span data-ttu-id="e8f05-108">封存代理程式（也稱為 [整合資料收集代理程式]）會自動安裝並在每個前端池和標準版伺服器上啟用。</span><span class="sxs-lookup"><span data-stu-id="e8f05-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="e8f05-109">雖然封存代理程式會自動啟用，但在啟用封存並適當設定前，不會實際捕獲任何訊息。</span><span class="sxs-lookup"><span data-stu-id="e8f05-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="e8f05-110">**歸檔資料儲存空間**。</span><span class="sxs-lookup"><span data-stu-id="e8f05-110">**Archiving data storage**.</span></span> <span data-ttu-id="e8f05-111">Lync Server 2013 的資料儲存空間可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e8f05-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="e8f05-112">Exchange 2013 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e8f05-112">Exchange 2013 storage.</span></span> <span data-ttu-id="e8f05-113">如果您啟用 Microsoft Exchange 整合選項，則駐留在 Exchange 2013 伺服器的使用者信箱會將 Exchange 2013 儲存空間用於已歸檔的資料，但只有在已將信箱放在就地保留中的情況下。</span><span class="sxs-lookup"><span data-stu-id="e8f05-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="e8f05-114">SQL Server 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e8f05-114">SQL Server storage.</span></span> <span data-ttu-id="e8f05-115">如果您的部署中有駐留在 Lync Server 2013 的使用者，您可以設定封存資料庫來執行受支援版本的 SQL Server，以便為這些使用者啟用封存。</span><span class="sxs-lookup"><span data-stu-id="e8f05-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="e8f05-116">封存也需要檔案儲存空間，但封存會使用與前端伺服器或標準版伺服器相同的檔案儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e8f05-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="e8f05-117">如需封存的硬體和軟體需求清單，請參閱可支援性檔中的[Lync server 2013 支援的硬體](lync-server-2013-supported-hardware.md)和[lync server 2013 中的伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="e8f05-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="e8f05-118">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="e8f05-118">Supported Topologies</span></span>

<span data-ttu-id="e8f05-119">您在擁有需要封存支援之使用者的每個池中部署封存。</span><span class="sxs-lookup"><span data-stu-id="e8f05-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="e8f05-120">在企業版池和標準版伺服器上，封存是在前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="e8f05-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="e8f05-121">歸檔資料儲存空間可能如下：</span><span class="sxs-lookup"><span data-stu-id="e8f05-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="e8f05-122">與 Exchange 2013 存儲整合</span><span class="sxs-lookup"><span data-stu-id="e8f05-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="e8f05-123">使用個別的 SQL Server 資料庫部署</span><span class="sxs-lookup"><span data-stu-id="e8f05-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="e8f05-124">如果您的 Exchange 2013 部署不包括 Lync Server 部署中的所有使用者，您必須針對其信箱是 Exchange 2013 伺服器上的主使用者，使用 Microsoft Exchange 整合，而且您必須部署個別的 SQL Server 資料庫，以供所有其他專案使用要用來進行封存的 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="e8f05-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="e8f05-125">支援的 Collocation</span><span class="sxs-lookup"><span data-stu-id="e8f05-125">Supported Collocation</span></span>

<span data-ttu-id="e8f05-126">Lync Server 2013 支援各種不同的 collocation 案例，可讓您靈活地在一部伺服器（如果您有小型組織）上執行多個元件來儲存硬體成本，或在不同的伺服器上執行個別元件（如果您有較大需要可伸縮性和效能的組織）。</span><span class="sxs-lookup"><span data-stu-id="e8f05-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="e8f05-127">在您決定是否要 collocate 元件之前，請務必先考慮伸縮性因素。</span><span class="sxs-lookup"><span data-stu-id="e8f05-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="e8f05-128">存檔是在 pool 或 Standard Edition 伺服器的前端伺服器上部署。</span><span class="sxs-lookup"><span data-stu-id="e8f05-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="e8f05-129">如需可在該處 collocated 之元件的詳細資訊，請參閱支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="e8f05-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="e8f05-130">如果您使用個別的 SQL Server 資料庫進行歸檔，而不是或除了整合 Exchange 2013 儲存空間之外，您可以使用下列任何一種方式來 collocate 封存資料庫：</span><span class="sxs-lookup"><span data-stu-id="e8f05-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="e8f05-131">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="e8f05-131">Monitoring database</span></span>

  - <span data-ttu-id="e8f05-132">企業版頂層端池的後端資料庫</span><span class="sxs-lookup"><span data-stu-id="e8f05-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8f05-133">裝載存檔資料庫的伺服器可以裝載其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="e8f05-133">The server hosting the Archiving database can host other databases.</span></span> <span data-ttu-id="e8f05-134">不過，當您考慮將封存資料庫與其他資料庫 collocating 時，請注意，如果您要封存的郵件超過幾個使用者，存檔資料庫所需的磁碟空間就會變得很大。</span><span class="sxs-lookup"><span data-stu-id="e8f05-134">However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="e8f05-135">基於這個原因，我們不建議您 collocating 封存資料庫與後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="e8f05-135">For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="e8f05-136">如果您使用監視資料庫、後端資料庫或這兩個資料庫 collocate 封存資料庫，您可以針對任何或所有資料庫使用單一 SQL 實例，或者，您也可以針對每個資料庫使用個別的 SQL 實例，包括下列各項：責任</span><span class="sxs-lookup"><span data-stu-id="e8f05-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="e8f05-137">每個 SQL 實例只能包含一個後端資料庫、單一監視資料庫及單一存檔資料庫。</span><span class="sxs-lookup"><span data-stu-id="e8f05-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="e8f05-138">如需 collocation 所有伺服器角色和資料庫的詳細資料，請參閱可支援檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="e8f05-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

