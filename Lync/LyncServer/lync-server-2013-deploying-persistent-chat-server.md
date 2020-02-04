---
title: Lync Server 2013：部署常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fe18bf750eabdb1f53c97a349b553da4f13dec8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3732d-102">在 Lync Server 2013 中部署常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3732d-103">_**主題上次修改日期：** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="3732d-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="3732d-104">Lync server 2013，持續聊天伺服器是 Lync Server 2013 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="3732d-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="3732d-105">部署持久聊天伺服器時，您必須：</span><span class="sxs-lookup"><span data-stu-id="3732d-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="3732d-106">使用拓撲建立器來定義或匯入，並隨後發佈您要部署的拓撲和元件。</span><span class="sxs-lookup"><span data-stu-id="3732d-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="3732d-107">準備部署持久聊天伺服器元件的環境。</span><span class="sxs-lookup"><span data-stu-id="3732d-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="3732d-108">針對您的部署安裝及設定持續聊天伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="3732d-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="3732d-109">在 Lync Server 2013 企業版中，您可以使用永久性聊天伺服器作為獨立的文件庫（而不是與企業版前端伺服器 collocated）。</span><span class="sxs-lookup"><span data-stu-id="3732d-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="3732d-110">持續聊天伺服器需要企業版池中的 SQL Server 後端伺服器，才能儲存聊天室內容和其他相關中繼資料。</span><span class="sxs-lookup"><span data-stu-id="3732d-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="3732d-111">我們建議您將**PersistentChatStore**安裝在專用的 Sql Server 後端伺服器上，不過 Collocating 的 Lync Server 2013 後端伺服器和**PersistentChatStore**都支援相同的 sql server 實例。</span><span class="sxs-lookup"><span data-stu-id="3732d-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="3732d-112">持久聊天伺服器也可以使用 Lync Server 2013 標準版來部署。</span><span class="sxs-lookup"><span data-stu-id="3732d-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="3732d-113">在這種情況下， **PersistentChatService**前端伺服器是在標準版電腦上 collocated，而**PersistentChatStore**後端伺服器可以部署在本機 SQL Server Express 實例上。</span><span class="sxs-lookup"><span data-stu-id="3732d-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="3732d-114">如需支援的 colocation 設定的詳細資訊，請參閱[Lync server 2013 中支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="3732d-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3732d-115">我們不支援持續聊天伺服器&nbsp;標準版的高可用性。</span><span class="sxs-lookup"><span data-stu-id="3732d-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="3732d-116">效能和比例會受到限制。</span><span class="sxs-lookup"><span data-stu-id="3732d-116">Performance and scale will be limited.</span></span> <span data-ttu-id="3732d-117">此外，我們只支援新的持續聊天&nbsp;伺服器標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="3732d-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="3732d-118">我們不支援將 Lync Server 2010、群組聊天伺服器升級為 Lync Server 2013&nbsp;持續聊天伺服器&nbsp;標準版。</span><span class="sxs-lookup"><span data-stu-id="3732d-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="3732d-119">如果您的組織需要合規性支援，您可以在永久聊天伺服器前端伺服器上安裝持續式聊天伺服器合規性服務。</span><span class="sxs-lookup"><span data-stu-id="3732d-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="3732d-120">需要一個單獨的資料庫來實現合規性。</span><span class="sxs-lookup"><span data-stu-id="3732d-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="3732d-121">每個拓撲至少都需要裝有 Lync Server 2013 的伺服器，以及已安裝 SQL Server database 軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3732d-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="3732d-122">使用拓撲建立器，將持續聊天伺服器新增到您的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="3732d-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="3732d-123">您可以選擇使用 [拓撲建立器] 新增一或多個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="3732d-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="3732d-124">遵循相同的部署指示來部署多個持續聊天伺服器池，就像為任何一個池所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="3732d-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="3732d-125">如需詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。</span><span class="sxs-lookup"><span data-stu-id="3732d-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3732d-126">如需有關可用拓撲的詳細資料，以及安裝持續聊天伺服器的技術和軟體需求，請參閱規劃[2013](lync-server-2013-how-persistent-chat-server-works.md)檔中的 [在 lync server [2013 中規劃持久聊天](lync-server-2013-planning-for-persistent-chat-server.md)伺服器]、[安裝] 檔、部署檔或操作檔，以及[支援的 lync server 2013 硬體](lync-server-2013-supported-hardware.md)（在可支援檔中）。</span><span class="sxs-lookup"><span data-stu-id="3732d-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="3732d-127">如需取得證書、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) ]。</span><span class="sxs-lookup"><span data-stu-id="3732d-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3732d-128">單一持續式聊天伺服器前端伺服器可以支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="3732d-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="3732d-129">您可以使用最多4個作用中的 [永久聊天伺服器] 池，同時支援全部80000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="3732d-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="3732d-130">虛擬伺服器也支援持續式聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="3732d-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="3732d-131">如果虛擬伺服器符合物理伺服器的規格，就能支援最多20000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="3732d-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3732d-132">持續聊天伺服器必須安裝在 NTFS 檔案系統上，以協助強制執行檔案系統安全性。</span><span class="sxs-lookup"><span data-stu-id="3732d-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="3732d-133">FAT32 不是持久聊天伺服器所支援的檔案系統。</span><span class="sxs-lookup"><span data-stu-id="3732d-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3732d-134">本節內容</span><span class="sxs-lookup"><span data-stu-id="3732d-134">In This Section</span></span>

  - [<span data-ttu-id="3732d-135">在 Lync Server 2013 中，持久聊天伺服器的運作方式</span><span class="sxs-lookup"><span data-stu-id="3732d-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="3732d-136">Lync Server 2013 中的常設聊天室伺服器的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3732d-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="3732d-137">Lync Server 2013 中持續聊天伺服器的技術需求</span><span class="sxs-lookup"><span data-stu-id="3732d-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="3732d-138">在 Lync Server 2013 中設定常設聊天室伺服器的系統與基礎結構</span><span class="sxs-lookup"><span data-stu-id="3732d-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="3732d-139">在 Lync Server 2013 中將常設聊天室伺服器新增至您的部署</span><span class="sxs-lookup"><span data-stu-id="3732d-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="3732d-140">在 Lync Server 2013 中安裝常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="3732d-141">在 Lync Server 2013 中新增常設聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="3732d-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="3732d-142">在 Lync Server 2013 中設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="3732d-143">使用 Windows PowerShell Cmdlet 設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="3732d-144">在 Lync Server 2013 中使用 Windows PowerShell Cmdlet 疑難排解常設聊天室伺服器設定</span><span class="sxs-lookup"><span data-stu-id="3732d-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="3732d-145">在 Lync Server 2013 中針對高可用性和災害復原設定常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="3732d-146">Lync Server 2013 中的容錯移轉和容錯回復常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="3732d-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

