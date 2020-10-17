---
title: Lync Server 2013：啟動或停止 Lync Server 服務
description: Lync Server 2013：啟動或停止 Lync Server 服務。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start or stop Lync Server 2013 services
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520958(v=OCS.15)
ms:contentKeyID: 48183554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d6e6520cbf6fda38676beab984c2d006061b019
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541859"
---
# <a name="start-or-stop-lync-server-2013-services"></a><span data-ttu-id="abf50-103">啟動或停止 Lync Server 2013 服務</span><span class="sxs-lookup"><span data-stu-id="abf50-103">Start or stop Lync Server 2013 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf50-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="abf50-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="abf50-105">您可以使用 Lync Server 控制台來啟動或停止在特定電腦上執行的所有 Lync Server 2013 服務，或是啟動或停止特定的服務。</span><span class="sxs-lookup"><span data-stu-id="abf50-105">You can use Lync Server Control Panel to start or stop all the Lync Server 2013 services running on a specific computer or to start or stop a specific service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="abf50-106">啟動或停止電腦上的所有 Lync Server 服務</span><span class="sxs-lookup"><span data-stu-id="abf50-106">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="abf50-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="abf50-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span> <span data-ttu-id="abf50-108">您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="abf50-108">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
        Get-CsAdminRoleAssignment -Identity "kenmyer"

2.  <span data-ttu-id="abf50-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="abf50-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="abf50-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="abf50-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="abf50-111">在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="abf50-112">在 **[狀態]** 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="abf50-112">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="abf50-113">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-113">Click **Action**.</span></span>

6.  <span data-ttu-id="abf50-114">按一下 **[啟動所有服務]** 或 **[停止所有服務]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-114">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="abf50-115">啟動或停止特定服務</span><span class="sxs-lookup"><span data-stu-id="abf50-115">To start or stop a specific service</span></span>

1.  <span data-ttu-id="abf50-116">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="abf50-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="abf50-117">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="abf50-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="abf50-118">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="abf50-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="abf50-119">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-119">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="abf50-120">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="abf50-120">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="abf50-121">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-121">Click **Properties**.</span></span>

6.  <span data-ttu-id="abf50-122">視需要排序服務清單，然後按一下您要啟動或停止的服務。</span><span class="sxs-lookup"><span data-stu-id="abf50-122">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

7.  <span data-ttu-id="abf50-123">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-123">Click **Action**.</span></span>

8.  <span data-ttu-id="abf50-124">按一下 **[啟動服務]** 或 **[停止服務]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-124">Click **Start service** or **Stop service**.</span></span>

9.  <span data-ttu-id="abf50-125">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="abf50-125">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abf50-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="abf50-126">See Also</span></span>


[<span data-ttu-id="abf50-127">在 Lync Server 2013 中禁止服務的會話</span><span class="sxs-lookup"><span data-stu-id="abf50-127">Prevent sessions for services in Lync Server 2013</span></span>](lync-server-2013-prevent-sessions-for-services.md)  


[<span data-ttu-id="abf50-128">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="abf50-128">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

