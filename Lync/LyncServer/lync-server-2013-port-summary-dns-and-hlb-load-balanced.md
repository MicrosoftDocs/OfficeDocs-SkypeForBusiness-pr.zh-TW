---
title: Lync Server 2013：埠摘要-DNS 與 HLB 負載平衡
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
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527940"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="11464-102">Lync Server 2013 中的埠摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="11464-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11464-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="11464-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="11464-104">單一 Director 的防火牆埠需求包含用於從反向 proxy 的內部介面或內部的網路與 Director 建立通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="11464-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="11464-105">Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="11464-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="11464-106">此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="11464-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="11464-107">SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="11464-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="11464-108">一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="11464-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="11464-109">防火牆定義的單一 Director 埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="11464-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11464-110">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="11464-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11464-111">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="11464-111">Source IP address</span></span></th>
<th><span data-ttu-id="11464-112">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="11464-112">Destination IP address</span></span></th>
<th><span data-ttu-id="11464-113">注意事項</span><span class="sxs-lookup"><span data-stu-id="11464-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11464-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="11464-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="11464-115">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="11464-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="11464-116">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="11464-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="11464-117">由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="11464-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11464-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="11464-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="11464-119">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="11464-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="11464-120">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="11464-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="11464-121">由反向 proxy 的外部端最初接收，通訊會傳送到 Director HLB VIP 和前端伺服器 web 服務。</span><span class="sxs-lookup"><span data-stu-id="11464-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11464-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="11464-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="11464-123">Director</span><span class="sxs-lookup"><span data-stu-id="11464-123">Director</span></span></p></td>
<td><p><span data-ttu-id="11464-124">前端集區或前端伺服器</span><span class="sxs-lookup"><span data-stu-id="11464-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="11464-125">Director HLB VIP 和前端伺服器或前端伺服器之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="11464-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11464-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="11464-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="11464-127">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="11464-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="11464-128">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="11464-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="11464-129">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="11464-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11464-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="11464-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="11464-131">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="11464-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="11464-132">Director 硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="11464-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="11464-133">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="11464-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11464-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="11464-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="11464-135">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="11464-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="11464-136">Director</span><span class="sxs-lookup"><span data-stu-id="11464-136">Director</span></span></p></td>
<td><p><span data-ttu-id="11464-137">從 Edge Server 到 Director 及前端伺服器的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="11464-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11464-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="11464-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="11464-139">任何</span><span class="sxs-lookup"><span data-stu-id="11464-139">Any</span></span></p></td>
<td><p><span data-ttu-id="11464-140">Director</span><span class="sxs-lookup"><span data-stu-id="11464-140">Director</span></span></p></td>
<td><p><span data-ttu-id="11464-141">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="11464-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11464-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="11464-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="11464-143">任何</span><span class="sxs-lookup"><span data-stu-id="11464-143">Any</span></span></p></td>
<td><p><span data-ttu-id="11464-144">Director</span><span class="sxs-lookup"><span data-stu-id="11464-144">Director</span></span></p></td>
<td><p><span data-ttu-id="11464-145">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="11464-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11464-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="11464-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="11464-147">任何</span><span class="sxs-lookup"><span data-stu-id="11464-147">Any</span></span></p></td>
<td><p><span data-ttu-id="11464-148">Director</span><span class="sxs-lookup"><span data-stu-id="11464-148">Director</span></span></p></td>
<td><p><span data-ttu-id="11464-149">集中式記錄服務控制器 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="11464-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

