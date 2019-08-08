---
title: 在商務用 Skype Server 中建立網路 interregional 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 在商務用 Skype Server 中建立或修改企業語音通話許可控制所使用的網路 interregional 路由。
ms.openlocfilehash: 6bf455236dc825023cc3c8ce94ee329a464fdde4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233725"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="cee65-103">在商務用 Skype Server 中建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="cee65-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="cee65-104">在商務用 Skype Server 中建立或修改企業語音通話許可控制所使用的網路 interregional 路由。</span><span class="sxs-lookup"><span data-stu-id="cee65-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="cee65-105">網路 interregional 路由定義一對網路區域之間的路由。</span><span class="sxs-lookup"><span data-stu-id="cee65-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="cee65-106">通話許可控制部署中的每一組網路區域都需要有網路 interregional 路由。</span><span class="sxs-lookup"><span data-stu-id="cee65-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="cee65-107">這可讓部署中的每個網路區域存取每一個其他區域。</span><span class="sxs-lookup"><span data-stu-id="cee65-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="cee65-108">雖然區域連結會針對區域之間的連線設定頻寬限制, 但 interregional 路由決定了連線將從一個區域傳遞到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="cee65-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="cee65-109">在範例拓朴中, 您必須為三個地區對中的每一組定義網路 interregional 路由: 北美/EMEA、EMEA/APAC, 以及北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="cee65-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="cee65-110">使用商務用 Skype Server Management Shell 建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="cee65-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="cee65-111">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="cee65-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="cee65-112">執行**新的 CsNetworkInterRegionRoute** Cmdlet, 以定義所需的路由。</span><span class="sxs-lookup"><span data-stu-id="cee65-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="cee65-113">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="cee65-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="cee65-114">北美/APAC 網路 interregional 路由需要兩個網路區域連結, 因為它們之間沒有直接的網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="cee65-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="cee65-115">使用商務用 Skype Server [控制台] 建立網路 interregional 路由</span><span class="sxs-lookup"><span data-stu-id="cee65-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="cee65-116">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="cee65-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="cee65-117">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="cee65-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="cee65-118">按一下 [**地區路線**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="cee65-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="cee65-119">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="cee65-119">Click **New**.</span></span>
    
5. <span data-ttu-id="cee65-120">在 [**新增地區路線**] 頁面上, 按一下 [**名稱**], 然後輸入網路 interregional 路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="cee65-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="cee65-121">按一下 [**網路區域 #1**], 然後按一下清單中您要路由至 [網路區域] 的網路區域 #2。</span><span class="sxs-lookup"><span data-stu-id="cee65-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="cee65-122">按一下 [**網路區域 #2**], 然後按一下清單中您要路由至 [網路區域] 的網路區域 #1。</span><span class="sxs-lookup"><span data-stu-id="cee65-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="cee65-123">按一下 [**網路區域連結**] 欄位旁的 [**新增**], 然後新增將在網路 interregional 路由中使用的 [網路區域] 連結。</span><span class="sxs-lookup"><span data-stu-id="cee65-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cee65-124">如果您要為兩個網路區域建立路線, 而這些區域之間沒有直接的網路區域連結, 您必須新增所有必要的連結, 才能完成路線。</span><span class="sxs-lookup"><span data-stu-id="cee65-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="cee65-125">例如, 北美/APAC 網路 interregional 路由需要兩個網路區域連結, 因為它們之間沒有直接的網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="cee65-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="cee65-126">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cee65-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="cee65-127">若要為您的拓撲完成建立網路 interregional 路由, 請重複步驟4到 9, 並設定其他網路 interregional 路由。</span><span class="sxs-lookup"><span data-stu-id="cee65-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cee65-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cee65-128">See also</span></span>

[<span data-ttu-id="cee65-129">新-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="cee65-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="cee65-130">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="cee65-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="cee65-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="cee65-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="cee65-132">移除-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="cee65-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
