---
title: Lync Server 2013：建立或修改網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52518c76efdb302661ed3f097cb382d399299798
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="43ed5-102">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="43ed5-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43ed5-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="43ed5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="43ed5-104">網路地區會與跨多個地理區域的網路不同部分交互連線。</span><span class="sxs-lookup"><span data-stu-id="43ed5-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="43ed5-105">每個網路地區都必須與中央網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="43ed5-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="43ed5-106">中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="43ed5-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="43ed5-107">您可以使用 Lync Server 控制台設定網路地區。</span><span class="sxs-lookup"><span data-stu-id="43ed5-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="43ed5-108">網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。</span><span class="sxs-lookup"><span data-stu-id="43ed5-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="43ed5-109">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區。</span><span class="sxs-lookup"><span data-stu-id="43ed5-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="43ed5-110">使用此主題可建立及修改網路地區。</span><span class="sxs-lookup"><span data-stu-id="43ed5-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="43ed5-111">如需刪除現有網路地區的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路地區](lync-server-2013-deleting-existing-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="43ed5-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="43ed5-112">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="43ed5-112">To create a network region</span></span>

1.  <span data-ttu-id="43ed5-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="43ed5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43ed5-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="43ed5-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43ed5-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="43ed5-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43ed5-116">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="43ed5-117">在 [**地區**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="43ed5-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="43ed5-118">在 [**新地區**] 頁面的 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="43ed5-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="43ed5-119">此值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="43ed5-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="43ed5-120">從 [**中央網站**] 下拉式清單中，選取這個網路地區的中央網站。</span><span class="sxs-lookup"><span data-stu-id="43ed5-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="43ed5-121">根據預設，會選取 [**啟用音訊替代路徑**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="43ed5-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="43ed5-122">此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送音訊通話。</span><span class="sxs-lookup"><span data-stu-id="43ed5-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="43ed5-123">只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="43ed5-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="43ed5-124">如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。</span><span class="sxs-lookup"><span data-stu-id="43ed5-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="43ed5-125">預設會選取 [**啟用影片替代路徑**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="43ed5-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="43ed5-126">此欄位會決定當主要路徑中不存在足夠的頻寬時，是否會透過替代路徑來路由傳送影片。</span><span class="sxs-lookup"><span data-stu-id="43ed5-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="43ed5-127">只有在您需要關閉對網際網路的卸載時，才清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="43ed5-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="43ed5-128">如果您的任何呼叫都是網際網路通話，則必須勾選此核取方塊（不論頻寬設定為何）。</span><span class="sxs-lookup"><span data-stu-id="43ed5-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="43ed5-129"> (選用) 在 [**描述**] 欄位中輸入值，以提供無法獨立以名稱表示的此地區的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="43ed5-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="43ed5-130">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-130">Click **Commit**.</span></span>

<span data-ttu-id="43ed5-131">**關聯的網站**資料表不會用來建立網路地區。</span><span class="sxs-lookup"><span data-stu-id="43ed5-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="43ed5-132">當您建立或修改網站時，會將網站與區域產生關聯。</span><span class="sxs-lookup"><span data-stu-id="43ed5-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="43ed5-133">如需詳細資訊，請參閱[建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-creating-or-modifying-network-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="43ed5-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="43ed5-134">若要修改網路地區</span><span class="sxs-lookup"><span data-stu-id="43ed5-134">To modify a network region</span></span>

1.  <span data-ttu-id="43ed5-135">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="43ed5-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="43ed5-136">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="43ed5-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43ed5-137">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="43ed5-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43ed5-138">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="43ed5-139">在 [**地區**] 頁面上，按一下您要修改的地區。</span><span class="sxs-lookup"><span data-stu-id="43ed5-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="43ed5-140">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="43ed5-141">在 [**編輯地區**] 頁面上，您可以修改啟用和停用音訊和影片替代路徑的設定，以及變更描述 (如需詳細資訊，請參閱本主題前面的「建立網路地區」一節。</span><span class="sxs-lookup"><span data-stu-id="43ed5-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="43ed5-142">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-142">Click **Commit**.</span></span>

<span data-ttu-id="43ed5-143">您無法在此頁面上修改**相關聯的網站**。</span><span class="sxs-lookup"><span data-stu-id="43ed5-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="43ed5-144">會提供相關網站的清單以供參考，因此當您修改地區設定時，您就會知道哪些網站會受到影響。</span><span class="sxs-lookup"><span data-stu-id="43ed5-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43ed5-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="43ed5-145">See Also</span></span>


[<span data-ttu-id="43ed5-146">在 Lync Server 2013 中刪除現有的網路地區</span><span class="sxs-lookup"><span data-stu-id="43ed5-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="43ed5-147">在 Lync Server 2013 中設定 CAC 的網路地區</span><span class="sxs-lookup"><span data-stu-id="43ed5-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="43ed5-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="43ed5-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="43ed5-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="43ed5-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="43ed5-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="43ed5-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="43ed5-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="43ed5-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

