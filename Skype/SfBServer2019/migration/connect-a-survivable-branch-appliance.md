---
title: 連接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。 SBA 時必須與前端集區解除關聯前端集區移轉至 Skype for Business Server 2019，SBA，升級之集區時，一旦 Business Server 2019 的集區移轉至 Skype 時，可以與升級前端 E 重新產生關聯nd 集區。 這包括刪除 SBA 從拓撲產生器的傳統拓撲並再將 SBA 新增至 Skype for Business Server 2019 拓樸。 隸屬於舊版 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。 一旦 SBA 新增至 Skype for Business Server 2019 拓撲後，這些使用者可以再移回 sba。 這些步驟的摘要如下：
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027784"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="e509a-108">連接 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="e509a-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="e509a-109">每個 Survivable Branch Appliance (SBA) 是做為備份登錄器 SBA 的前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="e509a-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="e509a-110">前端集區的移轉時 skype for Business Server 2019，SBA 必須分離從前端集區，而升級之集區。</span><span class="sxs-lookup"><span data-stu-id="e509a-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="e509a-111">商務 Server 2019 的集區移轉至 Skype 之後，SBA 可以重新相關聯的已升級的前端集區。</span><span class="sxs-lookup"><span data-stu-id="e509a-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="e509a-112">這包括刪除 SBA 從拓撲產生器的傳統拓撲並再將 SBA 新增至 Skype for Business Server 2019 拓樸。</span><span class="sxs-lookup"><span data-stu-id="e509a-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="e509a-113">隸屬於舊版 SBA 必須先將移至另一個前端集區從拓撲移除 SBA 之前的使用者。</span><span class="sxs-lookup"><span data-stu-id="e509a-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="e509a-114">SBA 新增到 Skype for Business Server 2019 拓撲後，這些使用者可以移回 sba。</span><span class="sxs-lookup"><span data-stu-id="e509a-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="e509a-115">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="e509a-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="e509a-116">將分支使用者隸屬於舊版 SBA 與另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="e509a-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="e509a-117">從舊版的拓撲，以中斷作為備份登錄器的現有前端集區中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="e509a-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="e509a-118">將 SBA 新增至 Skype for Business Server 2019 拓撲，並將此新前端集區設定為備份登錄器。</span><span class="sxs-lookup"><span data-stu-id="e509a-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="e509a-119">將分支使用者移至新的 Skype for Business Server 2019 SBA。</span><span class="sxs-lookup"><span data-stu-id="e509a-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="e509a-120">將舊版 SBA 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="e509a-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="e509a-121">開啟**拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="e509a-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="e509a-122">在左窗格中，以滑鼠右鍵按一下 [**分支站台**，，，然後按一下 [**新的分支網站**。</span><span class="sxs-lookup"><span data-stu-id="e509a-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="e509a-123">在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**] 中，，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="e509a-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="e509a-124">（選用）按一下 [**描述**] 中，，，然後輸入分支網站的有意義描述。</span><span class="sxs-lookup"><span data-stu-id="e509a-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="e509a-125">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e509a-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="e509a-126">（選用）在下的 [**定義新的分支網站**] 對話方塊中，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e509a-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="e509a-127">按一下 [**縣/市**、，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="e509a-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="e509a-128">按一下 [省/地區\*\*\*\*，然後輸入位置的省或地區的分支網站所在的名稱。</span><span class="sxs-lookup"><span data-stu-id="e509a-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="e509a-129">按一下 [**國碼/地區碼**，，，然後輸入分支網站所在國家/地區的兩位數呼叫程式碼。</span><span class="sxs-lookup"><span data-stu-id="e509a-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="e509a-130">按一下 [**下一步**，，然後，如果您在此網站使用 Survivable Branch Appliance 或 Server，請務必清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e509a-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="e509a-131">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e509a-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="e509a-132">若要建立舊版 SBA 與 Skype for Business Server 2019 前端集區的關聯：</span><span class="sxs-lookup"><span data-stu-id="e509a-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="e509a-133">展開已建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="e509a-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="e509a-134">在舊版中，以滑鼠右鍵按一下，然後按一下 [**新增]**。</span><span class="sxs-lookup"><span data-stu-id="e509a-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="e509a-135">按一下 [ **Survivable Branch Appliance**。</span><span class="sxs-lookup"><span data-stu-id="e509a-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="e509a-136">依照精靈隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="e509a-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="e509a-137">精靈項目的相關資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="e509a-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="e509a-138">Survivable Branch Appliance 僅能與監控存放區相關聯。</span><span class="sxs-lookup"><span data-stu-id="e509a-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="e509a-139">如果您未在此網站使用 Survivable Branch Appliance 或 Server，清除**開啟新的 survivable branch Appliance 精靈，當這個精靈關閉時**] 核取方塊，然後再按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="e509a-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="e509a-140">針對您想要新增至拓撲每一個分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="e509a-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

