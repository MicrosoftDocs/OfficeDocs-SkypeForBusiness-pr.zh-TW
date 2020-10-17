---
title: Lync Server 2013：定義及設定拓撲
description: Lync Server 2013：定義及設定拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec444a1ddf434c5a80fdc2d56bdba27573da14ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542079"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="7b76c-103">在 Lync Server 2013 中定義及設定拓撲</span><span class="sxs-lookup"><span data-stu-id="7b76c-103">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b76c-104">_**主題上次修改日期：** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="7b76c-104">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="7b76c-105">您可以使用拓撲產生器來定義及設定拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-105">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="7b76c-106">拓撲產生器不需要您是本機系統管理員群組的成員，或具有許可權的網域群組 (，例如 Domain Admins) 。</span><span class="sxs-lookup"><span data-stu-id="7b76c-106">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="7b76c-107">您可以標準使用者身分定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-107">You can define your topology as a standard user.</span></span> <span data-ttu-id="7b76c-108">當您在第一次使用時啟動拓撲產生器和後續的編輯會話時，系統會提示您輸入您想要拓撲產生器載入目前設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="7b76c-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="7b76c-109">選項如下：</span><span class="sxs-lookup"><span data-stu-id="7b76c-109">The choices are the following:</span></span>

  - <span data-ttu-id="7b76c-110">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="7b76c-110">Download topology from existing deployment</span></span>

  - <span data-ttu-id="7b76c-111">從本機檔案開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="7b76c-111">Open topology from a local file</span></span>

  - <span data-ttu-id="7b76c-112">新增拓撲</span><span class="sxs-lookup"><span data-stu-id="7b76c-112">New topology</span></span>

<span data-ttu-id="7b76c-113">如果您已定義拓撲，且已建立中央管理存放區，則應該選擇從現有的部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-113">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="7b76c-114">拓撲產生器會讀取資料庫，並取得目前的定義。</span><span class="sxs-lookup"><span data-stu-id="7b76c-114">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="7b76c-115">如果您有現有的中央管理存放區，則一定要選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="7b76c-115">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="7b76c-116">若尚未建立中央管理存放區，且想要編輯先前儲存的設定，您應該選擇從本機檔案開啟拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-116">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="7b76c-117">您將開啟的檔案，必須是先前工作階段中儲存的組態檔。</span><span class="sxs-lookup"><span data-stu-id="7b76c-117">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="7b76c-118">您可以透過這個選項，編輯先前儲存的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-118">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7b76c-p104">如果您已經有發行的拓撲，請勿載入本機組態檔。您應該選擇從現有部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="7b76c-121">如果您想要建立新的拓撲產生器設定，請選擇建立新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b76c-121">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="7b76c-122">除非您選擇將先前儲存的設計儲存您在先前設計工作階段裡建立的相同檔案，否則不會複寫先前儲存的設計。</span><span class="sxs-lookup"><span data-stu-id="7b76c-122">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="7b76c-123">在這些選項中，系統會提示您輸入存放拓撲產生器設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="7b76c-123">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="7b76c-124">該檔案位置可以是本機位置、已建立的檔案共用之共用位置，或是卸除式媒體。</span><span class="sxs-lookup"><span data-stu-id="7b76c-124">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b76c-125">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7b76c-125">In This Section</span></span>

  - [<span data-ttu-id="7b76c-126">在 Lync Server 2013 的拓撲產生器中定義及設定拓撲</span><span class="sxs-lookup"><span data-stu-id="7b76c-126">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="7b76c-127">在 Lync Server 2013 中定義及設定前端集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="7b76c-127">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="7b76c-128">在 Lync Server 2013 中為嚴重損壞修復部署成對的前端集區</span><span class="sxs-lookup"><span data-stu-id="7b76c-128">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="7b76c-129">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="7b76c-129">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="7b76c-130">在 Lync Server 2013 中編輯或設定簡單 URLs</span><span class="sxs-lookup"><span data-stu-id="7b76c-130">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="7b76c-131">在 Lync Server 2013 中選取中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="7b76c-131">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

