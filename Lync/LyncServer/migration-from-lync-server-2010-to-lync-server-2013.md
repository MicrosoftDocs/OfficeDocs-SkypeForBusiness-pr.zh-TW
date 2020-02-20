---
title: 從 Lync Server 2010 移轉至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0688fc80bb763a4b5aa3e7ff10970cef96465b84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="97994-102">從 Lync Server 2010 移轉至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97994-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97994-103">_**主題上次修改日期：** 2012年-09-17_</span><span class="sxs-lookup"><span data-stu-id="97994-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="97994-104">本節中的主題會引導您完成從 Lync Server 2010 移轉至 Lync Server 2013 的程序。</span><span class="sxs-lookup"><span data-stu-id="97994-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97994-105">本文件說明通常完成移轉的每個階段所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="97994-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="97994-106">它並未涵蓋每個可能的舊版部署拓樸或每個可能的移轉案例。</span><span class="sxs-lookup"><span data-stu-id="97994-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="97994-107">因此，您可能不需要執行每個步驟所述，或您可能需要執行額外步驟，根據您的部署。</span><span class="sxs-lookup"><span data-stu-id="97994-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="97994-108">這份文件也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="97994-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="97994-109">下列驗證步驟提供可協助您了解您要尋找以確保，每個階段成功完成為您的進行移轉。</span><span class="sxs-lookup"><span data-stu-id="97994-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="97994-110">調整您的特定移轉程序下列驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="97994-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="97994-111">本指南提供將升級的現有部署的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="97994-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="97994-112">它不會說明如何變更您現有的拓樸。</span><span class="sxs-lookup"><span data-stu-id="97994-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="97994-113">本指南並未涵蓋實作的新功能。</span><span class="sxs-lookup"><span data-stu-id="97994-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="97994-114">時的詳細程序會說明在其他地方，則本指南會引導您到適當的文件或文件] 區段中。</span><span class="sxs-lookup"><span data-stu-id="97994-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="97994-115">本文件定義字詞指定下列清單中。</span><span class="sxs-lookup"><span data-stu-id="97994-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="97994-116">*移轉*</span><span class="sxs-lookup"><span data-stu-id="97994-116">*migration*</span></span>  
    <span data-ttu-id="97994-117">將實際執行的部署從舊版 Lync Server 2010 移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="97994-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="97994-118">*升級*</span><span class="sxs-lookup"><span data-stu-id="97994-118">*upgrade*</span></span>  
    <span data-ttu-id="97994-119">伺服器或用戶端電腦上安裝較新版的軟體。</span><span class="sxs-lookup"><span data-stu-id="97994-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="97994-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="97994-120">*coexistence*</span></span>  
    <span data-ttu-id="97994-121">暫時環境，在移轉期間存在於，當某些功能會已移轉至 Lync Server 2013，以及其他功能則仍停留在前版的 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="97994-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="97994-122">*互通性*</span><span class="sxs-lookup"><span data-stu-id="97994-122">*interoperability*</span></span>  
    <span data-ttu-id="97994-123">共存期間順利運作您部署的能力。</span><span class="sxs-lookup"><span data-stu-id="97994-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97994-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="97994-124">In This Section</span></span>

  - [<span data-ttu-id="97994-125">開始移轉之前</span><span class="sxs-lookup"><span data-stu-id="97994-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="97994-126">階段 1： 規劃從 Lync Server 2010 移轉</span><span class="sxs-lookup"><span data-stu-id="97994-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="97994-127">階段 2： 準備移轉</span><span class="sxs-lookup"><span data-stu-id="97994-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="97994-128">階段 3： 部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="97994-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="97994-129">階段 4： 將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="97994-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="97994-130">階段 5： 將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="97994-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="97994-131">階段 6： 從試驗部署移至實際執行環境</span><span class="sxs-lookup"><span data-stu-id="97994-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="97994-132">階段 7： 完成移轉後工作</span><span class="sxs-lookup"><span data-stu-id="97994-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="97994-133">第 8 階段： 解除委任舊版的集區</span><span class="sxs-lookup"><span data-stu-id="97994-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

