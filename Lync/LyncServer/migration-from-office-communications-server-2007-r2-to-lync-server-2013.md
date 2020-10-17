---
title: 從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013
description: 從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0afdc754ae691bc674c200addb9fb97c1eb4199
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569589"
---
# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="bc01b-103">從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc01b-103">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc01b-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bc01b-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bc01b-105">本節中的主題將引導您完成從 Office 通訊伺服器 2007 R2 到 Lync Server 2013 的處理常式。</span><span class="sxs-lookup"><span data-stu-id="bc01b-105">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bc01b-106">本檔說明執行每個遷移階段時，通常需要執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="bc01b-106">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="bc01b-107">它不會解決每一個可能的舊版部署拓撲或每一種可能的遷移案例。</span><span class="sxs-lookup"><span data-stu-id="bc01b-107">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="bc01b-108">因此，您可能不需要執行所述的每一個步驟，否則您可能需要執行其他步驟，視您的部署而定。</span><span class="sxs-lookup"><span data-stu-id="bc01b-108">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="bc01b-109">這份檔也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="bc01b-109">This document also provides examples of verification steps.</span></span> <span data-ttu-id="bc01b-110">提供這些驗證步驟是為了協助您瞭解需要尋找哪些專案，以確保每個階段在您完成遷移時順利完成。</span><span class="sxs-lookup"><span data-stu-id="bc01b-110">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="bc01b-111">將這些驗證步驟調整為您特定的遷移程式。</span><span class="sxs-lookup"><span data-stu-id="bc01b-111">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="bc01b-112">本指南提供升級現有部署的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bc01b-112">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="bc01b-113">它不會說明如何變更現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="bc01b-113">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="bc01b-114">本指南並未涵蓋新功能的實施。</span><span class="sxs-lookup"><span data-stu-id="bc01b-114">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="bc01b-115">在其他地方記錄詳細的程式時，本指南會指引您使用適當的檔或檔區段。</span><span class="sxs-lookup"><span data-stu-id="bc01b-115">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="bc01b-116">這份檔會定義下列清單中所指定的字詞。</span><span class="sxs-lookup"><span data-stu-id="bc01b-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="bc01b-117">*遷移*</span><span class="sxs-lookup"><span data-stu-id="bc01b-117">*migration*</span></span>  
    <span data-ttu-id="bc01b-118">將實際執行部署從舊版 Office 通訊伺服器 2007 R2 移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="bc01b-118">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="bc01b-119">*升級*</span><span class="sxs-lookup"><span data-stu-id="bc01b-119">*upgrade*</span></span>  
    <span data-ttu-id="bc01b-120">在伺服器或用戶端電腦上安裝較新版本的軟體。</span><span class="sxs-lookup"><span data-stu-id="bc01b-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="bc01b-121">*共存*</span><span class="sxs-lookup"><span data-stu-id="bc01b-121">*coexistence*</span></span>  
    <span data-ttu-id="bc01b-122">當某些功能已遷移至 Lync Server 2013，而其他功能仍保留在先前版本的 Office 通訊伺服器 2007 R2 時，在遷移期間所存在的暫時環境。</span><span class="sxs-lookup"><span data-stu-id="bc01b-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="bc01b-123">*互 操作 性*</span><span class="sxs-lookup"><span data-stu-id="bc01b-123">*interoperability*</span></span>  
    <span data-ttu-id="bc01b-124">您的部署在共存期間順利運作的能力。</span><span class="sxs-lookup"><span data-stu-id="bc01b-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc01b-125">本章節內容</span><span class="sxs-lookup"><span data-stu-id="bc01b-125">In This Section</span></span>

  - [<span data-ttu-id="bc01b-126">開始移轉之前</span><span class="sxs-lookup"><span data-stu-id="bc01b-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="bc01b-127">移轉階段</span><span class="sxs-lookup"><span data-stu-id="bc01b-127">Migration phases</span></span>](migration-phases.md)

  - [<span data-ttu-id="bc01b-128">階段1：規劃從 Office 通訊伺服器 2007 R2 遷移</span><span class="sxs-lookup"><span data-stu-id="bc01b-128">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="bc01b-129">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="bc01b-129">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="bc01b-130">階段3：部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="bc01b-130">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="bc01b-131">階段4：合併拓撲</span><span class="sxs-lookup"><span data-stu-id="bc01b-131">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="bc01b-132">階段5：設定試驗集區</span><span class="sxs-lookup"><span data-stu-id="bc01b-132">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="bc01b-133">階段6：將使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="bc01b-133">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="bc01b-134">第7階段：將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="bc01b-134">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="bc01b-135">階段8：從試驗部署移至實際執行環境</span><span class="sxs-lookup"><span data-stu-id="bc01b-135">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="bc01b-136">階段9：完成遷移後工作</span><span class="sxs-lookup"><span data-stu-id="bc01b-136">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="bc01b-137">階段10：解除委任舊版網站</span><span class="sxs-lookup"><span data-stu-id="bc01b-137">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

