---
title: Lync Server 2013：開始規劃程式
description: Lync Server 2013：開始規劃程式。
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
ms.openlocfilehash: 9aa46d660ca60538f87c570dd2d7667afd23c609
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552299"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="cce0b-103">開始 Lync Server 2013 的規劃程式</span><span class="sxs-lookup"><span data-stu-id="cce0b-103">Beginning the planning process for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cce0b-104">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="cce0b-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="cce0b-105">在規劃內部部署的整合通訊部署時，可能似乎 intimidating，Lync Server 提供兩個有價值的工具來協助您：</span><span class="sxs-lookup"><span data-stu-id="cce0b-105">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="cce0b-106">**規劃工具** 是一個包含有關組織相關問題的嚮導、您想要啟用的 Lync Server 功能，以及您的容量規劃需求。</span><span class="sxs-lookup"><span data-stu-id="cce0b-106">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="cce0b-107">然後，它會根據您的回答建立建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="cce0b-107">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="cce0b-108">**拓撲** 產生器是 Lync Server 的安裝元件。</span><span class="sxs-lookup"><span data-stu-id="cce0b-108">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="cce0b-109">您可以使用拓撲產生器來建立、調整和發行您規劃的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-109">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="cce0b-110">在您開始伺服器安裝之前，它也會驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-110">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="cce0b-111">當您在個別伺服器上安裝 Lync Server 時，伺服器會在安裝過程中讀取已發佈的拓撲，而且安裝程式會以拓撲中的導向方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="cce0b-111">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="cce0b-112">Lync Server 規劃工具</span><span class="sxs-lookup"><span data-stu-id="cce0b-112">Lync Server Planning Tool</span></span>

<span data-ttu-id="cce0b-113">規劃工具採用工具中問題的答案，並根據 Lync Server 指導方針和最佳作法產生拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-113">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="cce0b-114">它也會根據您的回答，提供數個部署的視圖。</span><span class="sxs-lookup"><span data-stu-id="cce0b-114">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="cce0b-115">它會顯示所有網站的全域視圖 (，包括「中央網站」和「分支網站」) ，以及顯示每個網站上的伺服器及其他元件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="cce0b-115">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="cce0b-116">執行規劃工具並不會向您認可任何特定的部署或啟動任何程式。</span><span class="sxs-lookup"><span data-stu-id="cce0b-116">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="cce0b-117">實際上，即使在您準備好方案之前執行規劃工具，也可能是一種非常有益的方式，可瞭解在規劃程式中需要考慮的問題種類。</span><span class="sxs-lookup"><span data-stu-id="cce0b-117">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="cce0b-118">您可以多次執行計畫工具，以不同方式回答問題，並比較結果。</span><span class="sxs-lookup"><span data-stu-id="cce0b-118">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="cce0b-119">如果您有大部分的設計，但您需要變更，您可以回到規劃工具、載入設計，然後進行變更。</span><span class="sxs-lookup"><span data-stu-id="cce0b-119">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="cce0b-120">完成規劃工具一次大約需要15分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="cce0b-120">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="cce0b-121">當您滿意後，您可以使用規劃工具來建立規劃的部署圖表。</span><span class="sxs-lookup"><span data-stu-id="cce0b-121">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="cce0b-122">您可以在拓撲產生器中建立部署時使用此圖表。</span><span class="sxs-lookup"><span data-stu-id="cce0b-122">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cce0b-123">此版本的 Lync Server 2013 包含的計畫工具是一個預先發行版本本。</span><span class="sxs-lookup"><span data-stu-id="cce0b-123">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="cce0b-124">請注意，規劃工具中的容量規劃編號是初步的，且不支援最後的版本。</span><span class="sxs-lookup"><span data-stu-id="cce0b-124">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="cce0b-125">Lync Server 拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="cce0b-125">Lync Server Topology Builder</span></span>

<span data-ttu-id="cce0b-126">決定部署計畫之後，您可以使用拓撲產生器開始部署。</span><span class="sxs-lookup"><span data-stu-id="cce0b-126">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="cce0b-127">完成後，您可以使用拓撲產生器來驗證拓撲，然後在它通過後，您就可以發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-127">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="cce0b-128">當您發佈拓撲時，Lync Server 會將拓撲放入中央管理存放區中（如果尚未存在），便會建立拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-128">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="cce0b-129">當您在部署中的每一部伺服器上安裝 Lync Server 時，伺服器會從中央管理存放區讀取拓撲，並自行安裝以符合其在您的部署中的角色。</span><span class="sxs-lookup"><span data-stu-id="cce0b-129">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="cce0b-130">或者，如果您很熟悉 Lync Server，且需要較少的規範性指導，您可以略過規劃工具並使用拓撲產生器中的嚮導，以進行部署的初始設計，以及驗證與發佈步驟。</span><span class="sxs-lookup"><span data-stu-id="cce0b-130">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="cce0b-131">使用拓撲產生器來規劃及發行拓撲是必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="cce0b-131">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="cce0b-132">您無法略過拓撲產生器，並在部署中的伺服器上個別安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="cce0b-132">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="cce0b-133">每個伺服器都必須從中央管理存放區中已驗證、已發佈的拓撲讀取拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-133">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="cce0b-134">規劃程式 High-Level</span><span class="sxs-lookup"><span data-stu-id="cce0b-134">High-Level Planning Process</span></span>

<span data-ttu-id="cce0b-135">我們建議您在使用檔和規劃工具來規劃 Lync Server 部署時，使用下列一般處理常式。</span><span class="sxs-lookup"><span data-stu-id="cce0b-135">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="cce0b-136">如果您熟悉舊版的 Lync Server，請閱讀 [Lync server 2013 中的新功能](lync-server-2013-new-features.md) ，以熟悉 lync server 2013 中的新功能和需求。</span><span class="sxs-lookup"><span data-stu-id="cce0b-136">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="cce0b-137">請閱讀本檔本節中的其他主題： [您必須2013知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)、 [lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、lync [server 2013 的初始規劃決策](lync-server-2013-initial-planning-decisions.md)，以及 [lync server 2013 的用戶端](lync-server-2013-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="cce0b-137">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="cce0b-138">請注意 [Lync Server 2013 的參考拓撲中](lync-server-2013-reference-topologies.md)所代表的規劃決策。</span><span class="sxs-lookup"><span data-stu-id="cce0b-138">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="cce0b-139">現在，您更熟悉 Lync Server 功能和必須回答的問題種類，請執行規劃工具，然後查看產生的拓撲及其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cce0b-139">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="cce0b-140">請確定拓撲符合您組織的獨特需求。</span><span class="sxs-lookup"><span data-stu-id="cce0b-140">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="cce0b-141">如果有您感興趣的特定工作負載或功能或需要深入瞭解，請參閱 [規劃 Lync Server 2013](lync-server-2013-planning.md)的適當章節。</span><span class="sxs-lookup"><span data-stu-id="cce0b-141">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="cce0b-142">再次執行計畫工具。</span><span class="sxs-lookup"><span data-stu-id="cce0b-142">Run the Planning Tool again.</span></span> <span data-ttu-id="cce0b-143">您可以從您在步驟3中建立的部署開始，並修改結果，或從頭開始。</span><span class="sxs-lookup"><span data-stu-id="cce0b-143">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="cce0b-144">如有需要，請在第三次執行計畫工具，並重複此步驟，直到您對輸出滿意為止。</span><span class="sxs-lookup"><span data-stu-id="cce0b-144">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="cce0b-145">當您完成拓撲計畫時，請使用規劃工具來建立及列印拓撲的 Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="cce0b-145">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="cce0b-146">使用拓撲產生器時，您可以使用此列印輸出來輸入您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cce0b-146">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="cce0b-147">開始部署之前，請先閱讀 [判斷您的 Lync server 2013 的系統需求](lync-server-2013-determining-your-system-requirements.md) ，並 [決定 lync server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) ，以熟悉 lync server 的必要條件及必要基礎結構。</span><span class="sxs-lookup"><span data-stu-id="cce0b-147">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="cce0b-148">此外，請確定您已閱讀適用于您計畫要部署之工作負載和功能之所有 [規劃的 Lync Server 2013](lync-server-2013-planning.md) 的部分。</span><span class="sxs-lookup"><span data-stu-id="cce0b-148">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="cce0b-149">從先前版本遷移</span><span class="sxs-lookup"><span data-stu-id="cce0b-149">Migrating from Previous Versions</span></span>

<span data-ttu-id="cce0b-150">若要從先前版本遷移至 Lync Server，請參閱遷移和部署的特定指示的 [遷移](migration.md) 檔。</span><span class="sxs-lookup"><span data-stu-id="cce0b-150">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

