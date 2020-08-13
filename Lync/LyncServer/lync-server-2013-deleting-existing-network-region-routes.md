---
title: Lync Server 2013：刪除現有的網路地區路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a8674e635bb5663ebbca994d7d8f865601a193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="68202-102">在 Lync Server 2013 中刪除現有的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="68202-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68202-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="68202-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="68202-104">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="68202-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="68202-105">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="68202-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="68202-106">您可以使用 Lync Server 控制台設定網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="68202-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="68202-107">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="68202-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="68202-108">若要刪除現有的網路地區路由，請利用本主題。</span><span class="sxs-lookup"><span data-stu-id="68202-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="68202-109">如需建立或修改網路地區路由的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改網路地區路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="68202-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="68202-110">刪除網路地區路由</span><span class="sxs-lookup"><span data-stu-id="68202-110">To delete a network region route</span></span>

1.  <span data-ttu-id="68202-111">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="68202-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="68202-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="68202-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68202-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="68202-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68202-114">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。</span><span class="sxs-lookup"><span data-stu-id="68202-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="68202-115">在 **[地區路由]** 頁面上，按一下您要刪除的地區路由。</span><span class="sxs-lookup"><span data-stu-id="68202-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68202-p103">您可以同時刪除多個地區路由。如果要執行這項作業，請按住 CTRL 鍵，然後選取多個地區路由。或者，若要選取所有地區路由，請按一下 <STRONG>[編輯]</STRONG> 功能表上的 <STRONG>[全選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="68202-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="68202-119">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="68202-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="68202-120">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68202-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68202-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="68202-121">See Also</span></span>


[<span data-ttu-id="68202-122">在 Lync Server 2013 中建立或修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="68202-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="68202-123">[設定網路地區路由](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="68202-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="68202-124">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="68202-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="68202-125">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="68202-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="68202-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="68202-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="68202-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="68202-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

