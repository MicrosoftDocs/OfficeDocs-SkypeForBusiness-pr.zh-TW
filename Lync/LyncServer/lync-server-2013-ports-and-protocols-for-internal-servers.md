---
title: Lync Server 2013：內部伺服器的埠與通訊協定
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
ms.openlocfilehash: 42f40265cf7b8fff7fd6cbf3d4f67a2fb9f558fa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="b6443-102">Lync Server 2013 中內部伺服器的埠與通訊協定</span><span class="sxs-lookup"><span data-stu-id="b6443-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6443-103">_**主題上次修改日期：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="b6443-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="b6443-104">本節摘要說明 Lync Server 部署中的伺服器、負載平衡器和用戶端所使用的埠和通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b6443-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b6443-105">Lync 和 Communicator 用戶端與單一通訊相關時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="b6443-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="b6443-106">從技術角度來看，這兩個用戶端是透過單一交談進行通訊，而立即訊息 multipoint control unit (IMMCU) 中間。</span><span class="sxs-lookup"><span data-stu-id="b6443-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="b6443-107">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="b6443-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="b6443-108">在所需的通訊工作流程中放置 IMMCU，可讓您在前端伺服器上啟用詳細通話記錄及其他功能。</span><span class="sxs-lookup"><span data-stu-id="b6443-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="b6443-109">通訊來自用戶端的動態來源埠至前端伺服器埠 TLS/TCP/5061 (假設使用建議的傳輸層安全性) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="b6443-110">根據設計，對等通訊 (，而且只有在 Lync Server 和 IMMCU 為使用中且可用時，才可以進行多方的 IM) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b6443-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="b6443-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6443-112">在伺服器上啟動 Lync Server 服務之前，必須先執行 Windows 防火牆，因為這是 Lync Server 在防火牆中開啟必要的埠。</span><span class="sxs-lookup"><span data-stu-id="b6443-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="b6443-113">如需 edge 元件的防火牆設定的詳細資訊，請參閱[決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6443-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="b6443-114">下表列出每個內部伺服器角色上必須開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="b6443-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="b6443-115">伺服器角色所 (的必要伺服器埠) </span><span class="sxs-lookup"><span data-stu-id="b6443-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="b6443-116">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="b6443-116">Server role</span></span></th>
<th><span data-ttu-id="b6443-117">服務名稱</span><span class="sxs-lookup"><span data-stu-id="b6443-117">Service name</span></span></th>
<th><span data-ttu-id="b6443-118">連接埠</span><span class="sxs-lookup"><span data-stu-id="b6443-118">Port</span></span></th>
<th><span data-ttu-id="b6443-119">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="b6443-119">Protocol</span></span></th>
<th><span data-ttu-id="b6443-120">附註</span><span class="sxs-lookup"><span data-stu-id="b6443-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6443-121">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-122">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="b6443-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="b6443-123">1434</span><span class="sxs-lookup"><span data-stu-id="b6443-123">1434</span></span></p></td>
<td><p><span data-ttu-id="b6443-124">Udp</span><span class="sxs-lookup"><span data-stu-id="b6443-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-125">SQL Browser 的中央管理存放區資料庫本地複寫複本。</span><span class="sxs-lookup"><span data-stu-id="b6443-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-126">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-127">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-128">5060</span><span class="sxs-lookup"><span data-stu-id="b6443-128">5060</span></span></p></td>
<td><p><span data-ttu-id="b6443-129">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-130">可選擇性地由 Standard Edition server 和前端伺服器用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6443-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-131">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-132">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-133">5061</span><span class="sxs-lookup"><span data-stu-id="b6443-133">5061</span></span></p></td>
<td><p><span data-ttu-id="b6443-134">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-135">由 Standard Edition server 和前端集區用於伺服器 (MTLS) 、伺服器與用戶端之間的 SIP 通訊 (TLS) 及前端伺服器與轉送伺服器之間的 SIP 通訊 (MTLS) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="b6443-136">也用於與監控伺服器的通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-137">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-138">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-139">444</span><span class="sxs-lookup"><span data-stu-id="b6443-139">444</span></span></p></td>
<td><p><span data-ttu-id="b6443-140">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-140">HTTPS</span></span></p>
<p><span data-ttu-id="b6443-141">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-142">用於管理會議狀態) 和個別伺服器的焦點 (Lync Server 元件之間的 HTTPS 通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="b6443-143">此埠也用於 Survivable 分支裝置和前端伺服器之間的 TCP 通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-144">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-145">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-146">135</span><span class="sxs-lookup"><span data-stu-id="b6443-146">135</span></span></p></td>
<td><p><span data-ttu-id="b6443-147">DCOM 和遠端過程呼叫 (RPC) </span><span class="sxs-lookup"><span data-stu-id="b6443-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="b6443-148">用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製器同步處理及通訊錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="b6443-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-149">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-150">Lync Server IM 會議服務</span><span class="sxs-lookup"><span data-stu-id="b6443-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-151">5062</span><span class="sxs-lookup"><span data-stu-id="b6443-151">5062</span></span></p></td>
<td><p><span data-ttu-id="b6443-152">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-153">用於立即訊息 (IM) 會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-154">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-155">Lync Server Web 會議服務</span><span class="sxs-lookup"><span data-stu-id="b6443-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-156">8057</span><span class="sxs-lookup"><span data-stu-id="b6443-156">8057</span></span></p></td>
<td><p><span data-ttu-id="b6443-157">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-158">用於聆聽持續性共用物件模型 (PSOM) 來自用戶端的連線。</span><span class="sxs-lookup"><span data-stu-id="b6443-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-159">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-160">Lync Server Web 會議相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-161">8058</span><span class="sxs-lookup"><span data-stu-id="b6443-161">8058</span></span></p></td>
<td><p><span data-ttu-id="b6443-162">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-163">用於聆聽持續性共用物件模型 (從 Live Meeting 用戶端和舊版的 Lync Server PSOM) 連線。</span><span class="sxs-lookup"><span data-stu-id="b6443-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-164">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-165">Lync Server Audio/Video 會議服務</span><span class="sxs-lookup"><span data-stu-id="b6443-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-166">5063</span><span class="sxs-lookup"><span data-stu-id="b6443-166">5063</span></span></p></td>
<td><p><span data-ttu-id="b6443-167">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-168">用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-169">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-170">Lync Server Audio/Video 會議服務</span><span class="sxs-lookup"><span data-stu-id="b6443-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="b6443-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="b6443-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b6443-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-173">用於視訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="b6443-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-174">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-175">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-176">80</span><span class="sxs-lookup"><span data-stu-id="b6443-176">80</span></span></p></td>
<td><p><span data-ttu-id="b6443-177">HTTP:</span><span class="sxs-lookup"><span data-stu-id="b6443-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="b6443-178">用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 不使用 HTTPS 時。</span><span class="sxs-lookup"><span data-stu-id="b6443-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-179">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-180">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-181">443</span><span class="sxs-lookup"><span data-stu-id="b6443-181">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-182">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b6443-183">用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-184">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-185">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-186">8080</span><span class="sxs-lookup"><span data-stu-id="b6443-186">8080</span></span></p></td>
<td><p><span data-ttu-id="b6443-187">TCP 和 HTTP</span><span class="sxs-lookup"><span data-stu-id="b6443-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="b6443-188">供外部存取的 web 元件使用。</span><span class="sxs-lookup"><span data-stu-id="b6443-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-189">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-190">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="b6443-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b6443-191">4443</span><span class="sxs-lookup"><span data-stu-id="b6443-191">4443</span></span></p></td>
<td><p><span data-ttu-id="b6443-192">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b6443-193">HTTPS (，來自反向 Proxy) 與 HTTPS 前端集區間的自動探索登入通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-194">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-195">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="b6443-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b6443-196">8060</span><span class="sxs-lookup"><span data-stu-id="b6443-196">8060</span></span></p></td>
<td><p><span data-ttu-id="b6443-197">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-198">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-199">網頁伺服器元件</span><span class="sxs-lookup"><span data-stu-id="b6443-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="b6443-200">8061</span><span class="sxs-lookup"><span data-stu-id="b6443-200">8061</span></span></p></td>
<td><p><span data-ttu-id="b6443-201">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-202">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-203">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="b6443-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b6443-204">5086</span><span class="sxs-lookup"><span data-stu-id="b6443-204">5086</span></span></p></td>
<td><p><span data-ttu-id="b6443-205">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-206">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="b6443-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-207">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-208">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="b6443-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b6443-209">5087</span><span class="sxs-lookup"><span data-stu-id="b6443-209">5087</span></span></p></td>
<td><p><span data-ttu-id="b6443-210">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-211">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="b6443-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-212">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-213">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="b6443-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="b6443-214">443</span><span class="sxs-lookup"><span data-stu-id="b6443-214">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-215">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-216">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-217">Lync Server 會議助理服務 (電話撥入式會議) </span><span class="sxs-lookup"><span data-stu-id="b6443-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="b6443-218">5064</span><span class="sxs-lookup"><span data-stu-id="b6443-218">5064</span></span></p></td>
<td><p><span data-ttu-id="b6443-219">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-220">用於電話撥入式會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-221">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-222">Lync Server 會議助理服務 (電話撥入式會議) </span><span class="sxs-lookup"><span data-stu-id="b6443-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="b6443-223">5072</span><span class="sxs-lookup"><span data-stu-id="b6443-223">5072</span></span></p></td>
<td><p><span data-ttu-id="b6443-224">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-225">用於在會議) 中傳入的 SIP 要求 (撥號語音應答。</span><span class="sxs-lookup"><span data-stu-id="b6443-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-226">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-227">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-228">5070</span><span class="sxs-lookup"><span data-stu-id="b6443-228">5070</span></span></p></td>
<td><p><span data-ttu-id="b6443-229">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-230">由轉送伺服器用於來自前端伺服器到轉送伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-231">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-232">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-233">5067</span><span class="sxs-lookup"><span data-stu-id="b6443-233">5067</span></span></p></td>
<td><p><span data-ttu-id="b6443-234">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-235">用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-236">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-237">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-238">5068</span><span class="sxs-lookup"><span data-stu-id="b6443-238">5068</span></span></p></td>
<td><p><span data-ttu-id="b6443-239">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-240">用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-241">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-242">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-243">5081</span><span class="sxs-lookup"><span data-stu-id="b6443-243">5081</span></span></p></td>
<td><p><span data-ttu-id="b6443-244">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-245">用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-246">同時執行組合轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-247">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-248">5082</span><span class="sxs-lookup"><span data-stu-id="b6443-248">5082</span></span></p></td>
<td><p><span data-ttu-id="b6443-249">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-250">用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-251">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-252">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="b6443-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-253">5065</span><span class="sxs-lookup"><span data-stu-id="b6443-253">5065</span></span></p></td>
<td><p><span data-ttu-id="b6443-254">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-255">用於應用程式共用的傳入 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-256">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-257">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="b6443-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="b6443-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="b6443-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="b6443-259">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-260">用於應用程式共用的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="b6443-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-261">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-262">Lync Server 會議宣告服務</span><span class="sxs-lookup"><span data-stu-id="b6443-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="b6443-263">5073</span><span class="sxs-lookup"><span data-stu-id="b6443-263">5073</span></span></p></td>
<td><p><span data-ttu-id="b6443-264">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-265">用於 Lync Server 會議宣告服務 (的傳入 SIP 要求，也就是用於電話撥入式會議) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-266">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-267">Lync Server 通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="b6443-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="b6443-268">5075</span><span class="sxs-lookup"><span data-stu-id="b6443-268">5075</span></span></p></td>
<td><p><span data-ttu-id="b6443-269">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-270">用於通話駐留應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-271">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-272">Lync Server 音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="b6443-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="b6443-273">5076</span><span class="sxs-lookup"><span data-stu-id="b6443-273">5076</span></span></p></td>
<td><p><span data-ttu-id="b6443-274">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-275">用於音訊測試服務的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-276">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-277">不適用</span><span class="sxs-lookup"><span data-stu-id="b6443-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="b6443-278">5066</span><span class="sxs-lookup"><span data-stu-id="b6443-278">5066</span></span></p></td>
<td><p><span data-ttu-id="b6443-279">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-280">用於輸出增強型 9-1-1 (E9-1-1) 閘道。</span><span class="sxs-lookup"><span data-stu-id="b6443-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-281">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-282">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="b6443-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="b6443-283">5071</span><span class="sxs-lookup"><span data-stu-id="b6443-283">5071</span></span></p></td>
<td><p><span data-ttu-id="b6443-284">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-285">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-286">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-287">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="b6443-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="b6443-288">8404</span><span class="sxs-lookup"><span data-stu-id="b6443-288">8404</span></span></p></td>
<td><p><span data-ttu-id="b6443-289">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-290">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-291">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-292">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="b6443-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="b6443-293">5080</span><span class="sxs-lookup"><span data-stu-id="b6443-293">5080</span></span></p></td>
<td><p><span data-ttu-id="b6443-294">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-295">用於 A/V Edge 輪流流量的頻寬原則服務的通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="b6443-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-296">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-297">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="b6443-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="b6443-298">448</span><span class="sxs-lookup"><span data-stu-id="b6443-298">448</span></span></p></td>
<td><p><span data-ttu-id="b6443-299">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-300">Lync Server 頻寬原則服務用於通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="b6443-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-301">中央管理存放區所在的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="b6443-302">Lync Server 主複製器代理程式服務</span><span class="sxs-lookup"><span data-stu-id="b6443-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="b6443-303">445</span><span class="sxs-lookup"><span data-stu-id="b6443-303">445</span></span></p></td>
<td><p><span data-ttu-id="b6443-304">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-305">用來將設定資料從中央管理存放區推入執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6443-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-306">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-307">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="b6443-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="b6443-308">1434</span><span class="sxs-lookup"><span data-stu-id="b6443-308">1434</span></span></p></td>
<td><p><span data-ttu-id="b6443-309">Udp</span><span class="sxs-lookup"><span data-stu-id="b6443-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-310">本機 SQL Server 實例中中央管理存放區資料的本機複製副本的 SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="b6443-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-311">所有內部伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-312">各種</span><span class="sxs-lookup"><span data-stu-id="b6443-312">Various</span></span></p></td>
<td><p><span data-ttu-id="b6443-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="b6443-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="b6443-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b6443-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-315">用於所有內部伺服器的音訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="b6443-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="b6443-316">由終止音訊的所有伺服器使用：前端伺服器 (的 Lync Server 會議應答服務、Lync Server 會議宣告服務，以及 Lync Server Audio/Video 會議服務) 和轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6443-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-317">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="b6443-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6443-318">443</span><span class="sxs-lookup"><span data-stu-id="b6443-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6443-319">由 Lync Server 2013 用來連線到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="b6443-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-320">董事</span><span class="sxs-lookup"><span data-stu-id="b6443-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="b6443-321">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-322">5060</span><span class="sxs-lookup"><span data-stu-id="b6443-322">5060</span></span></p></td>
<td><p><span data-ttu-id="b6443-323">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-324">選擇性地用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="b6443-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-325">董事</span><span class="sxs-lookup"><span data-stu-id="b6443-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="b6443-326">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-327">444</span><span class="sxs-lookup"><span data-stu-id="b6443-327">444</span></span></p></td>
<td><p><span data-ttu-id="b6443-328">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-328">HTTPS</span></span></p>
<p><span data-ttu-id="b6443-329">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-330">前端和 Director 之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="b6443-331">此外，用戶端憑證發行 (至前端伺服器) 或驗證是否已發佈用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="b6443-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-332">董事</span><span class="sxs-lookup"><span data-stu-id="b6443-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="b6443-333">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-334">80</span><span class="sxs-lookup"><span data-stu-id="b6443-334">80</span></span></p></td>
<td><p><span data-ttu-id="b6443-335">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-336">用於從 Director 到 web 伺服器陣列 Fqdn (的初始通訊) IIS web 元件所使用的 URLs。</span><span class="sxs-lookup"><span data-stu-id="b6443-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="b6443-337">在正常作業中，會使用埠443和通訊協定類型 TCP 切換到 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="b6443-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-338">董事</span><span class="sxs-lookup"><span data-stu-id="b6443-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="b6443-339">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="b6443-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="b6443-340">443</span><span class="sxs-lookup"><span data-stu-id="b6443-340">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-341">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="b6443-342">用於從 Director 到 web 伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-343">董事</span><span class="sxs-lookup"><span data-stu-id="b6443-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="b6443-344">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="b6443-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="b6443-345">5061</span><span class="sxs-lookup"><span data-stu-id="b6443-345">5061</span></span></p></td>
<td><p><span data-ttu-id="b6443-346">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-347">用於伺服器與用戶端連線之間的內部通訊。</span><span class="sxs-lookup"><span data-stu-id="b6443-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-348">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-349">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-350">5070</span><span class="sxs-lookup"><span data-stu-id="b6443-350">5070</span></span></p></td>
<td><p><span data-ttu-id="b6443-351">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-352">由轉送伺服器用於來自前端伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-353">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-354">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-355">5067</span><span class="sxs-lookup"><span data-stu-id="b6443-355">5067</span></span></p></td>
<td><p><span data-ttu-id="b6443-356">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-357">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-358">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-359">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-360">5068</span><span class="sxs-lookup"><span data-stu-id="b6443-360">5068</span></span></p></td>
<td><p><span data-ttu-id="b6443-361">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-362">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-363">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="b6443-364">Lync Server 中繼服務</span><span class="sxs-lookup"><span data-stu-id="b6443-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="b6443-365">5070</span><span class="sxs-lookup"><span data-stu-id="b6443-365">5070</span></span></p></td>
<td><p><span data-ttu-id="b6443-366">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-367">用於來自前端伺服器的 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="b6443-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-368">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-369">Persistent Chat SIP</span><span class="sxs-lookup"><span data-stu-id="b6443-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="b6443-370">5041</span><span class="sxs-lookup"><span data-stu-id="b6443-370">5041</span></span></p></td>
<td><p><span data-ttu-id="b6443-371">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-372">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-373">Persistent Chat Windows Communication Foundation (WCF) </span><span class="sxs-lookup"><span data-stu-id="b6443-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="b6443-374">881</span><span class="sxs-lookup"><span data-stu-id="b6443-374">881</span></span></p></td>
<td><p><span data-ttu-id="b6443-375">TCP (TLS) 和 TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-376">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b6443-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="b6443-377">Persistent Chat File 傳遞服務</span><span class="sxs-lookup"><span data-stu-id="b6443-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="b6443-378">443</span><span class="sxs-lookup"><span data-stu-id="b6443-378">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-379">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b6443-380">某些遠端呼叫控制案例需要在前端伺服器或 Director 和 PBX 之間建立 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="b6443-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="b6443-381">雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，此設定會將 RCC 線路伺服器 FQDN 與前端伺服器或 Director 用來連接 PBX 系統的 TCP 通訊埠產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b6443-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="b6443-382">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6443-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="b6443-383">針對只使用硬體負載平衡的集區 (不) DNS 負載平衡]，下表顯示需要開啟硬體負載平衡器的埠。</span><span class="sxs-lookup"><span data-stu-id="b6443-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="b6443-384">硬體負載平衡器埠（如果只使用硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="b6443-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6443-385">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-385">Load Balancer</span></span></th>
<th><span data-ttu-id="b6443-386">連接埠</span><span class="sxs-lookup"><span data-stu-id="b6443-386">Port</span></span></th>
<th><span data-ttu-id="b6443-387">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="b6443-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6443-388">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-389">5061</span><span class="sxs-lookup"><span data-stu-id="b6443-389">5061</span></span></p></td>
<td><p><span data-ttu-id="b6443-390">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-391">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-392">444</span><span class="sxs-lookup"><span data-stu-id="b6443-392">444</span></span></p></td>
<td><p><span data-ttu-id="b6443-393">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-394">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-395">135</span><span class="sxs-lookup"><span data-stu-id="b6443-395">135</span></span></p></td>
<td><p><span data-ttu-id="b6443-396">DCOM 和遠端過程呼叫 (RPC) </span><span class="sxs-lookup"><span data-stu-id="b6443-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-397">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-398">80</span><span class="sxs-lookup"><span data-stu-id="b6443-398">80</span></span></p></td>
<td><p><span data-ttu-id="b6443-399">HTTP:</span><span class="sxs-lookup"><span data-stu-id="b6443-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-400">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-401">8080</span><span class="sxs-lookup"><span data-stu-id="b6443-401">8080</span></span></p></td>
<td><p><span data-ttu-id="b6443-402">TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="b6443-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-403">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-404">443</span><span class="sxs-lookup"><span data-stu-id="b6443-404">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-405">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-406">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-407">4443</span><span class="sxs-lookup"><span data-stu-id="b6443-407">4443</span></span></p></td>
<td><p><span data-ttu-id="b6443-408">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="b6443-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-409">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-410">5072</span><span class="sxs-lookup"><span data-stu-id="b6443-410">5072</span></span></p></td>
<td><p><span data-ttu-id="b6443-411">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-412">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-413">5073</span><span class="sxs-lookup"><span data-stu-id="b6443-413">5073</span></span></p></td>
<td><p><span data-ttu-id="b6443-414">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-415">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-416">5075</span><span class="sxs-lookup"><span data-stu-id="b6443-416">5075</span></span></p></td>
<td><p><span data-ttu-id="b6443-417">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-418">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-419">5076</span><span class="sxs-lookup"><span data-stu-id="b6443-419">5076</span></span></p></td>
<td><p><span data-ttu-id="b6443-420">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-421">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-422">5071</span><span class="sxs-lookup"><span data-stu-id="b6443-422">5071</span></span></p></td>
<td><p><span data-ttu-id="b6443-423">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-424">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-425">5080</span><span class="sxs-lookup"><span data-stu-id="b6443-425">5080</span></span></p></td>
<td><p><span data-ttu-id="b6443-426">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-427">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-428">448</span><span class="sxs-lookup"><span data-stu-id="b6443-428">448</span></span></p></td>
<td><p><span data-ttu-id="b6443-429">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-430">轉送伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-431">5070</span><span class="sxs-lookup"><span data-stu-id="b6443-431">5070</span></span></p></td>
<td><p><span data-ttu-id="b6443-432">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-433">前端伺服器負載平衡器 (如果集區也執行轉送伺服器) </span><span class="sxs-lookup"><span data-stu-id="b6443-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="b6443-434">5070</span><span class="sxs-lookup"><span data-stu-id="b6443-434">5070</span></span></p></td>
<td><p><span data-ttu-id="b6443-435">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-436">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-437">443</span><span class="sxs-lookup"><span data-stu-id="b6443-437">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-438">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-439">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-440">444</span><span class="sxs-lookup"><span data-stu-id="b6443-440">444</span></span></p></td>
<td><p><span data-ttu-id="b6443-441">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-442">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-443">5061</span><span class="sxs-lookup"><span data-stu-id="b6443-443">5061</span></span></p></td>
<td><p><span data-ttu-id="b6443-444">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-445">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-446">4443</span><span class="sxs-lookup"><span data-stu-id="b6443-446">4443</span></span></p></td>
<td><p><span data-ttu-id="b6443-447">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="b6443-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b6443-448">使用 DNS 負載平衡的前端集區和 Director 集區也必須部署硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="b6443-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="b6443-449">下表顯示這些硬體負載平衡器上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="b6443-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="b6443-450">硬體負載平衡器埠（如果使用 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="b6443-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6443-451">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-451">Load Balancer</span></span></th>
<th><span data-ttu-id="b6443-452">連接埠</span><span class="sxs-lookup"><span data-stu-id="b6443-452">Port</span></span></th>
<th><span data-ttu-id="b6443-453">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="b6443-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6443-454">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-455">80</span><span class="sxs-lookup"><span data-stu-id="b6443-455">80</span></span></p></td>
<td><p><span data-ttu-id="b6443-456">HTTP:</span><span class="sxs-lookup"><span data-stu-id="b6443-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-457">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-458">443</span><span class="sxs-lookup"><span data-stu-id="b6443-458">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-459">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-460">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-461">8080</span><span class="sxs-lookup"><span data-stu-id="b6443-461">8080</span></span></p></td>
<td><p><span data-ttu-id="b6443-462">TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="b6443-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-463">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-464">4443</span><span class="sxs-lookup"><span data-stu-id="b6443-464">4443</span></span></p></td>
<td><p><span data-ttu-id="b6443-465">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="b6443-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-466">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-467">443</span><span class="sxs-lookup"><span data-stu-id="b6443-467">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-468">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="b6443-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-469">Director 負載平衡器</span><span class="sxs-lookup"><span data-stu-id="b6443-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="b6443-470">4443</span><span class="sxs-lookup"><span data-stu-id="b6443-470">4443</span></span></p></td>
<td><p><span data-ttu-id="b6443-471">反向 proxy 中的 HTTPS () </span><span class="sxs-lookup"><span data-stu-id="b6443-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="b6443-472">必要的用戶端埠</span><span class="sxs-lookup"><span data-stu-id="b6443-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6443-473">元件</span><span class="sxs-lookup"><span data-stu-id="b6443-473">Component</span></span></th>
<th><span data-ttu-id="b6443-474">連接埠</span><span class="sxs-lookup"><span data-stu-id="b6443-474">Port</span></span></th>
<th><span data-ttu-id="b6443-475">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="b6443-475">Protocol</span></span></th>
<th><span data-ttu-id="b6443-476">附註</span><span class="sxs-lookup"><span data-stu-id="b6443-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6443-477">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-478">67/68</span><span class="sxs-lookup"><span data-stu-id="b6443-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="b6443-479">Dhcp</span><span class="sxs-lookup"><span data-stu-id="b6443-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-480">由 Lync Server 用來尋找註冊機 FQDN (也就是說，如果 DNS SRV 失敗，且未設定) 手動設定。</span><span class="sxs-lookup"><span data-stu-id="b6443-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-481">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-482">443</span><span class="sxs-lookup"><span data-stu-id="b6443-482">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-483">TCP (TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-484">用於外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="b6443-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-485">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-486">443</span><span class="sxs-lookup"><span data-stu-id="b6443-486">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-487">TCP (PSOM/TLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-488">用於外部使用者存取 web 會議會話。</span><span class="sxs-lookup"><span data-stu-id="b6443-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-489">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-490">443</span><span class="sxs-lookup"><span data-stu-id="b6443-490">443</span></span></p></td>
<td><p><span data-ttu-id="b6443-491">TCP (STUN/MSTURN) </span><span class="sxs-lookup"><span data-stu-id="b6443-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="b6443-492">用於外部使用者存取 A/V 會話和媒體 (TCP) </span><span class="sxs-lookup"><span data-stu-id="b6443-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-493">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-494">3478</span><span class="sxs-lookup"><span data-stu-id="b6443-494">3478</span></span></p></td>
<td><p><span data-ttu-id="b6443-495">UDP (STUN/MSTURN) </span><span class="sxs-lookup"><span data-stu-id="b6443-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="b6443-496">用於外部使用者存取 A/V 會話和媒體 (UDP) </span><span class="sxs-lookup"><span data-stu-id="b6443-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-497">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-498">5061</span><span class="sxs-lookup"><span data-stu-id="b6443-498">5061</span></span></p></td>
<td><p><span data-ttu-id="b6443-499">TCP (MTLS) </span><span class="sxs-lookup"><span data-stu-id="b6443-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="b6443-500">用於外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="b6443-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-501">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="b6443-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="b6443-503">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-504">用於 Lync 用戶端和舊版用戶端之間的檔案傳輸 (Microsoft Office 通訊伺服器 2007 R2、Microsoft Office 通訊伺服器2007及 Live 通訊伺服器 2005) 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b6443-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-505">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b6443-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b6443-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b6443-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-508">音訊埠範圍 (至少需要20個埠) </span><span class="sxs-lookup"><span data-stu-id="b6443-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-509">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b6443-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b6443-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="b6443-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="b6443-512">影片埠範圍 (至少需要20個埠) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-513">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b6443-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b6443-515">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-516">對等檔案傳輸 (若為會議檔案傳輸，用戶端會使用 PSOM) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6443-517">用戶端</span><span class="sxs-lookup"><span data-stu-id="b6443-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="b6443-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="b6443-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="b6443-519">TCP</span><span class="sxs-lookup"><span data-stu-id="b6443-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-520">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="b6443-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6443-521">Aastra 6721ip 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="b6443-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="b6443-522">Aastra 6725ip 電話機</span><span class="sxs-lookup"><span data-stu-id="b6443-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="b6443-523">HP 4110 IP 電話 (通用區域電話) </span><span class="sxs-lookup"><span data-stu-id="b6443-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="b6443-524">HP 4120 IP 電話 (電話機)</span><span class="sxs-lookup"><span data-stu-id="b6443-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="b6443-525">Polycom CX500 IP 公共區域電話</span><span class="sxs-lookup"><span data-stu-id="b6443-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="b6443-526">Polycom CX600 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="b6443-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="b6443-527">Polycom CX700 IP 服務台電話</span><span class="sxs-lookup"><span data-stu-id="b6443-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="b6443-528">Polycom CX3000 IP 會議電話</span><span class="sxs-lookup"><span data-stu-id="b6443-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="b6443-529">67/68</span><span class="sxs-lookup"><span data-stu-id="b6443-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="b6443-530">Dhcp</span><span class="sxs-lookup"><span data-stu-id="b6443-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="b6443-531">由所列裝置使用以尋找 Lync Server 憑證、布建 FQDN 和註冊機 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b6443-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b6443-532">**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 及 ClientMediaPortRange 參數) 。</span><span class="sxs-lookup"><span data-stu-id="b6443-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6443-533">設定的 Lync 用戶端程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="b6443-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b6443-534">在用戶端必須透過組織的防火牆 (的任何情況下（例如，其他組織所主控的外部通訊或會議) ），都需要用於外部使用者存取的埠。</span><span class="sxs-lookup"><span data-stu-id="b6443-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

