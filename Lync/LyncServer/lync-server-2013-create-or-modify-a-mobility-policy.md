---
title: Lync Server 2013：建立或修改行動原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="179a5-102">在 Lync Server 2013 中建立或修改行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="179a5-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="179a5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="179a5-104">您可以建立或修改行動原則，以允許行動使用者針對 Lync 功能（例如立即訊息（IM）、目前狀態及連絡人）使用支援的行動裝置。</span><span class="sxs-lookup"><span data-stu-id="179a5-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="179a5-105">您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 建立或修改行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="179a5-106">若要使用 Lync Server [控制台] 建立行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="179a5-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="179a5-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="179a5-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="179a5-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="179a5-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="179a5-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="179a5-110">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**行動原則**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="179a5-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="179a5-111">在 [**行動原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="179a5-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="179a5-112">若要建立網站行動原則，請按一下 [**網站原則**]，按一下網站，按一下 **[確定]**，查看預設設定，如果您想要的話，請進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="179a5-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="179a5-113">若要建立使用者行動原則，請按一下 [**使用者原則**]，輸入名稱，查看預設設定，並視需要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="179a5-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="179a5-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="179a5-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="179a5-115">使用 Lync Server [控制台] 修改行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="179a5-116">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="179a5-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="179a5-117">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="179a5-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="179a5-118">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="179a5-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="179a5-119">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**行動原則**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="179a5-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="179a5-120">在 [**行動原則**] 頁面上，按一下其中一個現有行動原則。</span><span class="sxs-lookup"><span data-stu-id="179a5-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="179a5-121">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="179a5-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="179a5-122">編輯任何設定。</span><span class="sxs-lookup"><span data-stu-id="179a5-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="179a5-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="179a5-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="179a5-124">使用 Windows PowerShell Cmdlet 建立外部存取原則</span><span class="sxs-lookup"><span data-stu-id="179a5-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="179a5-125">您可以使用 Windows PowerShell 和**新的 CsMobilityPolicy** Cmdlet，建立行動原則（在網站範圍或每個使用者範圍內）。</span><span class="sxs-lookup"><span data-stu-id="179a5-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="179a5-126">此外，您可以使用**CsMobilityPolicy** Cmdlet 來修改任何現有的原則，包括全域原則。</span><span class="sxs-lookup"><span data-stu-id="179a5-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="179a5-127">這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="179a5-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="179a5-128">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="179a5-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="179a5-129">在網站範圍建立行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="179a5-130">這個命令會為雷德蒙網站建立新的行動原則：</span><span class="sxs-lookup"><span data-stu-id="179a5-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="179a5-131">因為在上述命令中沒有指定任何參數（除了強制身分識別參數以外），所以這些原則會針對其所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="179a5-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="179a5-132">在每個使用者範圍建立行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="179a5-133">若要在每個使用者範圍建立行動原則，請指定原則的唯一身分識別：</span><span class="sxs-lookup"><span data-stu-id="179a5-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="179a5-134">若要在建立行動原則時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="179a5-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="179a5-135">若要建立使用不同屬性值的原則，請包括適當的參數和參數值。</span><span class="sxs-lookup"><span data-stu-id="179a5-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="179a5-136">例如，這個命令會建立行動原則，透過工作停用通話：</span><span class="sxs-lookup"><span data-stu-id="179a5-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="179a5-137">若要在建立行動原則時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="179a5-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="179a5-138">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="179a5-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="179a5-139">例如，這個命令會建立一個策略，透過工作停用行動與通話：</span><span class="sxs-lookup"><span data-stu-id="179a5-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="179a5-140">如需詳細資訊，請參閱[新的 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)和[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="179a5-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="179a5-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="179a5-141">See Also</span></span>


[<span data-ttu-id="179a5-142">在 Lync Server 2013 中設定行動原則</span><span class="sxs-lookup"><span data-stu-id="179a5-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

