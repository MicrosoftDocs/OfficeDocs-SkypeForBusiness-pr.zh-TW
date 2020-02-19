---
title: Lync Server 2013： 連接埠摘要-DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c58a9b2e4932087945322db0bd8980191c7c5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="22a0c-102">Lync Server 2013 中的連接埠摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="22a0c-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a0c-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="22a0c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="22a0c-104">單一 Director 的防火牆連接埠需求是由用來建立從內部介面或反向 proxy 內部面向網路 Director 與通訊的連接埠所組成。</span><span class="sxs-lookup"><span data-stu-id="22a0c-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="22a0c-105">預設的 Microsoft Lync Server 2013 所預期的 HTTP/TCP 8080 和 HTTPS/TCP 4443 指向 Director，開啟從反向 proxy 的連接埠以及前端集區與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="22a0c-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="22a0c-106">此外，必須是工作階段初始通訊協定 (SIP) 通訊的 Edge Server 內部介面從指向 Director 與前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="22a0c-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="22a0c-107">SIP 通訊協定使用 SIP/MTLS/TCP 5061 從 Edge Server 至前端集區與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="22a0c-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="22a0c-108">也必須建立允許 SIP/MTLS/TCP 5061 通訊來自 Director、 前端集區與前端伺服器到 Edge Server 內部介面的規則。</span><span class="sxs-lookup"><span data-stu-id="22a0c-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="22a0c-109">單一 Director 連接埠和防火牆定義的通訊協定</span><span class="sxs-lookup"><span data-stu-id="22a0c-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22a0c-110">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="22a0c-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="22a0c-111">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="22a0c-111">Source IP address</span></span></th>
<th><span data-ttu-id="22a0c-112">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="22a0c-112">Destination IP address</span></span></th>
<th><span data-ttu-id="22a0c-113">附註</span><span class="sxs-lookup"><span data-stu-id="22a0c-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22a0c-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="22a0c-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="22a0c-115">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="22a0c-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="22a0c-116">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="22a0c-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="22a0c-117">先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 與前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="22a0c-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a0c-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="22a0c-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="22a0c-119">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="22a0c-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="22a0c-120">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="22a0c-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="22a0c-121">先由反向 proxy 的外部端接收，通訊會傳送至 Director HLB VIP 與前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="22a0c-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a0c-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="22a0c-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="22a0c-123">Director</span><span class="sxs-lookup"><span data-stu-id="22a0c-123">Director</span></span></p></td>
<td><p><span data-ttu-id="22a0c-124">前端集區或前端伺服器</span><span class="sxs-lookup"><span data-stu-id="22a0c-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="22a0c-125">Director HLB VIP 與前端伺服器或前端伺服器之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="22a0c-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a0c-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="22a0c-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="22a0c-127">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="22a0c-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="22a0c-128">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="22a0c-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="22a0c-129">Director 內部以及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="22a0c-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a0c-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="22a0c-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="22a0c-131">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="22a0c-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="22a0c-132">Director 的硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="22a0c-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="22a0c-133">Director 內部以及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="22a0c-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a0c-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="22a0c-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="22a0c-135">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="22a0c-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="22a0c-136">Director</span><span class="sxs-lookup"><span data-stu-id="22a0c-136">Director</span></span></p></td>
<td><p><span data-ttu-id="22a0c-137">從 SIP 通訊 Edge Server Director，以及前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="22a0c-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a0c-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="22a0c-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="22a0c-139">任何</span><span class="sxs-lookup"><span data-stu-id="22a0c-139">Any</span></span></p></td>
<td><p><span data-ttu-id="22a0c-140">Director</span><span class="sxs-lookup"><span data-stu-id="22a0c-140">Director</span></span></p></td>
<td><p><span data-ttu-id="22a0c-141">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="22a0c-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22a0c-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="22a0c-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="22a0c-143">任何</span><span class="sxs-lookup"><span data-stu-id="22a0c-143">Any</span></span></p></td>
<td><p><span data-ttu-id="22a0c-144">Director</span><span class="sxs-lookup"><span data-stu-id="22a0c-144">Director</span></span></p></td>
<td><p><span data-ttu-id="22a0c-145">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="22a0c-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22a0c-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="22a0c-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="22a0c-147">任何</span><span class="sxs-lookup"><span data-stu-id="22a0c-147">Any</span></span></p></td>
<td><p><span data-ttu-id="22a0c-148">Director</span><span class="sxs-lookup"><span data-stu-id="22a0c-148">Director</span></span></p></td>
<td><p><span data-ttu-id="22a0c-149">Centralized Logging Service 控制器 (ClsController.exe) 或代理程式 （ClsAgent.exe)commands 和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="22a0c-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

