---
title: 管理網路地區路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 網路地區路由會定義一對網路地區之間的路由。 在您的通話許可控制部署中的每一對網路地區都需要網路地區路由。
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816433"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="c91a0-104">管理商務用 Skype Server 中的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="c91a0-105">*網路地區路由* 會定義一對網路地區之間的路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="c91a0-106">在您的通話許可控制部署中的每一對網路地區都需要網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="c91a0-107">這可讓部署中的每一個網路地區都可以存取所有其他的地區。</span><span class="sxs-lookup"><span data-stu-id="c91a0-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="c91a0-108">使用此 artilce 中的程式來查看、建立、修改或刪除網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="c91a0-109">查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c91a0-109">View network region route information</span></span> 

<span data-ttu-id="c91a0-110">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="c91a0-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c91a0-111">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="c91a0-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c91a0-112">使用下列程式可在商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面中，查看現有的網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c91a0-113">在商務用 Skype Server 控制台中查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c91a0-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c91a0-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c91a0-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c91a0-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c91a0-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c91a0-116">在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="c91a0-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c91a0-117">在 [ **地區路由** ] 頁面上，按一下您要查看的地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="c91a0-118">您一次只能查看一個區域路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="c91a0-119">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c91a0-120">使用 Windows PowerShell Cmdlet 來查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c91a0-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c91a0-121">您可以使用 Windows PowerShell 和 Get-CsNetworkInterRegionRoute Cmdlet 來查看網路地區路由資訊。</span><span class="sxs-lookup"><span data-stu-id="c91a0-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="c91a0-122">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c91a0-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="c91a0-123">若要查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c91a0-123">To view network region route information</span></span>

  - <span data-ttu-id="c91a0-124">若要查看所有網路地區路由的資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="c91a0-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="c91a0-125">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="c91a0-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="c91a0-126">如需詳細資訊，請參閱 [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c91a0-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="c91a0-127">建立或修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-127">Create or modify network region routes</span></span>

<span data-ttu-id="c91a0-128">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="c91a0-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c91a0-129">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="c91a0-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c91a0-130">您可以使用商務用 Skype Server 控制台來設定網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="c91a0-131">在商務用 Skype Server 控制台中，您可以建立、修改或刪除網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="c91a0-132">若要建立或修改網路地區路由，請利用本節主題。</span><span class="sxs-lookup"><span data-stu-id="c91a0-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="c91a0-133">若要建立網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-133">To create a network region route</span></span>

1.  <span data-ttu-id="c91a0-134">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c91a0-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c91a0-135">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c91a0-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c91a0-136">在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="c91a0-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c91a0-137">在 **[地區路由]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="c91a0-138">在 **[新的地區路由]** 的 **[名稱]** 欄位中，輸入一個值。</span><span class="sxs-lookup"><span data-stu-id="c91a0-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="c91a0-139">此值在商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c91a0-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="c91a0-140">從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個區域中的其中一個要透過此路由來連線。</span><span class="sxs-lookup"><span data-stu-id="c91a0-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="c91a0-141">從 [ **網路地區 \# 2** ] 下拉式清單中，選取此路由的其他地區。</span><span class="sxs-lookup"><span data-stu-id="c91a0-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="c91a0-142">此區域必須與為網路地區1所選取的區域不同 \# 。</span><span class="sxs-lookup"><span data-stu-id="c91a0-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="c91a0-p107">使用 **[網路地區連結]** 清單方塊，將地區連結新增至路由。按一下 **[新增]** 按鈕以顯示 **[地區連結]** 頁面。按一下要新增至此路由的地區連結，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="c91a0-146">若要新增更多連結，請繼續按 **[新增]** 按鈕；若要移除連結，請選取連結，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="c91a0-147">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="c91a0-148">若要修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-148">To modify a network region route</span></span>

1.  <span data-ttu-id="c91a0-149">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c91a0-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c91a0-150">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c91a0-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c91a0-151">在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="c91a0-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c91a0-152">在 **[地區路由]** 頁面上，按一下您要修改的地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="c91a0-153">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c91a0-154">在 **[編輯地區路由]** 中，您可以修改此路由所聯結的地區，以及與路由相關聯的地區連結。</span><span class="sxs-lookup"><span data-stu-id="c91a0-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="c91a0-155">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="c91a0-156">刪除現有的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-156">Delete existing network region routes</span></span>

<span data-ttu-id="c91a0-157">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="c91a0-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c91a0-158">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="c91a0-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c91a0-159">您可以使用商務用 Skype Server 控制台來設定網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="c91a0-160">在商務用 Skype Server 控制台中，您可以建立、修改或刪除網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="c91a0-161">若要刪除現有的網路地區路由，請利用本主題。</span><span class="sxs-lookup"><span data-stu-id="c91a0-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="c91a0-162">刪除網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c91a0-162">To delete a network region route</span></span>

1.  <span data-ttu-id="c91a0-163">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c91a0-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c91a0-164">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c91a0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c91a0-165">在左導覽列中，依序按一下 [ **網路** 設定] 和 [ **地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="c91a0-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c91a0-166">在 **[地區路由]** 頁面上，按一下您要刪除的地區路由。</span><span class="sxs-lookup"><span data-stu-id="c91a0-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c91a0-p109">您可以同時刪除多個地區路由。如果要執行這項作業，請按住 CTRL 鍵，然後選取多個地區路由。或者，若要選取所有地區路由，請按一下 **[編輯]** 功能表上的 **[全選]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="c91a0-170">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="c91a0-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c91a0-171">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c91a0-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="c91a0-172">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c91a0-172">See Also</span></span>

[<span data-ttu-id="c91a0-173">管理商務用 Skype Server 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="c91a0-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="c91a0-174">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c91a0-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="c91a0-175">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c91a0-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="c91a0-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c91a0-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="c91a0-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c91a0-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
