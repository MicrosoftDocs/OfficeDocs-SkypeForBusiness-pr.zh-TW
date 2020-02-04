---
title: Lync Server 2013：查看服務的詳細資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bc8f0f9f6e0296f279cb09495a92fd9950625e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="d6de7-102">在 Lync Server 2013 中查看服務的詳細資料</span><span class="sxs-lookup"><span data-stu-id="d6de7-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6de7-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d6de7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d6de7-104">您可以使用 Lync Server [控制台] 來查看在拓撲中特定電腦上執行的每個服務的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d6de7-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="d6de7-105">您可以查看每個服務的狀態，以及相關聯的資料庫、埠和相依服務等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d6de7-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="d6de7-106">若要查看服務的詳細資料</span><span class="sxs-lookup"><span data-stu-id="d6de7-106">To view details for a service</span></span>

1.  <span data-ttu-id="d6de7-107">從指派給 Lync Server 2013 任何預先定義之系統管理角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d6de7-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="d6de7-108">如需有關 Lync Server 2013 中預先定義的管理角色的詳細資訊，請參閱[在 Lync server 2013 中規劃角色式存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d6de7-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="d6de7-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d6de7-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d6de7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d6de7-111">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="d6de7-112">在 [**狀態**] 頁面中，排序或搜尋清單，然後按一下您要查看的電腦。</span><span class="sxs-lookup"><span data-stu-id="d6de7-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="d6de7-113">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="d6de7-114">如有需要，請在 [**查看電腦詳細資料**] 視窗中排序服務清單，然後按一下您要查看的服務。</span><span class="sxs-lookup"><span data-stu-id="d6de7-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="d6de7-115">視需要執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="d6de7-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="d6de7-116">若要查看該特定服務的最新狀態，請按一下 [**取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="d6de7-117">若要查看該特定服務的詳細資料，請按一下 [**屬性**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="d6de7-118">若要返回拓撲中所有電腦的清單，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d6de7-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6de7-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="d6de7-119">See Also</span></span>


[<span data-ttu-id="d6de7-120">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="d6de7-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

