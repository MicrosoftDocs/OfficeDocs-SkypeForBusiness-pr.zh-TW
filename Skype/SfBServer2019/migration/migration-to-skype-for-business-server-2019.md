---
title: 遷移至商務用 Skype Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本節中的主題會引導您逐步完成遷移至商務用 Skype Server 2019 的程式。
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193059"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="cca5d-103">遷移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="cca5d-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="cca5d-104">本節中的主題會引導您逐步完成遷移至商務用 Skype Server 2019 的程式。</span><span class="sxs-lookup"><span data-stu-id="cca5d-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="cca5d-105">本文涵蓋將 Lync Server 2013 或商務用 Skype Server 2015 遷移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="cca5d-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cca5d-106">在整個內容中, 我們使用*舊版的舊版*Lync server 2013 或您要遷移至商務用 skype server 2019 的商務用 skype server 2015。</span><span class="sxs-lookup"><span data-stu-id="cca5d-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cca5d-107">本指南描述完成每個遷移階段通常需要執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="cca5d-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="cca5d-108">它不會針對每個可能的舊版部署拓撲或每個可能的遷移案例進行處理。</span><span class="sxs-lookup"><span data-stu-id="cca5d-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="cca5d-109">因此, 您可能不需要執行所述的每個步驟, 或者您可能需要執行其他步驟 (視您的部署而定)。</span><span class="sxs-lookup"><span data-stu-id="cca5d-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="cca5d-110">本指南也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="cca5d-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="cca5d-111">提供這些驗證步驟是為了協助您瞭解所需尋找的專案, 以確保每個階段都能在您完成遷移時順利完成。</span><span class="sxs-lookup"><span data-stu-id="cca5d-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="cca5d-112">將這些驗證步驟調整為您特定的遷移程式。</span><span class="sxs-lookup"><span data-stu-id="cca5d-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="cca5d-113">本指南提供升級現有部署的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cca5d-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="cca5d-114">它不會說明如何變更您現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="cca5d-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="cca5d-115">本指南並未涵蓋新功能的實現。</span><span class="sxs-lookup"><span data-stu-id="cca5d-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="cca5d-116">在其他地方記錄詳細的程式時, 本指南會將您導向至文章或文章區段。</span><span class="sxs-lookup"><span data-stu-id="cca5d-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="cca5d-117">本文將根據下列清單中所指定的字詞加以定義。</span><span class="sxs-lookup"><span data-stu-id="cca5d-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="cca5d-118">**遷移:** 將您的生產部署從 Lync Server 2013 或商務用 Skype Server 2015 移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="cca5d-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="cca5d-119">**共存:** 在遷移期間, 當某些功能已遷移至商務用 Skype Server 2019 且其他功能仍保留在先前版本時, 在遷移期間所存在的臨時環境。</span><span class="sxs-lookup"><span data-stu-id="cca5d-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="cca5d-120">**互通性:** 您的部署在共存期間成功運作的能力。</span><span class="sxs-lookup"><span data-stu-id="cca5d-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="cca5d-121">**舊版:** 您要從中移出的系統, 即 Lync Server 2013 或商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="cca5d-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="cca5d-122">本節內容</span><span class="sxs-lookup"><span data-stu-id="cca5d-122">In this section</span></span>

- [<span data-ttu-id="cca5d-123">開始進行遷移之前</span><span class="sxs-lookup"><span data-stu-id="cca5d-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="cca5d-124">階段 1: 規劃您的遷移</span><span class="sxs-lookup"><span data-stu-id="cca5d-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="cca5d-125">階段 2: 準備遷移</span><span class="sxs-lookup"><span data-stu-id="cca5d-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="cca5d-126">階段 3: 部署試生產池</span><span class="sxs-lookup"><span data-stu-id="cca5d-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- <span data-ttu-id="cca5d-127">[階段 4: 將測試使用者移至 [試驗] 池](phase-4-move-test-users-to-the-pilot-pool.md)</span><span class="sxs-lookup"><span data-stu-id="cca5d-127">[Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md)</span></span>
    
- [<span data-ttu-id="cca5d-128">階段 5: 將邊緣伺服器新增至試驗池</span><span class="sxs-lookup"><span data-stu-id="cca5d-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="cca5d-129">階段 6: 從試驗部署移至生產環境</span><span class="sxs-lookup"><span data-stu-id="cca5d-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="cca5d-130">階段 7: 完成遷移後的工作</span><span class="sxs-lookup"><span data-stu-id="cca5d-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="cca5d-131">階段 8: 解除授權舊版池</span><span class="sxs-lookup"><span data-stu-id="cca5d-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

