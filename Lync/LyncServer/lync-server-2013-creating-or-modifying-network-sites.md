---
title: Lync Server 2013：建立或修改網路網站
description: Lync Server 2013：建立或修改網路網站。
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
ms.openlocfilehash: 700f089cfe190a8f46b5eefc05e656e7c62a59a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544009"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="bcc99-103">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="bcc99-103">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcc99-104">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="bcc99-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="bcc99-105">網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="bcc99-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="bcc99-106">您可以使用 Microsoft Lync Server 2013 控制台來設定網站，並將其與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc99-106">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="bcc99-107">例如，北美洲的網路區域可能會和 Chicago、Redmond 及 Vancouver 等網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc99-107">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="bcc99-108">您必須為組織內的每個網站建立 CAC 網路網站，即使該網站沒有頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="bcc99-108">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="bcc99-109">您可以從 Lync Server 控制台建立、修改和刪除網路網站。</span><span class="sxs-lookup"><span data-stu-id="bcc99-109">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="bcc99-110">請使用下列程序來建立或修改網站。</span><span class="sxs-lookup"><span data-stu-id="bcc99-110">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="bcc99-111">如需刪除現有的網路網站的詳細資訊，請參閱 [在 Lync Server 2013 中刪除現有的網路網站](lync-server-2013-deleting-an-existing-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc99-111">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="bcc99-112">若要建立網路網站</span><span class="sxs-lookup"><span data-stu-id="bcc99-112">To create a network site</span></span>

1.  <span data-ttu-id="bcc99-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bcc99-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bcc99-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bcc99-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcc99-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc99-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bcc99-116">在左導覽列中，依序按一下 **[網路設定]** 和 **[網站]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-116">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="bcc99-117">在 **[網站]** 頁面上，按 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-117">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="bcc99-118">在 **[新增網站]** 的 **[名稱]** 欄位中，輸入網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="bcc99-118">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc99-119">網站名稱在 Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bcc99-119">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="bcc99-120">在 **[地區]** 下拉式清單中，選取要與此網站產生關聯的網域地區。</span><span class="sxs-lookup"><span data-stu-id="bcc99-120">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="bcc99-121">(選用) 如果您要對此網站的音訊或視訊通話限制頻寬，請從 **[頻寬原則]** 下拉式清單中選取含有適當設定的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bcc99-121">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc99-122">您可以在 <STRONG>[網路設定]</STRONG> 群組的 <STRONG>[原則設定檔]</STRONG> 頁面上，檢視可用頻寬原則設定檔的詳細資訊，或是建立新的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="bcc99-122">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="bcc99-123">如需詳細資訊，請參閱 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">建立或修改 Lync Server 2013 中的頻寬原則設定檔</A>。</span><span class="sxs-lookup"><span data-stu-id="bcc99-123">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="bcc99-124">(選用) 如果您要提供此網站的位置設定，請從 **[位置原則]** 下拉式清單中選取位置原則。</span><span class="sxs-lookup"><span data-stu-id="bcc99-124">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc99-125">此位置原則將特定的增強型 9-1-1 (E9-1-1) 功能和用戶端位置設定指派給網站。</span><span class="sxs-lookup"><span data-stu-id="bcc99-125">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="bcc99-126">您可以在 <STRONG>[網路設定]</STRONG> 群組的 <STRONG>[位置原則]</STRONG> 頁面上，檢視可用位置原則的詳細資訊，或是建立新的位置原則。</span><span class="sxs-lookup"><span data-stu-id="bcc99-126">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="bcc99-127">如需詳細資訊，請參閱 <A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置原則資訊</A>。</span><span class="sxs-lookup"><span data-stu-id="bcc99-127">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="bcc99-128">(選用) 在 **[描述]** 欄位中輸入值，提供無法用名稱完整表達的網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bcc99-128">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="bcc99-129">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-129">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc99-130">建立新的網路網站時不會使用 <STRONG>[關聯的子網路]</STRONG> 表格。</span><span class="sxs-lookup"><span data-stu-id="bcc99-130">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="bcc99-131">建立或修改子網路時才會讓子網路與網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc99-131">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="bcc99-132">如需詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnet In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="bcc99-132">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="bcc99-133">修改網站</span><span class="sxs-lookup"><span data-stu-id="bcc99-133">To modify a network site</span></span>

1.  <span data-ttu-id="bcc99-134">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bcc99-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bcc99-135">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bcc99-135">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcc99-136">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc99-136">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bcc99-137">在左導覽列中，依序按一下 **[網路設定]** 和 **[網站]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-137">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="bcc99-138">在 **[網站]** 頁面中，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="bcc99-138">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="bcc99-139">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-139">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="bcc99-p107">在 **[編輯網站]** 頁面上，您可以修改與網站相關聯的描述、地區、頻寬原則設定檔和位置原則。如需詳細資訊，請參閱本主題稍早的＜若要建立網路網站＞一節。</span><span class="sxs-lookup"><span data-stu-id="bcc99-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="bcc99-142">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-142">Click **Commit**.</span></span>

<span data-ttu-id="bcc99-p108">您無法修改此頁面上的 **[關聯的子網路]** 表格。關聯的子網路清單僅供參考，讓您知道修改網站設定會影響哪些子網路。</span><span class="sxs-lookup"><span data-stu-id="bcc99-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="bcc99-145">若要刪除網路網站</span><span class="sxs-lookup"><span data-stu-id="bcc99-145">To delete a network site</span></span>

1.  <span data-ttu-id="bcc99-146">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bcc99-146">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bcc99-147">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bcc99-147">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcc99-148">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc99-148">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bcc99-149">在左導覽列中，依序按一下 [網路設定]\*\*\*\* 和 [網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcc99-149">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="bcc99-150">在 [網站]\*\*\*\* 頁面上，按一下您要刪除的網站。</span><span class="sxs-lookup"><span data-stu-id="bcc99-150">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc99-p110">您可以一次刪除多個網站。若要這樣做，請按 CTRL 並在按住 CTRL 鍵的同時選取多個網站。或者，若要選取所有網站，請按一下 [編輯]<STRONG></STRONG> 功能表上的 [全選]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="bcc99-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="bcc99-154">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="bcc99-154">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="bcc99-155">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcc99-155">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="bcc99-p111">但是如果網站與某個網路子網路相關聯時，則無法移除該網路網站。如果您嘗試移除與子網路相關聯的網站，則會收到錯誤訊息。若要查看網站是否與子網路相關聯，請按一下網站並按一下 [編輯]<STRONG></STRONG> 功能表上的 [顯示詳細資料]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="bcc99-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcc99-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bcc99-159">See Also</span></span>


[<span data-ttu-id="bcc99-160">在 Lync Server 2013 中刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="bcc99-160">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="bcc99-161">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="bcc99-161">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="bcc99-162">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="bcc99-162">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="bcc99-163">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="bcc99-163">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="bcc99-164">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="bcc99-164">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

