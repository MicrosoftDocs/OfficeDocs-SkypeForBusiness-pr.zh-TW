---
title: Lync Server 2013：查看網路區域路由資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="59932-102">在 Lync Server 2013 中查看網路區域路線資訊</span><span class="sxs-lookup"><span data-stu-id="59932-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59932-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="59932-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="59932-104">呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="59932-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="59932-105">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="59932-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="59932-106">使用下列程式來查看 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 中的現有網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="59932-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="59932-107">如需建立或修改網路區域路由的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="59932-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="59932-108">在 Lync Server [控制台] 中查看網路區域路由資訊</span><span class="sxs-lookup"><span data-stu-id="59932-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="59932-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="59932-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59932-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="59932-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59932-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="59932-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59932-112">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="59932-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="59932-113">在 [**地區路線**] 頁面上，按一下您要查看的地區路線。</span><span class="sxs-lookup"><span data-stu-id="59932-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59932-114">一次只能查看一個區域路線。</span><span class="sxs-lookup"><span data-stu-id="59932-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="59932-115">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="59932-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="59932-116">使用 Windows PowerShell Cmdlet 查看網路區域路由資訊</span><span class="sxs-lookup"><span data-stu-id="59932-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="59932-117">您可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute Cmdlet 來查看網路區域路由資訊。</span><span class="sxs-lookup"><span data-stu-id="59932-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="59932-118">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="59932-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="59932-119">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="59932-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="59932-120">若要查看網路區域路線資訊</span><span class="sxs-lookup"><span data-stu-id="59932-120">To view network region route information</span></span>

  - <span data-ttu-id="59932-121">若要查看所有網路區域路由的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="59932-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="59932-122">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="59932-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="59932-123">如需詳細資訊，請參閱[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="59932-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59932-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="59932-124">See Also</span></span>


[<span data-ttu-id="59932-125">在 Lync Server 2013 中建立或修改網路區路由</span><span class="sxs-lookup"><span data-stu-id="59932-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="59932-126">在 Lync Server 2013 中刪除現有的網路區域路由</span><span class="sxs-lookup"><span data-stu-id="59932-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

