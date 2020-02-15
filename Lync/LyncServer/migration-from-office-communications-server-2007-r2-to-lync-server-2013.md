---
title: 從 Office Communications Server 2007 R2 移轉至 Lync Server 2013
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
ms.openlocfilehash: 624891658fb925fbc2522e98f8b216e535d2bf0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="c9fb2-102">從 Office Communications Server 2007 R2 移轉至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9fb2-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9fb2-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="c9fb2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c9fb2-104">本節中的主題將引導您完成從 Office Communications Server 2007 R2 移轉至 Lync Server 2013 的程序</span><span class="sxs-lookup"><span data-stu-id="c9fb2-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9fb2-105">本文件說明通常完成移轉的每個階段所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="c9fb2-106">它並未涵蓋每個可能的舊版部署拓樸或每個可能的移轉案例。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="c9fb2-107">因此，您可能不需要執行每個步驟所述，或您可能需要執行額外步驟，根據您的部署。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="c9fb2-108">這份文件也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="c9fb2-109">下列驗證步驟提供可協助您了解您要尋找以確保，每個階段成功完成為您的進行移轉。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="c9fb2-110">調整您的特定移轉程序下列驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="c9fb2-111">本指南提供將升級的現有部署的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="c9fb2-112">它不會說明如何變更您現有的拓樸。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="c9fb2-113">本指南並未涵蓋實作的新功能。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="c9fb2-114">時的詳細程序會說明在其他地方，則本指南會引導您到適當的文件或文件] 區段中。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="c9fb2-115">本文件定義字詞指定下列清單中。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="c9fb2-116">*移轉*</span><span class="sxs-lookup"><span data-stu-id="c9fb2-116">*migration*</span></span>  
    <span data-ttu-id="c9fb2-117">將實際執行的部署從舊版 Office Communications Server 2007 R2 移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="c9fb2-118">*升級*</span><span class="sxs-lookup"><span data-stu-id="c9fb2-118">*upgrade*</span></span>  
    <span data-ttu-id="c9fb2-119">伺服器或用戶端電腦上安裝較新版的軟體。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="c9fb2-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="c9fb2-120">*coexistence*</span></span>  
    <span data-ttu-id="c9fb2-121">暫時環境，在移轉期間存在於，當某些功能會已移轉至 Lync Server 2013，以及其他功能則仍停留在前版的 Office Communications Server 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="c9fb2-122">*互通性*</span><span class="sxs-lookup"><span data-stu-id="c9fb2-122">*interoperability*</span></span>  
    <span data-ttu-id="c9fb2-123">共存期間順利運作您部署的能力。</span><span class="sxs-lookup"><span data-stu-id="c9fb2-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9fb2-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c9fb2-124">In This Section</span></span>

  - [<span data-ttu-id="c9fb2-125">開始移轉之前</span><span class="sxs-lookup"><span data-stu-id="c9fb2-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="c9fb2-126">移轉階段</span><span class="sxs-lookup"><span data-stu-id="c9fb2-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="c9fb2-127">階段 1： 規劃從 Office Communications Server 2007 R2 移轉</span><span class="sxs-lookup"><span data-stu-id="c9fb2-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="c9fb2-128">階段 2： 準備移轉</span><span class="sxs-lookup"><span data-stu-id="c9fb2-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="c9fb2-129">階段 3： 部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9fb2-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="c9fb2-130">階段 4： 合併拓撲</span><span class="sxs-lookup"><span data-stu-id="c9fb2-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="c9fb2-131">階段 5： 設定試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9fb2-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="c9fb2-132">階段 6： 將使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9fb2-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="c9fb2-133">階段 7： 將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9fb2-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="c9fb2-134">階段 8： 從試驗部署移至實際執行環境</span><span class="sxs-lookup"><span data-stu-id="c9fb2-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="c9fb2-135">階段 9： 完成移轉後工作</span><span class="sxs-lookup"><span data-stu-id="c9fb2-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="c9fb2-136">階段 10： 解除委任舊版站台</span><span class="sxs-lookup"><span data-stu-id="c9fb2-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

