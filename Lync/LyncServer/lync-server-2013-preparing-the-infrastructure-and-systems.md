---
title: Lync Server 2013：準備基礎結構和系統
description: Lync Server 2013：準備基礎結構和系統。
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
ms.openlocfilehash: bfabdda9d117af1534578c8543f9ce72808d5a53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579989"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="4d2de-103">準備 Lync Server 2013 的基礎結構和系統</span><span class="sxs-lookup"><span data-stu-id="4d2de-103">Preparing the infrastructure and systems for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d2de-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4d2de-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4d2de-105">部署 Lync Server 2013 需要使用拓撲產生器來定義及發行拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="4d2de-105">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="4d2de-106">若要識別拓撲所需的元件，您可以使用拓撲產生器來建立及儲存拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="4d2de-106">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="4d2de-107">在拓撲產生器中發行拓撲之前，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="4d2de-107">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="4d2de-108">使用拓撲產生器，針對您建立及儲存的拓撲設計中的每個元件，取得並安裝硬體，包括所有必要的電腦 (執行 Lync Server 2013 的伺服器、資料庫伺服器、執行網際網路資訊服務的伺服器 (IIS) 和反向 proxy 伺服器，如檔案伺服器 (等) 、網路介面卡、硬體負載平衡器和儲存裝置) 等。</span><span class="sxs-lookup"><span data-stu-id="4d2de-108">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="4d2de-109">如需如何定義拓撲以指定部署所需的元件的詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2de-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="4d2de-110">如需有關伺服器硬體需求的詳細資訊，請參閱支援檔中的 [支援的 Lync Server 2013 硬體](lync-server-2013-supported-hardware.md) 。</span><span class="sxs-lookup"><span data-stu-id="4d2de-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="4d2de-111">請確定網路基礎結構符合需求。</span><span class="sxs-lookup"><span data-stu-id="4d2de-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="4d2de-112">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 的網路基礎結構需求](lync-server-2013-network-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="4d2de-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="4d2de-113">設定 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="4d2de-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="4d2de-114">若要發行及啟用拓撲，您需要 AD DS 中的電腦帳戶來代表內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="4d2de-114">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="4d2de-115">您可以將電腦加入 AD DS 來達到這個目的。</span><span class="sxs-lookup"><span data-stu-id="4d2de-115">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="4d2de-116">如需有關準備 AD DS 的詳細資訊，請參閱 [準備 Active Directory 網域服務 For Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2de-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="4d2de-117">建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="4d2de-117">Create a file share.</span></span> <span data-ttu-id="4d2de-118">Standard Edition Server 可以裝載必要檔案的檔案共用，而在 Enterprise 部署中，檔案共用不能裝載在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4d2de-118">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="4d2de-119">在資料夾和共用上部署及設定存取控制清單 (ACL) 時所需的權限和群組成員資格必須正確設定，拓撲產生器才能順利完成。</span><span class="sxs-lookup"><span data-stu-id="4d2de-119">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="4d2de-120">您應確定執行拓撲產生器的人員具備下列許可權和群組成員資格：</span><span class="sxs-lookup"><span data-stu-id="4d2de-120">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="4d2de-121">本機系統管理員成員</span><span class="sxs-lookup"><span data-stu-id="4d2de-121">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="4d2de-122">網域使用者成員</span><span class="sxs-lookup"><span data-stu-id="4d2de-122">Member of Domain Users</span></span>
    
      - <span data-ttu-id="4d2de-123">共用和檔案存放區之資料夾的完全控制權限</span><span class="sxs-lookup"><span data-stu-id="4d2de-123">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="4d2de-p106">若為 Enterprise Edition，請安裝及設定 SQL Server。為了讓 SQL Server 安裝成功，SQL Server 型伺服器必須在線上，而發行拓撲的人員必須是 SQL Server 上的本機管理員，也必須是 SQL Server 執行個體上的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="4d2de-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="4d2de-126">完成本主題說明的所有準備工作後，您還需要在發行拓撲前執行其他準備工作，包括安裝 Windows 作業系統和其他必要的軟體、設定 IIS 及設定 DNS。</span><span class="sxs-lookup"><span data-stu-id="4d2de-126">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="4d2de-127">如需這些工作的詳細資訊，請參閱執行 [Lync server 2013 之伺服器的系統需求](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md)、為 [lync SERVER 2013 設定 IIS](lync-server-2013-configure-iis.md)，以及 [準備 lync server 2013 的基礎結構和系統](lync-server-2013-preparing-the-infrastructure-and-systems.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2de-127">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="4d2de-128">此外，您應該要熟悉用戶端和用戶端需求。</span><span class="sxs-lookup"><span data-stu-id="4d2de-128">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="4d2de-129">如需詳細資訊，請參閱 [在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2de-129">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d2de-130">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4d2de-130">In This Section</span></span>

  - [<span data-ttu-id="4d2de-131">Lync Server 2013 的硬體設定</span><span class="sxs-lookup"><span data-stu-id="4d2de-131">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="4d2de-132">Lync Server 2013 的軟體安裝</span><span class="sxs-lookup"><span data-stu-id="4d2de-132">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="4d2de-133">為 Lync Server 2013 準備 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="4d2de-133">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="4d2de-134">針對 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d2de-134">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="4d2de-135">設定前端集區或 Standard Edition Server 的 Lync Server 2013 中的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4d2de-135">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="4d2de-136">安裝 Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="4d2de-136">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

