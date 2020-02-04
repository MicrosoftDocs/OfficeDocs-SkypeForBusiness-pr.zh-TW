---
title: Lync Server 2013：建立或修改網路區域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="331f1-102">在 Lync Server 2013 中建立或修改網路區路由</span><span class="sxs-lookup"><span data-stu-id="331f1-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="331f1-103">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="331f1-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="331f1-104">呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="331f1-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="331f1-105">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="331f1-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="331f1-106">您可以使用 Lync Server [控制台] 來設定網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="331f1-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="331f1-107">您可以從 Lync Server [控制台] 建立、修改或刪除網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="331f1-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="331f1-108">使用本主題來建立或修改網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="331f1-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="331f1-109">如需有關刪除現有網路區域路由的詳細資訊，請參閱[在 Lync Server 2013 中刪除現有的網路區域路由](lync-server-2013-deleting-existing-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="331f1-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="331f1-110">建立網路區域路由</span><span class="sxs-lookup"><span data-stu-id="331f1-110">To create a network region route</span></span>

1.  <span data-ttu-id="331f1-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="331f1-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="331f1-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="331f1-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="331f1-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="331f1-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="331f1-114">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="331f1-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="331f1-115">在 [**地區路線**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="331f1-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="331f1-116">在 [**新區域路由**] 中，于 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="331f1-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="331f1-117">這個值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="331f1-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="331f1-118">從 [**網路區域\#1** ] 下拉式清單中，選取要由此路由連接的兩個區域中的其中一個。</span><span class="sxs-lookup"><span data-stu-id="331f1-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="331f1-119">從 [**網路區域\#2** ] 下拉式清單中，選取此路由的另一個區域。</span><span class="sxs-lookup"><span data-stu-id="331f1-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="331f1-120">這個區域必須與針對 [網路區\#1] 所選取的區域不同。</span><span class="sxs-lookup"><span data-stu-id="331f1-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="331f1-121">使用 [**網路區域連結**] 清單方塊來新增路由的區域連結。</span><span class="sxs-lookup"><span data-stu-id="331f1-121">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="331f1-122">按一下 [**新增**] 按鈕以顯示 [**地區連結**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="331f1-122">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="331f1-123">按一下要新增至此路線的區域連結，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="331f1-123">Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="331f1-124">繼續按一下 [<STRONG>新增</STRONG>] 按鈕以新增更多連結，或選取連結，然後按一下 [<STRONG>移除</STRONG>] 以移除連結。</span><span class="sxs-lookup"><span data-stu-id="331f1-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="331f1-125">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="331f1-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="331f1-126">修改網路區域路由</span><span class="sxs-lookup"><span data-stu-id="331f1-126">To modify a network region route</span></span>

1.  <span data-ttu-id="331f1-127">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="331f1-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="331f1-128">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="331f1-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="331f1-129">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="331f1-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="331f1-130">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="331f1-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="331f1-131">在 [**地區路線**] 頁面上，按一下您要修改的地區路線。</span><span class="sxs-lookup"><span data-stu-id="331f1-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="331f1-132">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="331f1-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="331f1-133">在 [**編輯區域] 路由**中，您可以修改由此路由加入的區域，以及與路由相關聯的區域連結。</span><span class="sxs-lookup"><span data-stu-id="331f1-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="331f1-134">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="331f1-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="331f1-135">請參閱</span><span class="sxs-lookup"><span data-stu-id="331f1-135">See Also</span></span>


[<span data-ttu-id="331f1-136">在 Lync Server 2013 中刪除現有的網路區域路由</span><span class="sxs-lookup"><span data-stu-id="331f1-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

