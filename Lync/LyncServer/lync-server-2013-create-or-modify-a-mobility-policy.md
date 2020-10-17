---
title: Lync Server 2013：建立或修改行動性原則
description: Lync Server 2013：建立或修改行動性原則。
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
ms.openlocfilehash: fcf593c568a8ecf1bd6791641affc4076672b250
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566099"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="0978f-103">在 Lync Server 2013 中建立或修改行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-103">Create or modify a mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0978f-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0978f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0978f-105">您可以建立或修改行動性原則，讓行動使用者可以使用支援的行動裝置進行 Lync 功能（如立即訊息 (IM) 、目前狀態及連絡人）。</span><span class="sxs-lookup"><span data-stu-id="0978f-105">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0978f-106">您可以從 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面建立或修改行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-106">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="0978f-107">使用 Lync Server 控制台建立行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-107">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0978f-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0978f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0978f-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0978f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0978f-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0978f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0978f-111">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **行動性原則** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="0978f-111">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="0978f-112">在 [ **行動性原則** ] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="0978f-112">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="0978f-113">若要建立網站行動性原則，請依序按一下 [ **網站原則**]、網站、 **[確定]**、[檢查預設設定]，如果您想要，請進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="0978f-113">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="0978f-114">若要建立使用者行動性原則，請依序按一下 [ **使用者原則**]、[名稱]、[複查預設設定] 及 [您要做任何變更]。</span><span class="sxs-lookup"><span data-stu-id="0978f-114">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="0978f-115">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0978f-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="0978f-116">使用 Lync Server 控制台修改行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-116">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0978f-117">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0978f-117">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0978f-118">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0978f-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0978f-119">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0978f-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0978f-120">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **行動性原則** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="0978f-120">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="0978f-121">在 [ **行動性原則** ] 頁面上，按一下其中一個現有的行動性原則。</span><span class="sxs-lookup"><span data-stu-id="0978f-121">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="0978f-122">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="0978f-122">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0978f-123">編輯任何設定。</span><span class="sxs-lookup"><span data-stu-id="0978f-123">Edit any of the settings.</span></span>

7.  <span data-ttu-id="0978f-124">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0978f-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0978f-125">使用 Windows PowerShell Cmdlet 建立外部存取原則</span><span class="sxs-lookup"><span data-stu-id="0978f-125">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0978f-126">您可以使用 Windows PowerShell 和 **New-CsMobilityPolicy** Cmdlet，在網站範圍或個別使用者範圍) 中建立行動性原則 (。</span><span class="sxs-lookup"><span data-stu-id="0978f-126">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="0978f-127">此外，您也可以使用 **Set-CsMobilityPolicy** Cmdlet，修改任何現有的原則，包括全域原則。</span><span class="sxs-lookup"><span data-stu-id="0978f-127">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="0978f-128">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0978f-128">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0978f-129">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="0978f-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="0978f-130">若要在網站範圍建立行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-130">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="0978f-131">此命令會為 Redmond 網站建立新的行動性原則：</span><span class="sxs-lookup"><span data-stu-id="0978f-131">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="0978f-132">由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此原則會將其所有屬性的預設值都使用。</span><span class="sxs-lookup"><span data-stu-id="0978f-132">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="0978f-133">在每個使用者範圍建立行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-133">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="0978f-134">若要在每個使用者範圍建立行動性原則，請指定原則的唯一身分識別：</span><span class="sxs-lookup"><span data-stu-id="0978f-134">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="0978f-135">在建立行動性原則時變更單一屬性值</span><span class="sxs-lookup"><span data-stu-id="0978f-135">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="0978f-136">若要建立使用不同屬性值的原則，請加入適當的參數和參數值。</span><span class="sxs-lookup"><span data-stu-id="0978f-136">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="0978f-137">例如，此命令會建立行動原則，以停用通過工作的呼叫：</span><span class="sxs-lookup"><span data-stu-id="0978f-137">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="0978f-138">在建立行動性原則時變更多個屬性值</span><span class="sxs-lookup"><span data-stu-id="0978f-138">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="0978f-139">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="0978f-139">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="0978f-140">例如，此命令會建立同時停用行動及透過工作呼叫的原則：</span><span class="sxs-lookup"><span data-stu-id="0978f-140">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="0978f-141">如需詳細資訊，請參閱 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 和 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="0978f-141">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0978f-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0978f-142">See Also</span></span>


[<span data-ttu-id="0978f-143">在 Lync Server 2013 中設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="0978f-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

