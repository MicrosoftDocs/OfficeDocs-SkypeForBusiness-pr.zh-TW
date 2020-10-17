---
title: Lync Server 2013：查看網路地區路由資訊
description: Lync Server 2013：查看網路地區路由資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eca6348ecb13cd0b0b28950d57c741c056c1bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549839"
---
# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="c8a96-103">在 Lync Server 2013 中查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c8a96-103">Viewing network region route information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8a96-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c8a96-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c8a96-105">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="c8a96-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c8a96-106">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="c8a96-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c8a96-107">使用下列程式可在 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面中查看現有的網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="c8a96-107">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="c8a96-108">如需建立或修改網路地區路由的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路地區路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a96-108">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="c8a96-109">在 Lync Server 控制台中查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c8a96-109">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c8a96-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c8a96-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8a96-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c8a96-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8a96-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a96-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8a96-113">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。</span><span class="sxs-lookup"><span data-stu-id="c8a96-113">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c8a96-114">在 [ **地區路由** ] 頁面上，按一下您要查看的地區路由。</span><span class="sxs-lookup"><span data-stu-id="c8a96-114">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8a96-115">您一次只能查看一個區域路由。</span><span class="sxs-lookup"><span data-stu-id="c8a96-115">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="c8a96-116">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c8a96-116">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8a96-117">使用 Windows PowerShell Cmdlet 來查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c8a96-117">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c8a96-118">您可以使用 Windows PowerShell 和 Get-CsNetworkInterRegionRoute Cmdlet 來查看網路地區路由資訊。</span><span class="sxs-lookup"><span data-stu-id="c8a96-118">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="c8a96-119">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8a96-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c8a96-120">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="c8a96-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="c8a96-121">若要查看網路地區路由資訊</span><span class="sxs-lookup"><span data-stu-id="c8a96-121">To view network region route information</span></span>

  - <span data-ttu-id="c8a96-122">若要查看所有網路地區路由的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="c8a96-122">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="c8a96-123">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="c8a96-123">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="c8a96-124">如需詳細資訊，請參閱 [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c8a96-124">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8a96-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c8a96-125">See Also</span></span>


[<span data-ttu-id="c8a96-126">在 Lync Server 2013 中建立或修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c8a96-126">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="c8a96-127">在 Lync Server 2013 中刪除現有的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="c8a96-127">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

