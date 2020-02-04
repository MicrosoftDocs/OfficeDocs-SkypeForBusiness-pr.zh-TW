---
title: Lync Server 2013：準備基礎結構和系統
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="632f8-102">準備 Lync Server 2013 的基礎結構和系統</span><span class="sxs-lookup"><span data-stu-id="632f8-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632f8-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="632f8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="632f8-104">部署 Lync Server 2013 需要使用拓撲建立器來定義及發佈拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="632f8-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="632f8-105">若要找出您的拓撲所需的元件，請使用 [拓撲建立器] 來建立並儲存拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="632f8-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="632f8-106">在拓撲建立器中發佈拓撲前，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="632f8-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="632f8-107">在您使用拓撲建立器建立並儲存的拓撲設計中，針對每個元件取得並安裝硬體，包括所有所需的電腦（執行 Lync Server 2013 的伺服器、資料庫伺服器、運行 Internet 資訊服務的伺服器）（IIS）及反向 proxy 伺服器（視需要）、網路介面卡、硬體負載平衡器，以及儲存裝置（例如檔案伺服器）。</span><span class="sxs-lookup"><span data-stu-id="632f8-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="632f8-108">如需如何定義拓朴以指定您的部署所需元件的詳細資料，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="632f8-109">如需伺服器硬體需求的詳細資料，請參閱支援檔中的[Lync Server 2013 支援的硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="632f8-110">請確定網路基礎結構符合需求。</span><span class="sxs-lookup"><span data-stu-id="632f8-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="632f8-111">如需詳細資訊，請參閱規劃檔中[Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="632f8-112">設定 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="632f8-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="632f8-113">若要發佈並啟用拓撲，您必須在 AD DS 中，由電腦帳戶來代表內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="632f8-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="632f8-114">這是透過將電腦加入到 AD DS 來完成。</span><span class="sxs-lookup"><span data-stu-id="632f8-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="632f8-115">如需有關準備 AD DS 的詳細資料，請參閱[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="632f8-116">建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="632f8-116">Create a file share.</span></span> <span data-ttu-id="632f8-117">標準版伺服器可託管所需檔案的檔案共用，而在企業版部署中，檔案共用不能裝載在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="632f8-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="632f8-118">在資料夾和共用上部署及設定存取控制清單（ACL）所需的許可權和群組成員資格必須正確地設定為拓撲建立程式才能順利完成。</span><span class="sxs-lookup"><span data-stu-id="632f8-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="632f8-119">您應該確定執行拓撲建立器的人員具有下列許可權和群組成員資格：</span><span class="sxs-lookup"><span data-stu-id="632f8-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="632f8-120">本機管理員的成員</span><span class="sxs-lookup"><span data-stu-id="632f8-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="632f8-121">網域使用者的成員</span><span class="sxs-lookup"><span data-stu-id="632f8-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="632f8-122">檔案存放區的 [共用] 和 [資料夾] 完全控制</span><span class="sxs-lookup"><span data-stu-id="632f8-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="632f8-123">針對企業版，請安裝並設定 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="632f8-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="632f8-124">若要讓 SQL Server 安裝程式成功，必須在線上，且發佈拓朴的人員是 SQL Server 上的本機系統管理員，而且必須是 SQL server 實例上 SQL Server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="632f8-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="632f8-125">完成本主題所述的所有準備工作，但在發佈拓撲之前，您也需要執行其他準備工作，包括安裝 Windows 作業系統及其他必備軟體，以及設定[IIS]，然後設定 DNS。</span><span class="sxs-lookup"><span data-stu-id="632f8-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="632f8-126">如需這些工作的詳細資訊，請參閱執行[Lync server 2013 的伺服器系統需求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、[設定 lync SERVER 2013 的 IIS](lync-server-2013-configure-iis.md)，以及[準備 lync server 2013 的基礎結構和系統](lync-server-2013-preparing-the-infrastructure-and-systems.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="632f8-127">此外，您應該熟悉用戶端和用戶端需求。</span><span class="sxs-lookup"><span data-stu-id="632f8-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="632f8-128">如需詳細資訊，請參閱[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="632f8-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="632f8-129">本節內容</span><span class="sxs-lookup"><span data-stu-id="632f8-129">In This Section</span></span>

  - [<span data-ttu-id="632f8-130">Lync Server 2013 的硬體設定</span><span class="sxs-lookup"><span data-stu-id="632f8-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="632f8-131">Lync Server 2013 的軟體設定</span><span class="sxs-lookup"><span data-stu-id="632f8-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="632f8-132">為 Lync Server 2013 準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="632f8-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="632f8-133">為 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="632f8-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="632f8-134">在 Lync Server 2013 中設定前端集區或 Standard Edition Server 的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="632f8-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="632f8-135">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="632f8-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

