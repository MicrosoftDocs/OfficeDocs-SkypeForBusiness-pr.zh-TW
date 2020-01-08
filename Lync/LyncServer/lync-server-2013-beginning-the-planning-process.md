---
title: Lync Server 2013：開始規劃程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="dde58-102">開始 Lync Server 2013 的規劃程序</span><span class="sxs-lookup"><span data-stu-id="dde58-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde58-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="dde58-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="dde58-104">規劃內部部署的整合通訊部署可能看起來 intimidating，Lync Server 提供兩個實用的工具來協助您：</span><span class="sxs-lookup"><span data-stu-id="dde58-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="dde58-105">**規劃工具**是一個說明您組織的一系列問題、您想要啟用的 Lync Server 功能，以及您的容量規劃需求的嚮導。</span><span class="sxs-lookup"><span data-stu-id="dde58-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="dde58-106">然後根據您的回答建立建議的部署拓撲，並產生此部署的 Microsoft Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="dde58-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="dde58-107">[**拓撲**建立器] 是 Lync Server 的安裝元件。</span><span class="sxs-lookup"><span data-stu-id="dde58-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="dde58-108">您可以使用 [拓撲建立器] 來建立、調整及發佈規劃的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="dde58-109">它也會在您開始伺服器安裝之前驗證您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="dde58-110">當您在個別伺服器上安裝 Lync Server 時，伺服器會讀取已發佈的拓撲，作為安裝程式的一部分，而安裝程式會以拓撲中的指示方式來部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="dde58-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="dde58-111">Lync Server 規劃工具</span><span class="sxs-lookup"><span data-stu-id="dde58-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="dde58-112">規劃工具會針對工具中的問題提出您的答案，並根據 Lync Server 指導方針和最佳做法產生拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="dde58-113">它也會根據您的答案，提供幾個部署的視圖。</span><span class="sxs-lookup"><span data-stu-id="dde58-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="dde58-114">它同時顯示所有網站的全域視圖（也就是包括中央網站和分支網站），以及每個網站上顯示伺服器與其他元件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dde58-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="dde58-115">執行規劃工具不會將您提交至任何特定部署或啟動任何進程。</span><span class="sxs-lookup"><span data-stu-id="dde58-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="dde58-116">事實上，即使在您有固定方案之前，仍要執行規劃工具，才能瞭解您在規劃程式中需要考慮的問題類型。</span><span class="sxs-lookup"><span data-stu-id="dde58-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="dde58-117">您可以多次執行規劃工具、以不同方式回答問題，以及比較結果。</span><span class="sxs-lookup"><span data-stu-id="dde58-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="dde58-118">如果您的設計主要是滿意的，但您需要變更，您可以返回規劃工具、載入設計，然後進行變更。</span><span class="sxs-lookup"><span data-stu-id="dde58-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="dde58-119">完成規劃工具需要大約15分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="dde58-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="dde58-120">當您滿意時，您可以使用規劃工具來建立規劃的部署圖表。</span><span class="sxs-lookup"><span data-stu-id="dde58-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="dde58-121">您可以使用此圖表，同時在拓撲建立器中建立部署。</span><span class="sxs-lookup"><span data-stu-id="dde58-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dde58-122">此版本 Lync Server 2013 隨附的規劃工具是預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="dde58-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="dde58-123">請注意，規劃工具中的容量規劃數位是初步的，而且最終版本不支援。</span><span class="sxs-lookup"><span data-stu-id="dde58-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="dde58-124">Lync Server 拓撲建立器</span><span class="sxs-lookup"><span data-stu-id="dde58-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="dde58-125">在您決定部署方案之後，您可以使用拓撲建立器開始部署。</span><span class="sxs-lookup"><span data-stu-id="dde58-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="dde58-126">完成後，您可以使用 [拓撲建立器] 來驗證拓撲，然後，如果它透過，您就可以發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="dde58-127">當您發佈拓撲時，Lync Server 會將拓朴放入中央管理儲存區中（如果目前還不存在），就會建立拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="dde58-128">當您在部署中的每個伺服器上安裝 Lync Server 時，伺服器都會從中央管理儲存體讀取拓撲，並自行安裝，以納入其在您的部署中的角色。</span><span class="sxs-lookup"><span data-stu-id="dde58-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="dde58-129">或者，如果您很熟悉 Lync Server，且需要更少的規範性指示，您可以略過規劃工具，並使用拓撲建立器中的嚮導來進行部署的初始設計，以及驗證與發佈步驟。</span><span class="sxs-lookup"><span data-stu-id="dde58-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="dde58-130">使用 [拓撲建立器] 來規劃及發佈拓撲是必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="dde58-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="dde58-131">您不能略過拓撲建立器，並在部署中的伺服器上個別安裝 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="dde58-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="dde58-132">每個伺服器都必須從中央管理儲存體中已驗證且已發佈的拓撲讀取拓撲。</span><span class="sxs-lookup"><span data-stu-id="dde58-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="dde58-133">高層規劃流程</span><span class="sxs-lookup"><span data-stu-id="dde58-133">High-Level Planning Process</span></span>

<span data-ttu-id="dde58-134">我們建議您在使用檔和規劃工具來規劃 Lync Server 部署時，進行下列一般處理常式。</span><span class="sxs-lookup"><span data-stu-id="dde58-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="dde58-135">如果您熟悉舊版 Lync Server，請閱讀[Lync server 2013 中的新功能](lync-server-2013-new-features.md)，以熟悉 lync server 2013 中的新功能和需求。</span><span class="sxs-lookup"><span data-stu-id="dde58-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="dde58-136">閱讀本章節中的其他主題：在[規劃 Lync server 2013 之前，您必須瞭解](lync-server-2013-topology-basics-you-must-know-before-planning.md) [lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)、 [lync server 2013 的初始規劃決定](lync-server-2013-initial-planning-decisions.md)，以及[lync server 2013 的用戶端](lync-server-2013-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="dde58-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="dde58-137">請注意在[Lync Server 2013 的參考拓朴](lync-server-2013-reference-topologies.md)中所代表的規劃決策。</span><span class="sxs-lookup"><span data-stu-id="dde58-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="dde58-138">現在您更熟悉 Lync Server 功能及必須回答的問題種類，請執行規劃工具並查看產生的拓撲及其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dde58-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="dde58-139">確定拓朴符合貴組織的獨特需求。</span><span class="sxs-lookup"><span data-stu-id="dde58-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="dde58-140">如果有您感興趣或需要瞭解的特定工作負載或功能，請閱讀[規劃 Lync Server 2013](lync-server-2013-planning.md)的適當章節。</span><span class="sxs-lookup"><span data-stu-id="dde58-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="dde58-141">再次執行規劃工具。</span><span class="sxs-lookup"><span data-stu-id="dde58-141">Run the Planning Tool again.</span></span> <span data-ttu-id="dde58-142">您可以從您在步驟3中建立的部署開始，並修改結果，或從開頭開始。</span><span class="sxs-lookup"><span data-stu-id="dde58-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="dde58-143">如有需要，請在第三次執行規劃工具，然後重複上述步驟，直到您對輸出滿意為止。</span><span class="sxs-lookup"><span data-stu-id="dde58-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="dde58-144">當您完成拓撲方案後，請使用規劃工具來建立及列印您拓撲的 Visio 圖表。</span><span class="sxs-lookup"><span data-stu-id="dde58-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="dde58-145">您可以在使用 [拓撲建立器] 來輸入您的拓撲中使用此列印成品。</span><span class="sxs-lookup"><span data-stu-id="dde58-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="dde58-146">開始部署之前，請先閱讀[判斷 Lync server 2013 的系統需求](lync-server-2013-determining-your-system-requirements.md)，並[判斷 lync server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)，以熟悉 lync server 的先決條件與必要基礎結構。</span><span class="sxs-lookup"><span data-stu-id="dde58-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="dde58-147">此外，請確定您已閱讀所有適用于您規劃部署之工作量與功能的[Lync Server 2013 規劃](lync-server-2013-planning.md)區段。</span><span class="sxs-lookup"><span data-stu-id="dde58-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="dde58-148">從先前的版本遷移</span><span class="sxs-lookup"><span data-stu-id="dde58-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="dde58-149">如果您是從舊版遷移至 Lync Server，請參閱[遷移](migration.md)檔，以取得有關您的遷移和部署的特定指示。</span><span class="sxs-lookup"><span data-stu-id="dde58-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

