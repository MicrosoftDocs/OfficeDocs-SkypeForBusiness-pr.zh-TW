---
title: Lync Server 2013： 定義和設定拓撲
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
ms.openlocfilehash: 8bb1f4ce9ec10b8babbf5507d56b9acb4bfb2494
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="47ee5-102">定義和設定 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="47ee5-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47ee5-103">_**主題上次修改日期：** 2012年-09-14_</span><span class="sxs-lookup"><span data-stu-id="47ee5-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="47ee5-104">您定義，並使用拓撲產生器設定您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="47ee5-105">拓撲產生器不需要是本機 Administrators 群組或特殊權限的網域群組 （如網域系統管理員） 的成員。</span><span class="sxs-lookup"><span data-stu-id="47ee5-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="47ee5-106">您可以標準使用者身分定義拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="47ee5-107">當您啟動拓撲產生器中第一次使用以及後續編輯工作階段，會提示您輸入您希望拓撲產生器來載入目前的設定文件的位置。</span><span class="sxs-lookup"><span data-stu-id="47ee5-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="47ee5-108">選項如下：</span><span class="sxs-lookup"><span data-stu-id="47ee5-108">The choices are the following:</span></span>

  - <span data-ttu-id="47ee5-109">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="47ee5-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="47ee5-110">從本機檔案開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="47ee5-110">Open topology from a local file</span></span>

  - <span data-ttu-id="47ee5-111">新增拓撲</span><span class="sxs-lookup"><span data-stu-id="47ee5-111">New topology</span></span>

<span data-ttu-id="47ee5-112">如果您已定義拓撲，並已建立的中央管理存放區，您應該選擇 [從現有部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="47ee5-113">拓撲產生器將讀取資料庫，並擷取目前的定義。</span><span class="sxs-lookup"><span data-stu-id="47ee5-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="47ee5-114">如果您有現有的中央管理存放區，您應該一律選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="47ee5-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="47ee5-115">如果您不具有建立中央管理存放區，並想要編輯先前儲存的設定，您應該選擇 [從本機檔案開啟拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="47ee5-116">您將開啟的檔案，必須是先前工作階段中儲存的組態檔。</span><span class="sxs-lookup"><span data-stu-id="47ee5-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="47ee5-117">您可以透過這個選項，編輯先前儲存的拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="47ee5-p104">如果您已經有發行的拓撲，請勿載入本機組態檔。您應該選擇從現有部署下載拓撲。</span><span class="sxs-lookup"><span data-stu-id="47ee5-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="47ee5-120">選擇建立新的拓撲中，如果您想要建立新的拓撲產生器設定。</span><span class="sxs-lookup"><span data-stu-id="47ee5-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="47ee5-121">除非您選擇將先前儲存的設計儲存您在先前設計工作階段裡建立的相同檔案，否則不會複寫先前儲存的設計。</span><span class="sxs-lookup"><span data-stu-id="47ee5-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="47ee5-122">在每個這些選項，將會提示您用於儲存拓撲產生器設定檔的位置。</span><span class="sxs-lookup"><span data-stu-id="47ee5-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="47ee5-123">該檔案位置可以是本機位置、已建立的檔案共用之共用位置，或是卸除式媒體。</span><span class="sxs-lookup"><span data-stu-id="47ee5-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47ee5-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="47ee5-124">In This Section</span></span>

  - [<span data-ttu-id="47ee5-125">定義和設定拓撲中的 Lync Server 2013 的拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="47ee5-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="47ee5-126">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="47ee5-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="47ee5-127">Lync Server 2013 的災害復原部署配對的前端集區</span><span class="sxs-lookup"><span data-stu-id="47ee5-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="47ee5-128">部署 SQL 鏡像後端伺服器高可用性的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47ee5-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="47ee5-129">編輯或 Lync Server 2013 中設定簡單 Url</span><span class="sxs-lookup"><span data-stu-id="47ee5-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="47ee5-130">Lync Server 2013 中選取中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="47ee5-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

