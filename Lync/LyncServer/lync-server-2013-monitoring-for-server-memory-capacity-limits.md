---
title: Lync Server 2013： 監控伺服器記憶體容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e969de7198eecf43b57ea00fa0591bbeb06da0b1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="3addb-102">監控的 Lync Server 2013 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="3addb-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3addb-103">_**主題上次修改日期：** 2016年-12-08_</span><span class="sxs-lookup"><span data-stu-id="3addb-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="3addb-104">容量規劃是指此主題中的資訊只各與 Lync 2010 Mobile 用戶端和行動性服務 (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="3addb-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="3addb-105">Lync Server 2013 規劃工具會提供容量規劃的 Unified Communications Web API (UCWA)、 Lync 2013 行動用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="3addb-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="3addb-106">兩個行動效能計數器可協助您判斷您目前的使用量，並協助您規劃容量 Lync Server 2013 行動性服務 (Mcx)，以及想 UCWA 監視記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="3addb-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="3addb-107">Ucwa 的參考，該計數器類別是**LS:WEB – ucwa 的參考**。</span><span class="sxs-lookup"><span data-stu-id="3addb-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="3addb-108">Mobility Service (Mcx) 的計數器可**LS:WEB-行動通訊服務**] 類別底下。</span><span class="sxs-lookup"><span data-stu-id="3addb-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="3addb-109">計數器可監視如下：</span><span class="sxs-lookup"><span data-stu-id="3addb-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="3addb-110">透過 ucwa 的參考，或是有作用中的目前狀態訂閱 （自動連線的行動使用者數目） 的行動性服務 (Mcx) 登錄**Currently Active Session Count with Active Presence Subscriptions**]，這是目前的端點數目</span><span class="sxs-lookup"><span data-stu-id="3addb-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="3addb-111">透過 UCWA 或 Mobility Service 登錄**Currently Active Session Count**]，這是目前的端點數目</span><span class="sxs-lookup"><span data-stu-id="3addb-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="3addb-112">如果**Currently Active Session Count with Active Presence Subscriptions**和**Currently Active Session Count**之間的差異是小型經過一段時間，這表示大部分的行動裝置使用者具有總是連線裝置，例如 Android 或 Nokia 行動裝置 （適用於僅 Mcx)。</span><span class="sxs-lookup"><span data-stu-id="3addb-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="3addb-113">UCWA 總是連線的裝置包括執行 Lync 2013 行動用戶端的 Apple 和 Android 裝置）。</span><span class="sxs-lookup"><span data-stu-id="3addb-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="3addb-114">如果**Currently Active Session Count**是遠高於**Currently Active Session Count with Active Presence Subscriptions**，這表示更多使用者會使用背景端點裝置，例如 Apple iOS 裝置或 Windows Phone Mcx 底下。</span><span class="sxs-lookup"><span data-stu-id="3addb-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="3addb-115">（在 Windows Phone 是唯一的 Lync 2013 行動用戶端，會註冊為這）。</span><span class="sxs-lookup"><span data-stu-id="3addb-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="3addb-116">您應該根據您預期的使用狀況、 容量規劃的結果，並持續監控 Mobility Service 和其他前端伺服器計數器的**Currently Active Session Count with Active Presence Subscriptions**及**Currently Active Session Count**效能計數器設定限制。</span><span class="sxs-lookup"><span data-stu-id="3addb-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="3addb-117">您所設定的限制應該能夠讓您評估伺服器容量，當容量不足時會引發警示。</span><span class="sxs-lookup"><span data-stu-id="3addb-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="3addb-118">若要決定適當的限制，您需要先判斷多少記憶體使用的 Mobility Service 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="3addb-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="3addb-119">監視計數器，以決定當您需要額外容量計劃根據下列公式：</span><span class="sxs-lookup"><span data-stu-id="3addb-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="3addb-120">總記憶體使用 Mcx 行動性服務 (MB) = 164 + (400 + 134) / 1024年\* **Currently Active Session Count with Active Presence Subscriptions** ] + 400 / 1024年\*(]**Currently Active Session Count** – [ **Currently Active Session Count with Active Presence Subscriptions**)</span><span class="sxs-lookup"><span data-stu-id="3addb-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3addb-121">Microsoft Lync Server 2010 Capacity Calculator 是預先填入所有啟用至判斷需求將會針對伺服器，包括 CPU、 記憶體及硬碟 planner 公式的試算表。</span><span class="sxs-lookup"><span data-stu-id="3addb-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="3addb-122">您可以下載試算表和相關文件：<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="3addb-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="3addb-123">前端伺服器所需記憶體不足，無法在容錯移轉情況中支援 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="3addb-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="3addb-124">您可以監視前端伺服器上目前可用的記憶體使用**記憶體\\Available Mbytes**計數器，或使用先前所述，若要規劃您預計要使用的行動性服務的記憶體量的方程式。</span><span class="sxs-lookup"><span data-stu-id="3addb-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="3addb-125">如果在前端伺服器上可用的記憶體量低於 1500 MB 計劃的預期的行動使用者數目時，您需要新增更多的硬體，以支援 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="3addb-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="3addb-126">如需詳細資訊，請參閱作業文件中的[Lync Server 2013 的效能監控行動性](lync-server-2013-monitoring-mobility-for-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="3addb-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3addb-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3addb-127">See Also</span></span>


[<span data-ttu-id="3addb-128">Lync Server 2013 的效能監控行動性</span><span class="sxs-lookup"><span data-stu-id="3addb-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

