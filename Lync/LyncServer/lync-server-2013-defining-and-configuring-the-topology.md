---
title: Lync Server 2013：定義和設定拓撲
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
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="49d11-102">在 Lync Server 2013 中定義和設定拓撲</span><span class="sxs-lookup"><span data-stu-id="49d11-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49d11-103">_**主題上次修改日期：** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="49d11-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="49d11-104">您可以使用 [拓撲建立器] 來定義及設定您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="49d11-105">拓撲建立器不需要您是本機管理員群組或許可權網域群組的成員（例如網域管理員）。</span><span class="sxs-lookup"><span data-stu-id="49d11-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="49d11-106">您可以將拓朴定義為標準使用者。</span><span class="sxs-lookup"><span data-stu-id="49d11-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="49d11-107">當您在第一次使用及後續編輯會話時啟動拓撲產生器時，系統會提示您輸入您想要拓撲建立器載入目前設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="49d11-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="49d11-108">選項如下：</span><span class="sxs-lookup"><span data-stu-id="49d11-108">The choices are the following:</span></span>

  - <span data-ttu-id="49d11-109">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="49d11-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="49d11-110">從本機檔案開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="49d11-110">Open topology from a local file</span></span>

  - <span data-ttu-id="49d11-111">新拓撲</span><span class="sxs-lookup"><span data-stu-id="49d11-111">New topology</span></span>

<span data-ttu-id="49d11-112">如果您已定義拓撲，且已建立中央管理儲存區，您應該選擇從現有的部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="49d11-113">拓撲建立器將會讀取資料庫並檢索目前的定義。</span><span class="sxs-lookup"><span data-stu-id="49d11-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="49d11-114">如果您有現有的中央管理存放區，請務必選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="49d11-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="49d11-115">如果您沒有建立中央管理儲存體，且想要編輯先前儲存的設定，您應該選擇從本機檔案開啟拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="49d11-116">您要開啟的檔案會是儲存在先前會話中的設定檔。</span><span class="sxs-lookup"><span data-stu-id="49d11-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="49d11-117">您可以使用這個選項來編輯先前儲存的拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="49d11-118">如果您已經有已發佈的拓撲，則不應載入本機設定檔。</span><span class="sxs-lookup"><span data-stu-id="49d11-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="49d11-119">您應該選擇從現有的部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="49d11-120">如果您想要建立新的拓撲建立器配置，請選擇建立新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="49d11-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="49d11-121">除非您選擇將先前儲存的設計儲存為與您在舊版設計會話中建立的檔案，否則不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="49d11-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="49d11-122">在這些選項中，系統會提示您輸入拓撲建立器設定檔的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="49d11-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="49d11-123">檔案的位置可以是本機位置、已建立的檔案共用上的共用位置或卸除式媒體。</span><span class="sxs-lookup"><span data-stu-id="49d11-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="49d11-124">本節內容</span><span class="sxs-lookup"><span data-stu-id="49d11-124">In This Section</span></span>

  - [<span data-ttu-id="49d11-125">針對 Lync Server 2013 在拓撲建置器中定義和設定拓撲</span><span class="sxs-lookup"><span data-stu-id="49d11-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="49d11-126">在 Lync Server 2013 中定義和設定前端集區或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="49d11-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="49d11-127">在 Lync Server 2013 中針對災害復原部署配對前端集區</span><span class="sxs-lookup"><span data-stu-id="49d11-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="49d11-128">在 Lync Server 2013 中針對後端伺服器高可用性部署 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="49d11-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="49d11-129">在 Lync Server 2013 中編輯或設定簡單 URL</span><span class="sxs-lookup"><span data-stu-id="49d11-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="49d11-130">在 Lync Server 2013 中選取中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="49d11-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

