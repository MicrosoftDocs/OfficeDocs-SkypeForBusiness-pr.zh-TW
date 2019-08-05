---
title: 管理網路區域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 網路區域路由定義一對網路區域之間的路由。 通話許可控制部署中的每一組網路區域都需要網路區域路由。
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188566"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="ff73e-104">在商務用 Skype Server 中管理網路區域路由</span><span class="sxs-lookup"><span data-stu-id="ff73e-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="ff73e-105">*網路區域路由*定義一對網路區域之間的路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="ff73e-106">通話許可控制部署中的每一組網路區域都需要網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="ff73e-107">這可讓部署中的每個網路區域存取每一個其他區域。</span><span class="sxs-lookup"><span data-stu-id="ff73e-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="ff73e-108">使用此 artilce 中的程式來查看、建立、修改或刪除網路區路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="ff73e-109">查看網路區域路線資訊</span><span class="sxs-lookup"><span data-stu-id="ff73e-109">View network region route information</span></span> 

<span data-ttu-id="ff73e-110">呼叫許可控制 (CAC) 配置中的每個地區都必須有一些方法, 才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="ff73e-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="ff73e-111">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制, 同時也代表物理連結, 但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="ff73e-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="ff73e-112">使用下列程式, 在商務用 Skype Server 控制台或商務用 Skype Server Management Shell 中, 查看現有的網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ff73e-113">若要在商務用 Skype Server [控制台] 中查看網路區域路線資訊</span><span class="sxs-lookup"><span data-stu-id="ff73e-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ff73e-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ff73e-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff73e-115">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff73e-116">在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區路線**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ff73e-117">在 [**地區路線**] 頁面上, 按一下您要查看的地區路線。</span><span class="sxs-lookup"><span data-stu-id="ff73e-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="ff73e-118">一次只能查看一個區域路線。</span><span class="sxs-lookup"><span data-stu-id="ff73e-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="ff73e-119">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff73e-120">使用 Windows PowerShell Cmdlet 查看網路區域路由資訊</span><span class="sxs-lookup"><span data-stu-id="ff73e-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff73e-121">您可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute Cmdlet 來查看網路區域路由資訊。</span><span class="sxs-lookup"><span data-stu-id="ff73e-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="ff73e-122">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff73e-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="ff73e-123">若要查看網路區域路線資訊</span><span class="sxs-lookup"><span data-stu-id="ff73e-123">To view network region route information</span></span>

  - <span data-ttu-id="ff73e-124">若要查看所有網路區域路由的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER 鍵:</span><span class="sxs-lookup"><span data-stu-id="ff73e-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="ff73e-125">這會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="ff73e-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="ff73e-126">如需詳細資訊, 請參閱[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ff73e-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="ff73e-127">建立或修改網路區路由</span><span class="sxs-lookup"><span data-stu-id="ff73e-127">Create or modify network region routes</span></span>

<span data-ttu-id="ff73e-128">呼叫許可控制 (CAC) 配置中的每個地區都必須有一些方法, 才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="ff73e-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="ff73e-129">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制, 同時也代表物理連結, 但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="ff73e-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="ff73e-130">您可以使用商務用 Skype Server 的 [控制台] 來設定網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="ff73e-131">從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="ff73e-132">使用本主題來建立或修改網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="ff73e-133">建立網路區域路由</span><span class="sxs-lookup"><span data-stu-id="ff73e-133">To create a network region route</span></span>

1.  <span data-ttu-id="ff73e-134">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ff73e-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff73e-135">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff73e-136">在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區路線**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ff73e-137">在 [**地區路線**] 頁面上, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="ff73e-138">在 [**新區域路由**] 中, 于 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="ff73e-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="ff73e-139">此值在您的商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ff73e-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ff73e-140">從 [**網路區域\#1** ] 下拉式清單中, 選取要由此路由連接的兩個區域中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="ff73e-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="ff73e-141">從 [**網路區域\#2** ] 下拉式清單中, 選取此路由的另一個區域。</span><span class="sxs-lookup"><span data-stu-id="ff73e-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="ff73e-142">這個區域必須與針對 [網路區\#1] 所選取的區域不同。</span><span class="sxs-lookup"><span data-stu-id="ff73e-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="ff73e-143">使用 [**網路區域連結**] 清單方塊來新增路由的區域連結。</span><span class="sxs-lookup"><span data-stu-id="ff73e-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="ff73e-144">按一下 [**新增**] 按鈕以顯示 [**地區連結**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ff73e-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="ff73e-145">按一下要新增至此路線的區域連結, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ff73e-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="ff73e-146">繼續按一下 [**新增**] 按鈕以新增更多連結, 或選取連結, 然後按一下 [**移除**] 以移除連結。</span><span class="sxs-lookup"><span data-stu-id="ff73e-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="ff73e-147">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ff73e-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="ff73e-148">修改網路區域路由</span><span class="sxs-lookup"><span data-stu-id="ff73e-148">To modify a network region route</span></span>

1.  <span data-ttu-id="ff73e-149">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ff73e-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff73e-150">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff73e-151">在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區路線**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ff73e-152">在 [**地區路線**] 頁面上, 按一下您要修改的地區路線。</span><span class="sxs-lookup"><span data-stu-id="ff73e-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="ff73e-153">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ff73e-154">在 [**編輯區域] 路由**中, 您可以修改由此路由加入的區域, 以及與路由相關聯的區域連結。</span><span class="sxs-lookup"><span data-stu-id="ff73e-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="ff73e-155">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ff73e-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="ff73e-156">刪除現有的網路區域路由</span><span class="sxs-lookup"><span data-stu-id="ff73e-156">Delete existing network region routes</span></span>

<span data-ttu-id="ff73e-157">呼叫許可控制 (CAC) 配置中的每個地區都必須有一些方法, 才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="ff73e-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="ff73e-158">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制, 同時也代表物理連結, 但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="ff73e-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="ff73e-159">您可以使用商務用 Skype Server 的 [控制台] 來設定網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="ff73e-160">從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="ff73e-161">使用本主題刪除現有的網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="ff73e-162">刪除網路區域路線</span><span class="sxs-lookup"><span data-stu-id="ff73e-162">To delete a network region route</span></span>

1.  <span data-ttu-id="ff73e-163">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ff73e-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff73e-164">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff73e-165">在左導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區路線**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="ff73e-166">在 [**地區路線**] 頁面上, 按一下您要刪除的地區路線。</span><span class="sxs-lookup"><span data-stu-id="ff73e-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ff73e-167">您可以一次刪除一個以上的區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="ff73e-168">若要這樣做, 請在按住 CTRL 鍵的同時, 按住 CTRL 並選取多個區域路由。</span><span class="sxs-lookup"><span data-stu-id="ff73e-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="ff73e-169">或者, 若要選取所有地區路線, 請按一下 [**編輯**] 功能表上的 [全**選**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ff73e-170">在 [**編輯**] 功能表上, 按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ff73e-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ff73e-171">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ff73e-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="ff73e-172">請參閱</span><span class="sxs-lookup"><span data-stu-id="ff73e-172">See Also</span></span>

[<span data-ttu-id="ff73e-173">在商務用 Skype Server 中管理網路區域</span><span class="sxs-lookup"><span data-stu-id="ff73e-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="ff73e-174">新-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ff73e-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="ff73e-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ff73e-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="ff73e-176">移除-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ff73e-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="ff73e-177">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="ff73e-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
