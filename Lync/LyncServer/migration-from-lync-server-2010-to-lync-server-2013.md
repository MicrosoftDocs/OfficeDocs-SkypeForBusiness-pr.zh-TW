---
title: 從 Lync Server 2010 遷移至 Lync Server 2013
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
ms.openlocfilehash: 89bc70635ac941398a71515e77dd1a792973fc35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527300"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="713a1-102">從 Lync Server 2010 遷移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713a1-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="713a1-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="713a1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="713a1-104">本節中的主題將引導您完成從 Lync Server 2010 遷移至 Lync Server 2013 的程式。</span><span class="sxs-lookup"><span data-stu-id="713a1-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="713a1-105">本檔說明執行每個遷移階段時，通常需要執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="713a1-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="713a1-106">它不會解決每一個可能的舊版部署拓撲或每一種可能的遷移案例。</span><span class="sxs-lookup"><span data-stu-id="713a1-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="713a1-107">因此，您可能不需要執行所述的每一個步驟，否則您可能需要執行其他步驟，視您的部署而定。</span><span class="sxs-lookup"><span data-stu-id="713a1-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="713a1-108">這份檔也提供驗證步驟的範例。</span><span class="sxs-lookup"><span data-stu-id="713a1-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="713a1-109">提供這些驗證步驟是為了協助您瞭解需要尋找哪些專案，以確保每個階段在您完成遷移時順利完成。</span><span class="sxs-lookup"><span data-stu-id="713a1-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="713a1-110">將這些驗證步驟調整為您特定的遷移程式。</span><span class="sxs-lookup"><span data-stu-id="713a1-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="713a1-111">本指南提供升級現有部署的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="713a1-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="713a1-112">它不會說明如何變更現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="713a1-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="713a1-113">本指南並未涵蓋新功能的實施。</span><span class="sxs-lookup"><span data-stu-id="713a1-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="713a1-114">在其他地方記錄詳細的程式時，本指南會指引您使用適當的檔或檔區段。</span><span class="sxs-lookup"><span data-stu-id="713a1-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="713a1-115">這份檔會定義下列清單中所指定的字詞。</span><span class="sxs-lookup"><span data-stu-id="713a1-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="713a1-116">*遷移*</span><span class="sxs-lookup"><span data-stu-id="713a1-116">*migration*</span></span>  
    <span data-ttu-id="713a1-117">將實際執行的部署從舊版的 Lync Server 2010 移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="713a1-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="713a1-118">*升級*</span><span class="sxs-lookup"><span data-stu-id="713a1-118">*upgrade*</span></span>  
    <span data-ttu-id="713a1-119">在伺服器或用戶端電腦上安裝較新版本的軟體。</span><span class="sxs-lookup"><span data-stu-id="713a1-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="713a1-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="713a1-120">*coexistence*</span></span>  
    <span data-ttu-id="713a1-121">在遷移期間，當某些功能已遷移至 Lync Server 2013，而其他功能仍保留在舊版的 Lync Server 2010 時，便會存在的臨時環境。</span><span class="sxs-lookup"><span data-stu-id="713a1-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="713a1-122">*互 操作 性*</span><span class="sxs-lookup"><span data-stu-id="713a1-122">*interoperability*</span></span>  
    <span data-ttu-id="713a1-123">您的部署在共存期間順利運作的能力。</span><span class="sxs-lookup"><span data-stu-id="713a1-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="713a1-124">本章節內容</span><span class="sxs-lookup"><span data-stu-id="713a1-124">In This Section</span></span>

  - [<span data-ttu-id="713a1-125">開始移轉之前</span><span class="sxs-lookup"><span data-stu-id="713a1-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="713a1-126">階段1：規劃從 Lync Server 2010 進行遷移</span><span class="sxs-lookup"><span data-stu-id="713a1-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="713a1-127">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="713a1-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="713a1-128">階段3：部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="713a1-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="713a1-129">階段4：將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="713a1-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="713a1-130">第5階段：將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="713a1-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="713a1-131">階段 6：從試驗部署移至生產</span><span class="sxs-lookup"><span data-stu-id="713a1-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="713a1-132">階段 7：完成移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="713a1-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="713a1-133">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="713a1-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

