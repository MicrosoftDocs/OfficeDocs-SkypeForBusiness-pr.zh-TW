---
title: 管理網站的呼叫許可控制
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
description: Network sites 是呼叫許可控制（CAC）、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817512"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="78035-103">在商務用 Skype Server 中的網站管理通話許可控制</span><span class="sxs-lookup"><span data-stu-id="78035-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="78035-104">Network sites 是呼叫許可控制（CAC）、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="78035-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="78035-105">使用本文中的程式來設定網路網站的呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="78035-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="78035-106">設定網路網站連結</span><span class="sxs-lookup"><span data-stu-id="78035-106">Configure network site links</span></span>

<span data-ttu-id="78035-107">在呼叫許可控制（CAC）配置中，您可以建立網路間原則，以定義直接連結之網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="78035-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="78035-108">當網路網站共用直接連結時，音訊與視頻連線的頻寬限制可以在這兩個網站之間定義。</span><span class="sxs-lookup"><span data-stu-id="78035-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="78035-109">您無法使用商務用 Skype Server 的 [控制台] 來設定網路網站原則，只能使用商務用 Skype Server Management Shell 中的 Cmdlet 來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="78035-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="78035-110">您可以從商務用 Skype Server Management Shell 建立、修改及移除網路網站連結（又稱為「網路間」原則）。</span><span class="sxs-lookup"><span data-stu-id="78035-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="78035-111">建立網路網站連結</span><span class="sxs-lookup"><span data-stu-id="78035-111">To create a network site link</span></span>

1.  <span data-ttu-id="78035-112">登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="78035-113">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="78035-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="78035-114">在命令提示字元中，輸入下列命令，以取代有效的設定值：</span><span class="sxs-lookup"><span data-stu-id="78035-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="78035-115">這個範例會建立名為 Reno\_的新網路網站連結，以設定 Reno 與新的網路網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="78035-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="78035-116">在執行這個命令之前，必須已經存在網路網站和頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="78035-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="78035-117">如需詳細的參數描述，請參閱[新的 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="78035-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="78035-118">若要取得可套用至 network site link 的頻寬原則配置檔案清單，請呼叫**CsNetworkBandwidthPolicyProfile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78035-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="78035-119">如需詳細資訊，請參閱[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="78035-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="78035-120">修改網路網站連結</span><span class="sxs-lookup"><span data-stu-id="78035-120">To modify a network site link</span></span>

1.  <span data-ttu-id="78035-121">登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="78035-122">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="78035-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="78035-123">使用**CsNetworkInterSitePolicy** Cmdlet 來修改指定的網路網站連結的屬性。</span><span class="sxs-lookup"><span data-stu-id="78035-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="78035-124">您可以修改（或兩者）或連線的網站，也可以修改與連結相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="78035-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="78035-125">以下是修改名為 Reno\_的網站連結的頻寬原則設定檔範例：</span><span class="sxs-lookup"><span data-stu-id="78035-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="78035-126">如需詳細的參數描述，請參閱[設定 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="78035-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="78035-127">刪除網路網站連結</span><span class="sxs-lookup"><span data-stu-id="78035-127">To delete a network site link</span></span>

1.  <span data-ttu-id="78035-128">登入將商務用 Skype Server Management Shell 安裝為 RTCUniversalServerAdmins 群組的成員或必要的使用者權利的電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="78035-129">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype 伺服器**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="78035-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="78035-130">使用**CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。</span><span class="sxs-lookup"><span data-stu-id="78035-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="78035-131">下列範例會刪除 Reno\_的 [上海網路] 網站連結：</span><span class="sxs-lookup"><span data-stu-id="78035-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="78035-132">如需詳細的參數描述，請參閱[移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="78035-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="78035-133">查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="78035-133">View network site information</span></span>

<span data-ttu-id="78035-134">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="78035-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="78035-135">您可以在商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面上，查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="78035-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="78035-136">若要在商務用 Skype Server [控制台] 中查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="78035-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="78035-137">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78035-138">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="78035-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78035-139">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="78035-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="78035-140">在 [**網站**] 頁面上，按一下您要查看的網站。</span><span class="sxs-lookup"><span data-stu-id="78035-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="78035-141">您一次只能查看一個網站的資訊。</span><span class="sxs-lookup"><span data-stu-id="78035-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="78035-142">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="78035-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="78035-143">使用 Windows PowerShell Cmdlet 查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="78035-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="78035-144">您可以使用 Windows PowerShell 和 CsNetworkSite Cmdlet 來查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="78035-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="78035-145">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78035-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="78035-146">若要查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="78035-146">To view network site information</span></span>

  - <span data-ttu-id="78035-147">若要查看所有網路網站的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="78035-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="78035-148">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="78035-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="78035-149">如需詳細資訊，請參閱[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="78035-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="78035-150">建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="78035-150">Create or modify network sites</span></span> 

<span data-ttu-id="78035-151">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="78035-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="78035-152">您可以使用商務用 Skype Server 的 [控制台] 來設定網站，並將它們與區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="78035-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="78035-153">例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="78035-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="78035-154">您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。</span><span class="sxs-lookup"><span data-stu-id="78035-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="78035-155">您可以從商務用 Skype Server 的 [控制台] 建立、修改及刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="78035-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="78035-156">使用下列程式來建立或修改網路網站。</span><span class="sxs-lookup"><span data-stu-id="78035-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="78035-157">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="78035-157">To create a network site</span></span>

1.  <span data-ttu-id="78035-158">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78035-159">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="78035-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78035-160">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="78035-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="78035-161">在 [**網站**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="78035-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="78035-162">在 [**新增網站**] 的 [**名稱**] 欄位中，輸入此網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="78035-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="78035-163">網站名稱在商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="78035-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="78035-164">在 [**地區**] 下拉式清單中，選取要與此網站建立關聯的網路區域。</span><span class="sxs-lookup"><span data-stu-id="78035-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="78035-165">可選如果您想要將音訊或視頻通話的頻寬限制放到此網站，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔和適當的設定。</span><span class="sxs-lookup"><span data-stu-id="78035-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="78035-166">您可以在 [**網路**設定] 群組的 [**原則 Profil** ] 頁面上，查看可用頻寬原則設定檔的詳細資料，或建立新的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="78035-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="78035-167">如需詳細資訊，請參閱[管理網路頻寬原則設定檔](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="78035-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="78035-168">可選如果您想要提供此網站的位置設定，請從 [**位置原則**] 下拉式清單中選取位置原則。</span><span class="sxs-lookup"><span data-stu-id="78035-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="78035-169">位置原則會將特定的增強型9-1-1 （E9-1-1）及用戶端位置設定指派至網站。</span><span class="sxs-lookup"><span data-stu-id="78035-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="78035-170">您可以從 [**網路**設定] 群組的 [**位置原則**] 頁面，查看可用位置原則的詳細資料，或建立新的位置原則。</span><span class="sxs-lookup"><span data-stu-id="78035-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="78035-171">可選在 [**描述**] 欄位中輸入一個值，以提供此網站的詳細資訊，而不能單獨以名稱表示。</span><span class="sxs-lookup"><span data-stu-id="78035-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="78035-172">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78035-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="78035-173">當您建立新的網路網站時，請不要使用**相關聯的子網**資料表。</span><span class="sxs-lookup"><span data-stu-id="78035-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="78035-174">當您建立或修改子網時，您可以將子網與網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="78035-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="78035-175">如需詳細資訊，請參閱[管理網路子網](managing-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="78035-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="78035-176">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="78035-176">To modify a network site</span></span>

1.  <span data-ttu-id="78035-177">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78035-178">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="78035-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78035-179">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="78035-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="78035-180">在 [**網站**] 頁面上，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="78035-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="78035-181">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="78035-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="78035-182">在 [**編輯網站**] 頁面上，您可以修改與網站相關聯的描述、區域、頻寬原則設定檔，以及位置原則。</span><span class="sxs-lookup"><span data-stu-id="78035-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="78035-183">如需詳細資訊，請參閱上面的[建立網路網站](#to-create-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="78035-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="78035-184">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78035-184">Click **Commit**.</span></span>

<span data-ttu-id="78035-185">您無法在此頁面上修改**關聯的子網**資料表。</span><span class="sxs-lookup"><span data-stu-id="78035-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="78035-186">相關子網的清單是為參考提供的，因此您在修改網站設定時，您會發現哪些子網會受到影響。</span><span class="sxs-lookup"><span data-stu-id="78035-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="78035-187">刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="78035-187">Delete an existing network site</span></span>

<span data-ttu-id="78035-188">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="78035-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="78035-189">您可以使用商務用 Skype Server 的 [控制台] 來設定網站，並將它們與區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="78035-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="78035-190">例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="78035-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="78035-191">您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。</span><span class="sxs-lookup"><span data-stu-id="78035-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="78035-192">您可以從商務用 Skype Server 的 [控制台] 建立、修改及刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="78035-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="78035-193">使用下列程式刪除現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="78035-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="78035-194">如需建立或修改網路網站的詳細資料，請參閱[管理網站的呼叫許可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="78035-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="78035-195">刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="78035-195">To delete a network site</span></span>

1.  <span data-ttu-id="78035-196">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78035-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78035-197">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="78035-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="78035-198">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="78035-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="78035-199">在 [**網站**] 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="78035-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="78035-200">您可以一次刪除一個以上的網站。</span><span class="sxs-lookup"><span data-stu-id="78035-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="78035-201">若要這樣做，請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。</span><span class="sxs-lookup"><span data-stu-id="78035-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="78035-202">或者，若要選取 [所有網站]，請按一下 [**編輯**] 功能表上的 [全**選**]。</span><span class="sxs-lookup"><span data-stu-id="78035-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="78035-203">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="78035-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="78035-204">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78035-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="78035-205">如果網路網站與網路子網相關聯，您就無法移除它。</span><span class="sxs-lookup"><span data-stu-id="78035-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="78035-206">如果您嘗試移除與子網相關聯的網站，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="78035-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="78035-207">若要查看網站是否與任何子網產生關聯，請按一下該網站，然後按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="78035-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="78035-208">請參閱</span><span class="sxs-lookup"><span data-stu-id="78035-208">See Also</span></span>


[<span data-ttu-id="78035-209">新-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="78035-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="78035-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="78035-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="78035-211">移除-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="78035-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="78035-212">CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="78035-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="78035-213">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="78035-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="78035-214">新-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="78035-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="78035-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="78035-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="78035-216">移除-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="78035-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="78035-217">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="78035-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
