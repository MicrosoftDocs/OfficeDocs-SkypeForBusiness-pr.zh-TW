---
title: Lync Server 2013：監控行動服務和 UCWA 使用狀況
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
ms.openlocfilehash: 2248bbd2eea4bb9204a98b5c5805ef196cbf2015
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531790"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="519e8-102">在 Lync Server 2013 中監控行動服務和 UCWA 使用狀況</span><span class="sxs-lookup"><span data-stu-id="519e8-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="519e8-103">_**主題上次修改日期：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="519e8-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="519e8-104">在不斷的基礎上，您應該監視 Lync Server 行動服務 (Mcx) 和整合通訊網頁 API (UCWA) 所使用的 CPU 和記憶體。</span><span class="sxs-lookup"><span data-stu-id="519e8-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="519e8-105">若要監視使用狀況，您可以使用下列各項：</span><span class="sxs-lookup"><span data-stu-id="519e8-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="519e8-106">**針對整合通訊網頁 API (UCWA) ：**</span><span class="sxs-lookup"><span data-stu-id="519e8-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="519e8-107">網際網路資訊服務中的 **LyncUcwa** 工作者進程 (IIS) 管理員。</span><span class="sxs-lookup"><span data-stu-id="519e8-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="519e8-108">在 [工作者處理序]\*\*\*\* 窗格中，查看 [CPU %]\*\*\*\* 和 [私用位元組 (KB)]\*\*\*\* (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="519e8-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="519e8-109">[CPU]\*\*\*\* 和 [Processor]\*\*\*\* 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="519e8-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="519e8-110">在大多數的部署中，UCWA CPU 使用量的平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="519e8-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="519e8-111">記憶體使用量應該在 [Lync server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="519e8-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="519e8-112">除了 CPU 和記憶體使用量計數器之外，您還可以使用下列效能計數器，以協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="519e8-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="519e8-113">**LS：網路–節流和驗證 \\WEB –正在處理的要求總數**，表示伺服器上的擱置 web 要求數目。</span><span class="sxs-lookup"><span data-stu-id="519e8-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="519e8-114">當此計數器達到10000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="519e8-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="519e8-115">**ASP.NET \\佇列** (的要求應永遠為零) 。</span><span class="sxs-lookup"><span data-stu-id="519e8-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="519e8-116">如果您達到或超過這些值，您應該重新取得容量規劃，以確定 CPU 大小是否正確，以及主控 Web 服務之電腦的核心和記憶體數目。</span><span class="sxs-lookup"><span data-stu-id="519e8-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="519e8-117">**若為行動服務 (Mcx) ：**</span><span class="sxs-lookup"><span data-stu-id="519e8-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="519e8-118">Internet Information Services 中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作者進程 (IIS) 管理員。</span><span class="sxs-lookup"><span data-stu-id="519e8-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="519e8-119">在 [工作者處理序]\*\*\*\* 窗格中，查看 [CPU %]\*\*\*\* 和 [私用位元組 (KB)]\*\*\*\* (記憶體) 欄。</span><span class="sxs-lookup"><span data-stu-id="519e8-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="519e8-120">[CPU]\*\*\*\* 和 [Processor]\*\*\*\* 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="519e8-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="519e8-121">在大多數的部署中，行動性服務 CPU 使用量的平均應低於15%。</span><span class="sxs-lookup"><span data-stu-id="519e8-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="519e8-122">記憶體使用量應該在 [Lync server 2013 中監控伺服器記憶體容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)所述的限制範圍內。</span><span class="sxs-lookup"><span data-stu-id="519e8-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="519e8-123">除了 CPU 和記憶體使用量計數器，您也可以使用下列 ASP.NET 效能計數器來協助判斷伺服器何時超載要求：</span><span class="sxs-lookup"><span data-stu-id="519e8-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="519e8-124">**ASP.NET v v2.0.50727 \\要求 Current**，這表示伺服器上的擱置 web 要求數目。</span><span class="sxs-lookup"><span data-stu-id="519e8-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="519e8-125">當此計數器達到5000時，後續的要求會失敗，並顯示錯誤訊息「503-服務無法使用」。</span><span class="sxs-lookup"><span data-stu-id="519e8-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="519e8-126">**ASP.NET \\佇列** (的要求應永遠為零) 。</span><span class="sxs-lookup"><span data-stu-id="519e8-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="519e8-127">如果您達到或超過這些值，您應該重新查看並重新計算您的容量規劃，以瞭解主控 Web 服務之電腦的 CPU、核心數目及記憶體大小是否正確。</span><span class="sxs-lookup"><span data-stu-id="519e8-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="519e8-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="519e8-128">See Also</span></span>


[<span data-ttu-id="519e8-129">在 Lync Server 2013 中監控伺服器記憶體容量限制</span><span class="sxs-lookup"><span data-stu-id="519e8-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

