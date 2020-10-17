---
title: Lync Server 2013：部署 Persistent Chat Server
description: Lync Server 2013：部署 Persistent Chat Server。
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
ms.openlocfilehash: b85c0070ab4bcd60d80d57738c25daac1de4faf1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566089"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="00128-103">在 Lync Server 2013 中部署 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="00128-103">Deploying Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00128-104">_**主題上次修改日期：** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="00128-104">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="00128-105">Lync Server 2013，Persistent Chat Server 是 Lync Server 2013 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="00128-105">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="00128-106">部署 Persistent Chat Server 需要您：</span><span class="sxs-lookup"><span data-stu-id="00128-106">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="00128-107">使用拓撲產生器來定義或匯入，然後發佈您要部署的拓撲和元件。</span><span class="sxs-lookup"><span data-stu-id="00128-107">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="00128-108">準備部署持久聊天伺服器元件的環境。</span><span class="sxs-lookup"><span data-stu-id="00128-108">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="00128-109">為您的部署安裝及設定 Persistent Chat Server 元件。</span><span class="sxs-lookup"><span data-stu-id="00128-109">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="00128-110">Persistent Chat Server 可搭配 Lync Server 2013 Enterprise Edition 做為個別集區 (不會與 Enterprise Edition 前端伺服器) 進行組合。</span><span class="sxs-lookup"><span data-stu-id="00128-110">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="00128-111">Persistent Chat Server 要求企業版集區中的 SQL Server 後端伺服器，以儲存聊天室內容及其他相關的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="00128-111">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="00128-112">建議您將 **PersistentChatStore** 安裝在專用的 Sql Server 後端伺服器上，不過在相同的 sql server 實例上，組合 Lync Server 2013 後端伺服器和 **PersistentChatStore** 皆受支援。</span><span class="sxs-lookup"><span data-stu-id="00128-112">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="00128-113">Persistent Chat Server 也可以與 Lync Server 2013 Standard Edition 一起部署。</span><span class="sxs-lookup"><span data-stu-id="00128-113">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="00128-114">在此情況下，Standard Edition 電腦上的 **PersistentChatService** 前端伺服器是組合， **PersistentChatStore** 後端伺服器可部署在本機 SQL Server Express 實例上。</span><span class="sxs-lookup"><span data-stu-id="00128-114">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="00128-115">如需支援的 colocation 設定的詳細資訊，請參閱 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="00128-115">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00128-116">我們不支援 Persistent Chat Server Standard Edition 的高可用性 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="00128-116">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="00128-117">效能及規模將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="00128-117">Performance and scale will be limited.</span></span> <span data-ttu-id="00128-118">此外，我們僅支援新的 Persistent Chat Server &nbsp; Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="00128-118">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="00128-119">我們不支援將 Lync Server 2010，Group Chat Server 升級成 Lync Server 2013 &nbsp; Persistent Chat server &nbsp; Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="00128-119">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="00128-120">如果您的組織需要規範支援，您可以在 Persistent Chat Server 前端伺服器上安裝 Persistent Chat Server 合規性服務。</span><span class="sxs-lookup"><span data-stu-id="00128-120">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="00128-121">合規性需要個別的資料庫。</span><span class="sxs-lookup"><span data-stu-id="00128-121">A separate database is required for compliance.</span></span>

<span data-ttu-id="00128-122">每個拓撲至少需要安裝 Lync Server 2013 的伺服器，以及已安裝 SQL Server 資料庫軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="00128-122">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="00128-123">使用拓撲產生器，將 Persistent Chat Server 新增至您的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="00128-123">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="00128-124">您可以選擇使用拓撲產生器來新增一或多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="00128-124">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="00128-125">遵循部署多個 Persistent Chat Server 集區的相同部署指示。</span><span class="sxs-lookup"><span data-stu-id="00128-125">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="00128-126">如需詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="00128-126">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="00128-127">如需有關安裝 Persistent Chat Server 的可用拓撲及技術和軟體需求的詳細資訊，請參閱規劃檔、部署檔或作業檔中的「在 lync server [2013](lync-server-2013-how-persistent-chat-server-works.md)中[規劃 Persistent chat 2013 server](lync-server-2013-planning-for-persistent-chat-server.md) 」，以及支援檔中的[lync server 2013 的支援硬體](lync-server-2013-supported-hardware.md)。</span><span class="sxs-lookup"><span data-stu-id="00128-127">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="00128-128">如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱部署檔中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="00128-128">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="00128-129">單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="00128-129">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="00128-130">您最多可以有最多4個作用中前端伺服器的持久聊天伺服器集區，以支援所有80000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="00128-130">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="00128-131">虛擬伺服器也支援 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="00128-131">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="00128-132">虛擬伺服器若符合實體伺服器的規格，最多可支援20000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="00128-132">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="00128-133">必須在 NTFS 檔案系統上安裝 Persistent Chat Server，以協助強制執行檔案系統安全性。</span><span class="sxs-lookup"><span data-stu-id="00128-133">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="00128-134">FAT32 不是持久聊天伺服器支援的檔案系統。</span><span class="sxs-lookup"><span data-stu-id="00128-134">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="00128-135">本章節內容</span><span class="sxs-lookup"><span data-stu-id="00128-135">In This Section</span></span>

  - [<span data-ttu-id="00128-136">在 Lync Server 2013 中，Persistent Chat Server 的運作方式</span><span class="sxs-lookup"><span data-stu-id="00128-136">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="00128-137">Lync Server 2013 中 Persistent Chat Server 的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="00128-137">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="00128-138">Lync Server 2013 中 Persistent Chat Server 的技術需求</span><span class="sxs-lookup"><span data-stu-id="00128-138">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="00128-139">在 Lync Server 2013 中設定 Persistent Chat Server 的系統和基礎結構</span><span class="sxs-lookup"><span data-stu-id="00128-139">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="00128-140">在 Lync Server 2013 中將 Persistent Chat Server 新增至您的部署</span><span class="sxs-lookup"><span data-stu-id="00128-140">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="00128-141">在 Lync Server 2013 中安裝 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="00128-141">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="00128-142">在 Lync Server 2013 中新增 Persistent Chat 系統管理員</span><span class="sxs-lookup"><span data-stu-id="00128-142">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="00128-143">在 Lync Server 2013 中設定 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="00128-143">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="00128-144">使用 Windows PowerShell Cmdlet 設定 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="00128-144">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="00128-145">使用 Lync Server 2013 中的 Windows PowerShell Cmdlet 來疑難排解 Persistent Chat Server 設定</span><span class="sxs-lookup"><span data-stu-id="00128-145">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="00128-146">在 Lync Server 2013 中設定持久聊天伺服器以取得高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="00128-146">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="00128-147">在 Lync Server 2013 中容錯移轉和失敗回復持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="00128-147">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

