---
title: 在商務用 Skype Server 中建立網路 interregional 路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 在商務用 Skype Server 中建立或修改網路 interregional 路由，以供 Enterprise Voice 通話許可控制使用。
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093121"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="ce189-103">在商務用 Skype Server 中建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="ce189-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="ce189-104">在商務用 Skype Server 中建立或修改網路 interregional 路由，以供 Enterprise Voice 通話許可控制使用。</span><span class="sxs-lookup"><span data-stu-id="ce189-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ce189-105">網路 interregional 路由會定義一對網路地區之間的路由。</span><span class="sxs-lookup"><span data-stu-id="ce189-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="ce189-106">通話許可控制部署中的每一對網路地區都需要網路 interregional 路由。</span><span class="sxs-lookup"><span data-stu-id="ce189-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="ce189-107">這可讓部署中的每一個網路地區都可以存取所有其他的地區。</span><span class="sxs-lookup"><span data-stu-id="ce189-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="ce189-108">雖然地區連結設定了區域間連線的頻寬限制，但 interregional 路由會決定連線到另一個地區的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="ce189-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="ce189-109">在範例拓撲中，必須為三個地區成對定義網路 interregional 路由：北 America/EMEA、EMEA/APAC 及北 America/APAC。</span><span class="sxs-lookup"><span data-stu-id="ce189-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ce189-110">使用商務用 Skype Server 管理命令介面建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="ce189-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ce189-111">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ce189-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ce189-112">執行 **New-CsNetworkInterRegionRoute** Cmdlet 以定義所需的路由。</span><span class="sxs-lookup"><span data-stu-id="ce189-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="ce189-113">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="ce189-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="ce189-114">北美 America/APAC 網路 interregional 路由需要兩個網路地區連結，因為兩者之間沒有任何直接的網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="ce189-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ce189-115">使用商務用 Skype Server 控制台建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="ce189-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ce189-116">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ce189-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ce189-117">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ce189-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ce189-118">按一下 **[地區路由]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce189-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="ce189-119">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ce189-119">Click **New**.</span></span>
    
5. <span data-ttu-id="ce189-120">在 [ **新增地區路由** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路 interregional 路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="ce189-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="ce189-121">按一下 **[網路地區 #1]**，再從您要路由轉送至網路地區 #2 的清單中，按一下網路地區。</span><span class="sxs-lookup"><span data-stu-id="ce189-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="ce189-122">按一下 **[網路地區 #2]**，再從您要路由轉送至網路地區 #1 的清單中，按一下網路地區。</span><span class="sxs-lookup"><span data-stu-id="ce189-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="ce189-123">按一下 [**網路地區連結**] 欄位旁的 [**新增**]，然後新增網路地區連結，將用於網路 interregional 路由。</span><span class="sxs-lookup"><span data-stu-id="ce189-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce189-124">如果您即將為尚未擁有直接網路地區連結的兩個網路地區建立路由，請新增所有必要的連結以便完成該路由。</span><span class="sxs-lookup"><span data-stu-id="ce189-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="ce189-125">例如，北 America/APAC 網路 interregional 路由需要兩個網路地區連結，因為兩者之間沒有任何直接的網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="ce189-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="ce189-126">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ce189-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="ce189-127">若要完成建立拓撲的網路 interregional 路由，請使用其他網路 interregional 路由的設定重複步驟4到9。</span><span class="sxs-lookup"><span data-stu-id="ce189-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ce189-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce189-128">See also</span></span>

[<span data-ttu-id="ce189-129">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ce189-129">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ce189-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ce189-130">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ce189-131">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ce189-131">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="ce189-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ce189-132">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)