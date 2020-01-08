---
title: Lync Server 2013：建立或修改頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f44d759a77fea03b285d2e1af10838d508a6ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="775bc-102">在 Lync Server 2013 中建立或修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="775bc-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="775bc-103">_**主題上次修改日期：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="775bc-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="775bc-104">在呼叫許可控制（CAC）中，頻寬原則是用來定義特定形式的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="775bc-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="775bc-105">在 Microsoft Lync Server 2013 中，只有音訊和視頻形式可獲指派頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="775bc-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="775bc-106">您可以設定整體頻寬限制及會話限制。</span><span class="sxs-lookup"><span data-stu-id="775bc-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="775bc-107">您可以使用 Lync Server [控制台] 來建立、修改或刪除這些原則的容器設定檔。</span><span class="sxs-lookup"><span data-stu-id="775bc-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="775bc-108">每個頻寬原則設定檔都可以與一個或多個網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="775bc-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="775bc-109">使用下列程式來建立或修改頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="775bc-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="775bc-110">若要刪除頻寬原則設定檔，請參閱[在 Lync Server 2013 中刪除網路頻寬原則設定檔](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="775bc-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="775bc-111">建立新的頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="775bc-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="775bc-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="775bc-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="775bc-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="775bc-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="775bc-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="775bc-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="775bc-115">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="775bc-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="775bc-116">在 [**頻寬原則**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="775bc-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="775bc-117">在**新的頻寬原則設定檔**中，在 [**名稱**] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="775bc-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="775bc-118">這個名稱在所有頻寬原則設定檔中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="775bc-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="775bc-119">在 [**音訊限制**] 欄位中，輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="775bc-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="775bc-120">此值為所有音訊連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="775bc-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="775bc-121">在 [**音訊會話限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="775bc-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="775bc-122">此值為個別音訊連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="775bc-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="775bc-123">此值必須是40或更高版本。</span><span class="sxs-lookup"><span data-stu-id="775bc-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="775bc-124">在 [**影片限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="775bc-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="775bc-125">此值為所有視頻連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="775bc-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="775bc-126">在 [**視頻會話限制**] 欄位中輸入一個數值。</span><span class="sxs-lookup"><span data-stu-id="775bc-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="775bc-127">此值為個別視頻連線所要配置的最大頻寬量，以 kbps 表示。</span><span class="sxs-lookup"><span data-stu-id="775bc-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="775bc-128">此值必須是100或更高版本。</span><span class="sxs-lookup"><span data-stu-id="775bc-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="775bc-129">可選在**描述**欄位中輸入一個值，以提供此頻寬原則設定檔無法單獨表示的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="775bc-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="775bc-130">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="775bc-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="775bc-131">建立新的頻寬原則設定檔並不會自動強制執行頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="775bc-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="775bc-132">您必須先將原則設定檔與網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="775bc-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="775bc-133">如需有關如何將原則設定檔與網站建立關聯的詳細資訊，請參閱<A href="lync-server-2013-creating-or-modifying-network-sites.md">在 Lync Server 2013 中建立或修改網路網站</A>。</span><span class="sxs-lookup"><span data-stu-id="775bc-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="775bc-134">修改頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="775bc-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="775bc-135">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="775bc-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="775bc-136">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="775bc-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="775bc-137">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="775bc-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="775bc-138">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**頻寬規則**]。</span><span class="sxs-lookup"><span data-stu-id="775bc-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="775bc-139">在 [**頻寬原則**] 頁面上，按一下您要修改的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="775bc-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="775bc-140">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="775bc-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="775bc-141">在 [**編輯頻寬原則策略設定檔**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱本主題前面的「建立頻寬原則設定檔」一節）。</span><span class="sxs-lookup"><span data-stu-id="775bc-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="775bc-142">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="775bc-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="775bc-143">當您修改頻寬原則設定檔時，它會立即更新與此頻寬原則設定檔相關聯之所有網路網站的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="775bc-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="775bc-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="775bc-144">See Also</span></span>


[<span data-ttu-id="775bc-145">刪除 Lync Server 2013 的網路頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="775bc-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="775bc-146">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="775bc-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="775bc-147">新-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="775bc-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="775bc-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="775bc-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="775bc-149">CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="775bc-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

