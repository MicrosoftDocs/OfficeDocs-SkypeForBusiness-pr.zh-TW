---
title: Lync Server 2013： 連接埠摘要-調整式 Director 集區、 硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72d059cc32015409377ab0b12bbe8c3ebc7da7d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="5596a-102">連接埠摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="5596a-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5596a-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="5596a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5596a-104">Director 集區的防火牆連接埠需求用來建立 Edge Server 或向內介面的反向 proxy 內部介面從 Director 與通訊的連接埠所組成。</span><span class="sxs-lookup"><span data-stu-id="5596a-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="5596a-105">預設的 Microsoft Lync Server 2013 所預期的 HTTP/TCP 8080 和 HTTPS/TCP 4443 指向 Director，開啟從反向 proxy 的連接埠以及前端集區與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5596a-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="5596a-106">此外，必須是工作階段初始通訊協定 (SIP) 通訊的 Edge Server 內部介面從指向 Director 與前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5596a-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="5596a-107">SIP 通訊協定使用 SIP/MTLS/TCP 5061 從 Edge Server 至前端集區與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5596a-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="5596a-108">也必須建立允許 SIP/MTLS/TCP 5061 通訊來自 Director、 前端集區與前端伺服器到 Edge Server 內部介面的規則。</span><span class="sxs-lookup"><span data-stu-id="5596a-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="5596a-109">適用於防火牆的 Director 連接埠和通訊協定定義</span><span class="sxs-lookup"><span data-stu-id="5596a-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5596a-110">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5596a-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5596a-111">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5596a-111">Source IP address</span></span></th>
<th><span data-ttu-id="5596a-112">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5596a-112">Destination IP address</span></span></th>
<th><span data-ttu-id="5596a-113">附註</span><span class="sxs-lookup"><span data-stu-id="5596a-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5596a-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="5596a-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="5596a-115">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="5596a-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="5596a-116">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="5596a-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="5596a-117">先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="5596a-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5596a-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="5596a-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="5596a-119">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="5596a-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="5596a-120">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="5596a-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="5596a-121">先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="5596a-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5596a-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="5596a-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="5596a-123">Director</span><span class="sxs-lookup"><span data-stu-id="5596a-123">Director</span></span></p></td>
<td><p><span data-ttu-id="5596a-124">前端伺服器或前端集區</span><span class="sxs-lookup"><span data-stu-id="5596a-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="5596a-125">Director HLB VIP 與前端伺服器之間的伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="5596a-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5596a-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="5596a-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="5596a-127">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="5596a-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="5596a-128">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="5596a-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="5596a-129">Director 內部以及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="5596a-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5596a-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="5596a-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="5596a-131">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="5596a-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="5596a-132">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="5596a-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="5596a-133">Director 內部以及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="5596a-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5596a-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="5596a-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="5596a-135">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5596a-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5596a-136">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="5596a-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="5596a-137">從 SIP 通訊 Edge Server 至 Director 與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5596a-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5596a-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="5596a-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="5596a-139">任何</span><span class="sxs-lookup"><span data-stu-id="5596a-139">Any</span></span></p></td>
<td><p><span data-ttu-id="5596a-140">Director</span><span class="sxs-lookup"><span data-stu-id="5596a-140">Director</span></span></p></td>
<td><p><span data-ttu-id="5596a-141">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="5596a-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5596a-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="5596a-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="5596a-143">任何</span><span class="sxs-lookup"><span data-stu-id="5596a-143">Any</span></span></p></td>
<td><p><span data-ttu-id="5596a-144">Director</span><span class="sxs-lookup"><span data-stu-id="5596a-144">Director</span></span></p></td>
<td><p><span data-ttu-id="5596a-145">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="5596a-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5596a-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="5596a-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="5596a-147">任何</span><span class="sxs-lookup"><span data-stu-id="5596a-147">Any</span></span></p></td>
<td><p><span data-ttu-id="5596a-148">Director</span><span class="sxs-lookup"><span data-stu-id="5596a-148">Director</span></span></p></td>
<td><p><span data-ttu-id="5596a-149">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="5596a-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

