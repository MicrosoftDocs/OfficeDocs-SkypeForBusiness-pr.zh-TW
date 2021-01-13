---
title: 管理網站的通話許可控制
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
description: 網站是指通話許可控制 (CAC)、E9-1-1 和媒體旁路部署的每一個網路地區內的辦公室或位置。
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816453"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="6d62f-103">在商務用 Skype Server 中的網站管理通話許可控制</span><span class="sxs-lookup"><span data-stu-id="6d62f-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="6d62f-104">網站是指通話許可控制 (CAC)、E9-1-1 和媒體旁路部署的每一個網路地區內的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d62f-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="6d62f-105">使用本文中的程式設定網路網站的通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="6d62f-106">設定網路站台連結</span><span class="sxs-lookup"><span data-stu-id="6d62f-106">Configure network site links</span></span>

<span data-ttu-id="6d62f-107">在通話許可控制 (CAC) 組態中，您可以建立網路網站間原則以定義直接連結的網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="6d62f-108">當網路網站共用直接連結時，您可以定義這兩個網站之間音訊與視訊連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="6d62f-109">您無法使用商務用 Skype Server 控制台來設定網路網站原則，只能使用來自商務用 Skype Server 管理命令介面的 Cmdlet 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="6d62f-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="6d62f-110">您可以建立、修改及移除網路站台連結 (也稱為從商務用 Skype Server 管理命令介面) 網路內部網站原則。</span><span class="sxs-lookup"><span data-stu-id="6d62f-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="6d62f-111">若要建立網路網站連結</span><span class="sxs-lookup"><span data-stu-id="6d62f-111">To create a network site link</span></span>

1.  <span data-ttu-id="6d62f-112">以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d62f-113">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d62f-114">在命令提示字元中輸入下列命令，其中的值換成您組態適用的有效值：</span><span class="sxs-lookup"><span data-stu-id="6d62f-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="6d62f-115">這個範例會建立名為雷諾的新網路站台連結 \_ ，此連結會設定雷諾和上點網路網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="6d62f-116">網路網站與頻寬原則設定檔在執行此命令前即必須存在。</span><span class="sxs-lookup"><span data-stu-id="6d62f-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="6d62f-117">如需詳細的參數描述，請參閱 [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="6d62f-118">若要擷取可套用至網路網站連結之頻寬原則設定檔的清單，請呼叫 **Get-CsNetworkBandwidthPolicyProfile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d62f-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="6d62f-119">如需詳細資訊，請參閱 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="6d62f-120">若要修改網路網站連結</span><span class="sxs-lookup"><span data-stu-id="6d62f-120">To modify a network site link</span></span>

1.  <span data-ttu-id="6d62f-121">以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d62f-122">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d62f-123">使用 **Set-CsNetworkInterSitePolicy** Cmdlet 來修改某個網路網站連結的內容。</span><span class="sxs-lookup"><span data-stu-id="6d62f-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="6d62f-124">您可以修改相連網站的其中一端網站 (或兩端網站都修改)，並且可以修改與連結相關聯的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="6d62f-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="6d62f-125">以下是修改名為雷諾上海之網站連結的頻寬原則設定檔的範例 \_ ：</span><span class="sxs-lookup"><span data-stu-id="6d62f-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="6d62f-126">如需詳細的參數描述，請參閱 [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="6d62f-127">若要刪除網路網站連結</span><span class="sxs-lookup"><span data-stu-id="6d62f-127">To delete a network site link</span></span>

1.  <span data-ttu-id="6d62f-128">以 RTCUniversalServerAdmins 群組成員的身分或必要的使用者權限，登入安裝商務用 Skype Server 管理命令介面的電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="6d62f-129">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 伺服器**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d62f-130">使用 **Remove-CsNetworkInterSitePolicy** Cmdlet 來移除網路網站連結。</span><span class="sxs-lookup"><span data-stu-id="6d62f-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="6d62f-131">下列範例會刪除雷諾 \_ 上海網路站台連結：</span><span class="sxs-lookup"><span data-stu-id="6d62f-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="6d62f-132">如需詳細的參數描述，請參閱 [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="6d62f-133">查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="6d62f-133">View network site information</span></span>

<span data-ttu-id="6d62f-134">網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d62f-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d62f-135">您可以在商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面中查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="6d62f-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="6d62f-136">在商務用 Skype Server 控制台中查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="6d62f-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6d62f-137">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d62f-138">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6d62f-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d62f-139">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d62f-140">在 [網站] 頁面上，按一下您要檢視的網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="6d62f-141">您一次僅可檢視一個網站的網站資訊。</span><span class="sxs-lookup"><span data-stu-id="6d62f-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="6d62f-142">在 [編輯] 功能表上，按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6d62f-143">使用 Windows PowerShell Cmdlet 來查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="6d62f-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6d62f-144">您可以使用 Windows PowerShell 和 Get-CsNetworkSite Cmdlet 來查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="6d62f-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="6d62f-145">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d62f-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="6d62f-146">若要檢視網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="6d62f-146">To view network site information</span></span>

  - <span data-ttu-id="6d62f-147">若要查看所有網路網站的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="6d62f-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="6d62f-148">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="6d62f-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="6d62f-149">如需詳細資訊，請參閱＜[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)＞Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="6d62f-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="6d62f-150">建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="6d62f-150">Create or modify network sites</span></span> 

<span data-ttu-id="6d62f-151">網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d62f-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d62f-152">您可以使用商務用 Skype Server 控制台來設定網站，並將其與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6d62f-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="6d62f-153">例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="6d62f-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="6d62f-154">您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="6d62f-155">您可以從商務用 Skype Server 控制台建立、修改和刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="6d62f-156">請使用下列程序來建立或修改網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="6d62f-157">若要建立網路網站</span><span class="sxs-lookup"><span data-stu-id="6d62f-157">To create a network site</span></span>

1.  <span data-ttu-id="6d62f-158">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d62f-159">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6d62f-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d62f-160">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d62f-161">在 **[網站]** 頁面上，按 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="6d62f-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="6d62f-162">在 **[新增網站]** 的 **[名稱]** 欄位中，輸入網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="6d62f-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d62f-163">網站名稱在商務用 Skype Server 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6d62f-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="6d62f-164">在 **[地區]** 下拉式清單中，選取要與此網站產生關聯的網域地區。</span><span class="sxs-lookup"><span data-stu-id="6d62f-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="6d62f-165">(選用) 如果您要對此網站的音訊或視訊通話限制頻寬，請從 **[頻寬原則]** 下拉式清單中選取含有適當設定的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="6d62f-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="6d62f-166">您可以在 [**網路** 設定] 群組的 [**原則 Profil** ] 頁面上，查看可用頻寬原則設定檔的詳細資料，或建立新的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="6d62f-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="6d62f-167">如需詳細資訊，請參閱 [管理網路頻寬原則設定檔](managing-network-bandwidth-policy-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="6d62f-168">(選用) 如果您要提供此網站的位置設定，請從 **[位置原則]** 下拉式清單中選取位置原則。</span><span class="sxs-lookup"><span data-stu-id="6d62f-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d62f-169">此位置原則將特定的增強型 9-1-1 (E9-1-1) 功能和用戶端位置設定指派給網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="6d62f-170">您可以在 **[網路設定]** 群組的 **[位置原則]** 頁面上，檢視可用位置原則的詳細資訊，或是建立新的位置原則。</span><span class="sxs-lookup"><span data-stu-id="6d62f-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="6d62f-171">(選用) 在 **[描述]** 欄位中輸入值，提供無法用名稱完整表達的網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="6d62f-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="6d62f-172">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="6d62f-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d62f-173">建立新的網路網站時不會使用 **[關聯的子網路]** 表格。</span><span class="sxs-lookup"><span data-stu-id="6d62f-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="6d62f-174">建立或修改子網路時才會讓子網路與網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="6d62f-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="6d62f-175">如需詳細資訊，請參閱 [管理網路子網](managing-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="6d62f-176">修改網站</span><span class="sxs-lookup"><span data-stu-id="6d62f-176">To modify a network site</span></span>

1.  <span data-ttu-id="6d62f-177">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d62f-178">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6d62f-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d62f-179">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d62f-180">在 **[網站]** 頁面中，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="6d62f-181">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="6d62f-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6d62f-182">在 **[編輯網站]** 頁面上，您可以修改與網站相關聯的描述、地區、頻寬原則設定檔和位置原則。</span><span class="sxs-lookup"><span data-stu-id="6d62f-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="6d62f-183">如需詳細資訊，請參閱 [建立上述網路網站](#to-create-a-network-site) 。</span><span class="sxs-lookup"><span data-stu-id="6d62f-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="6d62f-184">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="6d62f-184">Click **Commit**.</span></span>

<span data-ttu-id="6d62f-p114">您無法修改此頁面上的 **[關聯的子網路]** 表格。關聯的子網路清單僅供參考，讓您知道修改網站設定會影響哪些子網路。</span><span class="sxs-lookup"><span data-stu-id="6d62f-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="6d62f-187">刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="6d62f-187">Delete an existing network site</span></span>

<span data-ttu-id="6d62f-188">網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="6d62f-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6d62f-189">您可以使用商務用 Skype Server 控制台來設定網站，並將其與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="6d62f-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="6d62f-190">例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="6d62f-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="6d62f-191">您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6d62f-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="6d62f-192">您可以從商務用 Skype Server 控制台建立、修改和刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="6d62f-193">使用下列程序刪除現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="6d62f-194">如需建立或修改網路網站的詳細資訊，請參閱 [管理網站的通話許可控制](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="6d62f-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="6d62f-195">刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="6d62f-195">To delete a network site</span></span>

1.  <span data-ttu-id="6d62f-196">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6d62f-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d62f-197">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6d62f-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6d62f-198">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="6d62f-199">在 [網站] 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="6d62f-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="6d62f-p116">您可以一次刪除多個網站。若要這樣做，請按 CTRL 並在按住 CTRL 鍵的同時選取多個網站。或者，若要選取所有網站，請按一下 [編輯] 功能表上的 [全選]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="6d62f-203">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="6d62f-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="6d62f-204">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="6d62f-p117">但是如果網站與某個網路子網路相關聯時，則無法移除該網路網站。如果您嘗試移除與子網路相關聯的網站，則會收到錯誤訊息。若要查看網站是否與子網路相關聯，請按一下網站並按一下 [編輯] 功能表上的 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="6d62f-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="6d62f-208">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6d62f-208">See Also</span></span>


[<span data-ttu-id="6d62f-209">新 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d62f-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="6d62f-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d62f-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d62f-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d62f-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d62f-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6d62f-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="6d62f-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="6d62f-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="6d62f-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d62f-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="6d62f-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d62f-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="6d62f-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d62f-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="6d62f-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6d62f-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
