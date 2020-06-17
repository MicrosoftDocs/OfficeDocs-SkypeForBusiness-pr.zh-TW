---
title: 遷移至商務用 Skype Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本節中的主題將引導您完成遷移至商務用 Skype Server 2019 的程式。
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752615"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="38426-103">遷移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="38426-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="38426-104">本節中的主題將引導您完成遷移至商務用 Skype Server 2019 的程式。</span><span class="sxs-lookup"><span data-stu-id="38426-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="38426-105">本文涵蓋如何將 Lync Server 2013 或商務用 Skype Server 2015 遷移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="38426-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38426-106">在整個內容中，我們使用*傳統*的 Lync server 2013 或您要遷移至商務用 skype server 2019 的商務用 skype server 2015。</span><span class="sxs-lookup"><span data-stu-id="38426-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38426-107">本指南說明完成每一階段遷移的一般必要步驟。</span><span class="sxs-lookup"><span data-stu-id="38426-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="38426-108">它不會解決每一個可能的舊版部署拓撲或每一種可能的遷移案例。</span><span class="sxs-lookup"><span data-stu-id="38426-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="38426-109">因此，您可能不需要執行所述的每一個步驟，否則您可能需要執行其他步驟，視您的部署而定。</span><span class="sxs-lookup"><span data-stu-id="38426-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="38426-110">本指南也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="38426-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="38426-111">提供這些驗證步驟是為了協助您瞭解需要尋找哪些專案，以確保每個階段在您完成遷移時順利完成。</span><span class="sxs-lookup"><span data-stu-id="38426-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="38426-112">將這些驗證步驟調整為您特定的遷移程式。</span><span class="sxs-lookup"><span data-stu-id="38426-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="38426-113">本指南提供升級現有部署的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="38426-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="38426-114">它不會說明如何變更現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="38426-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="38426-115">本指南並未涵蓋新功能的實施。</span><span class="sxs-lookup"><span data-stu-id="38426-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="38426-116">在其他地方記錄詳細的程式時，本指南會指引您前往 [文章] 或 [文章] 區段。</span><span class="sxs-lookup"><span data-stu-id="38426-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="38426-117">本文依照下列清單所指定的方式來定義字詞。</span><span class="sxs-lookup"><span data-stu-id="38426-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="38426-118">**遷移：** 將實際執行部署從 Lync Server 2013 或商務用 Skype Server 2015 移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="38426-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="38426-119">**共存：** 在遷移過程中，當某些功能已遷移至商務用 Skype Server 2019，而其他功能仍然保留在先前的版本中時，會在遷移期間存在的臨時環境。</span><span class="sxs-lookup"><span data-stu-id="38426-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="38426-120">**互通性：** 您的部署在共存期間順利運作的能力。</span><span class="sxs-lookup"><span data-stu-id="38426-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="38426-121">**舊版：** 您要從其中遷移的系統，也就是 Lync Server 2013 或商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="38426-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="38426-122">本節內容</span><span class="sxs-lookup"><span data-stu-id="38426-122">In this section</span></span>

- [<span data-ttu-id="38426-123">開始移轉之前</span><span class="sxs-lookup"><span data-stu-id="38426-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="38426-124">階段 1：規劃移轉</span><span class="sxs-lookup"><span data-stu-id="38426-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="38426-125">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="38426-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="38426-126">階段 3：部署試驗集區</span><span class="sxs-lookup"><span data-stu-id="38426-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="38426-127">階段4：將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="38426-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="38426-128">階段 5：將 Edge Server 新增到試驗集區</span><span class="sxs-lookup"><span data-stu-id="38426-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="38426-129">階段 6：從試驗部署移至生產</span><span class="sxs-lookup"><span data-stu-id="38426-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="38426-130">階段 7：完成移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="38426-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="38426-131">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="38426-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

