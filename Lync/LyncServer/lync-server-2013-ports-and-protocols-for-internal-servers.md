---
title: Lync Server 2013：內部伺服器的埠與通訊協定
description: Lync Server 2013：內部伺服器的埠與通訊協定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d8f12c78c5dec5caacaeb1156f4d228b7cd591
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566351"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="fd21d-103">Lync Server 2013 中內部伺服器的埠與通訊協定</span><span class="sxs-lookup"><span data-stu-id="fd21d-103">Ports and protocols for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd21d-104">_**主題上次修改日期：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="fd21d-104">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="fd21d-105">本節摘要說明 Lync Server 部署中的伺服器、負載平衡器和用戶端所使用的埠和通訊協定。</span><span class="sxs-lookup"><span data-stu-id="fd21d-105">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd21d-106">Lync 和 Communicator 用戶端與單一通訊相關時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="fd21d-106">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="fd21d-107">從技術角度來看，這兩個用戶端是透過單一交談進行通訊，而立即訊息 multipoint control unit (IMMCU) 中間。</span><span class="sxs-lookup"><span data-stu-id="fd21d-107">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="fd21d-108">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="fd21d-108">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="fd21d-109">在所需的通訊工作流程中放置 IMMCU，可讓您在前端伺服器上啟用詳細通話記錄及其他功能。</span><span class="sxs-lookup"><span data-stu-id="fd21d-109">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="fd21d-110">通訊來自用戶端的動態來源埠至前端伺服器埠 TLS/TCP/5061 (假設使用建議的傳輸層安全性) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-110">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="fd21d-111">根據設計，對等通訊 (，而且只有在 Lync Server 和 IMMCU 為使用中且可用時，才可以進行多方的 IM) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-111">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="fd21d-112">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="fd21d-112">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd21d-113">在伺服器上啟動 Lync Server 服務之前，必須先執行 Windows 防火牆，因為這是 Lync Server 在防火牆中開啟必要的埠。</span><span class="sxs-lookup"><span data-stu-id="fd21d-113">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="fd21d-114">如需 edge 元件的防火牆設定的詳細資訊，請參閱 [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd21d-114">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="fd21d-115">下表列出每個內部伺服器角色上必須開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="fd21d-115">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="fd21d-116">伺服器角色所 (的必要伺服器埠) </span><span class="sxs-lookup"><span data-stu-id="fd21d-116">Required Server Ports (by Server Role)</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd21d-117">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="fd21d-117">Server role</span></span></th>
<th><span data-ttu-id="fd21d-118">服務名稱</span><span class="sxs-lookup"><span data-stu-id="fd21d-118">Service name</span></span></th>
<th><span data-ttu-id="fd21d-119">連接埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-119">Port</span></span></th>
<th><span data-ttu-id="fd21d-120">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fd21d-120">Protocol</span></span></th>
<th><span data-ttu-id="fd21d-121">注意事項</span><span class="sxs-lookup"><span data-stu-id="fd21d-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-122">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-122">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-123">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="fd21d-123">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fd21d-124">1434</span><span class="sxs-lookup"><span data-stu-id="fd21d-124">1434</span></span></p></td>
<td><p><span data-ttu-id="fd21d-125">Udp</span><span class="sxs-lookup"><span data-stu-id="fd21d-125">UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-126">SQL Browser 的中央管理存放區資料庫本地複寫複本。</span><span class="sxs-lookup"><span data-stu-id="fd21d-126">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-127">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-127">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-128">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-128">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-129">5060</span><span class="sxs-lookup"><span data-stu-id="fd21d-129">5060</span></span></p></td>
<td><p><span data-ttu-id="fd21d-130">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-130">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-131">可選擇性地由 Standard Edition server 和前端伺服器用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd21d-131">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-132">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-132">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-133">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-133">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-134">5061</span><span class="sxs-lookup"><span data-stu-id="fd21d-134">5061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-135">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-135">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-136">由 Standard Edition server 和前端集區用於伺服器 (MTLS) 、伺服器與用戶端之間的 SIP 通訊 (TLS) 及前端伺服器與轉送伺服器之間的 SIP 通訊 (MTLS) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-136">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="fd21d-137">也用於與監控伺服器的通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-137">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-138">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-138">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-139">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-139">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-140">444</span><span class="sxs-lookup"><span data-stu-id="fd21d-140">444</span></span></p></td>
<td><p><span data-ttu-id="fd21d-141">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-141">HTTPS</span></span></p>
<p><span data-ttu-id="fd21d-142">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-142">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-143">用於管理會議狀態) 和個別伺服器的焦點 (Lync Server 元件之間的 HTTPS 通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-143">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="fd21d-144">此埠也用於 Survivable 分支裝置和前端伺服器之間的 TCP 通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-144">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-145">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-145">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-146">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-146">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-147">135</span><span class="sxs-lookup"><span data-stu-id="fd21d-147">135</span></span></p></td>
<td><p><span data-ttu-id="fd21d-148">DCOM 和遠端過程呼叫 (RPC) </span><span class="sxs-lookup"><span data-stu-id="fd21d-148">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-149">用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製器同步處理及通訊錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="fd21d-149">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-150">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-150">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-151">Lync Server IM 會議服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-151">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-152">5062</span><span class="sxs-lookup"><span data-stu-id="fd21d-152">5062</span></span></p></td>
<td><p><span data-ttu-id="fd21d-153">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-153">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-154">用於立即訊息 (IM) 會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-154">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-155">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-155">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-156">Lync Server Web 會議服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-156">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-157">8057</span><span class="sxs-lookup"><span data-stu-id="fd21d-157">8057</span></span></p></td>
<td><p><span data-ttu-id="fd21d-158">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-158">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-159">用於聆聽持續性共用物件模型 (PSOM) 來自用戶端的連線。</span><span class="sxs-lookup"><span data-stu-id="fd21d-159">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-160">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-160">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-161">Lync Server Web 會議相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-161">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-162">8058</span><span class="sxs-lookup"><span data-stu-id="fd21d-162">8058</span></span></p></td>
<td><p><span data-ttu-id="fd21d-163">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-163">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-164">用於聆聽持續性共用物件模型 (從 Live Meeting 用戶端和舊版的 Lync Server PSOM) 連線。</span><span class="sxs-lookup"><span data-stu-id="fd21d-164">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-165">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-165">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-166">Lync Server Audio/Video 會議服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-166">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-167">5063</span><span class="sxs-lookup"><span data-stu-id="fd21d-167">5063</span></span></p></td>
<td><p><span data-ttu-id="fd21d-168">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-168">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-169">用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-169">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-170">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-170">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-171">Lync Server Audio/Video 會議服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-171">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-172">57501-65535</span><span class="sxs-lookup"><span data-stu-id="fd21d-172">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="fd21d-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fd21d-173">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-174">用於視訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fd21d-174">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-175">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-176">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-176">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-177">80</span><span class="sxs-lookup"><span data-stu-id="fd21d-177">80</span></span></p></td>
<td><p><span data-ttu-id="fd21d-178">HTTP:</span><span class="sxs-lookup"><span data-stu-id="fd21d-178">HTTP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-179">用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 不使用 HTTPS 時。</span><span class="sxs-lookup"><span data-stu-id="fd21d-179">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-180">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-180">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-181">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-181">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-182">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-182">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-183">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-183">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fd21d-184">用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-184">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-185">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-185">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-186">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-186">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-187">8080</span><span class="sxs-lookup"><span data-stu-id="fd21d-187">8080</span></span></p></td>
<td><p><span data-ttu-id="fd21d-188">TCP 和 HTTP</span><span class="sxs-lookup"><span data-stu-id="fd21d-188">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-189">供外部存取的 web 元件使用。</span><span class="sxs-lookup"><span data-stu-id="fd21d-189">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-190">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-190">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-191">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-191">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-192">4443</span><span class="sxs-lookup"><span data-stu-id="fd21d-192">4443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-193">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-193">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fd21d-194">HTTPS (，來自反向 Proxy) 與 HTTPS 前端集區間的自動探索登入通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-194">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-195">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-195">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-196">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-196">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-197">8060</span><span class="sxs-lookup"><span data-stu-id="fd21d-197">8060</span></span></p></td>
<td><p><span data-ttu-id="fd21d-198">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-198">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-199">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-199">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-200">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-200">Web server component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-201">8061</span><span class="sxs-lookup"><span data-stu-id="fd21d-201">8061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-202">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-202">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-203">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-203">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-204">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-204">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-205">5086</span><span class="sxs-lookup"><span data-stu-id="fd21d-205">5086</span></span></p></td>
<td><p><span data-ttu-id="fd21d-206">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-206">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-207">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-207">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-208">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-208">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-209">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-209">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-210">5087</span><span class="sxs-lookup"><span data-stu-id="fd21d-210">5087</span></span></p></td>
<td><p><span data-ttu-id="fd21d-211">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-211">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-212">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-212">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-213">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-213">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-214">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-214">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="fd21d-215">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-215">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-216">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-216">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-217">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-217">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-218">Lync Server 會議助理服務 (電話撥入式會議) </span><span class="sxs-lookup"><span data-stu-id="fd21d-218">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-219">5064</span><span class="sxs-lookup"><span data-stu-id="fd21d-219">5064</span></span></p></td>
<td><p><span data-ttu-id="fd21d-220">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-220">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-221">用於電話撥入式會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-221">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-222">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-222">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-223">Lync Server 會議助理服務 (電話撥入式會議) </span><span class="sxs-lookup"><span data-stu-id="fd21d-223">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-224">5072</span><span class="sxs-lookup"><span data-stu-id="fd21d-224">5072</span></span></p></td>
<td><p><span data-ttu-id="fd21d-225">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-225">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-226">用於在會議) 中傳入的 SIP 要求 (撥號語音應答。</span><span class="sxs-lookup"><span data-stu-id="fd21d-226">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-227">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-227">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-228">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-228">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-229">5070</span><span class="sxs-lookup"><span data-stu-id="fd21d-229">5070</span></span></p></td>
<td><p><span data-ttu-id="fd21d-230">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-230">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-231">由轉送伺服器用於來自前端伺服器到轉送伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-231">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-232">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-232">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-233">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-233">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-234">5067</span><span class="sxs-lookup"><span data-stu-id="fd21d-234">5067</span></span></p></td>
<td><p><span data-ttu-id="fd21d-235">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-235">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-236">用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-236">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-237">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-237">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-238">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-238">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-239">5068</span><span class="sxs-lookup"><span data-stu-id="fd21d-239">5068</span></span></p></td>
<td><p><span data-ttu-id="fd21d-240">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-240">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-241">用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-241">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-242">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-242">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-243">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-243">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-244">5081</span><span class="sxs-lookup"><span data-stu-id="fd21d-244">5081</span></span></p></td>
<td><p><span data-ttu-id="fd21d-245">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-245">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-246">用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-246">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-247">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-247">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-248">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-248">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-249">5082</span><span class="sxs-lookup"><span data-stu-id="fd21d-249">5082</span></span></p></td>
<td><p><span data-ttu-id="fd21d-250">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-250">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-251">用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-251">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-252">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-252">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-253">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-253">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-254">5065</span><span class="sxs-lookup"><span data-stu-id="fd21d-254">5065</span></span></p></td>
<td><p><span data-ttu-id="fd21d-255">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-255">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-256">用於應用程式共用的傳入 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-256">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-257">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-257">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-258">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-258">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-259">49152-65535</span><span class="sxs-lookup"><span data-stu-id="fd21d-259">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="fd21d-260">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-260">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-261">用於應用程式共用的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fd21d-261">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-262">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-262">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-263">Lync Server 會議宣告服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-263">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-264">5073</span><span class="sxs-lookup"><span data-stu-id="fd21d-264">5073</span></span></p></td>
<td><p><span data-ttu-id="fd21d-265">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-265">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-266">用於 Lync Server 會議宣告服務 (的傳入 SIP 要求，也就是用於電話撥入式會議) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-266">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-267">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-267">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-268">Lync Server 通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-268">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-269">5075</span><span class="sxs-lookup"><span data-stu-id="fd21d-269">5075</span></span></p></td>
<td><p><span data-ttu-id="fd21d-270">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-270">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-271">用於通話駐留應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-271">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-272">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-272">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-273">Lync Server 音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-273">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-274">5076</span><span class="sxs-lookup"><span data-stu-id="fd21d-274">5076</span></span></p></td>
<td><p><span data-ttu-id="fd21d-275">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-275">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-276">用於音訊測試服務的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-276">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-277">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-277">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-278">不適用</span><span class="sxs-lookup"><span data-stu-id="fd21d-278">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="fd21d-279">5066</span><span class="sxs-lookup"><span data-stu-id="fd21d-279">5066</span></span></p></td>
<td><p><span data-ttu-id="fd21d-280">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-280">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-281">用於輸出增強型 9-1-1 (E9-1-1) 閘道。</span><span class="sxs-lookup"><span data-stu-id="fd21d-281">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-282">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-282">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-283">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-283">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-284">5071</span><span class="sxs-lookup"><span data-stu-id="fd21d-284">5071</span></span></p></td>
<td><p><span data-ttu-id="fd21d-285">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-285">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-286">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-286">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-287">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-287">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-288">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-288">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-289">8404</span><span class="sxs-lookup"><span data-stu-id="fd21d-289">8404</span></span></p></td>
<td><p><span data-ttu-id="fd21d-290">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-290">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-291">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-291">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-292">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-292">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-293">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-293">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-294">5080</span><span class="sxs-lookup"><span data-stu-id="fd21d-294">5080</span></span></p></td>
<td><p><span data-ttu-id="fd21d-295">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-295">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-296">用於 A/V Edge 輪流流量的頻寬原則服務的通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="fd21d-296">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-297">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-297">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-298">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-298">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-299">448</span><span class="sxs-lookup"><span data-stu-id="fd21d-299">448</span></span></p></td>
<td><p><span data-ttu-id="fd21d-300">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-300">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-301">Lync Server 頻寬原則服務用於通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="fd21d-301">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-302">中央管理存放區所在的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-302">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="fd21d-303">Lync Server 主複製器代理程式服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-303">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-304">445</span><span class="sxs-lookup"><span data-stu-id="fd21d-304">445</span></span></p></td>
<td><p><span data-ttu-id="fd21d-305">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-305">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-306">用來將設定資料從中央管理存放區推入執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd21d-306">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-307">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-307">All Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-308">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="fd21d-308">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="fd21d-309">1434</span><span class="sxs-lookup"><span data-stu-id="fd21d-309">1434</span></span></p></td>
<td><p><span data-ttu-id="fd21d-310">Udp</span><span class="sxs-lookup"><span data-stu-id="fd21d-310">UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-311">本機 SQL Server 實例中中央管理存放區資料的本機複製副本的 SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="fd21d-311">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-312">所有內部伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-312">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-313">各種</span><span class="sxs-lookup"><span data-stu-id="fd21d-313">Various</span></span></p></td>
<td><p><span data-ttu-id="fd21d-314">49152-57500</span><span class="sxs-lookup"><span data-stu-id="fd21d-314">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="fd21d-315">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fd21d-315">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-316">用於所有內部伺服器的音訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="fd21d-316">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="fd21d-317">由終止音訊的所有伺服器使用：前端伺服器 (的 Lync Server 會議應答服務、Lync Server 會議宣告服務，以及 Lync Server Audio/Video 會議服務) 和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd21d-317">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-318">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="fd21d-318">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd21d-319">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-319">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd21d-320">由 Lync Server 2013 用來連線到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="fd21d-320">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-321">董事</span><span class="sxs-lookup"><span data-stu-id="fd21d-321">Directors</span></span></p></td>
<td><p><span data-ttu-id="fd21d-322">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-322">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-323">5060</span><span class="sxs-lookup"><span data-stu-id="fd21d-323">5060</span></span></p></td>
<td><p><span data-ttu-id="fd21d-324">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-324">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-325">選擇性地用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="fd21d-325">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-326">董事</span><span class="sxs-lookup"><span data-stu-id="fd21d-326">Directors</span></span></p></td>
<td><p><span data-ttu-id="fd21d-327">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-327">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-328">444</span><span class="sxs-lookup"><span data-stu-id="fd21d-328">444</span></span></p></td>
<td><p><span data-ttu-id="fd21d-329">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-329">HTTPS</span></span></p>
<p><span data-ttu-id="fd21d-330">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-330">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-331">前端和 Director 之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-331">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="fd21d-332">此外，用戶端憑證發行 (至前端伺服器) 或驗證是否已發佈用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="fd21d-332">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-333">董事</span><span class="sxs-lookup"><span data-stu-id="fd21d-333">Directors</span></span></p></td>
<td><p><span data-ttu-id="fd21d-334">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-334">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-335">80</span><span class="sxs-lookup"><span data-stu-id="fd21d-335">80</span></span></p></td>
<td><p><span data-ttu-id="fd21d-336">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-336">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-337">用於從 Director 到 web 伺服器陣列 Fqdn (的初始通訊) IIS web 元件所使用的 URLs。</span><span class="sxs-lookup"><span data-stu-id="fd21d-337">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="fd21d-338">在正常作業中，會使用埠443和通訊協定類型 TCP 切換到 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="fd21d-338">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-339">董事</span><span class="sxs-lookup"><span data-stu-id="fd21d-339">Directors</span></span></p></td>
<td><p><span data-ttu-id="fd21d-340">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-340">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-341">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-341">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-342">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-342">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="fd21d-343">用於從 Director 到 web 伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-343">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-344">董事</span><span class="sxs-lookup"><span data-stu-id="fd21d-344">Directors</span></span></p></td>
<td><p><span data-ttu-id="fd21d-345">Lync Server Front-End 服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-345">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-346">5061</span><span class="sxs-lookup"><span data-stu-id="fd21d-346">5061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-347">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-347">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-348">用於伺服器與用戶端連線之間的內部通訊。</span><span class="sxs-lookup"><span data-stu-id="fd21d-348">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-349">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-349">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-350">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-350">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-351">5070</span><span class="sxs-lookup"><span data-stu-id="fd21d-351">5070</span></span></p></td>
<td><p><span data-ttu-id="fd21d-352">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-352">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-353">由轉送伺服器用於來自前端伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-353">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-354">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-354">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-355">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-355">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-356">5067</span><span class="sxs-lookup"><span data-stu-id="fd21d-356">5067</span></span></p></td>
<td><p><span data-ttu-id="fd21d-357">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-357">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-358">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-358">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-359">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-359">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-360">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-360">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-361">5068</span><span class="sxs-lookup"><span data-stu-id="fd21d-361">5068</span></span></p></td>
<td><p><span data-ttu-id="fd21d-362">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-362">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-363">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-363">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-364">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-364">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="fd21d-365">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-365">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-366">5070</span><span class="sxs-lookup"><span data-stu-id="fd21d-366">5070</span></span></p></td>
<td><p><span data-ttu-id="fd21d-367">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-367">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-368">用於來自前端伺服器的 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="fd21d-368">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-369">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-369">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-370">Persistent Chat SIP</span><span class="sxs-lookup"><span data-stu-id="fd21d-370">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-371">5041</span><span class="sxs-lookup"><span data-stu-id="fd21d-371">5041</span></span></p></td>
<td><p><span data-ttu-id="fd21d-372">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-372">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-373">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-373">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-374">Persistent Chat Windows Communication Foundation (WCF) </span><span class="sxs-lookup"><span data-stu-id="fd21d-374">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-375">881</span><span class="sxs-lookup"><span data-stu-id="fd21d-375">881</span></span></p></td>
<td><p><span data-ttu-id="fd21d-376">TCP (TLS) 和 TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-376">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-377">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="fd21d-377">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="fd21d-378">Persistent Chat File 傳遞服務</span><span class="sxs-lookup"><span data-stu-id="fd21d-378">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="fd21d-379">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-379">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-380">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-380">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fd21d-381">某些遠端呼叫控制案例需要在前端伺服器或 Director 和 PBX 之間建立 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="fd21d-381">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="fd21d-382">雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，此設定會將 RCC 線路伺服器 FQDN 與前端伺服器或 Director 用來連接 PBX 系統的 TCP 通訊埠產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fd21d-382">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="fd21d-383">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 <STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd21d-383">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="fd21d-384">針對只使用硬體負載平衡的集區 (不) DNS 負載平衡]，下表顯示需要開啟硬體負載平衡器的埠。</span><span class="sxs-lookup"><span data-stu-id="fd21d-384">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="fd21d-385">硬體負載平衡器埠（如果只使用硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="fd21d-385">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd21d-386">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-386">Load Balancer</span></span></th>
<th><span data-ttu-id="fd21d-387">連接埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-387">Port</span></span></th>
<th><span data-ttu-id="fd21d-388">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fd21d-388">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-389">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-389">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-390">5061</span><span class="sxs-lookup"><span data-stu-id="fd21d-390">5061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-391">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-391">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-392">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-392">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-393">444</span><span class="sxs-lookup"><span data-stu-id="fd21d-393">444</span></span></p></td>
<td><p><span data-ttu-id="fd21d-394">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-394">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-395">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-395">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-396">135</span><span class="sxs-lookup"><span data-stu-id="fd21d-396">135</span></span></p></td>
<td><p><span data-ttu-id="fd21d-397">DCOM 和遠端過程呼叫 (RPC) </span><span class="sxs-lookup"><span data-stu-id="fd21d-397">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-398">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-398">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-399">80</span><span class="sxs-lookup"><span data-stu-id="fd21d-399">80</span></span></p></td>
<td><p><span data-ttu-id="fd21d-400">HTTP:</span><span class="sxs-lookup"><span data-stu-id="fd21d-400">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-401">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-401">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-402">8080</span><span class="sxs-lookup"><span data-stu-id="fd21d-402">8080</span></span></p></td>
<td><p><span data-ttu-id="fd21d-403">TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="fd21d-403">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-404">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-404">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-405">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-405">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-406">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-406">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-407">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-407">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-408">4443</span><span class="sxs-lookup"><span data-stu-id="fd21d-408">4443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-409">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="fd21d-409">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-410">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-410">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-411">5072</span><span class="sxs-lookup"><span data-stu-id="fd21d-411">5072</span></span></p></td>
<td><p><span data-ttu-id="fd21d-412">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-412">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-413">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-413">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-414">5073</span><span class="sxs-lookup"><span data-stu-id="fd21d-414">5073</span></span></p></td>
<td><p><span data-ttu-id="fd21d-415">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-415">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-416">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-416">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-417">5075</span><span class="sxs-lookup"><span data-stu-id="fd21d-417">5075</span></span></p></td>
<td><p><span data-ttu-id="fd21d-418">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-418">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-419">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-419">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-420">5076</span><span class="sxs-lookup"><span data-stu-id="fd21d-420">5076</span></span></p></td>
<td><p><span data-ttu-id="fd21d-421">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-421">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-422">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-422">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-423">5071</span><span class="sxs-lookup"><span data-stu-id="fd21d-423">5071</span></span></p></td>
<td><p><span data-ttu-id="fd21d-424">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-424">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-425">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-425">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-426">5080</span><span class="sxs-lookup"><span data-stu-id="fd21d-426">5080</span></span></p></td>
<td><p><span data-ttu-id="fd21d-427">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-427">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-428">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-428">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-429">448</span><span class="sxs-lookup"><span data-stu-id="fd21d-429">448</span></span></p></td>
<td><p><span data-ttu-id="fd21d-430">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-430">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-431">轉送伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-431">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-432">5070</span><span class="sxs-lookup"><span data-stu-id="fd21d-432">5070</span></span></p></td>
<td><p><span data-ttu-id="fd21d-433">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-433">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-434">前端伺服器負載平衡器 (如果集區也執行轉送伺服器) </span><span class="sxs-lookup"><span data-stu-id="fd21d-434">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-435">5070</span><span class="sxs-lookup"><span data-stu-id="fd21d-435">5070</span></span></p></td>
<td><p><span data-ttu-id="fd21d-436">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-436">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-437">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-437">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-438">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-438">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-439">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-439">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-440">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-440">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-441">444</span><span class="sxs-lookup"><span data-stu-id="fd21d-441">444</span></span></p></td>
<td><p><span data-ttu-id="fd21d-442">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-442">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-443">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-443">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-444">5061</span><span class="sxs-lookup"><span data-stu-id="fd21d-444">5061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-445">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-445">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-446">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-446">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-447">4443</span><span class="sxs-lookup"><span data-stu-id="fd21d-447">4443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-448">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="fd21d-448">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd21d-449">使用 DNS 負載平衡的前端集區和 Director 集區也必須部署硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="fd21d-449">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="fd21d-450">下表顯示這些硬體負載平衡器上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="fd21d-450">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="fd21d-451">硬體負載平衡器埠（如果使用 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="fd21d-451">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd21d-452">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-452">Load Balancer</span></span></th>
<th><span data-ttu-id="fd21d-453">連接埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-453">Port</span></span></th>
<th><span data-ttu-id="fd21d-454">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fd21d-454">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-455">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-455">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-456">80</span><span class="sxs-lookup"><span data-stu-id="fd21d-456">80</span></span></p></td>
<td><p><span data-ttu-id="fd21d-457">HTTP:</span><span class="sxs-lookup"><span data-stu-id="fd21d-457">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-458">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-458">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-459">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-459">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-460">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-460">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-461">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-461">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-462">8080</span><span class="sxs-lookup"><span data-stu-id="fd21d-462">8080</span></span></p></td>
<td><p><span data-ttu-id="fd21d-463">TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="fd21d-463">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-464">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-464">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-465">4443</span><span class="sxs-lookup"><span data-stu-id="fd21d-465">4443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-466">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="fd21d-466">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-467">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-467">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-468">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-468">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-469">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fd21d-469">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-470">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="fd21d-470">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="fd21d-471">4443</span><span class="sxs-lookup"><span data-stu-id="fd21d-471">4443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-472">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="fd21d-472">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="fd21d-473">必要的用戶端埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-473">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd21d-474">元件</span><span class="sxs-lookup"><span data-stu-id="fd21d-474">Component</span></span></th>
<th><span data-ttu-id="fd21d-475">連接埠</span><span class="sxs-lookup"><span data-stu-id="fd21d-475">Port</span></span></th>
<th><span data-ttu-id="fd21d-476">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="fd21d-476">Protocol</span></span></th>
<th><span data-ttu-id="fd21d-477">注意事項</span><span class="sxs-lookup"><span data-stu-id="fd21d-477">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-478">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-478">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-479">67/68</span><span class="sxs-lookup"><span data-stu-id="fd21d-479">67/68</span></span></p></td>
<td><p><span data-ttu-id="fd21d-480">Dhcp</span><span class="sxs-lookup"><span data-stu-id="fd21d-480">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-481">由 Lync Server 用來尋找註冊機 FQDN (也就是說，如果 DNS SRV 失敗，且未設定) 手動設定。</span><span class="sxs-lookup"><span data-stu-id="fd21d-481">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-482">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-482">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-483">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-483">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-484">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-484">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-485">用於外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="fd21d-485">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-486">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-486">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-487">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-487">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-488">TCP (PSOM/TLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-488">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-489">用於外部使用者存取 web 會議會話。</span><span class="sxs-lookup"><span data-stu-id="fd21d-489">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-490">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-490">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-491">443</span><span class="sxs-lookup"><span data-stu-id="fd21d-491">443</span></span></p></td>
<td><p><span data-ttu-id="fd21d-492">TCP (STUN/MSTURN) </span><span class="sxs-lookup"><span data-stu-id="fd21d-492">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-493">用於外部使用者存取 A/V 會話和媒體 (TCP) </span><span class="sxs-lookup"><span data-stu-id="fd21d-493">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-494">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-494">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-495">3478</span><span class="sxs-lookup"><span data-stu-id="fd21d-495">3478</span></span></p></td>
<td><p><span data-ttu-id="fd21d-496">UDP (STUN/MSTURN) </span><span class="sxs-lookup"><span data-stu-id="fd21d-496">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-497">用於外部使用者存取 A/V 會話和媒體 (UDP) </span><span class="sxs-lookup"><span data-stu-id="fd21d-497">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-498">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-498">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-499">5061</span><span class="sxs-lookup"><span data-stu-id="fd21d-499">5061</span></span></p></td>
<td><p><span data-ttu-id="fd21d-500">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="fd21d-500">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="fd21d-501">用於外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="fd21d-501">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-502">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-502">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-503">6891-6901</span><span class="sxs-lookup"><span data-stu-id="fd21d-503">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="fd21d-504">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-504">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-505">用於 Lync 用戶端和舊版用戶端之間的檔案傳輸 (Microsoft Office 通訊伺服器 2007 R2、Microsoft Office 通訊伺服器2007及 Live 通訊伺服器 2005) 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="fd21d-505">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-506">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-506">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-507">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fd21d-507">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fd21d-508">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fd21d-508">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-509">音訊埠範圍 (至少需要20個埠) </span><span class="sxs-lookup"><span data-stu-id="fd21d-509">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-510">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-510">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-511">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fd21d-511">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fd21d-512">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="fd21d-512">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-513">影片埠範圍 (至少需要20個埠) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-513">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-514">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-514">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-515">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fd21d-515">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fd21d-516">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-516">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-517">對等檔案傳輸 (若為會議檔案傳輸，用戶端會使用 PSOM) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-517">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd21d-518">用戶端</span><span class="sxs-lookup"><span data-stu-id="fd21d-518">Clients</span></span></p></td>
<td><p><span data-ttu-id="fd21d-519">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="fd21d-519">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="fd21d-520">TCP</span><span class="sxs-lookup"><span data-stu-id="fd21d-520">TCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-521">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="fd21d-521">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd21d-522">Aastra 6721ip 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="fd21d-522">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="fd21d-523">Aastra 6725ip 電話機</span><span class="sxs-lookup"><span data-stu-id="fd21d-523">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="fd21d-524">HP 4110 IP 電話 (通用區域電話) </span><span class="sxs-lookup"><span data-stu-id="fd21d-524">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="fd21d-525">HP 4120 IP 電話 (電話機)</span><span class="sxs-lookup"><span data-stu-id="fd21d-525">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="fd21d-526">Polycom CX500 IP 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="fd21d-526">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="fd21d-527">Polycom CX600 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="fd21d-527">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="fd21d-528">Polycom CX700 IP 服務台電話</span><span class="sxs-lookup"><span data-stu-id="fd21d-528">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="fd21d-529">Polycom CX3000 IP 會議電話</span><span class="sxs-lookup"><span data-stu-id="fd21d-529">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="fd21d-530">67/68</span><span class="sxs-lookup"><span data-stu-id="fd21d-530">67/68</span></span></p></td>
<td><p><span data-ttu-id="fd21d-531">Dhcp</span><span class="sxs-lookup"><span data-stu-id="fd21d-531">DHCP</span></span></p></td>
<td><p><span data-ttu-id="fd21d-532">由所列裝置使用以尋找 Lync Server 憑證、布建 FQDN 和註冊機 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fd21d-532">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd21d-533">**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 及 ClientMediaPortRange 參數) 。</span><span class="sxs-lookup"><span data-stu-id="fd21d-533">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd21d-534">設定的 Lync 用戶端程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="fd21d-534">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fd21d-535">在用戶端必須透過組織的防火牆 (的任何情況下（例如，其他組織所主控的外部通訊或會議) ），都需要用於外部使用者存取的埠。</span><span class="sxs-lookup"><span data-stu-id="fd21d-535">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

