---
title: Lync Server 2013： 硬體設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d55ac04a06984889a3038aceee7fd0f311efcfb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="6bfd9-102">Lync Server 2013 的硬體設定</span><span class="sxs-lookup"><span data-stu-id="6bfd9-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bfd9-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="6bfd9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6bfd9-104">設定硬體和其他所需的基礎結構，您必須實作您的拓撲中的元件需要，在拓撲產生器中發行拓撲之前, 您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6bfd9-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="6bfd9-105">在您建立及使用拓撲產生器，包括所有必要的電腦儲存拓撲設計中安裝每個元件的硬體 (執行 Lync Server 2013、 資料庫伺服器、 執行網際網路資訊服務 (IIS) 伺服器的伺服器和反向 proxy 伺服器，視）、 網路介面卡，硬體負載平衡器，以及儲存裝置 （例如檔案伺服器）。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="6bfd9-106">確認已遵照網路介面卡之數量及速度的建議。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="6bfd9-107">如果您使用硬體負載平衡器，請確定您已從廠商連絡，以將其設定與 Lync Server 2013 搭配使用的適當資訊。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="6bfd9-108">您將使用 「 檔案伺服器或另一部伺服器來家檔案共用所需的 Lync Server，請確定伺服器可以使用並準備好進行檔案共用的組態。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="6bfd9-109">如需如何定義拓撲，指定您的部署所需的元件的詳細資訊，請參閱[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="6bfd9-110">如需伺服器硬體需求的詳細資訊，請參閱支援文件中的[Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="6bfd9-111">請確定網路基礎結構符合需求。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="6bfd9-112">如需詳細資訊，請參閱規劃文件中的[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="6bfd9-113">設定 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="6bfd9-114">設定 AD DS 的動作包括準備 AD DS 和定義所有您想在 AD DS 中部署的元件。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="6bfd9-115">如需準備 AD DS 的詳細資訊，請參閱部署文件中的[準備 Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6bfd9-116">設定建立檔案共用所需的權限。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="6bfd9-117">發行拓撲時，使用的 Lync Server 2013 的檔案共用的權限會自動會由拓撲產生器設定。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="6bfd9-118">不過，用來發行拓撲的使用者帳戶必須具有完全控制權 （讀取/寫入/修改） 在檔案共用為了讓拓撲產生器來設定必要的權限。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="6bfd9-119">若要確定檔案共用可以妥善管理在拓撲產生器的發佈程序期間，使用者為成員的網域群組應進行本機 Administrators 群組的成員的檔案共用所在電腦上。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="6bfd9-120">在多網域的情況下，則網域 A 的使用者或群組在檔案共用所在網域 B 電腦上必須是本機 Administrators 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="6bfd9-121">如需更新的詳細資訊使用檔案共用中分散式檔案系統 (DFS)，請參閱[Lync Server 2013 的設定檔儲存](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="6bfd9-122">前端伺服器上找不到 Lync Server 2013，企業版的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="6bfd9-123">安裝及設定 Web 服務的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="6bfd9-124">部署網域名稱系統 (DNS) 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="6bfd9-125">硬體負載平衡器用於連接埠 443 和 80 上來自用戶端的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="6bfd9-126">雖然這些集區仍然需要硬體負載平衡器，但其設定和管理主要是針對 HTTP/HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。</span><span class="sxs-lookup"><span data-stu-id="6bfd9-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="6bfd9-127">完成本主題所述的所有準備工作後，在發行拓撲前，您還需要：</span><span class="sxs-lookup"><span data-stu-id="6bfd9-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="6bfd9-128">Lync Server 2013 伺服器上安裝作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="6bfd9-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="6bfd9-129">將 Lync Server 2013 的 IIS 設定</span><span class="sxs-lookup"><span data-stu-id="6bfd9-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="6bfd9-130">針對 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="6bfd9-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="6bfd9-131">設定 Lync Server 2013 中的前端集區或 Standard Edition server 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="6bfd9-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

