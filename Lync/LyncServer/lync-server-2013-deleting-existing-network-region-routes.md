---
title: Lync Server 2013：刪除現有的網路區域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="e3a35-102">在 Lync Server 2013 中刪除現有的網路區域路由</span><span class="sxs-lookup"><span data-stu-id="e3a35-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a35-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e3a35-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e3a35-104">呼叫許可控制（CAC）配置中的每個地區都必須有一些方法，才能存取其他每個區域。</span><span class="sxs-lookup"><span data-stu-id="e3a35-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="e3a35-105">雖然 [地區] 連結會針對區域之間的連線設定頻寬限制，同時也代表物理連結，但是路由會判斷連線從一個地區到另一個區域的連結路徑。</span><span class="sxs-lookup"><span data-stu-id="e3a35-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="e3a35-106">您可以使用 Lync Server [控制台] 來設定網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="e3a35-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="e3a35-107">您可以從 Lync Server [控制台] 建立、修改或刪除網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="e3a35-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="e3a35-108">使用本主題刪除現有的網路區域路由。</span><span class="sxs-lookup"><span data-stu-id="e3a35-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="e3a35-109">如需建立或修改網路區域路由的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="e3a35-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="e3a35-110">刪除網路區域路線</span><span class="sxs-lookup"><span data-stu-id="e3a35-110">To delete a network region route</span></span>

1.  <span data-ttu-id="e3a35-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e3a35-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3a35-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e3a35-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3a35-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e3a35-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3a35-114">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區路由**]。</span><span class="sxs-lookup"><span data-stu-id="e3a35-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="e3a35-115">在 [**地區路線**] 頁面上，按一下您要刪除的地區路線。</span><span class="sxs-lookup"><span data-stu-id="e3a35-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3a35-116">您可以一次刪除一個以上的區域路由。</span><span class="sxs-lookup"><span data-stu-id="e3a35-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="e3a35-117">若要這樣做，請在按住 CTRL 鍵的同時，按住 CTRL 並選取多個區域路由。</span><span class="sxs-lookup"><span data-stu-id="e3a35-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="e3a35-118">或者，若要選取所有地區路線，請按一下 [<STRONG>編輯</STRONG>] 功能表上的 [全<STRONG>選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="e3a35-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="e3a35-119">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e3a35-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e3a35-120">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3a35-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3a35-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="e3a35-121">See Also</span></span>


[<span data-ttu-id="e3a35-122">在 Lync Server 2013 中建立或修改網路區路由</span><span class="sxs-lookup"><span data-stu-id="e3a35-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="e3a35-123">[設定網路地區路由](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e3a35-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="e3a35-124">新-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e3a35-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="e3a35-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e3a35-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="e3a35-126">移除-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e3a35-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="e3a35-127">CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="e3a35-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

