---
title: 監視商務用 Skype Server 中的伺服器記憶體容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '摘要: 瞭解如何監視商務用 Skype Server 中的伺服器記憶體容量限制。'
ms.openlocfilehash: f089ab9b5be693872754691050133ad27e992896
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188692"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a><span data-ttu-id="a4f81-103">監視商務用 Skype Server 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="a4f81-103">Monitor for server memory capacity limits in Skype for Business Server</span></span>
 
<span data-ttu-id="a4f81-104">**摘要:** 瞭解如何在商務用 Skype Server 中監視伺服器記憶體容量限制。</span><span class="sxs-lookup"><span data-stu-id="a4f81-104">**Summary:** Learn how to monitor for server memory capacity limits in Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a4f81-105">本主題中參照容量規劃的資訊, 只適用于 Lync 2010 行動用戶端和行動服務 (Mcx)。</span><span class="sxs-lookup"><span data-stu-id="a4f81-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="a4f81-106">Lync 2013 行動用戶端所使用之整合通訊網頁 API (UCWA) 的容量規劃是由 Lync Server 2013、規劃工具所提供。</span><span class="sxs-lookup"><span data-stu-id="a4f81-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span> 

> [!NOTE]
> <span data-ttu-id="a4f81-107">MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="a4f81-107">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a4f81-108">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="a4f81-108">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a4f81-109">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a4f81-109">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a4f81-110">兩個行動效能計數器可協助您判斷目前的使用方式, 並協助您規劃商務用 Skype Server 行動服務 (Mcx) 的容量, 以及監視 UCWA 的記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="a4f81-110">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Skype for Business Server Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="a4f81-111">針對 UCWA, 計數器類別是**LS: WEB-UCWA**。</span><span class="sxs-lookup"><span data-stu-id="a4f81-111">For UCWA, the counter category is **LS:WEB - UCWA**.</span></span> <span data-ttu-id="a4f81-112">針對行動服務 (Mcx), 計數器位於類別**LS: WEB Mobile 通訊服務**。</span><span class="sxs-lookup"><span data-stu-id="a4f81-112">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="a4f81-113">要監視的計數器包括:</span><span class="sxs-lookup"><span data-stu-id="a4f81-113">The counters to monitor are:</span></span>
  
- <span data-ttu-id="a4f81-114">**目前使用中的目前狀態訂閱的目前活動會話計數**, 也就是透過 UCWA 或行動服務 (Mcx) 提供作用中的目前狀態訂閱 (永不連線的行動使用者數目)</span><span class="sxs-lookup"><span data-stu-id="a4f81-114">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>
    
- <span data-ttu-id="a4f81-115">目前使用中的**會話計數**, 是透過 UCWA 或行動服務註冊的目前端點數目</span><span class="sxs-lookup"><span data-stu-id="a4f81-115">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>
    
<span data-ttu-id="a4f81-116">如果**目前使用中狀態訂閱的目前活動會話計數**與**目前的活動會話計數**相差較小, 這表示大多數行動裝置使用者都有一個一直連線的裝置, 例如 Android 或Nokia 行動裝置 (僅適用于 Mcx)。</span><span class="sxs-lookup"><span data-stu-id="a4f81-116">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="a4f81-117">UCWA [永不連線的裝置] 包括執行 Lync 2013 行動用戶端的 Apple 和 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="a4f81-117">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="a4f81-118">如果**目前的活動會話計數**比目前使用中**的目前狀態訂閱**要高許多, 這表示您的使用者使用的是背景端點裝置, 例如 Apple IOS 裝置或 Windows PhoneMcx.</span><span class="sxs-lookup"><span data-stu-id="a4f81-118">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="a4f81-119">(Windows Phone 是唯一的 Lync 2013 行動用戶端, 會以這種方式註冊)。</span><span class="sxs-lookup"><span data-stu-id="a4f81-119">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>
  
<span data-ttu-id="a4f81-120">您應該根據預期使用量、容量規劃結果及持續監測的方式, 在目前的使用中**狀態訂閱**和**目前的活動會話計數**效能計數器設定限制行動服務與其他前端伺服器計數器。</span><span class="sxs-lookup"><span data-stu-id="a4f81-120">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="a4f81-121">您設定的限制應該能讓您評估伺服器容量, 並在超過容量時引發警示。</span><span class="sxs-lookup"><span data-stu-id="a4f81-121">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>
  
<span data-ttu-id="a4f81-122">若要判斷適當的限制, 您必須先決定可在行動服務的前端伺服器上使用多少記憶體。</span><span class="sxs-lookup"><span data-stu-id="a4f81-122">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="a4f81-123">根據下列公式監視計數器, 以判斷您何時需要規劃額外的容量:</span><span class="sxs-lookup"><span data-stu-id="a4f81-123">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>
  
<span data-ttu-id="a4f81-124">Mcx 行動服務 (MB) 所使用的記憶體總量 = 164 + (400 + 134)/1024 \***目前使用中目前狀態訂閱的活動會話計數**+ 400/1024 \* (**目前** - 作用中會話計數**目前使用中的會話計數作用中的目前狀態訂閱**)</span><span class="sxs-lookup"><span data-stu-id="a4f81-124">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* ( **Currently Active Session Count** - **Currently Active Session Count with Active Presence Subscriptions**)</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a4f81-125">Microsoft Lync Server 2010 容量計算機是預先填入了所有公式的試算表, 可讓 planner 判斷商務用 Skype 伺服器 (包括 CPU、記憶體及硬碟) 的需求。</span><span class="sxs-lookup"><span data-stu-id="a4f81-125">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the Skype for Business servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="a4f81-126">您可以[下載試算表及相關聯的檔](https://go.microsoft.com/fwlink/p/?LinkID=212657)。</span><span class="sxs-lookup"><span data-stu-id="a4f81-126">You can [download the spreadsheet and an associated document](https://go.microsoft.com/fwlink/p/?LinkID=212657).</span></span> 
  
<span data-ttu-id="a4f81-127">前端伺服器需要足夠的可用記憶體, 才能在容錯移轉情況下支援行動服務。</span><span class="sxs-lookup"><span data-stu-id="a4f81-127">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="a4f81-128">您可以使用**Memory\Available mb**計數器監視前端伺服器上目前可用的記憶體, 或使用先前所述的方程式, 來規劃預期行動服務要使用的記憶體量。</span><span class="sxs-lookup"><span data-stu-id="a4f81-128">You can monitor the current available memory on the Front End Server by using the **Memory\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>
  
<span data-ttu-id="a4f81-129">如果在您規劃預期的行動使用者數量時, 前端伺服器上可用的記憶體量低於 1500 MB, 您需要新增更多硬體來支援行動服務。</span><span class="sxs-lookup"><span data-stu-id="a4f81-129">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="a4f81-130">如需詳細資訊, 請參閱在作業檔中[監視商務用 Skype 伺服器的效能](monitor-mobility-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f81-130">For more details, see [Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4f81-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a4f81-131">See also</span></span>

[<span data-ttu-id="a4f81-132">監視行動在商務用 Skype Server 中的效能</span><span class="sxs-lookup"><span data-stu-id="a4f81-132">Monitor mobility for performance in Skype for Business Server</span></span>](monitor-mobility-performance.md)
