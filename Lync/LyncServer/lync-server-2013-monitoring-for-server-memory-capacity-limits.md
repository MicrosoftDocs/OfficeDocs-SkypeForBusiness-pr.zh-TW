---
title: Lync Server 2013：監控伺服器記憶體容量限制
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
ms.openlocfilehash: 160d90a5a79291d18afdab00c23ff0a6726fa5b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531940"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="55bc3-102">在 Lync Server 2013 中監控伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="55bc3-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55bc3-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="55bc3-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="55bc3-104">本主題所述的容量規劃的資訊僅適用于 Lync 2010 行動用戶端和行動服務 (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="55bc3-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="55bc3-105">Lync Server 2013 （計畫工具）提供的整合通訊網頁 API (UCWA) （供 Lync 2013 行動用戶端使用）的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="55bc3-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="55bc3-106">兩個行動性效能計數器可協助您判斷目前的使用狀況，並協助您規劃 Lync Server 2013 行動性服務的容量 (Mcx) ，以及監視 UCWA 的記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="55bc3-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="55bc3-107">針對 UCWA，計數器類別為 **LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="55bc3-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="55bc3-108">針對行動服務 (Mcx) ，計數器位於類別 **LS： WEB Mobile Communication Service**。</span><span class="sxs-lookup"><span data-stu-id="55bc3-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="55bc3-109">要監視的計數器包括：</span><span class="sxs-lookup"><span data-stu-id="55bc3-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="55bc3-110">**目前使用中的會話計數與使用中狀態訂閱**，這是透過 UCWA 所註冊的端點數目，也就是具有使用中狀態訂閱的行動 (服務) ， (永不連線的行動使用者數目) </span><span class="sxs-lookup"><span data-stu-id="55bc3-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="55bc3-111">目前使用中的**會話計數**，也就是透過 UCWA 或行動性服務註冊的目前端點數目</span><span class="sxs-lookup"><span data-stu-id="55bc3-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="55bc3-112">如果 **目前使用中狀態訂閱** 和目前作用中的會話計數之間的差異， **目前的會話計數** 很小，這表示大多數行動裝置使用者都有一個永不連線的裝置，例如 Android 或 Nokia mobile Device (僅限 Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="55bc3-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="55bc3-113">UCWA always 連裝置，包括執行 Lync 2013 行動用戶端) 的 Apple 和 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="55bc3-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="55bc3-114">如果目前作用中的 **會話計數** 比 **目前使用中狀態訂閱目前使用中的會話計數**高，這表示有更多使用者在 Mcx 下使用背景端點裝置，例如 Apple IOS 裝置或 Windows Phone。</span><span class="sxs-lookup"><span data-stu-id="55bc3-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="55bc3-115"> (Windows Phone 是唯一會註冊為此) 的 Lync 2013 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="55bc3-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="55bc3-116">您應該根據預期的使用量、容量規劃結果，以及即時監控行動性服務和其他前端伺服器計數器，來設定目前作用中的 **會話計數與使用中狀態訂閱** 及目前使用中 **會話計數** 效能計數器的限制。</span><span class="sxs-lookup"><span data-stu-id="55bc3-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="55bc3-117">您設定的限制應可讓您評估伺服器容量，並在超出容量時引發警示。</span><span class="sxs-lookup"><span data-stu-id="55bc3-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="55bc3-118">若要判斷適當的限制，您必須先決定可在行動服務的前端伺服器上使用多少記憶體。</span><span class="sxs-lookup"><span data-stu-id="55bc3-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="55bc3-119">根據下列公式，監視計數器，以判斷何時需要規劃額外的容量：</span><span class="sxs-lookup"><span data-stu-id="55bc3-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="55bc3-120">Mcx 行動服務使用的總記憶體 (MB) = 164 + (400 + 134) /1024 目前作用中 \* **的會話計數與使用中的目前狀態訂閱** + 400/1024 (目前作用中的 \* **會話計數** – **目前使用中狀態訂閱的主動會話計數**) </span><span class="sxs-lookup"><span data-stu-id="55bc3-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="55bc3-121">Microsoft Lync Server 2010 容量計算機是預先填入的試算表，其可讓規劃人員判斷伺服器的需求（包括 CPU、記憶體和硬碟）。</span><span class="sxs-lookup"><span data-stu-id="55bc3-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="55bc3-122">您可以在下列位置下載試算表和相關聯的檔： <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="55bc3-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="55bc3-123">前端伺服器需要足夠的可用記憶體，以在容錯移轉的情況下支援行動性服務。</span><span class="sxs-lookup"><span data-stu-id="55bc3-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="55bc3-124">您可以使用 **可用記憶體（ \\ mb** ）計數器（或先前所述的方程式）來監視前端伺服器上目前可用的記憶體，以規劃預期行動服務所要使用的記憶體量。</span><span class="sxs-lookup"><span data-stu-id="55bc3-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="55bc3-125">若當您規劃預期的行動使用者數目時，前端伺服器上可用的記憶體量低於 1500 MB，您需要新增更多硬體以支援行動性服務。</span><span class="sxs-lookup"><span data-stu-id="55bc3-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="55bc3-126">如需詳細資訊，請參閱 Operations 檔中的 [監控在 Lync Server 2013 中的行動性效能](lync-server-2013-monitoring-mobility-for-performance.md) 。</span><span class="sxs-lookup"><span data-stu-id="55bc3-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="55bc3-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55bc3-127">See Also</span></span>


[<span data-ttu-id="55bc3-128">在 Lync Server 2013 中監控行動性以取得效能</span><span class="sxs-lookup"><span data-stu-id="55bc3-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

