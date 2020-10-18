---
title: Lync Server 2013：阻止服務的會話
description: Lync Server 2013：阻止服務的會話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182553(v=OCS.15)
ms:contentKeyID: 48184866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 846a9da5330c3e64f61c27dfadd883f0c43a0ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579809"
---
# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="5082b-103">在 Lync Server 2013 中禁止服務的會話</span><span class="sxs-lookup"><span data-stu-id="5082b-103">Prevent sessions for services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5082b-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5082b-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5082b-105">您可以使用 Lync Server 控制台，避免在特定電腦上執行的所有 Lync Server 2013 服務的新會話，或阻止特定 Lync Server 2013 服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="5082b-105">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="5082b-106">阻止所有 Lync Server 服務的新工作階段於電腦上執行</span><span class="sxs-lookup"><span data-stu-id="5082b-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="5082b-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5082b-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5082b-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5082b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5082b-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5082b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5082b-110">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-110">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="5082b-111">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="5082b-111">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="5082b-112">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-112">Click **Action**.</span></span>

6.  <span data-ttu-id="5082b-113">按一下 **[阻止對所有服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-113">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="5082b-114">阻止特定服務的新工作階段</span><span class="sxs-lookup"><span data-stu-id="5082b-114">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="5082b-115">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5082b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5082b-116">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5082b-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5082b-117">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5082b-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5082b-118">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-118">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="5082b-119">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="5082b-119">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="5082b-120">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-120">Click **Properties**.</span></span>

6.  <span data-ttu-id="5082b-121">視需要排序服務清單，然後按一下要阻止新工作階段的服務。</span><span class="sxs-lookup"><span data-stu-id="5082b-121">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="5082b-122">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-122">Click **Action**.</span></span>

8.  <span data-ttu-id="5082b-123">按一下 **[阻止對服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-123">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="5082b-124">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="5082b-124">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5082b-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5082b-125">See Also</span></span>


[<span data-ttu-id="5082b-126">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="5082b-126">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

