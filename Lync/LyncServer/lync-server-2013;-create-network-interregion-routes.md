---
title: Lync Server 2013;建立網路區間路由
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="b2c73-102">在 Lync Server 2013 中建立網路區間路由</span><span class="sxs-lookup"><span data-stu-id="b2c73-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2c73-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b2c73-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b2c73-p101">*網路區間路由*定義了一組網路地區之間的路由。在您的通話許可控制部署中，每一組網路地區都需要搭配一個網路區間路由，以便讓部署內的每個網路地區都能互相存取。</span><span class="sxs-lookup"><span data-stu-id="b2c73-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="b2c73-107">地區連結會設定地區間連線的頻寬限制，而區間路由會決定從甲地連線到乙地時要採取的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="b2c73-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="b2c73-108">如需使用網路區間路由的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b2c73-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b2c73-109">新 CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b2c73-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b2c73-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b2c73-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b2c73-111">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b2c73-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b2c73-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b2c73-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="b2c73-113">在範例拓撲當中，下列三組地區每一組都需要定義網路區間路由：North America/EMEA、EMEA/APAC，以及 North America/APAC。</span><span class="sxs-lookup"><span data-stu-id="b2c73-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="b2c73-114">使用 Lync Server 管理命令介面建立網路區間路由</span><span class="sxs-lookup"><span data-stu-id="b2c73-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="b2c73-115">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b2c73-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b2c73-116">執行 **New-CsNetworkInterRegionRoute** Cmdlet 以定義所需的路由。</span><span class="sxs-lookup"><span data-stu-id="b2c73-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="b2c73-117">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="b2c73-117">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b2c73-118">由於 North America/APAC 網路區間路由之間沒有直接的網路地區連結，因此需要用到兩個網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="b2c73-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="b2c73-119">使用 Lync Server 控制台建立網路區間路由</span><span class="sxs-lookup"><span data-stu-id="b2c73-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b2c73-120">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b2c73-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b2c73-121">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b2c73-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b2c73-122">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="b2c73-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b2c73-123">按一下 **[地區路由]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="b2c73-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="b2c73-124">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b2c73-124">Click **New**.</span></span>

5.  <span data-ttu-id="b2c73-125">按一下 **[新的地區路由]** 頁面上的 **[名稱]**，然後輸入網路區間路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="b2c73-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="b2c73-126">按一下 [**網路地區 \# 1**]，然後按一下清單中您要路由傳送至 [網路地區 2] 的網路地區 \# 。</span><span class="sxs-lookup"><span data-stu-id="b2c73-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="b2c73-127">按一下 [**網路地區 \# 2**]，然後按一下清單中您要路由傳送至網路地區1的網路地區 \# 。</span><span class="sxs-lookup"><span data-stu-id="b2c73-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="b2c73-128">按一下 **[網路地區連結]** 欄位旁邊的 **[新增]**，接著新增將用於網路區間路由的網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="b2c73-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b2c73-p104">如果您即將為尚未擁有直接網路地區連結的兩個網路地區建立路由，請新增所有必要的連結以便完成該路由。例如，由於 North America/APAC 網路區間路由之間沒有直接的網路地區連結，因此需要用到兩個網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="b2c73-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="b2c73-131">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b2c73-131">Click **Commit**.</span></span>

10. <span data-ttu-id="b2c73-132">若要為您的拓撲完成建立網路區間路由，使用其他網路區間路由的設定並重複步驟 4 到 9。</span><span class="sxs-lookup"><span data-stu-id="b2c73-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

