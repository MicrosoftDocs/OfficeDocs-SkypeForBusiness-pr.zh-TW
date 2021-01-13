---
title: 連結網路地區
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
description: '您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。 '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816463"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="14234-103">連結商務用 Skype Server 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="14234-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="14234-104">您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="14234-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="14234-105">請使用本文中的章節來查看 newtwork 區域連結資訊，或設定或刪除網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="14234-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="14234-106">查看網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="14234-106">View network region link information</span></span> 

<span data-ttu-id="14234-107">您可以透過通話許可控制 (CAC) 檢視兩個網路地區之間的連結。</span><span class="sxs-lookup"><span data-stu-id="14234-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="14234-108">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="14234-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="14234-109">您可以使用商務用 Skype Server 控制台，以查看兩個網路地區之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="14234-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="14234-110">在商務用 Skype Server 控制台中查看網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="14234-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="14234-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14234-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="14234-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="14234-113">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="14234-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="14234-114">在 [區域連結] 頁面中，按一下要檢視的區域連結。</span><span class="sxs-lookup"><span data-stu-id="14234-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="14234-115">一次只能檢視一個區域的資訊。</span><span class="sxs-lookup"><span data-stu-id="14234-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="14234-116">從 [編輯] 功能表中，選取 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="14234-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="14234-117">使用 Windows PowerShell Cmdlet 來查看網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="14234-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="14234-118">您可以使用 Windows PowerShell 和 **Get-CsNetworkRegionLink** Cmdlet 來查看網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="14234-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="14234-119">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="14234-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="14234-120">檢視網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="14234-120">To view network region link information</span></span>

  - <span data-ttu-id="14234-121">若要查看所有網路地區連結的資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="14234-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="14234-122">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="14234-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="14234-123">如需詳細資訊，請參閱 [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="14234-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="14234-124">設定網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-124">Configure network region links</span></span> 

<span data-ttu-id="14234-125">您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="14234-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="14234-126">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="14234-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="14234-127">您可以使用商務用 Skype Server 控制台來定義兩個網路地區之間的連結，並設定這些地區之間音訊和影片連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="14234-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="14234-128">建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-128">To create a network region link</span></span>

1.  <span data-ttu-id="14234-129">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="14234-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14234-130">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="14234-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="14234-131">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="14234-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="14234-132">在 [ **地區連結** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="14234-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="14234-133">在 [ **新增地區連結**] 的 [ **名稱** ] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="14234-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="14234-134">此值在商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="14234-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="14234-135">從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個要連結的地區之一。</span><span class="sxs-lookup"><span data-stu-id="14234-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="14234-136">從 [ **網路地區 \# 2** ] 下拉式清單中，選取要連結的其他地區。</span><span class="sxs-lookup"><span data-stu-id="14234-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="14234-137">此區域必須與為網路地區1所選取的區域不同 \# 。</span><span class="sxs-lookup"><span data-stu-id="14234-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="14234-138"> (選用) 若您想要在這些地區之間的音訊或視頻通話上進行頻寬限制，請從 [ **頻寬原則** ] 下拉式清單中選取頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="14234-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="14234-139">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="14234-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="14234-140">若要修改網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-140">To modify a network region link</span></span>

1.  <span data-ttu-id="14234-141">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="14234-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14234-142">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="14234-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="14234-143">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="14234-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="14234-144">在 [ **地區連結** ] 頁面上，按一下您要修改的地區連結。</span><span class="sxs-lookup"><span data-stu-id="14234-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="14234-145">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="14234-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="14234-146">在 [ **編輯地區連結**] 中，您可以修改連結的區域或此連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="14234-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="14234-147">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="14234-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="14234-148">刪除網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-148">Delete network region links</span></span>

<span data-ttu-id="14234-149">您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="14234-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="14234-150">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="14234-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="14234-151">您可以使用商務用 Skype Server 控制台刪除兩個網路地區之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="14234-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="14234-152">刪除網路地區連結</span><span class="sxs-lookup"><span data-stu-id="14234-152">To delete a network region link</span></span>

1.  <span data-ttu-id="14234-153">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="14234-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14234-154">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="14234-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="14234-155">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="14234-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="14234-156">在 [地區連結] 頁面中，按一下要刪除的地區連結。</span><span class="sxs-lookup"><span data-stu-id="14234-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="14234-p107">您可以一次刪除一個以上的地區連結。若要一次刪除一個以上的地區連結，請按住 CTRL 鍵並同時選取多個地區連結。若要選取多個地區，您也可以按一下 [編輯]<STRONG></STRONG> 功能表中的 [全選]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="14234-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="14234-160">選取 [編輯] 功能表中的 [刪除]。</span><span class="sxs-lookup"><span data-stu-id="14234-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="14234-161">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="14234-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="14234-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="14234-162">See Also</span></span>

[<span data-ttu-id="14234-163">新 CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="14234-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="14234-164">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="14234-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="14234-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="14234-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="14234-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="14234-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
