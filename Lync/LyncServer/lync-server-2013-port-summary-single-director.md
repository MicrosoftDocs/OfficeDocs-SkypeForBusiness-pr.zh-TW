---
title: Lync Server 2013：連接埠摘要 - 單一 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="9d3a6-102">Lync Server 2013 中的連接埠摘要 - 單一 Director</span><span class="sxs-lookup"><span data-stu-id="9d3a6-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d3a6-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="9d3a6-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9d3a6-104">單一控制器的防火牆埠需求是由用來從內部介面或反向 proxy 的內部介面網路與主管建立通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="9d3a6-105">Microsoft Lync Server 2013 預設會要求將埠 HTTP/TCP 8080 和 HTTPS/TCP 4443 從反向 proxy 開啟至控制器，以及前端池和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="9d3a6-106">此外，您必須從 Edge 伺服器內部介面將會話初始通訊協定（SIP）與主管及前端池和前端伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="9d3a6-107">SIP 通訊協定會將 SIP/MTLS/TCP 5061 從 Edge 伺服器使用到前端池和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="9d3a6-108">您也必須建立一個規則，讓來自 Director、前端池和前端伺服器的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="9d3a6-109">針對防火牆定義的單一控制器埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="9d3a6-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d3a6-110">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="9d3a6-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9d3a6-111">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9d3a6-111">Source IP address</span></span></th>
<th><span data-ttu-id="9d3a6-112">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9d3a6-112">Destination IP address</span></span></th>
<th><span data-ttu-id="9d3a6-113">筆記</span><span class="sxs-lookup"><span data-stu-id="9d3a6-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d3a6-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="9d3a6-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-115">反向 proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-116">Director</span><span class="sxs-lookup"><span data-stu-id="9d3a6-116">Director</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-117">從反向 proxy 的外部端開始，通訊會傳送到控制器和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="9d3a6-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3a6-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="9d3a6-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-119">反向 proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-120">Director</span><span class="sxs-lookup"><span data-stu-id="9d3a6-120">Director</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-121">從反向 proxy 的外部端開始，通訊會傳送到控制器和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="9d3a6-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3a6-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="9d3a6-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-123">Director</span><span class="sxs-lookup"><span data-stu-id="9d3a6-123">Director</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-124">前端伺服器或前端池</span><span class="sxs-lookup"><span data-stu-id="9d3a6-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-125">控制器與前端伺服器之間的伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="9d3a6-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3a6-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="9d3a6-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-127">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="9d3a6-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-128">控制器 web 服務</span><span class="sxs-lookup"><span data-stu-id="9d3a6-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-129">控制器可向內部和外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3a6-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="9d3a6-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-131">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="9d3a6-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-132">控制器 web 服務</span><span class="sxs-lookup"><span data-stu-id="9d3a6-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-133">控制器可向內部和外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3a6-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="9d3a6-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-135">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-136">Director</span><span class="sxs-lookup"><span data-stu-id="9d3a6-136">Director</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-137">從邊緣伺服器到控制器的 SIP 通訊，以及前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d3a6-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3a6-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9d3a6-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-139">每</span><span class="sxs-lookup"><span data-stu-id="9d3a6-139">Any</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-140">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-141">集中式記錄服務控制器（ClsController）或 agent （ClasAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="9d3a6-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d3a6-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9d3a6-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-143">每</span><span class="sxs-lookup"><span data-stu-id="9d3a6-143">Any</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-144">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-145">集中式記錄服務控制器（ClsController）或 agent （ClasAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="9d3a6-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d3a6-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9d3a6-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-147">每</span><span class="sxs-lookup"><span data-stu-id="9d3a6-147">Any</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-148">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="9d3a6-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9d3a6-149">集中式記錄服務控制器（ClsController）或 agent （ClasAgent）命令及記錄集合</span><span class="sxs-lookup"><span data-stu-id="9d3a6-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

