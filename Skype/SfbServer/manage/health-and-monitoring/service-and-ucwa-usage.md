---
title: 在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814243"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="25de0-103">在商務用 Skype Server 中監視行動服務和 UCWA 使用狀況</span><span class="sxs-lookup"><span data-stu-id="25de0-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="25de0-104">**摘要：** 在商務用 Skype Server 中管理行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="25de0-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="25de0-105">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="25de0-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="25de0-106">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="25de0-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="25de0-107">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="25de0-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="25de0-108">您應該定期監視商務用 Skype Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 所使用的 CPU 和記憶體。</span><span class="sxs-lookup"><span data-stu-id="25de0-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="25de0-109">若要監視使用狀況，您可以使用下列各項：</span><span class="sxs-lookup"><span data-stu-id="25de0-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="25de0-110">**針對整合通訊網頁 API (UCWA) ：**</span><span class="sxs-lookup"><span data-stu-id="25de0-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="25de0-111">網際網路資訊服務中的 **LyncUcwa** 工作者進程 (IIS) 管理員。</span><span class="sxs-lookup"><span data-stu-id="25de0-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="25de0-112">在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="25de0-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="25de0-113">[CPU] 和 [Processor] 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="25de0-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="25de0-114">在大多數的部署中，UCWA CPU 使用量的平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="25de0-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="25de0-115">記憶體使用量應該位於 [監視器中為商務用 Skype 伺服器的伺服器記憶體容量限制](server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="25de0-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="25de0-116">除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，以協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="25de0-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="25de0-117">**LS：網路節流和 Authentication\WEB-總處理中的要求**，表示伺服器上的擱置 WEB 要求數目。</span><span class="sxs-lookup"><span data-stu-id="25de0-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="25de0-118">當此計數器達到10000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="25de0-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="25de0-119">**ASP.NET\Requests Queued** (應該永遠為零)。</span><span class="sxs-lookup"><span data-stu-id="25de0-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="25de0-120">如果您達到或超過這些值，您應該重新取得容量規劃，以確定 CPU 大小是否正確，以及主控 web 服務之電腦的核心和記憶體數目。</span><span class="sxs-lookup"><span data-stu-id="25de0-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="25de0-121">**若為行動服務 (Mcx) ：**</span><span class="sxs-lookup"><span data-stu-id="25de0-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="25de0-122">Internet Information Services 中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作者進程 (IIS) 管理員。</span><span class="sxs-lookup"><span data-stu-id="25de0-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="25de0-123">在 [工作者處理序] 窗格中，查看 [CPU %] 和 [私用位元組 (KB)] (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="25de0-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="25de0-124">[CPU] 和 [Processor] 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="25de0-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="25de0-125">在大多數的部署中，行動性服務 CPU 使用量的平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="25de0-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="25de0-126">記憶體使用量應該位於 [監視器中為商務用 Skype 伺服器的伺服器記憶體容量限制](server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="25de0-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="25de0-127">除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="25de0-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="25de0-128">**ASP.NET v2.0.50727\Requests Current**，指出伺服器上的擱置 Web 要求數。</span><span class="sxs-lookup"><span data-stu-id="25de0-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="25de0-129">當此計數器達到5000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="25de0-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="25de0-130">**ASP.NET\Requests Queued** (應該永遠為零)。</span><span class="sxs-lookup"><span data-stu-id="25de0-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="25de0-131">如果您達到或超過這些值，您應該重新查看並重新計算您的容量規劃，以瞭解主控 web 服務之電腦的 CPU、核心數目及記憶體大小是否正確。</span><span class="sxs-lookup"><span data-stu-id="25de0-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="25de0-132">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="25de0-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="25de0-133">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="25de0-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="25de0-134">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="25de0-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="25de0-135">另請參閱</span><span class="sxs-lookup"><span data-stu-id="25de0-135">See also</span></span>

[<span data-ttu-id="25de0-136">監視商務用 Skype Server 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="25de0-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
