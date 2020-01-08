---
title: Lync Server 2013;建立網路 interregion 路由
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff2c1dd75258451002a41e0f284c4ad05c9728
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40974435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="e8aae-102">在 Lync Server 2013 中建立網路 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="e8aae-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8aae-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e8aae-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e8aae-104">*網路 interregion 路由*定義一對網路區域之間的路由。</span><span class="sxs-lookup"><span data-stu-id="e8aae-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="e8aae-105">通話許可控制部署中的每一組網路區域都需要有網路 interregion 路由。</span><span class="sxs-lookup"><span data-stu-id="e8aae-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="e8aae-106">這可讓部署中的每個網路區域存取每一個其他區域。</span><span class="sxs-lookup"><span data-stu-id="e8aae-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="e8aae-107">雖然區域連結會針對區域之間的連線設定頻寬限制，但 interregion 路由決定了連線將從一個區域傳遞到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="e8aae-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="e8aae-108">如需使用網路 interregion 路由的詳細資料，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e8aae-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="e8aae-109">新-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e8aae-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="e8aae-110">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e8aae-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="e8aae-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e8aae-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="e8aae-112">移除-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e8aae-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="e8aae-113">在範例拓朴中，您必須為三個地區對中的每一組定義網路 interregion 路由：北美/EMEA、EMEA/APAC，以及北美/APAC。</span><span class="sxs-lookup"><span data-stu-id="e8aae-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="e8aae-114">使用 Lync Server 管理命令介面建立網路 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="e8aae-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="e8aae-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e8aae-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e8aae-116">執行**新的 CsNetworkInterRegionRoute** Cmdlet，以定義所需的路由。</span><span class="sxs-lookup"><span data-stu-id="e8aae-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="e8aae-117">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="e8aae-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="e8aae-118">北美/APAC 網路 interregion 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="e8aae-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="e8aae-119">使用 Lync Server [控制台] 建立網路 interregion 路由</span><span class="sxs-lookup"><span data-stu-id="e8aae-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8aae-120">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e8aae-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8aae-121">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e8aae-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="e8aae-122">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="e8aae-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="e8aae-123">按一下 [**地區路線**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="e8aae-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="e8aae-124">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e8aae-124">Click **New**.</span></span>

5.  <span data-ttu-id="e8aae-125">在 [**新增地區路線**] 頁面上，按一下 [**名稱**]，然後輸入網路 interregion 路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="e8aae-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="e8aae-126">按一下 [**網路\#區域 1**]，然後按一下清單中您要路由至 [網路區域\#2] 的網路區域。</span><span class="sxs-lookup"><span data-stu-id="e8aae-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="e8aae-127">按一下 [**網路\#區域 2**]，然後按一下清單中您要路由至 [網路區域\#1] 的網路區域。</span><span class="sxs-lookup"><span data-stu-id="e8aae-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="e8aae-128">按一下 [**網路區域連結**] 欄位旁的 [**新增**]，然後新增將在網路 interregion 路由中使用的 [網路區域] 連結。</span><span class="sxs-lookup"><span data-stu-id="e8aae-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="e8aae-129">如果您要為兩個網路區域建立路線，而這些區域之間沒有直接的網路區域連結，您必須新增所有必要的連結，才能完成路線。</span><span class="sxs-lookup"><span data-stu-id="e8aae-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="e8aae-130">例如，北美/APAC 網路 interregion 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="e8aae-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="e8aae-131">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e8aae-131">Click **Commit**.</span></span>

10. <span data-ttu-id="e8aae-132">若要為您的拓撲完成建立網路 interregion 路由，請重複步驟4到9，並設定其他網路 interregion 路由。</span><span class="sxs-lookup"><span data-stu-id="e8aae-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

