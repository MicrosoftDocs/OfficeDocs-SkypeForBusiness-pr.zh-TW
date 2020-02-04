---
title: Lync Server 2013：建立或修改網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="92f33-102">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="92f33-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f33-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="92f33-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="92f33-104">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="92f33-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="92f33-105">您可以使用 Microsoft Lync Server 2013 的 [控制台] 來設定網站，並將它們與區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="92f33-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="92f33-106">例如，北美的網路區域可能會與「芝加哥」、「雷德蒙」和「范與范」等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="92f33-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="92f33-107">您必須針對組織中的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制也一樣。</span><span class="sxs-lookup"><span data-stu-id="92f33-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="92f33-108">您可以從 Lync Server [控制台] 建立、修改及刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="92f33-109">使用下列程式來建立或修改網路網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="92f33-110">如需刪除現有網路網站的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路網站](lync-server-2013-deleting-an-existing-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="92f33-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="92f33-111">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="92f33-111">To create a network site</span></span>

1.  <span data-ttu-id="92f33-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="92f33-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92f33-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="92f33-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92f33-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="92f33-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="92f33-115">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="92f33-116">在 [**網站**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="92f33-117">在 [**新增網站**] 的 [**名稱**] 欄位中，輸入此網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="92f33-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f33-118">網站名稱在 Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="92f33-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="92f33-119">在 [**地區**] 下拉式清單中，選取要與此網站建立關聯的網路區域。</span><span class="sxs-lookup"><span data-stu-id="92f33-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="92f33-120">可選如果您想要將音訊或視頻通話的頻寬限制放到此網站，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔和適當的設定。</span><span class="sxs-lookup"><span data-stu-id="92f33-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f33-121">您可以在 [<STRONG>網路</STRONG>設定] 群組的 [<STRONG>原則設定檔</STRONG>] 頁面上，查看可用頻寬原則設定檔的詳細資料，或建立新的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="92f33-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="92f33-122">如需詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中建立或修改頻寬原則設定檔</A>。</span><span class="sxs-lookup"><span data-stu-id="92f33-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="92f33-123">可選如果您想要提供此網站的位置設定，請從 [**位置原則**] 下拉式清單中選取位置原則。</span><span class="sxs-lookup"><span data-stu-id="92f33-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f33-124">位置原則會將特定的增強型9-1-1 （E9-1-1）及用戶端位置設定指派至網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="92f33-125">您可以從 [<STRONG>網路</STRONG>設定] 群組的 [<STRONG>位置原則</STRONG>] 頁面，查看可用位置原則的詳細資料，或建立新的位置原則。</span><span class="sxs-lookup"><span data-stu-id="92f33-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="92f33-126">如需詳細資訊，請參閱<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置原則資訊</A>。</span><span class="sxs-lookup"><span data-stu-id="92f33-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="92f33-127">可選在 [**描述**] 欄位中輸入一個值，以提供此網站的詳細資訊，而不能單獨以名稱表示。</span><span class="sxs-lookup"><span data-stu-id="92f33-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="92f33-128">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92f33-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f33-129">當您建立新的網路網站時，請不要使用<STRONG>相關聯的子網</STRONG>資料表。</span><span class="sxs-lookup"><span data-stu-id="92f33-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="92f33-130">當您建立或修改子網時，您可以將子網與網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="92f33-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="92f33-131">如需詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中建立或修改網路子網</A>。</span><span class="sxs-lookup"><span data-stu-id="92f33-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="92f33-132">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="92f33-132">To modify a network site</span></span>

1.  <span data-ttu-id="92f33-133">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="92f33-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92f33-134">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="92f33-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92f33-135">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="92f33-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="92f33-136">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="92f33-137">在 [**網站**] 頁面上，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="92f33-138">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="92f33-139">在 [**編輯網站**] 頁面上，您可以修改與網站相關聯的描述、區域、頻寬原則設定檔，以及位置原則。</span><span class="sxs-lookup"><span data-stu-id="92f33-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="92f33-140">如需詳細資訊，請參閱本主題前面的「建立網路網站」一節。</span><span class="sxs-lookup"><span data-stu-id="92f33-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="92f33-141">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92f33-141">Click **Commit**.</span></span>

<span data-ttu-id="92f33-142">您無法在此頁面上修改**關聯的子網**資料表。</span><span class="sxs-lookup"><span data-stu-id="92f33-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="92f33-143">相關子網的清單是為參考提供的，因此您在修改網站設定時，您會發現哪些子網會受到影響。</span><span class="sxs-lookup"><span data-stu-id="92f33-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="92f33-144">刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="92f33-144">To delete a network site</span></span>

1.  <span data-ttu-id="92f33-145">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="92f33-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92f33-146">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="92f33-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92f33-147">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="92f33-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="92f33-148">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="92f33-149">在 [**網站**] 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92f33-150">您可以一次刪除一個以上的網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="92f33-151">若要這樣做，請按住 CTRL 並在按住 CTRL 鍵的同時選取多個網站。</span><span class="sxs-lookup"><span data-stu-id="92f33-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="92f33-152">或者，若要選取 [所有網站]，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="92f33-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="92f33-153">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="92f33-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="92f33-154">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="92f33-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="92f33-155">如果網路網站與網路子網相關聯，您就無法移除它。</span><span class="sxs-lookup"><span data-stu-id="92f33-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="92f33-156">如果您嘗試移除與子網相關聯的網站，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="92f33-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="92f33-157">若要查看網站是否與任何子網產生關聯，請按一下該網站，然後按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="92f33-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92f33-158">請參閱</span><span class="sxs-lookup"><span data-stu-id="92f33-158">See Also</span></span>


[<span data-ttu-id="92f33-159">在 Lync Server 2013 中刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="92f33-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="92f33-160">新-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="92f33-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="92f33-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="92f33-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="92f33-162">移除-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="92f33-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="92f33-163">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="92f33-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

