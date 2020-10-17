---
title: Lync Server 2013：埠摘要-調整式 Director 集區（硬體負載平衡器）
description: Lync Server 2013：埠摘要-調整式 Director 集區（硬體負載平衡器）。
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
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564549"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="81901-103">Lync Server 2013 中的埠摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="81901-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81901-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="81901-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="81901-105">Director 集區的防火牆埠需求包含的埠，用來從 Edge Server 的內部介面或反向 proxy 的內部介面，建立與 Director 的通訊。</span><span class="sxs-lookup"><span data-stu-id="81901-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="81901-106">Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="81901-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="81901-107">此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="81901-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="81901-108">SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="81901-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="81901-109">一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="81901-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="81901-110">適用於防火牆的 Director 連接埠和通訊協定定義</span><span class="sxs-lookup"><span data-stu-id="81901-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81901-111">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="81901-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81901-112">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="81901-112">Source IP address</span></span></th>
<th><span data-ttu-id="81901-113">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="81901-113">Destination IP address</span></span></th>
<th><span data-ttu-id="81901-114">注意事項</span><span class="sxs-lookup"><span data-stu-id="81901-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81901-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="81901-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="81901-116">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="81901-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="81901-117">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="81901-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="81901-118">從反向 proxy 的外部端開始，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="81901-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81901-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="81901-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="81901-120">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="81901-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="81901-121">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="81901-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="81901-122">從反向 proxy 的外部端開始，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="81901-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81901-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="81901-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="81901-124">Director</span><span class="sxs-lookup"><span data-stu-id="81901-124">Director</span></span></p></td>
<td><p><span data-ttu-id="81901-125">前端伺服器或前端集區</span><span class="sxs-lookup"><span data-stu-id="81901-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="81901-126">Director HLB VIP 與前端伺服器之間的伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="81901-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81901-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="81901-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="81901-128">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="81901-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="81901-129">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="81901-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="81901-130">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="81901-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81901-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="81901-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="81901-132">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="81901-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="81901-133">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="81901-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="81901-134">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="81901-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81901-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="81901-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="81901-136">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="81901-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81901-137">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="81901-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="81901-138">從 Edge Server 到 Director 和前端伺服器的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="81901-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81901-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="81901-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="81901-140">任何</span><span class="sxs-lookup"><span data-stu-id="81901-140">Any</span></span></p></td>
<td><p><span data-ttu-id="81901-141">Director</span><span class="sxs-lookup"><span data-stu-id="81901-141">Director</span></span></p></td>
<td><p><span data-ttu-id="81901-142">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="81901-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81901-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="81901-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="81901-144">任何</span><span class="sxs-lookup"><span data-stu-id="81901-144">Any</span></span></p></td>
<td><p><span data-ttu-id="81901-145">Director</span><span class="sxs-lookup"><span data-stu-id="81901-145">Director</span></span></p></td>
<td><p><span data-ttu-id="81901-146">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="81901-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81901-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="81901-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="81901-148">任何</span><span class="sxs-lookup"><span data-stu-id="81901-148">Any</span></span></p></td>
<td><p><span data-ttu-id="81901-149">Director</span><span class="sxs-lookup"><span data-stu-id="81901-149">Director</span></span></p></td>
<td><p><span data-ttu-id="81901-150">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="81901-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

