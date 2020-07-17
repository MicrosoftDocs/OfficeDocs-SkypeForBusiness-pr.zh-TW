---
title: 連線 Survivable Branch Appliance
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
description: 每個 Survivable Branch 裝置（SBA）都與一個前端集區相關聯，此集區充當 SBA 的備份註冊機。 當前端集區遷移至商務用 Skype Server 2019 時，SBA 必須在集區升級時解除與前端集區的關聯，一旦集區遷移至商務用 Skype Server 2019 後，SBA 就可以與升級的前端集區重新建立關聯。 這包括在拓撲產生器中從舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。 位於舊版 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。 將 SBA 新增至商務用 Skype Server 2019 拓撲之後，就可以將這些使用者移回 SBA。 這些步驟的摘要如下：
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751545"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="80dbb-108">連線 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="80dbb-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="80dbb-109">每個 Survivable Branch 裝置（SBA）都與一部前端集區相關聯，以充當 SBA 的備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="80dbb-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="80dbb-110">當前端集區遷移至商務用 Skype Server 2019 時，當集區升級時，SBA 必須與前端集區解除關聯。</span><span class="sxs-lookup"><span data-stu-id="80dbb-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="80dbb-111">將集區遷移至商務用 Skype Server 2019 之後，SBA 可以與已升級的前端集區重新產生關聯。</span><span class="sxs-lookup"><span data-stu-id="80dbb-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="80dbb-112">這包括在拓撲產生器中從舊版拓撲刪除 SBA，然後將 SBA 新增至商務用 Skype Server 2019 拓撲。</span><span class="sxs-lookup"><span data-stu-id="80dbb-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="80dbb-113">位於舊版 SBA 的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。</span><span class="sxs-lookup"><span data-stu-id="80dbb-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="80dbb-114">將 SBA 新增至商務用 Skype Server 2019 拓撲之後，可以將這些使用者移回 SBA。</span><span class="sxs-lookup"><span data-stu-id="80dbb-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="80dbb-115">這些步驟的摘要如下：</span><span class="sxs-lookup"><span data-stu-id="80dbb-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="80dbb-116">將駐留在舊版 SBA 的分支使用者移至另一個前端集區。</span><span class="sxs-lookup"><span data-stu-id="80dbb-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="80dbb-117">從舊版拓撲中移除 SBA，以中斷現有前端集區的備份註冊機的連線。</span><span class="sxs-lookup"><span data-stu-id="80dbb-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="80dbb-118">將 SBA 新增至商務用 Skype Server 2019 拓撲，並將這個新的前端集區設定為備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="80dbb-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="80dbb-119">將分支使用者移至新的商務用 Skype Server 2019 SBA。</span><span class="sxs-lookup"><span data-stu-id="80dbb-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="80dbb-120">將舊版 SBA 分支網站新增至您的拓撲</span><span class="sxs-lookup"><span data-stu-id="80dbb-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="80dbb-121">開啟**拓撲**產生器。</span><span class="sxs-lookup"><span data-stu-id="80dbb-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="80dbb-122">在左窗格中，以滑鼠右鍵按一下 [**分支網站**]，然後按一下 [**新增分支網站**]。</span><span class="sxs-lookup"><span data-stu-id="80dbb-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="80dbb-123">在 [**定義新的分支網站**] 對話方塊中，按一下 [**名稱**]，然後輸入分支網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="80dbb-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="80dbb-124">選按一下 [**描述**]，然後為分支網站輸入有意義的描述。</span><span class="sxs-lookup"><span data-stu-id="80dbb-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="80dbb-125">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80dbb-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="80dbb-126">選在下一個 [**定義新的分支網站**] 對話方塊中，執行下列任一項：</span><span class="sxs-lookup"><span data-stu-id="80dbb-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="80dbb-127">按一下 [**城市**]，然後輸入分支網站所在位置的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="80dbb-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="80dbb-128">按一下 [**省/地區**]，然後輸入分支網站所在位置的省或地區名稱。</span><span class="sxs-lookup"><span data-stu-id="80dbb-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="80dbb-129">按一下 [**國家/地區碼**]，然後輸入分支網站所在國家/地區的兩位數呼叫碼。</span><span class="sxs-lookup"><span data-stu-id="80dbb-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="80dbb-130">按 **[下一步]**，然後在此網站使用 Survivable 分支裝置或伺服器時，請務必清除 [**當此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="80dbb-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="80dbb-131">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80dbb-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="80dbb-132">若要將舊版 SBA 與商務用 Skype Server 2019 前端集區產生關聯：</span><span class="sxs-lookup"><span data-stu-id="80dbb-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="80dbb-133">展開已經建立的分支網站。</span><span class="sxs-lookup"><span data-stu-id="80dbb-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="80dbb-134">以滑鼠右鍵按一下 [舊版版本]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="80dbb-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="80dbb-135">按一下 [ **Survivable 分支裝置**]。</span><span class="sxs-lookup"><span data-stu-id="80dbb-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="80dbb-136">依照嚮導中開啟的指示進行。</span><span class="sxs-lookup"><span data-stu-id="80dbb-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="80dbb-137">如需嚮導專案的詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="80dbb-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="80dbb-138">Survivable 分支裝置只可與監控存放區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="80dbb-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="80dbb-139">如果您未使用此網站的 Survivable 分支裝置或伺服器，請清除 [在**此嚮導關閉時開啟新的 Survivable 嚮導]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="80dbb-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="80dbb-140">針對您要新增至拓撲的每一個分支網站重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="80dbb-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

