---
title: 管理網路地區
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
description: 網路地區 * 是網路中樞或骨幹，用於設定通話許可控制、E9-1-1 和媒體旁路。
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816413"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="2981f-103">管理商務用 Skype Server 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="2981f-104">「網路區域」是用於通話許可控制、E9-1-1 及媒體旁路設定的網路中樞或骨幹。</span><span class="sxs-lookup"><span data-stu-id="2981f-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="2981f-105">使用下列程序可以檢視、建立或修改網路區域。</span><span class="sxs-lookup"><span data-stu-id="2981f-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="2981f-106">例如，您已為一個語音功能建立網路區域，便不需要建立新的網路區域；其他的進階 Enterprise Voice 功能會使用那些相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="2981f-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="2981f-107">不過，您必須修改現有的網路區域定義，以套用功能特定的設定。</span><span class="sxs-lookup"><span data-stu-id="2981f-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="2981f-108">例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="2981f-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="2981f-109">使用本文中的程式來查看網路地區資訊，或建立、修改或刪除網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="2981f-110">查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="2981f-110">View network region information</span></span> 


<span data-ttu-id="2981f-111">網路地區會與跨多個地理區域的網路不同部分交互連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2981f-112">每個網路地區都必須與中央網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2981f-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="2981f-113">中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="2981f-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="2981f-114">您可以使用商務用 Skype Server 控制台來查看網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="2981f-115">網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="2981f-116">請使用本主題檢視現有的網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="2981f-117">若要透過商務用 Skype Server 控制台來查看網路區域的相關資訊</span><span class="sxs-lookup"><span data-stu-id="2981f-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2981f-118">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2981f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2981f-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2981f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2981f-120">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="2981f-121">在 **[地區]** 頁面上，按一下您要檢視的區域。</span><span class="sxs-lookup"><span data-stu-id="2981f-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="2981f-122">您一次僅可檢視一個區域。</span><span class="sxs-lookup"><span data-stu-id="2981f-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="2981f-123">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="2981f-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2981f-124">使用 Windows PowerShell Cmdlet 來查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="2981f-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2981f-125">您可以使用 Windows PowerShell 和 **Get-CsNetworkRegion** Cmdlet 來查看網路地區資訊。</span><span class="sxs-lookup"><span data-stu-id="2981f-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="2981f-126">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2981f-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="2981f-127">若要查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="2981f-127">To view network region information</span></span>

  - <span data-ttu-id="2981f-128">若要查看所有網路區域的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="2981f-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="2981f-129">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="2981f-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="2981f-130">如需詳細資訊，請參閱 [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="2981f-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="2981f-131">建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-131">Create or modify network regions</span></span> 

<span data-ttu-id="2981f-132">網路地區會與跨多個地理區域的網路不同部分交互連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2981f-133">每個網路地區都必須與中央網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2981f-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="2981f-134">中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="2981f-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="2981f-135">您可以使用商務用 Skype Server 控制台來設定網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="2981f-136">網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="2981f-137">在商務用 Skype Server 控制台中，您可以建立、修改或刪除網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="2981f-138">使用此主題可建立及修改網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="2981f-139">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-139">To create a network region</span></span>

1.  <span data-ttu-id="2981f-140">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2981f-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2981f-141">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2981f-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2981f-142">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="2981f-143">在 [ **地區** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="2981f-144">在 [ **新地區** ] 頁面的 [ **名稱** ] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="2981f-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="2981f-145">此值在商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2981f-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="2981f-146">從 [ **中央網站** ] 下拉式清單中，選取這個網路地區的中央網站。</span><span class="sxs-lookup"><span data-stu-id="2981f-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="2981f-147">根據預設，會選取 [ **啟用音訊替代路徑** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2981f-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="2981f-148">此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送音訊通話。</span><span class="sxs-lookup"><span data-stu-id="2981f-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="2981f-149">只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2981f-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="2981f-150">如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。</span><span class="sxs-lookup"><span data-stu-id="2981f-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="2981f-151">預設會選取 [ **啟用影片替代路徑** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2981f-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="2981f-152">此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送影片。</span><span class="sxs-lookup"><span data-stu-id="2981f-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="2981f-153">只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2981f-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="2981f-154">如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。</span><span class="sxs-lookup"><span data-stu-id="2981f-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="2981f-155"> (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示的此地區的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2981f-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="2981f-156">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="2981f-156">Click **Commit**.</span></span>

<span data-ttu-id="2981f-157">**關聯的網站** 資料表不會用來建立網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="2981f-158">當您建立或修改網站時，會將網站與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2981f-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="2981f-159">如需詳細資訊，請參閱 [管理網站的通話許可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="2981f-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="2981f-160">若要修改網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-160">To modify a network region</span></span>

1.  <span data-ttu-id="2981f-161">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2981f-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2981f-162">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2981f-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2981f-163">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="2981f-164">在 [ **地區** ] 頁面上，按一下您要修改的地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="2981f-165">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="2981f-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2981f-166">在 [ **編輯地區** ] 頁面上，您可以修改啟用和停用音訊和影片替代路徑的設定，以及變更描述 (如需詳細資訊，請參閱本主題前面的「建立網路地區」一節。</span><span class="sxs-lookup"><span data-stu-id="2981f-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="2981f-167">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="2981f-167">Click **Commit**.</span></span>

<span data-ttu-id="2981f-168">您無法在此頁面上修改 **相關聯的網站** 。</span><span class="sxs-lookup"><span data-stu-id="2981f-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="2981f-169">會提供相關網站的清單以供參考，因此當您修改地區設定時，您就會知道哪些網站會受到影響。</span><span class="sxs-lookup"><span data-stu-id="2981f-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="2981f-170">刪除現有的網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-170">Delete existing network regions</span></span> 

<span data-ttu-id="2981f-171">網路地區會與跨多個地理區域的網路不同部分交互連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2981f-172">每個網路地區都必須與中央網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="2981f-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="2981f-173">中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="2981f-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="2981f-174">您可以使用商務用 Skype Server 控制台來設定網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="2981f-175">網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。</span><span class="sxs-lookup"><span data-stu-id="2981f-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="2981f-176">在商務用 Skype Server 控制台中，您可以建立、修改或刪除網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="2981f-177">使用此主題可刪除現有的網路地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="2981f-178">若要刪除網路地區</span><span class="sxs-lookup"><span data-stu-id="2981f-178">To delete a network region</span></span>

1.  <span data-ttu-id="2981f-179">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2981f-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2981f-180">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2981f-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2981f-181">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **地區**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="2981f-182">在 [ **地區** ] 頁面上，按一下您要刪除的地區。</span><span class="sxs-lookup"><span data-stu-id="2981f-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="2981f-183">您可以一次刪除一個以上的區域。</span><span class="sxs-lookup"><span data-stu-id="2981f-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="2981f-184">若要執行此動作，請按住 CTRL 鍵並選取多個區域，並按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="2981f-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="2981f-185">或者，若要選取所有區域，請按一下 [**編輯**] 功能表上的 [全 **選**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="2981f-186">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="2981f-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="2981f-187">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="2981f-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="2981f-188">如果網路地區與網路網站相關聯，則無法加以移除。</span><span class="sxs-lookup"><span data-stu-id="2981f-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="2981f-189">如果您嘗試移除與網站相關聯的區域，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="2981f-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="2981f-190">若要查看是否有任何網站相關聯的區域，請選取該區域，然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2981f-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="2981f-191">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2981f-191">See Also</span></span>

[<span data-ttu-id="2981f-192">管理網路地區路由</span><span class="sxs-lookup"><span data-stu-id="2981f-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="2981f-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2981f-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="2981f-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2981f-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="2981f-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2981f-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="2981f-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2981f-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
