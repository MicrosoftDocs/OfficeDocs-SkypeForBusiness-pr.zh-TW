---
title: Lync Server 2013：建立或修改網路地區路由
description: Lync Server 2013：建立或修改網路地區路由。
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
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544089"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="dd15c-103">在 Lync Server 2013 中建立或修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="dd15c-103">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd15c-104">_**主題上次修改日期：** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="dd15c-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="dd15c-105">通話許可控制服務 (CAC) 組態內的每個地區，都必須要有辦法存取其他每個地區。</span><span class="sxs-lookup"><span data-stu-id="dd15c-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="dd15c-106">地區連結會設定地區間連線的頻寬限制，也代表實體連結，路由則會決定從甲地連線到乙地時要周遊的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="dd15c-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="dd15c-107">您可以使用 Lync Server 控制台設定網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="dd15c-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="dd15c-108">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路地區路由。</span><span class="sxs-lookup"><span data-stu-id="dd15c-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="dd15c-109">若要建立或修改網路地區路由，請利用本節主題。</span><span class="sxs-lookup"><span data-stu-id="dd15c-109">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="dd15c-110">如需刪除現有網路地區路由的詳細資訊，請參閱 [在 Lync Server 2013 中刪除現有的網路地區路由](lync-server-2013-deleting-existing-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="dd15c-110">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="dd15c-111">若要建立網路地區路由</span><span class="sxs-lookup"><span data-stu-id="dd15c-111">To create a network region route</span></span>

1.  <span data-ttu-id="dd15c-112">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dd15c-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dd15c-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="dd15c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd15c-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dd15c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd15c-115">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="dd15c-116">在 **[地區路由]** 頁面上，按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-116">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="dd15c-117">在 **[新的地區路由]** 的 **[名稱]** 欄位中，輸入一個值。</span><span class="sxs-lookup"><span data-stu-id="dd15c-117">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd15c-118">此值在您的 Microsoft Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dd15c-118">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="dd15c-119">從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個區域中的其中一個要透過此路由來連線。</span><span class="sxs-lookup"><span data-stu-id="dd15c-119">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="dd15c-120">從 [ **網路地區 \# 2** ] 下拉式清單中，選取此路由的其他地區。</span><span class="sxs-lookup"><span data-stu-id="dd15c-120">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="dd15c-121">此區域必須與為網路地區1所選取的區域不同 \# 。</span><span class="sxs-lookup"><span data-stu-id="dd15c-121">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="dd15c-p104">使用 **[網路地區連結]** 清單方塊，將地區連結新增至路由。按一下 **[新增]** 按鈕以顯示 **[地區連結]** 頁面。按一下要新增至此路由的地區連結，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd15c-125">若要新增更多連結，請繼續按 <STRONG>[新增]</STRONG> 按鈕；若要移除連結，請選取連結，然後按一下 <STRONG>[移除]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dd15c-125">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="dd15c-126">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="dd15c-127">若要修改網路地區路由</span><span class="sxs-lookup"><span data-stu-id="dd15c-127">To modify a network region route</span></span>

1.  <span data-ttu-id="dd15c-128">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="dd15c-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dd15c-129">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="dd15c-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd15c-130">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dd15c-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd15c-131">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區路由]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-131">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="dd15c-132">在 **[地區路由]** 頁面上，按一下您要修改的地區路由。</span><span class="sxs-lookup"><span data-stu-id="dd15c-132">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="dd15c-133">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="dd15c-134">在 **[編輯地區路由]** 中，您可以修改此路由所聯結的地區，以及與路由相關聯的地區連結。</span><span class="sxs-lookup"><span data-stu-id="dd15c-134">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="dd15c-135">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="dd15c-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd15c-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dd15c-136">See Also</span></span>


[<span data-ttu-id="dd15c-137">在 Lync Server 2013 中刪除現有的網路地區路由</span><span class="sxs-lookup"><span data-stu-id="dd15c-137">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

