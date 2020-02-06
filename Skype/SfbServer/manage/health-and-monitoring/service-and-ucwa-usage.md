---
title: 在商務用 Skype Server 中監視行動服務與 UCWA 使用量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在商務用 Skype Server 中管理行動服務（Mcx）和整合通訊網頁 API （UCWA）。
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817682"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="6bc72-103">在商務用 Skype Server 中監視行動服務與 UCWA 使用量</span><span class="sxs-lookup"><span data-stu-id="6bc72-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="6bc72-104">**摘要：** 在商務用 Skype Server 中管理行動服務（Mcx）和整合通訊網頁 API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="6bc72-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="6bc72-105">MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6bc72-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6bc72-106">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="6bc72-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6bc72-107">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="6bc72-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="6bc72-108">在持續性的基礎上，您應該監視商務用 Skype Server 行動服務（Mcx）和整合通訊網頁 API （UCWA）所使用的 CPU 和記憶體。</span><span class="sxs-lookup"><span data-stu-id="6bc72-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="6bc72-109">若要監視用法，您可以使用下列方法：</span><span class="sxs-lookup"><span data-stu-id="6bc72-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="6bc72-110">**針對整合通訊網頁 API （UCWA）：**</span><span class="sxs-lookup"><span data-stu-id="6bc72-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="6bc72-111">[網際網路資訊服務（IIS）管理員] 中的**LyncUcwa**工作進程。</span><span class="sxs-lookup"><span data-stu-id="6bc72-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="6bc72-112">在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。</span><span class="sxs-lookup"><span data-stu-id="6bc72-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="6bc72-113">**CPU**與**處理器**效能計數器。</span><span class="sxs-lookup"><span data-stu-id="6bc72-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="6bc72-114">在大部分的部署中，UCWA 的 CPU 使用量平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="6bc72-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="6bc72-115">記憶體使用量應該在監視器中的 [[商務用 Skype 伺服器的伺服器記憶體容量限制] 中](server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="6bc72-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="6bc72-116">除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，協助判斷伺服器何時以要求超載：</span><span class="sxs-lookup"><span data-stu-id="6bc72-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="6bc72-117">**LS：網路節流與 Authentication\WEB 總處理中的要求總數**，指出伺服器上的未決 WEB 要求數目。</span><span class="sxs-lookup"><span data-stu-id="6bc72-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="6bc72-118">當這個計數器達到10000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="6bc72-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="6bc72-119">**NET\Requests 已排入佇列**（應該總是為零）。</span><span class="sxs-lookup"><span data-stu-id="6bc72-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6bc72-120">如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 web 服務的電腦正確地調整 CPU 大小、核心和記憶體的數量。</span><span class="sxs-lookup"><span data-stu-id="6bc72-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="6bc72-121">**針對行動服務（Mcx）：**</span><span class="sxs-lookup"><span data-stu-id="6bc72-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="6bc72-122">[網際網路資訊服務（IIS）管理員] 中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作進程。</span><span class="sxs-lookup"><span data-stu-id="6bc72-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="6bc72-123">在 [**工作進程**] 窗格中，查看 [ **CPU%** ] 和 [**專用位元組（KB）** ] （記憶體）資料行。</span><span class="sxs-lookup"><span data-stu-id="6bc72-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="6bc72-124">**CPU**與**處理器**效能計數器。</span><span class="sxs-lookup"><span data-stu-id="6bc72-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="6bc72-125">在大部分的部署中，行動服務 CPU 使用量的平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="6bc72-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="6bc72-126">記憶體使用量應該在監視器中的 [[商務用 Skype 伺服器的伺服器記憶體容量限制] 中](server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="6bc72-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="6bc72-127">除了 CPU 和記憶體使用量計數器之外，您還可以使用下列 ASP.NET 效能計數器，協助判斷伺服器何時使用要求進行超載：</span><span class="sxs-lookup"><span data-stu-id="6bc72-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="6bc72-128">**ASP.NET v 2.0.50727 \ 請求 Current**，這表示伺服器上的未決 web 要求數目。</span><span class="sxs-lookup"><span data-stu-id="6bc72-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="6bc72-129">當這個計數器達到5000時，後續的要求將會失敗，並出現錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="6bc72-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="6bc72-130">**NET\Requests 已排入佇列**（應該總是為零）。</span><span class="sxs-lookup"><span data-stu-id="6bc72-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="6bc72-131">如果您達到或超過這些值，您應該重新進行容量規劃，以針對託管 web 服務的電腦正確地調整 CPU、核心數和記憶體大小。</span><span class="sxs-lookup"><span data-stu-id="6bc72-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="6bc72-132">MCX （行動服務）對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6bc72-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6bc72-133">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="6bc72-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6bc72-134">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="6bc72-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6bc72-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6bc72-135">See also</span></span>

[<span data-ttu-id="6bc72-136">監視商務用 Skype Server 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="6bc72-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
