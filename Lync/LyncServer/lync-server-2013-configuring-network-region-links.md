---
title: Lync Server 2013：設定網路地區連結
description: Lync Server 2013：設定網路地區連結。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547009"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="e2a62-103">在 Lync Server 2013 中設定網路地區連結</span><span class="sxs-lookup"><span data-stu-id="e2a62-103">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2a62-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e2a62-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e2a62-105">您可以將兩個網路地區間的連結設定為通話許可控制 (CAC) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e2a62-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="e2a62-106">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="e2a62-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="e2a62-107">您可以使用 Lync Server 控制台定義兩個網路地區之間的連結，並設定這些地區之間音訊和影片連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="e2a62-107">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="e2a62-108">如需刪除現有網路地區連結的詳細資訊，請參閱 [刪除網路地區連結的 Lync Server 2013](lync-server-2013-deleting-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a62-108">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="e2a62-109">建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="e2a62-109">To create a network region link</span></span>

1.  <span data-ttu-id="e2a62-110">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e2a62-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2a62-111">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e2a62-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a62-112">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a62-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2a62-113">按一下左導覽列中的 [網路設定]\*\*\*\*，然後按一下 [地區連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2a62-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e2a62-114">在 [ **地區連結** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="e2a62-114">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="e2a62-115">在 [ **新增地區連結**] 的 [ **名稱** ] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="e2a62-115">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2a62-116">此值在 Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e2a62-116">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="e2a62-117">從 [ **網路地區 \# 1** ] 下拉式清單中，選取兩個要連結的地區之一。</span><span class="sxs-lookup"><span data-stu-id="e2a62-117">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="e2a62-118">從 [ **網路地區 \# 2** ] 下拉式清單中，選取要連結的其他地區。</span><span class="sxs-lookup"><span data-stu-id="e2a62-118">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="e2a62-119">此區域必須與為網路地區1所選取的區域不同 \# 。</span><span class="sxs-lookup"><span data-stu-id="e2a62-119">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="e2a62-120"> (選用) 若您想要在這些地區之間的音訊或視頻通話上進行頻寬限制，請從 [ **頻寬原則** ] 下拉式清單中選取頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e2a62-120">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="e2a62-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e2a62-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="e2a62-122">若要修改網路地區連結</span><span class="sxs-lookup"><span data-stu-id="e2a62-122">To modify a network region link</span></span>

1.  <span data-ttu-id="e2a62-123">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e2a62-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2a62-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e2a62-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2a62-125">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e2a62-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2a62-126">按一下左導覽列中的 [網路設定]\*\*\*\*，然後按一下 [地區連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2a62-126">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e2a62-127">在 [ **地區連結** ] 頁面上，按一下您要修改的地區連結。</span><span class="sxs-lookup"><span data-stu-id="e2a62-127">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="e2a62-128">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="e2a62-128">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e2a62-129">在 [ **編輯地區連結**] 中，您可以修改連結的區域或此連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="e2a62-129">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="e2a62-130">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e2a62-130">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2a62-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e2a62-131">See Also</span></span>


[<span data-ttu-id="e2a62-132">在 Lync Server 2013 中刪除網路地區連結</span><span class="sxs-lookup"><span data-stu-id="e2a62-132">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="e2a62-133">新 CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e2a62-133">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="e2a62-134">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e2a62-134">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="e2a62-135">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e2a62-135">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="e2a62-136">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e2a62-136">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
