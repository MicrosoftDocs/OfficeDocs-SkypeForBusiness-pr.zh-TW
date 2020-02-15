---
title: 'Lync Server 2013: Monitoring Mobility Service 和 ucwa 的參考的使用狀況'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8fbdd2e411f3613519278f807caed334955810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="bbb3f-102">監控 Mobility Service 和 ucwa 的參考 Lync Server 2013 中的使用狀況</span><span class="sxs-lookup"><span data-stu-id="bbb3f-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb3f-103">_**上次修改主題：** 2013年-02-14_</span><span class="sxs-lookup"><span data-stu-id="bbb3f-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="bbb3f-104">持續，您應監視的 CPU 和記憶體所使用的 Lync Server 行動性服務 (Mcx) 和 Unified Communications Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="bbb3f-105">若要監視流量，您可以使用下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="bbb3f-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="bbb3f-106">**Unified 的 Communications web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="bbb3f-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="bbb3f-107">在 [網際網路資訊服務 (IIS) 管理員**LyncUcwa**工作者處理序。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="bbb3f-108">在 [工作者處理序]\*\*\*\* 窗格中，查看 [CPU %]\*\*\*\* 和 [私用位元組 (KB)]\*\*\*\* (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="bbb3f-109">[CPU]\*\*\*\* 和 [Processor]\*\*\*\* 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="bbb3f-110">對於大多數的部署，UCWA CPU 使用量應低於 15%平均。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="bbb3f-111">記憶體使用量應該改在[監視伺服器的記憶體容量限制 Lync Server 2013 中](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制內。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="bbb3f-112">除了 CPU 和記憶體使用量計數器，您可以使用下列效能計數器來協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="bbb3f-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="bbb3f-113">**LS:WEB – 節流及驗證\\WEB – 在處理中的總要求數**，這表示暫止的伺服器上的 web 要求的數目。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="bbb3f-114">當此計數器達到 10000 時，後續要求將會失敗，則錯誤訊息: 「 503-服務無法使用 」。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="bbb3f-115">**ASP.NET\\要求排入佇列**（應該永遠為零）。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbb3f-116">如果您達到或超過這些值，您應該回顧和重新計算您的容量規劃的 CPU 核心和記憶體主控 Web 服務的電腦數目正確調整大小。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="bbb3f-117">**行動性服務 (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="bbb3f-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="bbb3f-118">**CSIntMcxAppPool**和**CSExtMcxAppPool**工作者處理序在網際網路資訊服務 (IIS) 管理員] 中。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="bbb3f-119">在 [工作者處理序]\*\*\*\* 窗格中，查看 [CPU %]\*\*\*\* 和 [私用位元組 (KB)]\*\*\*\* (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="bbb3f-120">[CPU]\*\*\*\* 和 [Processor]\*\*\*\* 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="bbb3f-121">對於大多數的部署，Mobility Service CPU 使用量應低於 15%，平均。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="bbb3f-122">記憶體使用量應該改在[監視伺服器的記憶體容量限制 Lync Server 2013 中](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制內。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="bbb3f-123">除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="bbb3f-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="bbb3f-124">**ASP.NET v2.0.50727]\\要求目前**，這表示暫止的伺服器上的 web 要求的數目。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="bbb3f-125">當此計數器達到 5000 時，後續要求將會失敗則錯誤訊息: 「 503-服務無法使用 」。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="bbb3f-126">**ASP.NET\\要求排入佇列**（應該永遠為零）。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbb3f-127">如果您達到或超過這些值，您應該回顧並重新整理您的容量規劃的 CPU 核心和記憶體主控 Web 服務的電腦數目正確調整大小。</span><span class="sxs-lookup"><span data-stu-id="bbb3f-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbb3f-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bbb3f-128">See Also</span></span>


[<span data-ttu-id="bbb3f-129">監控的 Lync Server 2013 中的伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="bbb3f-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

