---
title: 管理網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Network region * 是網路中樞或 backbones, 用於設定通話許可控制、E9-1 及媒體旁路。
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188563"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="85124-103">在商務用 Skype Server 中管理網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="85124-104">*網路區域*是網路中樞或 backbones, 用於設定通話許可控制、E9-1 及媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="85124-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="85124-105">使用下列程式來查看、建立或修改網路區。</span><span class="sxs-lookup"><span data-stu-id="85124-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="85124-106">例如, 如果您已為單一語音功能建立網路區域, 就不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="85124-107">不過, 您可能需要修改現有的網路區域定義, 才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="85124-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="85124-108">例如, 如果您已建立 E9 的網路區域 (不需要關聯的中央網站), 而您想要部署 [呼叫許可控制], 您必須修改網路區域定義, 以指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="85124-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="85124-109">使用本文中的程式來查看網路區域資訊, 或建立、修改或刪除網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="85124-110">查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="85124-110">View network region information</span></span> 


<span data-ttu-id="85124-111">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="85124-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="85124-112">每個網路區域都必須與一個中央網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="85124-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="85124-113">中央網站是在其上執行呼叫許可控制 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="85124-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="85124-114">您可以使用商務用 Skype Server 的 [控制台] 來查看網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="85124-115">網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。</span><span class="sxs-lookup"><span data-stu-id="85124-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="85124-116">您可以使用本主題來查看現有的網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="85124-117">使用商務用 Skype Server 控制台查看網路區域的相關資訊</span><span class="sxs-lookup"><span data-stu-id="85124-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="85124-118">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="85124-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85124-119">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="85124-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85124-120">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="85124-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="85124-121">在 [**地區**] 頁面上, 按一下您要查看的地區。</span><span class="sxs-lookup"><span data-stu-id="85124-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="85124-122">一次只能查看一個區域。</span><span class="sxs-lookup"><span data-stu-id="85124-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="85124-123">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="85124-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85124-124">使用 Windows PowerShell Cmdlet 來查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="85124-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="85124-125">您可以使用 Windows PowerShell 和**CsNetworkRegion** Cmdlet 來查看網路區域資訊。</span><span class="sxs-lookup"><span data-stu-id="85124-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="85124-126">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85124-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="85124-127">若要查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="85124-127">To view network region information</span></span>

  - <span data-ttu-id="85124-128">若要查看所有網路區域的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER 鍵:</span><span class="sxs-lookup"><span data-stu-id="85124-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="85124-129">這會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="85124-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="85124-130">如需詳細資訊, 請參閱[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="85124-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="85124-131">建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-131">Create or modify network regions</span></span> 

<span data-ttu-id="85124-132">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="85124-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="85124-133">每個網路區域都必須與一個中央網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="85124-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="85124-134">中央網站是在其上執行呼叫許可控制 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="85124-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="85124-135">您可以使用商務用 Skype Server [控制台] 來設定網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="85124-136">網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。</span><span class="sxs-lookup"><span data-stu-id="85124-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="85124-137">從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="85124-138">使用本主題來建立及修改網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="85124-139">建立網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-139">To create a network region</span></span>

1.  <span data-ttu-id="85124-140">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="85124-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85124-141">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="85124-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85124-142">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="85124-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="85124-143">在 [**地區**] 頁面上, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="85124-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="85124-144">在 [**新區域**] 頁面上的 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="85124-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="85124-145">此值在您的商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="85124-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="85124-146">從 [**中央網站**] 下拉式清單中, 選取此網路區域的中心網站。</span><span class="sxs-lookup"><span data-stu-id="85124-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="85124-147">預設會選取 [**啟用音訊備用路徑**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85124-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="85124-148">此欄位會判斷在主要路徑中不存在足夠頻寬的情況下, 是否會透過替代路徑路由音訊通話。</span><span class="sxs-lookup"><span data-stu-id="85124-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="85124-149">如果您需要關閉卸載至網際網路, 請先清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85124-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="85124-150">如果您的任何通話是網際網路通話, 則必須核取此核取方塊 (無論頻寬設定為何)。</span><span class="sxs-lookup"><span data-stu-id="85124-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="85124-151">預設會選取 [**啟用影片替換路徑**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85124-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="85124-152">此欄位會判斷在主要路徑中不存在足夠頻寬時, 是否會透過備用路徑路由視頻通話。</span><span class="sxs-lookup"><span data-stu-id="85124-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="85124-153">如果您需要關閉卸載至網際網路, 請先清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="85124-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="85124-154">如果您的任何通話是網際網路通話, 則必須核取此核取方塊 (無論頻寬設定為何)。</span><span class="sxs-lookup"><span data-stu-id="85124-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="85124-155">可選在 [**描述**] 欄位中輸入一個值, 以提供關於此區域的詳細資訊, 而不能單獨以名稱表示。</span><span class="sxs-lookup"><span data-stu-id="85124-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="85124-156">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85124-156">Click **Commit**.</span></span>

<span data-ttu-id="85124-157">[**關聯的網站**] 資料表不是用來建立網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="85124-158">您可以在建立或修改網站時, 將網站與區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="85124-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="85124-159">如需詳細資訊, 請參閱[管理網站的呼叫許可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="85124-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="85124-160">修改網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-160">To modify a network region</span></span>

1.  <span data-ttu-id="85124-161">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="85124-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85124-162">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="85124-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85124-163">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="85124-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="85124-164">在 [**地區**] 頁面上, 按一下您要修改的地區。</span><span class="sxs-lookup"><span data-stu-id="85124-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="85124-165">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="85124-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="85124-166">在 [**編輯區域**] 頁面上, 您可以修改啟用及停用音訊及視頻替代路徑的設定, 以及變更描述 (如需詳細資訊, 請參閱本主題前面的「建立網路區域」一節。</span><span class="sxs-lookup"><span data-stu-id="85124-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="85124-167">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85124-167">Click **Commit**.</span></span>

<span data-ttu-id="85124-168">您無法在此頁面上修改**關聯的網站**。</span><span class="sxs-lookup"><span data-stu-id="85124-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="85124-169">已提供相關網站的清單供參考, 因此您知道在修改區域設定時, 哪些網站會受到影響。</span><span class="sxs-lookup"><span data-stu-id="85124-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="85124-170">刪除現有的網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-170">Delete existing network regions</span></span> 

<span data-ttu-id="85124-171">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="85124-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="85124-172">每個網路區域都必須與一個中央網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="85124-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="85124-173">中央網站是在其上執行呼叫許可控制 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="85124-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="85124-174">您可以使用商務用 Skype Server [控制台] 來設定網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="85124-175">網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。</span><span class="sxs-lookup"><span data-stu-id="85124-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="85124-176">從商務用 Skype Server 的 [控制台] 中, 您可以建立、修改或刪除網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="85124-177">使用本主題刪除現有的網路區域。</span><span class="sxs-lookup"><span data-stu-id="85124-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="85124-178">刪除網路區域</span><span class="sxs-lookup"><span data-stu-id="85124-178">To delete a network region</span></span>

1.  <span data-ttu-id="85124-179">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="85124-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85124-180">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="85124-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="85124-181">在左側導覽列中, 按一下 [**網路**設定], 然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="85124-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="85124-182">在 [**地區**] 頁面上, 按一下您要刪除的地區。</span><span class="sxs-lookup"><span data-stu-id="85124-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="85124-183">您可以一次刪除一個以上的區域。</span><span class="sxs-lookup"><span data-stu-id="85124-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="85124-184">若要這樣做, 請在按住 CTRL 鍵的同時, 按住 CTRL 並選取多個區域。</span><span class="sxs-lookup"><span data-stu-id="85124-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="85124-185">或者, 若要選取所有區域, 請按一下 [**編輯**] 功能表上的 [全**選**]。</span><span class="sxs-lookup"><span data-stu-id="85124-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="85124-186">在 [**編輯**] 功能表上, 按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="85124-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="85124-187">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="85124-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="85124-188">如果網路區域與網路網站相關聯, 則無法移除。</span><span class="sxs-lookup"><span data-stu-id="85124-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="85124-189">如果您嘗試移除與網站相關聯的區域, 您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="85124-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="85124-190">若要查看某個地區是否與任何網站相關聯, 請選取該區域, 然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="85124-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="85124-191">請參閱</span><span class="sxs-lookup"><span data-stu-id="85124-191">See Also</span></span>

[<span data-ttu-id="85124-192">管理網路區域路由</span><span class="sxs-lookup"><span data-stu-id="85124-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="85124-193">新-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="85124-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="85124-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="85124-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="85124-195">移除-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="85124-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="85124-196">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="85124-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
