---
title: 管理網路頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817502"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="e23ef-103">管理商務用 Skype Server 中的網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="e23ef-104">使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="e23ef-105">查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="e23ef-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="e23ef-106">在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="e23ef-107">在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="e23ef-108">您可以設定整體頻寬限制及會話限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="e23ef-109">您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="e23ef-110">每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e23ef-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="e23ef-111">使用下列程式來查看頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="e23ef-112">若要查看頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="e23ef-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e23ef-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e23ef-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e23ef-115">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="e23ef-116">在 [**頻寬原則**] 頁面上，按一下您要查看的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="e23ef-117">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e23ef-118">使用 Windows PowerShell Cmdlet 查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="e23ef-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e23ef-119">您可以使用 Windows PowerShell 和 CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="e23ef-120">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e23ef-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="e23ef-121">若要查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="e23ef-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="e23ef-122">若要查看所有網路頻寬策略設定檔的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="e23ef-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="e23ef-123">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="e23ef-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="e23ef-124">如需詳細資訊，請參閱[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="e23ef-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="e23ef-125">建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="e23ef-126">在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="e23ef-127">在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="e23ef-128">您可以設定整體頻寬限制及會話限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="e23ef-129">您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="e23ef-130">每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e23ef-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="e23ef-131">使用下列程式來建立或修改頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="e23ef-132">建立新的頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="e23ef-133">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e23ef-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e23ef-134">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e23ef-135">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="e23ef-136">在 [**頻寬原則**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="e23ef-137">在**新的頻寬原則設定檔**中，在 [**名稱**] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="e23ef-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="e23ef-138">這個名稱在所有頻寬原則設定檔中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e23ef-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="e23ef-139">在 [**音訊限制**] 欄位中，輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="e23ef-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="e23ef-140">此值為所有音訊連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="e23ef-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="e23ef-141">在 [**音訊會話限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="e23ef-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="e23ef-142">此值為個別音訊連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="e23ef-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="e23ef-143">此值必須是40或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e23ef-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="e23ef-144">在 [**影片限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="e23ef-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="e23ef-145">此值為所有視頻連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="e23ef-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="e23ef-146">在 [**視頻會話限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="e23ef-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="e23ef-147">此值為個別視頻連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="e23ef-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="e23ef-148">此值必須是100或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e23ef-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="e23ef-149">可選在**描述**欄位中輸入一個值，以提供此頻寬原則設定檔無法單獨表示的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e23ef-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="e23ef-150">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e23ef-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e23ef-151">建立新的頻寬原則設定檔並不會自動強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="e23ef-152">您必須先將原則設定檔與網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e23ef-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="e23ef-153">修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="e23ef-154">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e23ef-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e23ef-155">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e23ef-156">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="e23ef-157">在 [**頻寬原則**] 頁面上，按一下您要修改的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="e23ef-158">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e23ef-159">在 [**編輯頻寬策略設定檔**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱[建立新的頻寬原則設定檔](#to-create-a-new-bandwidth-policy-profile)）。</span><span class="sxs-lookup"><span data-stu-id="e23ef-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="e23ef-160">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e23ef-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e23ef-161">當您修改頻寬原則設定檔時，它會立即更新與此頻寬原則設定檔相關聯之所有網路網站的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="e23ef-162">刪除網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="e23ef-163">在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="e23ef-164">在商務用 Skype Server 中，只有音訊和視頻形式可以指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="e23ef-165">您可以設定整體頻寬限制及會話限制。</span><span class="sxs-lookup"><span data-stu-id="e23ef-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="e23ef-166">您可以使用商務用 Skype Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="e23ef-167">使用下列程式刪除網路頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="e23ef-168">刪除頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="e23ef-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="e23ef-169">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e23ef-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e23ef-170">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e23ef-171">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="e23ef-172">在 [**頻寬原則**] 頁面上，按一下您要刪除的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="e23ef-173">您可以一次刪除一個以上的設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="e23ef-174">若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="e23ef-175">或者，若要選取所有設定檔，請按一下 [**編輯**] 功能表上的 [全**選**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="e23ef-176">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e23ef-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="e23ef-177">您無法刪除與網路網站相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="e23ef-178">您必須先移除與網路網站的關聯，然後才能刪除設定檔。</span><span class="sxs-lookup"><span data-stu-id="e23ef-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e23ef-179">請參閱</span><span class="sxs-lookup"><span data-stu-id="e23ef-179">See Also</span></span>

[<span data-ttu-id="e23ef-180">管理網站的呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="e23ef-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="e23ef-181">新-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e23ef-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="e23ef-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e23ef-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="e23ef-183">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e23ef-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="e23ef-184">移除-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="e23ef-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

