---
title: Lync Server 2013：硬體安裝程式
description: Lync Server 2013：硬體設定。
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
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552909"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="56d32-103">Lync Server 2013 的硬體設定</span><span class="sxs-lookup"><span data-stu-id="56d32-103">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d32-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="56d32-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="56d32-105">若要在需要執行拓撲的基礎結構中設定硬體和其他元件，需要在在拓撲產生器中發佈拓撲之前，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="56d32-105">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="56d32-106">使用拓撲產生器來安裝拓撲設計中每個元件的硬體，包括所有必要的電腦 (執行 Lync Server 2013 的伺服器、資料庫伺服器、執行網際網路資訊服務的伺服器 (IIS) 和反向 proxy 伺服器，如檔案伺服器 (等) 、網路介面卡、硬體負載平衡器和儲存裝置) 等。</span><span class="sxs-lookup"><span data-stu-id="56d32-106">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="56d32-107">確認已遵照網路介面卡之數量及速度的建議。</span><span class="sxs-lookup"><span data-stu-id="56d32-107">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="56d32-108">若要使用硬體負載平衡器，請確定您有適當的資訊可供廠商設定，以用於 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="56d32-108">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="56d32-109">如果您要使用檔案伺服器或其他伺服器來存放 Lync Server 所需的檔案共用，請確定伺服器已可使用，且已準備好進行檔案共用的設定。</span><span class="sxs-lookup"><span data-stu-id="56d32-109">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="56d32-110">如需如何定義拓撲以指定部署所需的元件的詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="56d32-110">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="56d32-111">如需有關伺服器硬體需求的詳細資訊，請參閱支援檔中的 [支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md) 。</span><span class="sxs-lookup"><span data-stu-id="56d32-111">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="56d32-112">請確定網路基礎結構符合需求。</span><span class="sxs-lookup"><span data-stu-id="56d32-112">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="56d32-113">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="56d32-113">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="56d32-114">設定 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="56d32-114">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="56d32-115">設定 AD DS 的動作包括準備 AD DS 和定義所有您想在 AD DS 中部署的元件。</span><span class="sxs-lookup"><span data-stu-id="56d32-115">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="56d32-116">如需有關準備 AD DS 的詳細資訊，請參閱部署檔中的 [準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="56d32-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="56d32-117">設定建立檔案共用所需的權限。</span><span class="sxs-lookup"><span data-stu-id="56d32-117">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="56d32-118">當您發行拓撲時，拓撲產生器會自動設定使用 Lync Server 2013 的檔案共用的許可權。</span><span class="sxs-lookup"><span data-stu-id="56d32-118">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="56d32-119">不過，用來發佈拓撲的使用者帳戶必須具有檔案共用上的「完全控制」 (讀取/寫入/修改) ，才能讓拓撲產生器設定必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="56d32-119">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="56d32-120">若要確定在拓撲產生器發佈程式時可以正確地管理檔案共用，使用者所屬的使用者或網域群組應該成為檔案共用所在機器上的本機管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="56d32-120">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="56d32-121">在多網域的情況下，則網域 A 的使用者或群組在檔案共用所在網域 B 電腦上必須是本機 Administrators 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="56d32-121">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="56d32-122">如需使用分散式檔案系統中的檔案共用進行更新的詳細資訊 (DFS) ，請參閱 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="56d32-122">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="56d32-123">Lync Server 2013，Enterprise Edition 的檔案共用不能位於前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="56d32-123">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="56d32-124">安裝和設定 Web 服務的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="56d32-124">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="56d32-125">部署網域名稱系統 (DNS) 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限 HTTP/HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="56d32-125">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="56d32-126">硬體負載平衡器用於連接埠 443 和 80 上來自用戶端的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="56d32-126">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="56d32-127">雖然這些集區仍然需要硬體負載平衡器，但其設定和管理主要是針對 HTTP/HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。</span><span class="sxs-lookup"><span data-stu-id="56d32-127">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="56d32-128">完成本主題所述的所有準備工作後，在發行拓撲前，您還需要：</span><span class="sxs-lookup"><span data-stu-id="56d32-128">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="56d32-129">在 Lync Server 2013 的伺服器上安裝作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="56d32-129">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="56d32-130">設定 Lync Server 2013 的 IIS</span><span class="sxs-lookup"><span data-stu-id="56d32-130">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="56d32-131">針對 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="56d32-131">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="56d32-132">設定前端集區或 Standard Edition Server 的 Lync Server 2013 中的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="56d32-132">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

