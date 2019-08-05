---
title: 連結網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '您可以設定兩個網路區域之間的連結, 作為通話許可控制 (CAC) 的一部分。 '
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188584"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="4c0c0-103">在商務用 Skype Server 中連結網路區域</span><span class="sxs-lookup"><span data-stu-id="4c0c0-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="4c0c0-104">您可以設定兩個網路區域之間的連結, 作為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c0c0-105">使用本文中的章節來查看 newtwork 區域連結資訊, 或設定或刪除 netwrok 區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="4c0c0-106">[查看網路區域] 連結資訊</span><span class="sxs-lookup"><span data-stu-id="4c0c0-106">View network region link information</span></span> 

<span data-ttu-id="4c0c0-107">您可以在 [呼叫許可控制] (CAC) 中, 查看兩個網路區域之間的連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c0c0-108">網路中的區域是透過物理廣域網路 (WAN) 連線來連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c0c0-109">您可以使用商務用 Skype Server [控制台] 來查看兩個網路區域之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4c0c0-110">若要在商務用 Skype Server [控制台] 中查看網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4c0c0-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c0c0-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c0c0-113">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c0c0-114">在 [**地區連結**] 頁面上, 按一下您要查看的區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="4c0c0-115">您一次只能查看一個區域連結的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="4c0c0-116">從 [**編輯**] 功能表中, 選取 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c0c0-117">使用 Windows PowerShell Cmdlet 來查看網路區域連結資訊</span><span class="sxs-lookup"><span data-stu-id="4c0c0-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4c0c0-118">您可以使用 Windows PowerShell 和**CsNetworkRegionLink** Cmdlet 來查看網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="4c0c0-119">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="4c0c0-120">若要查看網路區域連結資訊</span><span class="sxs-lookup"><span data-stu-id="4c0c0-120">To view network region link information</span></span>

  - <span data-ttu-id="4c0c0-121">若要查看所有網路區域連結的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4c0c0-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="4c0c0-122">這個命令會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="4c0c0-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="4c0c0-123">如需詳細資訊, 請參閱[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="4c0c0-124">設定網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-124">Configure network region links</span></span> 

<span data-ttu-id="4c0c0-125">您可以設定兩個網路區域之間的連結, 作為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c0c0-126">網路中的區域是透過物理廣域網路 (WAN) 連線來連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c0c0-127">您可以使用商務用 Skype Server 的 [控制台] 來定義兩個網路區域之間的連結, 並設定這些區域之間音訊與視頻連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="4c0c0-128">建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-128">To create a network region link</span></span>

1.  <span data-ttu-id="4c0c0-129">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c0c0-130">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c0c0-131">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c0c0-132">在 [**地區連結**] 頁面上, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="4c0c0-133">在 [**新區域] 連結**的 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c0c0-134">此值在您的商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4c0c0-135">從 [**網路區域\#1** ] 下拉式清單中, 選取兩個要連結的區域之一。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="4c0c0-136">從 [**網路區域\#2** ] 下拉式清單中, 選取要連結的其他區域。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="4c0c0-137">這個區域必須與針對 [網路區\#1] 所選取的區域不同。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="4c0c0-138">可選如果您想要將頻寬限制放在這些區域之間的音訊或視頻通話中, 請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="4c0c0-139">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="4c0c0-140">修改網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-140">To modify a network region link</span></span>

1.  <span data-ttu-id="4c0c0-141">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c0c0-142">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c0c0-143">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c0c0-144">在 [**地區連結**] 頁面上, 按一下您要修改的區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="4c0c0-145">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4c0c0-146">在 [**編輯區域] 連結**中, 您可以修改連結的區域或此連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="4c0c0-147">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="4c0c0-148">刪除網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-148">Delete network region links</span></span>

<span data-ttu-id="4c0c0-149">您可以設定兩個網路區域之間的連結, 作為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4c0c0-150">網路中的區域是透過物理廣域網路 (WAN) 連線來連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4c0c0-151">您可以使用商務用 Skype Server [控制台] 來刪除兩個網路區域之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="4c0c0-152">刪除網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c0c0-152">To delete a network region link</span></span>

1.  <span data-ttu-id="4c0c0-153">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c0c0-154">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4c0c0-155">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4c0c0-156">在 [**地區連結**] 頁面上, 按一下您要刪除的區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4c0c0-157">您可以一次刪除一個以上的區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="4c0c0-158">若要這樣做, 請在按住 CTRL 鍵的同時, 按住 CTRL 並選取多個區域連結。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="4c0c0-159">或者, 若要選取所有區域連結, 請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="4c0c0-160">從 [**編輯**] 功能表中, 選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="4c0c0-161">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c0c0-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="4c0c0-162">請參閱</span><span class="sxs-lookup"><span data-stu-id="4c0c0-162">See Also</span></span>

[<span data-ttu-id="4c0c0-163">新-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c0c0-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="4c0c0-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c0c0-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="4c0c0-165">移除-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c0c0-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="4c0c0-166">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c0c0-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
