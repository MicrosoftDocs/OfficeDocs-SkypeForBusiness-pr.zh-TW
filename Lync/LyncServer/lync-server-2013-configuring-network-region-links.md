---
title: Lync Server 2013：設定網路區域連結
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
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="efe4f-102">在 Lync Server 2013 中設定網路區域連結</span><span class="sxs-lookup"><span data-stu-id="efe4f-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efe4f-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="efe4f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="efe4f-104">您可以設定兩個網路區域之間的連結，作為通話許可控制（CAC）的一部分。</span><span class="sxs-lookup"><span data-stu-id="efe4f-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="efe4f-105">網路中的區域是透過物理廣域網路（WAN）連線來連結。</span><span class="sxs-lookup"><span data-stu-id="efe4f-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="efe4f-106">您可以使用 Lync Server [控制台] 定義兩個網路區域之間的連結，並設定這些區域之間音訊與視頻連線的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="efe4f-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="efe4f-107">如需有關刪除現有網路區域連結的詳細資訊，請參閱[刪除 Lync Server 2013 中的 [網路區域] 連結](lync-server-2013-deleting-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="efe4f-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="efe4f-108">建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="efe4f-108">To create a network region link</span></span>

1.  <span data-ttu-id="efe4f-109">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="efe4f-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="efe4f-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efe4f-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="efe4f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efe4f-112">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="efe4f-113">在 [**地區連結**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="efe4f-114">在 [**新區域] 連結**的 [**名稱**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="efe4f-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="efe4f-115">這個值在您的 Lync Server 2013 部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="efe4f-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="efe4f-116">從 [**網路區域\#1** ] 下拉式清單中，選取兩個要連結的區域之一。</span><span class="sxs-lookup"><span data-stu-id="efe4f-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="efe4f-117">從 [**網路區域\#2** ] 下拉式清單中，選取要連結的其他區域。</span><span class="sxs-lookup"><span data-stu-id="efe4f-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="efe4f-118">這個區域必須與針對 [網路區\#1] 所選取的區域不同。</span><span class="sxs-lookup"><span data-stu-id="efe4f-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="efe4f-119">可選如果您想要將頻寬限制放在這些區域之間的音訊或視頻通話中，請從 [**頻寬原則**] 下拉式清單中選取 [頻寬原則] 設定檔。</span><span class="sxs-lookup"><span data-stu-id="efe4f-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="efe4f-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efe4f-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="efe4f-121">修改網路區域連結</span><span class="sxs-lookup"><span data-stu-id="efe4f-121">To modify a network region link</span></span>

1.  <span data-ttu-id="efe4f-122">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="efe4f-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="efe4f-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efe4f-124">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="efe4f-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efe4f-125">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="efe4f-126">在 [**地區連結**] 頁面上，按一下您要修改的區域連結。</span><span class="sxs-lookup"><span data-stu-id="efe4f-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="efe4f-127">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="efe4f-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="efe4f-128">在 [**編輯區域] 連結**中，您可以修改連結的區域或此連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="efe4f-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="efe4f-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="efe4f-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efe4f-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="efe4f-130">See Also</span></span>


<span data-ttu-id="efe4f-131">[刪除 Lync Server 2013 中的 [網路區域] 連結](lync-server-2013-deleting-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="efe4f-131">[Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md)</span></span>  


[<span data-ttu-id="efe4f-132">新-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="efe4f-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="efe4f-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="efe4f-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="efe4f-134">移除-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="efe4f-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="efe4f-135">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="efe4f-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
