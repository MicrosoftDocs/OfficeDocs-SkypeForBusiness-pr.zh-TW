---
title: Lync Server 2013：連接埠摘要 - 調整式 Director 集區 (硬體負載平衡器)
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
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="3e631-102">Lync Server 2013 中的連接埠摘要 - 調整式 Director 集區 (硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="3e631-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e631-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="3e631-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="3e631-104">控制器池的防火牆埠需求是由用來從邊緣伺服器內部介面或反向 proxy 的內部介面中與控制器建立通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="3e631-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="3e631-105">Microsoft Lync Server 2013 預設會要求將埠 HTTP/TCP 8080 和 HTTPS/TCP 4443 從反向 proxy 開啟至控制器，以及前端池和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3e631-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e631-106">此外，您必須從 Edge 伺服器內部介面將會話初始通訊協定（SIP）與主管及前端池和前端伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3e631-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e631-107">SIP 通訊協定會將 SIP/MTLS/TCP 5061 從 Edge 伺服器使用到前端池和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3e631-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="3e631-108">您也必須建立一個規則，讓來自 Director、前端池和前端伺服器的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="3e631-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="3e631-109">防火牆定義的控制器埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="3e631-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e631-110">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="3e631-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3e631-111">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="3e631-111">Source IP address</span></span></th>
<th><span data-ttu-id="3e631-112">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="3e631-112">Destination IP address</span></span></th>
<th><span data-ttu-id="3e631-113">筆記</span><span class="sxs-lookup"><span data-stu-id="3e631-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e631-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="3e631-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="3e631-115">反向 proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="3e631-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e631-116">控制器硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="3e631-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e631-117">從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 與前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="3e631-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e631-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="3e631-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="3e631-119">反向 proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="3e631-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e631-120">控制器硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="3e631-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e631-121">從反向 proxy 的外部端開始，通訊會傳送到控制器 HLB VIP 與前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="3e631-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e631-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="3e631-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="3e631-123">Director</span><span class="sxs-lookup"><span data-stu-id="3e631-123">Director</span></span></p></td>
<td><p><span data-ttu-id="3e631-124">前端伺服器或前端池</span><span class="sxs-lookup"><span data-stu-id="3e631-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="3e631-125">控制器 HLB VIP 與前端伺服器之間的伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="3e631-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e631-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="3e631-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="3e631-127">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="3e631-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="3e631-128">控制器硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="3e631-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e631-129">控制器為內部和外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="3e631-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e631-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e631-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="3e631-131">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="3e631-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="3e631-132">控制器硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="3e631-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e631-133">控制器為內部和外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="3e631-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e631-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="3e631-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="3e631-135">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="3e631-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3e631-136">控制器硬體負載平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="3e631-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="3e631-137">從邊緣伺服器到控制器的 SIP 通訊，以及前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="3e631-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e631-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3e631-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3e631-139">每</span><span class="sxs-lookup"><span data-stu-id="3e631-139">Any</span></span></p></td>
<td><p><span data-ttu-id="3e631-140">Director</span><span class="sxs-lookup"><span data-stu-id="3e631-140">Director</span></span></p></td>
<td><p><span data-ttu-id="3e631-141">集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="3e631-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e631-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3e631-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3e631-143">每</span><span class="sxs-lookup"><span data-stu-id="3e631-143">Any</span></span></p></td>
<td><p><span data-ttu-id="3e631-144">Director</span><span class="sxs-lookup"><span data-stu-id="3e631-144">Director</span></span></p></td>
<td><p><span data-ttu-id="3e631-145">集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="3e631-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e631-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3e631-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3e631-147">每</span><span class="sxs-lookup"><span data-stu-id="3e631-147">Any</span></span></p></td>
<td><p><span data-ttu-id="3e631-148">Director</span><span class="sxs-lookup"><span data-stu-id="3e631-148">Director</span></span></p></td>
<td><p><span data-ttu-id="3e631-149">集中式記錄服務控制器（ClsController）或 agent （ClsAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="3e631-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

