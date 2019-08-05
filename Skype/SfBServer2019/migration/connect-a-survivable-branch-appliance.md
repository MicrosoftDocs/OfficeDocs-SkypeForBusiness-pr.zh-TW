---
title: 連接 Survivable 分支裝置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '每個 Survivable 分支裝置 (SBA) 都與一個前端池相關聯, 可充當 SBA 的備份註冊機構。 當您將前端池移至商務用 Skype Server 2019 時, 當池已升級至商務用 Skype Server 2019 之後, 就必須從 SBA 中解除連線, SBA 才能與升級的前 E 重新關聯nd pool。 這涉及從拓撲產生器中的舊版拓撲刪除 SBA, 然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 必須先將駐留在舊版 SBA 的使用者移到另一個前端池, 然後才能從拓撲結構中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後, 這些使用者就可以移回 SBA。 下列步驟摘要如下所示:'
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187330"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="219da-108">連接 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="219da-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="219da-109">每個 Survivable 分支裝置 (SBA) 都與一個作為 SBA 備份註冊機構的前端池相關聯。</span><span class="sxs-lookup"><span data-stu-id="219da-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="219da-110">當頂層池遷移到商務用 Skype Server 2019 時, 必須在池升級時解除與前端池中的 SBA。</span><span class="sxs-lookup"><span data-stu-id="219da-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="219da-111">在將池遷移到商務用 Skype Server 2019 之後, SBA 可以與已升級的前端池重新關聯。</span><span class="sxs-lookup"><span data-stu-id="219da-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="219da-112">這涉及從拓撲產生器中的舊版拓撲刪除 SBA, 然後將 SBA 新增至商務用 Skype Server 2019 拓撲。</span><span class="sxs-lookup"><span data-stu-id="219da-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="219da-113">必須先將駐留在舊版 SBA 的使用者移到另一個前端池, 然後才能從拓撲結構中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="219da-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="219da-114">將 SBA 新增至商務用 Skype Server 2019 拓撲之後, 這些使用者就可以移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="219da-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="219da-115">下列步驟摘要如下所示:</span><span class="sxs-lookup"><span data-stu-id="219da-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="219da-116">將駐留在舊版 SBA 的分支使用者移至另一個前端池。</span><span class="sxs-lookup"><span data-stu-id="219da-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="219da-117">從舊版拓撲中移除 SBA, 將現有的前端池與備份註冊機構中斷連線。</span><span class="sxs-lookup"><span data-stu-id="219da-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="219da-118">在商務用 Skype Server 2019 拓撲中新增 SBA, 並將這個新的 [前端] 池設定為備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="219da-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="219da-119">將分支使用者移至新的商務用 Skype Server 2019 SBA。</span><span class="sxs-lookup"><span data-stu-id="219da-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="219da-120">將舊版 SBA 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="219da-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="219da-121">開啟**拓撲**建立器。</span><span class="sxs-lookup"><span data-stu-id="219da-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="219da-122">在左窗格中, 以滑鼠右鍵按一下 [**分支網站**], 然後按一下 [**新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="219da-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="219da-123">在 [**定義新分支網站**] 對話方塊中, 按一下 [**名稱**], 然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="219da-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="219da-124">可選按一下 [**描述**], 然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="219da-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="219da-125">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="219da-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="219da-126">可選在 [下一步**定義分支網站**] 對話方塊中, 執行下列任何一項操作:</span><span class="sxs-lookup"><span data-stu-id="219da-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="219da-127">按一下 [**城市**], 然後輸入分支網站所在城市的名稱。</span><span class="sxs-lookup"><span data-stu-id="219da-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="219da-128">按一下 [**狀態/地區**], 然後輸入分支網站所在的狀態或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="219da-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="219da-129">按一下 [**國家/地區碼**], 然後輸入分支網站所在國家/地區的兩位數電話號碼。</span><span class="sxs-lookup"><span data-stu-id="219da-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="219da-130">按一下 **[下一步]**, 然後, 如果您是在此網站使用 Survivable 分支裝置或伺服器, 請務必清除 [**當此嚮導關閉時, 開啟新的 Survivable 嚮導]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="219da-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="219da-131">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="219da-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="219da-132">若要將舊版 SBA 與商務用 Skype Server 2019 (前端端池) 關聯:</span><span class="sxs-lookup"><span data-stu-id="219da-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="219da-133">展開已建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="219da-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="219da-134">以滑鼠右鍵按一下舊版版本, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="219da-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="219da-135">按一下 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="219da-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="219da-136">依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="219da-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="219da-137">如需有關嚮導專案的資訊, 請參閱</span><span class="sxs-lookup"><span data-stu-id="219da-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="219da-138">Survivable 分支裝置只能與監視存放區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="219da-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="219da-139">如果您不是在此網站使用 Survivable 分支裝置或伺服器, 請清除 [在**關閉此嚮導時開啟新的 Survivable 嚮導]** 核取方塊, 然後按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="219da-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="219da-140">針對您要新增到拓撲結構中的每個分支網站, 重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="219da-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

