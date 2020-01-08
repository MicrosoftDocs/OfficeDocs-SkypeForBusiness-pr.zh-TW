---
title: Lync Server 2013：硬體設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="d5a16-102">Lync Server 2013 的硬體設定</span><span class="sxs-lookup"><span data-stu-id="d5a16-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a16-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d5a16-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d5a16-104">在您要實現拓朴所需的基礎結構中設定硬體及其他元件，需要在拓撲建立器中發佈拓撲之前，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d5a16-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="d5a16-105">針對您使用拓撲建立器建立並儲存的拓撲設計中的每個元件安裝硬體，包括所有所需的電腦（執行 Lync Server 2013、資料庫伺服器、執行網際網路資訊服務的伺服器（IIS），以及視需要反向 proxy 伺服器、網路介面卡、硬體負載平衡器和儲存裝置（例如檔案伺服器）。</span><span class="sxs-lookup"><span data-stu-id="d5a16-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="d5a16-106">確認您已遵循網路介面卡編號與速度的建議。</span><span class="sxs-lookup"><span data-stu-id="d5a16-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="d5a16-107">如果您要使用硬體負載平衡器，請確認您有供應商提供的適當資訊，以便將其設定為搭配 Lync Server 2013 使用。</span><span class="sxs-lookup"><span data-stu-id="d5a16-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="d5a16-108">如果您要使用檔案伺服器或其他伺服器來存放 Lync Server 所需的檔案共用，請確認伺服器可供使用，且已準備好配置檔案共用。</span><span class="sxs-lookup"><span data-stu-id="d5a16-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="d5a16-109">如需如何定義拓朴以指定您的部署所需元件的詳細資料，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a16-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="d5a16-110">如需伺服器硬體需求的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a16-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="d5a16-111">請確定網路基礎結構符合需求。</span><span class="sxs-lookup"><span data-stu-id="d5a16-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="d5a16-112">如需詳細資訊，請參閱規劃檔中[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a16-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d5a16-113">設定 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="d5a16-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="d5a16-114">設定 AD DS 包括準備 AD DS，並定義您想要部署在 AD DS 中的所有元件。</span><span class="sxs-lookup"><span data-stu-id="d5a16-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="d5a16-115">如需有關準備 AD DS 的詳細資料，請參閱在部署檔中[為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a16-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="d5a16-116">設定建立檔案共用所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="d5a16-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="d5a16-117">Lync Server 2013 使用檔案共用的許可權會在您發佈拓撲時自動由拓撲產生器進行設定。</span><span class="sxs-lookup"><span data-stu-id="d5a16-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="d5a16-118">不過，用於發佈拓朴的使用者帳戶必須在檔案共用上擁有 [完全控制] （讀取/寫入/修改），才能讓拓撲建立程式設定必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="d5a16-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="d5a16-119">若要確保在拓撲建立器發佈程式中能正確地管理檔案共用，使用者所屬的使用者或網域群組應該成為檔案共用所在電腦上的本機管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="d5a16-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="d5a16-120">在多網域案例中，您應該在網域 B 的電腦上，將網域 A 的使用者或群組設為本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d5a16-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="d5a16-121">如需使用分散式檔案系統（DFS）中的檔案共用進行更新的詳細資訊，請參閱[設定 Lync Server 2013 的檔案儲存空間](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a16-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d5a16-122">Lync Server 2013、Enterprise Edition 的檔案共用無法位於前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d5a16-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="d5a16-123">安裝並設定適用于 Web 服務的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="d5a16-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="d5a16-124">隨著已部署的網域名稱系統（DNS）負載平衡，您仍然需要同時針對這些池使用硬體負載平衡器，但僅適用于 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="d5a16-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="d5a16-125">硬體負載平衡器用於來自埠443和80的用戶端的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="d5a16-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="d5a16-126">雖然您仍需要這些池的硬體負載平衡器，但它們的設定和管理主要是針對 HTTP/HTTPS 流量（硬體負載平衡器的系統管理員習慣）。</span><span class="sxs-lookup"><span data-stu-id="d5a16-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="d5a16-127">完成本主題所述的所有準備工作之後，但在發佈拓撲之前，您也需要：</span><span class="sxs-lookup"><span data-stu-id="d5a16-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="d5a16-128">在伺服器上安裝 Lync Server 2013 的作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="d5a16-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="d5a16-129">針對 Lync Server 2013 設定 IIS</span><span class="sxs-lookup"><span data-stu-id="d5a16-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="d5a16-130">為 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5a16-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="d5a16-131">在 Lync Server 2013 中設定前端集區或 Standard Edition Server 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="d5a16-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

