---
title: Lync Server 2013：埠摘要-單一 Director
description: Lync Server 2013：埠摘要-單一 Director。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566369"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8ef5a-103">Lync Server 2013 中的埠摘要-單一 Director</span><span class="sxs-lookup"><span data-stu-id="8ef5a-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ef5a-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8ef5a-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8ef5a-105">單一 Director 的防火牆埠需求包含用於從反向 proxy 的內部介面或內部的網路與 Director 建立通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="8ef5a-106">Microsoft Lync Server 2013 預設會期望從反向 proxy 向 Director 開啟埠 HTTP/TCP 8080 和 HTTPS/TCP 4443，以及前端集區和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="8ef5a-107">此外，您必須要有會話初始通訊協定 (SIP) 從 Edge Server 內部介面到 Director 及前端集區和前端伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8ef5a-108">SIP 通訊協定使用從 Edge Server 到前端集區和前端伺服器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8ef5a-109">一種規則，允許從 Director、前端集區和前端伺服器到 Edge Server 內部介面的 SIP/MTLS/TCP 5061 通訊也必須建立。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="8ef5a-110">防火牆定義的單一 Director 埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="8ef5a-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ef5a-111">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="8ef5a-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8ef5a-112">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8ef5a-112">Source IP address</span></span></th>
<th><span data-ttu-id="8ef5a-113">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8ef5a-113">Destination IP address</span></span></th>
<th><span data-ttu-id="8ef5a-114">注意事項</span><span class="sxs-lookup"><span data-stu-id="8ef5a-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ef5a-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="8ef5a-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-116">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-117">Director</span><span class="sxs-lookup"><span data-stu-id="8ef5a-117">Director</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-118">從反向 proxy 的外部端開始，通訊會傳送到 Director 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="8ef5a-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef5a-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="8ef5a-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-120">反向 Proxy 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-121">Director</span><span class="sxs-lookup"><span data-stu-id="8ef5a-121">Director</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-122">從反向 proxy 的外部端開始，通訊會傳送到 Director 和前端伺服器 web 服務</span><span class="sxs-lookup"><span data-stu-id="8ef5a-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef5a-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="8ef5a-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-124">Director</span><span class="sxs-lookup"><span data-stu-id="8ef5a-124">Director</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-125">前端伺服器或前端集區</span><span class="sxs-lookup"><span data-stu-id="8ef5a-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-126">Director 與前端伺服器之間的伺服器間通訊</span><span class="sxs-lookup"><span data-stu-id="8ef5a-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef5a-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="8ef5a-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-128">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="8ef5a-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-129">Director web 服務</span><span class="sxs-lookup"><span data-stu-id="8ef5a-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-130">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef5a-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="8ef5a-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-132">內部用戶端</span><span class="sxs-lookup"><span data-stu-id="8ef5a-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-133">Director web 服務</span><span class="sxs-lookup"><span data-stu-id="8ef5a-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-134">Director 為內部及外部用戶端提供 web 服務。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef5a-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="8ef5a-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-136">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-137">Director</span><span class="sxs-lookup"><span data-stu-id="8ef5a-137">Director</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-138">從 Edge Server 到 Director 和前端伺服器的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="8ef5a-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef5a-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8ef5a-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-140">任何</span><span class="sxs-lookup"><span data-stu-id="8ef5a-140">Any</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-141">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-142">Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="8ef5a-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ef5a-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8ef5a-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-144">任何</span><span class="sxs-lookup"><span data-stu-id="8ef5a-144">Any</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-145">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-146">Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="8ef5a-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ef5a-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8ef5a-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-148">任何</span><span class="sxs-lookup"><span data-stu-id="8ef5a-148">Any</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-149">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="8ef5a-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8ef5a-150">Centralized Logging Service 控制站 (ClsController.exe) 或代理程式 (ClasAgent.exe) 命令和記錄檔收集</span><span class="sxs-lookup"><span data-stu-id="8ef5a-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

