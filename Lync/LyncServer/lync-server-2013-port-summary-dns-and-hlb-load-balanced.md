---
title: Lync Server 2013：埠摘要-DNS 與 HLB 負載平衡
description: Lync Server 2013：埠摘要-DNS 與 HLB 負載平衡。
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
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543129"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="dda50-103">Lync Server 2013 中的埠摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="dda50-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda50-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="dda50-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="dda50-105">單一 Director 的防火牆埠需求包含用於從反向 proxy 的內部介面或內部的網路與 Director 建立通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="dda50-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="dda50-106">Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dda50-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="dda50-107">此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="dda50-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="dda50-108">SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="dda50-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="dda50-109">一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="dda50-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="dda50-110">防火牆定義的單一 Director 埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="dda50-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dda50-111">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="dda50-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dda50-112">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dda50-112">Source IP address</span></span></th>
<th><span data-ttu-id="dda50-113">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dda50-113">Destination IP address</span></span></th>
<th><span data-ttu-id="dda50-114">注意事項</span><span class="sxs-lookup"><span data-stu-id="dda50-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dda50-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="dda50-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="dda50-116">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="dda50-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="dda50-117">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="dda50-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dda50-118">由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="dda50-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda50-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="dda50-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="dda50-120">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="dda50-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="dda50-121">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="dda50-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dda50-122">由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="dda50-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda50-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="dda50-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="dda50-124">Director</span><span class="sxs-lookup"><span data-stu-id="dda50-124">Director</span></span></p></td>
<td><p><span data-ttu-id="dda50-125">前端集區或前端伺服器</span><span class="sxs-lookup"><span data-stu-id="dda50-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="dda50-126">Director HLB VIP 和前端伺服器或前端伺服器之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="dda50-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda50-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="dda50-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="dda50-128">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="dda50-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="dda50-129">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="dda50-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dda50-130">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="dda50-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda50-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="dda50-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="dda50-132">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="dda50-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="dda50-133">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="dda50-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="dda50-134">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="dda50-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda50-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="dda50-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="dda50-136">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="dda50-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dda50-137">Director</span><span class="sxs-lookup"><span data-stu-id="dda50-137">Director</span></span></p></td>
<td><p><span data-ttu-id="dda50-138">從 Edge Server 到 Director 及前端伺服器的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="dda50-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda50-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="dda50-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="dda50-140">任何</span><span class="sxs-lookup"><span data-stu-id="dda50-140">Any</span></span></p></td>
<td><p><span data-ttu-id="dda50-141">Director</span><span class="sxs-lookup"><span data-stu-id="dda50-141">Director</span></span></p></td>
<td><p><span data-ttu-id="dda50-142">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="dda50-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda50-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="dda50-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="dda50-144">任何</span><span class="sxs-lookup"><span data-stu-id="dda50-144">Any</span></span></p></td>
<td><p><span data-ttu-id="dda50-145">Director</span><span class="sxs-lookup"><span data-stu-id="dda50-145">Director</span></span></p></td>
<td><p><span data-ttu-id="dda50-146">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="dda50-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda50-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="dda50-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="dda50-148">任何</span><span class="sxs-lookup"><span data-stu-id="dda50-148">Any</span></span></p></td>
<td><p><span data-ttu-id="dda50-149">Director</span><span class="sxs-lookup"><span data-stu-id="dda50-149">Director</span></span></p></td>
<td><p><span data-ttu-id="dda50-150">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="dda50-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

