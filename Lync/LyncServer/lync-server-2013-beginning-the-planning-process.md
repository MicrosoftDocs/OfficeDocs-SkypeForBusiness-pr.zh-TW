---
title: Lync Server 2013： 從開始規劃程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd0a83042415cd2cf919d0fd66fe5309a4cae9e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="d98d4-102">開始 Lync Server 2013 的規劃程序</span><span class="sxs-lookup"><span data-stu-id="d98d4-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d98d4-103">_**主題上次修改日期：** 2012年-09-24_</span><span class="sxs-lookup"><span data-stu-id="d98d4-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="d98d4-104">規劃內部部署時整合的通訊部署可能有些聲勢浩大，Lync Server 提供兩種非常有用的工具，可協助您：</span><span class="sxs-lookup"><span data-stu-id="d98d4-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="d98d4-105">**規劃工具**是提供一系列的組織，您想要啟用 Lync Server 功能和容量規劃需求的相關問題的精靈。</span><span class="sxs-lookup"><span data-stu-id="d98d4-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="d98d4-106">然後會建立根據您的答案，建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="d98d4-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="d98d4-107">**拓撲產生器**是 Lync Server 安裝元件。</span><span class="sxs-lookup"><span data-stu-id="d98d4-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="d98d4-108">您可以使用拓撲產生器來建立、 調整，及發佈您計劃的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d98d4-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="d98d4-109">若要安裝伺服器之前，它也會驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d98d4-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="d98d4-110">當您在個別伺服器上安裝 Lync Server 時，伺服器安裝過程中，讀取已發行的拓撲，並依照拓撲中的指示，安裝程式會部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="d98d4-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="d98d4-111">Lync Server 規劃工具</span><span class="sxs-lookup"><span data-stu-id="d98d4-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="d98d4-112">規劃工具接受您對問題的回答工具中，並產生根據 Lync Server 指導方針和最佳作法的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d98d4-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="d98d4-113">它也會提供數個檢視的部署，根據您的答案。</span><span class="sxs-lookup"><span data-stu-id="d98d4-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="d98d4-114">它會顯示所有網站 （也就，包括中央站台和分公司站台），這兩個全域檢視和顯示伺服器和其他元件，每個站台的詳細檢視。</span><span class="sxs-lookup"><span data-stu-id="d98d4-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="d98d4-115">執行規劃工具不會認可您向任何特定的部署或啟動任何程序。</span><span class="sxs-lookup"><span data-stu-id="d98d4-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="d98d4-116">事實上，即使之前必須記住的公司的計劃執行規劃工具可以是非常更有意義的方式了解您需要考慮在您規劃程序中的問題類型。</span><span class="sxs-lookup"><span data-stu-id="d98d4-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="d98d4-117">您可以執行規劃工具多次，以不同的回答問題並比較結果。</span><span class="sxs-lookup"><span data-stu-id="d98d4-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="d98d4-118">如果您有您滿意大部分，但是您需要進行的變更設計，您可以回到 [規劃工具、 載入設計]，並進行變更。</span><span class="sxs-lookup"><span data-stu-id="d98d4-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="d98d4-119">所需約 15 分鐘一次完成規劃工具。</span><span class="sxs-lookup"><span data-stu-id="d98d4-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="d98d4-120">您滿意之後，您可以使用規劃工具建立計劃部署的圖表。</span><span class="sxs-lookup"><span data-stu-id="d98d4-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="d98d4-121">在拓撲產生器建立部署時，您可以使用此圖表中。</span><span class="sxs-lookup"><span data-stu-id="d98d4-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d98d4-122">隨附於此版本的 Lync Server 2013 規劃工具是搶鮮版。</span><span class="sxs-lookup"><span data-stu-id="d98d4-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="d98d4-123">附註中規劃工具的容量規劃數字屬初始版本，並不支援的最終版本。</span><span class="sxs-lookup"><span data-stu-id="d98d4-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="d98d4-124">Lync Server 拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="d98d4-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="d98d4-125">一旦您已決定在您的部署計劃，您使用拓撲產生器開始部署。</span><span class="sxs-lookup"><span data-stu-id="d98d4-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="d98d4-126">完成後，您使用拓撲產生器來驗證拓撲，並接著，如果它通過，您可以發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="d98d4-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="d98d4-127">當您發行拓撲時，Lync Server 會將拓撲放至中央管理存放區，如果不存在，會建立這一次。</span><span class="sxs-lookup"><span data-stu-id="d98d4-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="d98d4-128">當您部署中，每部伺服器上安裝 Lync Server 時，伺服器會讀取從中央管理存放區的拓撲，並安裝以符合您在部署中其角色本身擷取。</span><span class="sxs-lookup"><span data-stu-id="d98d4-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="d98d4-129">或者，如果您是非常熟悉 Lync Server，而且不需要規定，您可以略過規劃工具，並在拓撲產生器中使用精靈，您的部署的初始設計也用來驗證和發佈的步驟。</span><span class="sxs-lookup"><span data-stu-id="d98d4-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="d98d4-130">若要規劃並發行拓撲使用拓撲產生器是必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="d98d4-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="d98d4-131">您無法略過拓撲產生器和 Lync Server 個別伺服器上安裝在您的部署中。</span><span class="sxs-lookup"><span data-stu-id="d98d4-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="d98d4-132">每部伺服器必須從中央管理存放區中的驗證、 發行拓撲讀取拓樸。</span><span class="sxs-lookup"><span data-stu-id="d98d4-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="d98d4-133">高階規劃程序</span><span class="sxs-lookup"><span data-stu-id="d98d4-133">High-Level Planning Process</span></span>

<span data-ttu-id="d98d4-134">我們建議使用文件和規劃工具規劃 Lync Server 部署的下列一般程序。</span><span class="sxs-lookup"><span data-stu-id="d98d4-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="d98d4-135">如果您已熟悉舊版的 Lync Server，請閱讀[Lync Server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉的新功能和 Lync Server 2013 中的需求。</span><span class="sxs-lookup"><span data-stu-id="d98d4-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="d98d4-136">閱讀本章節屬於文件中的其他主題：[規劃針對 Lync Server 2013 前必須知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、[初始規劃決策以便 Lync Server 2013](lync-server-2013-initial-planning-decisions.md)，和[Lync Server 2013 的用戶端](lync-server-2013-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="d98d4-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="d98d4-137">請注意在[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)中表示的規劃決策。</span><span class="sxs-lookup"><span data-stu-id="d98d4-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="d98d4-138">既然您已較熟悉 Lync Server 功能與幾種類型的必須回答的問題，執行規劃工具，並檢視產生的拓撲和其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d98d4-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="d98d4-139">請確定拓撲適合貴組織的獨特需求。</span><span class="sxs-lookup"><span data-stu-id="d98d4-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="d98d4-140">如果有特定的工作量或功能您感興趣，或需要若要了解，請閱讀[Planning for Lync Server 2013](lync-server-2013-planning.md)的適當區段。</span><span class="sxs-lookup"><span data-stu-id="d98d4-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="d98d4-141">再次執行規劃工具。</span><span class="sxs-lookup"><span data-stu-id="d98d4-141">Run the Planning Tool again.</span></span> <span data-ttu-id="d98d4-142">您可以開始部署您在步驟 3 中建立及修改結果，或從頭開始。</span><span class="sxs-lookup"><span data-stu-id="d98d4-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="d98d4-143">如有需要執行規劃工具第三個階段，並重複，直到您滿意輸出。</span><span class="sxs-lookup"><span data-stu-id="d98d4-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="d98d4-144">當您已完成的拓樸計劃時，使用規劃工具來建立及列印您的拓樸的 Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="d98d4-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="d98d4-145">您可以使用此 printout 時使用拓撲產生器中，輸入您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d98d4-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="d98d4-146">在您開始部署之前讀取[決定 Lync Server 2013 系統需求](lync-server-2013-determining-your-system-requirements.md)，以及[決定 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)以熟悉的先決條件和必要基礎結構的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="d98d4-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="d98d4-147">此外，請確定您已閱讀所有章節的[Planning for Lync Server 2013](lync-server-2013-planning.md)適用於工作負載和您計劃部署的功能。</span><span class="sxs-lookup"><span data-stu-id="d98d4-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="d98d4-148">從舊版移轉</span><span class="sxs-lookup"><span data-stu-id="d98d4-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="d98d4-149">如果您從舊版移轉至 Lync Server，請參閱[移轉](migration.md)文件的移轉和部署的特定指示。</span><span class="sxs-lookup"><span data-stu-id="d98d4-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

