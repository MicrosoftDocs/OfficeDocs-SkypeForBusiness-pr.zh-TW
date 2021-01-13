---
title: 管理網路頻寬原則設定檔
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
description: 使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816443"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="f41a7-103">管理商務用 Skype Server 中的網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="f41a7-104">使用本文中的程式來查看、建立、修改或刪除網路頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="f41a7-105">查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="f41a7-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="f41a7-106">頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f41a7-107">在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f41a7-108">您可以設定整體頻寬限制和工作階段限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f41a7-109">您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f41a7-110">每個頻寬原則設定檔可以與一或多個網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f41a7-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="f41a7-111">請使用下列程式來查看頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="f41a7-112">若要查看頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f41a7-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f41a7-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f41a7-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f41a7-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f41a7-115">在左導覽列中，按一下 **[網路設定]**，再按一下 **[頻寬原則]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f41a7-116">在 [ **頻寬原則** ] 頁面上，按一下您要查看的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="f41a7-117">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f41a7-118">使用 Windows PowerShell Cmdlet 來查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="f41a7-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f41a7-119">您可以使用 Windows PowerShell 和 Get-CsNetworkBandwidthPolicyProfile Cmdlet 來查看網路頻寬設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="f41a7-120">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f41a7-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="f41a7-121">若要查看網路頻寬原則設定檔資訊</span><span class="sxs-lookup"><span data-stu-id="f41a7-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="f41a7-122">若要查看所有網路頻寬原則設定檔的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="f41a7-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="f41a7-123">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f41a7-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="f41a7-124">如需詳細資訊，請參閱 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="f41a7-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="f41a7-125">建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="f41a7-126">頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f41a7-127">在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f41a7-128">您可以設定整體頻寬限制和工作階段限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f41a7-129">您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f41a7-130">每個頻寬原則設定檔可以與一或多個網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f41a7-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="f41a7-131">請使用下列程序來建立或修改頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="f41a7-132">若要建立新的頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="f41a7-133">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f41a7-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f41a7-134">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f41a7-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f41a7-135">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。</span><span class="sxs-lookup"><span data-stu-id="f41a7-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f41a7-136">在「頻寬原則」頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="f41a7-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="f41a7-p104">在 **[新增頻寬原則設定檔]** 的 **[名稱]** 欄位中輸入名稱。在所有頻寬原則設定檔中，此名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="f41a7-p105">在 **[音訊限制]** 欄位中輸入數值。此值是要配置給所有音訊連線的最大頻寬數量 (以 kbps 表示)。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="f41a7-p106">在 **[音訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別音訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 40 或更大。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="f41a7-p107">在 **[視訊限制]** 欄位中輸入數值。此值是要配置給所有視訊連線的最大頻寬數量 (以 kbps 表示)。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="f41a7-p108">在 **[視訊工作階段限制]** 欄位中輸入數值。此值是要配置給個別視訊連線的最大頻寬數量 (以 kbps 表示)。此值必須為 100 或更大。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="f41a7-149">(選用) 在 **[描述]** 欄位中輸入值，以提供更多有關此頻寬原則設定檔 (無法單獨以名稱表示) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="f41a7-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="f41a7-150">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f41a7-151">建立新的頻寬原則設定檔並不會自動強制頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="f41a7-152">您必須先讓原則設定檔與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f41a7-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="f41a7-153">若要修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f41a7-154">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f41a7-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f41a7-155">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f41a7-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f41a7-156">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。</span><span class="sxs-lookup"><span data-stu-id="f41a7-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f41a7-157">在「頻寬原則」頁面上，按一下您要修改的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="f41a7-158">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f41a7-159">在 [ **編輯頻寬原則設定檔** ] 頁面上，視需要修改欄位 (如需詳細資訊，請參閱 [建立新的頻寬原則設定檔](#to-create-a-new-bandwidth-policy-profile)) 。</span><span class="sxs-lookup"><span data-stu-id="f41a7-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="f41a7-160">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f41a7-161">當您修改頻寬原則設定檔時，將會立即更新與此頻寬原則設定檔關聯的所有網路網站的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="f41a7-162">刪除網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="f41a7-163">頻寬原則為通話許可控制 (CAC) 的一部分，用於定義某些形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f41a7-164">在商務用 Skype Server 中，只有音訊和影片形式可以獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f41a7-165">您可以設定整體頻寬限制和工作階段限制。</span><span class="sxs-lookup"><span data-stu-id="f41a7-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f41a7-166">您可以使用商務用 Skype Server 控制台建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f41a7-167">請使用下列程序來刪除網路頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="f41a7-168">刪除頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="f41a7-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f41a7-169">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f41a7-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f41a7-170">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f41a7-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f41a7-171">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **頻寬原則**]。</span><span class="sxs-lookup"><span data-stu-id="f41a7-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f41a7-172">在 **[頻寬原則]** 頁面上，按一下您要刪除的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f41a7-p111">您可以一次刪除一個以上的設定檔。若要這麼做，請按住 CTRL 鍵並同時選取多個設定檔。或者，若要選取所有設定檔，請按一下 **[編輯]** 功能表上的 **[全選]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f41a7-176">在 **[編輯]** 功能表上，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="f41a7-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="f41a7-177">您無法刪除與網站關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="f41a7-178">您必須先移除與網站的關聯，才可以刪除設定檔。</span><span class="sxs-lookup"><span data-stu-id="f41a7-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="f41a7-179">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f41a7-179">See Also</span></span>

[<span data-ttu-id="f41a7-180">管理網站的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="f41a7-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="f41a7-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f41a7-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f41a7-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f41a7-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f41a7-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f41a7-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f41a7-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f41a7-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

