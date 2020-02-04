---
title: Lync Server 2013：防止服務的會話
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
ms.openlocfilehash: dc90e58fecf5e386600ca91cf764dbb50f9d76c7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services-in-lync-server-2013"></a><span data-ttu-id="3460c-102">在 Lync Server 2013 中避免服務的會話</span><span class="sxs-lookup"><span data-stu-id="3460c-102">Prevent sessions for services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3460c-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3460c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3460c-104">您可以使用 Lync Server [控制台] 來避免在特定電腦上執行的所有 Lync Server 2013 服務的新會話，或防止特定 Lync Server 2013 服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="3460c-104">You can use Lync Server Control Panel to prevent new sessions for all the Lync Server 2013 services running on a specific computer or to prevent new sessions for a specific Lync Server 2013 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="3460c-105">避免電腦上所有 Lync Server 服務的新會話</span><span class="sxs-lookup"><span data-stu-id="3460c-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="3460c-106">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3460c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3460c-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3460c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3460c-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3460c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3460c-109">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3460c-110">在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="3460c-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="3460c-111">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-111">Click **Action**.</span></span>

6.  <span data-ttu-id="3460c-112">按一下 [**防止所有服務的新會話**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="3460c-113">若要防止特定服務的新會話</span><span class="sxs-lookup"><span data-stu-id="3460c-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="3460c-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3460c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3460c-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3460c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3460c-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3460c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3460c-117">在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-117">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3460c-118">在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="3460c-118">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="3460c-119">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-119">Click **Properties**.</span></span>

6.  <span data-ttu-id="3460c-120">如有需要，請排序服務清單，然後按一下您要防止新會話的服務。</span><span class="sxs-lookup"><span data-stu-id="3460c-120">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="3460c-121">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-121">Click **Action**.</span></span>

8.  <span data-ttu-id="3460c-122">按一下 [**避免新的服務會話**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-122">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="3460c-123">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="3460c-123">Click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3460c-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="3460c-124">See Also</span></span>


[<span data-ttu-id="3460c-125">管理 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="3460c-125">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

