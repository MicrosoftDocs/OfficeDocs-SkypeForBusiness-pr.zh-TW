---
title: Lync Server 2013：內部伺服器的埠和通訊協定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="351fc-102">Lync Server 2013 內部伺服器的埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="351fc-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351fc-103">_**主題上次修改日期：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="351fc-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="351fc-104">本節摘要說明伺服器、負載平衡器和 Lync Server 部署中的用戶端所使用的埠和通訊協定。</span><span class="sxs-lookup"><span data-stu-id="351fc-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="351fc-105">當 Lync 與 Communicator 用戶端參與單一通訊時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="351fc-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="351fc-106">從技術角度來看，兩個用戶端都是以單一交談的方式進行通訊，中間是中間的立即訊息 multipoint 控制項單位（IMMCU）。</span><span class="sxs-lookup"><span data-stu-id="351fc-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="351fc-107">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="351fc-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="351fc-108">將 IMMCU 放在所需的通訊工作流程中，即可允許通話詳細資料錄製，以及前端伺服器所能啟用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="351fc-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="351fc-109">通訊來自用戶端上的動態來源埠到前端伺服器埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性）。</span><span class="sxs-lookup"><span data-stu-id="351fc-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="351fc-110">透過設計、對等通訊（以及多方 IM），只有當 Lync Server 與 IMMCU 處於作用中且可用時，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="351fc-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="351fc-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="351fc-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="351fc-112">在伺服器上啟動 Lync Server services 之前，Windows 防火牆必須執行，因為 Lync Server 在防火牆中開啟必要的埠。</span><span class="sxs-lookup"><span data-stu-id="351fc-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="351fc-113">如需有關 edge 元件防火牆設定的詳細資料，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="351fc-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="351fc-114">下表列出每個內部伺服器角色上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="351fc-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="351fc-115">所需的伺服器埠（依伺服器角色）</span><span class="sxs-lookup"><span data-stu-id="351fc-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="351fc-116">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="351fc-116">Server role</span></span></th>
<th><span data-ttu-id="351fc-117">服務名稱</span><span class="sxs-lookup"><span data-stu-id="351fc-117">Service name</span></span></th>
<th><span data-ttu-id="351fc-118">通道</span><span class="sxs-lookup"><span data-stu-id="351fc-118">Port</span></span></th>
<th><span data-ttu-id="351fc-119">通訊協定</span><span class="sxs-lookup"><span data-stu-id="351fc-119">Protocol</span></span></th>
<th><span data-ttu-id="351fc-120">筆記</span><span class="sxs-lookup"><span data-stu-id="351fc-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351fc-121">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-122">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="351fc-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="351fc-123">1434</span><span class="sxs-lookup"><span data-stu-id="351fc-123">1434</span></span></p></td>
<td><p><span data-ttu-id="351fc-124">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="351fc-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-125">中央管理儲存資料庫的本機複製複本的 SQL 瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="351fc-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-126">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-127">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-128">5060</span><span class="sxs-lookup"><span data-stu-id="351fc-128">5060</span></span></p></td>
<td><p><span data-ttu-id="351fc-129">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-130">您也可以選擇將標準版伺服器與前端伺服器（例如遠端通話控制伺服器）的靜態路由使用。</span><span class="sxs-lookup"><span data-stu-id="351fc-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-131">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-132">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-133">5061</span><span class="sxs-lookup"><span data-stu-id="351fc-133">5061</span></span></p></td>
<td><p><span data-ttu-id="351fc-134">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-135">由標準版伺服器和前端池使用，可用於伺服器與用戶端（MTLS）之間的所有內部 SIP 通訊，以及前端伺服器與中繼伺服器（MTLS）之間的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="351fc-136">也用於與監控伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-137">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-138">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-139">444</span><span class="sxs-lookup"><span data-stu-id="351fc-139">444</span></span></p></td>
<td><p><span data-ttu-id="351fc-140">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-140">HTTPS</span></span></p>
<p><span data-ttu-id="351fc-141">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-142">用於焦點（管理會議狀態的 Lync 伺服器元件）與個別伺服器之間的 HTTPS 通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="351fc-143">此埠也用於 Survivable 分支裝置與前端伺服器之間的 TCP 通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-144">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-145">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-146">135</span><span class="sxs-lookup"><span data-stu-id="351fc-146">135</span></span></p></td>
<td><p><span data-ttu-id="351fc-147">DCOM 與遠端程式通話（RPC）</span><span class="sxs-lookup"><span data-stu-id="351fc-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="351fc-148">用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製程式同步處理和通訊錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="351fc-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-149">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-150">Lync Server IM 會議服務</span><span class="sxs-lookup"><span data-stu-id="351fc-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-151">5062</span><span class="sxs-lookup"><span data-stu-id="351fc-151">5062</span></span></p></td>
<td><p><span data-ttu-id="351fc-152">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-153">用於立即訊息（IM）會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-154">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-155">Lync Server Web 會議服務</span><span class="sxs-lookup"><span data-stu-id="351fc-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-156">8057</span><span class="sxs-lookup"><span data-stu-id="351fc-156">8057</span></span></p></td>
<td><p><span data-ttu-id="351fc-157">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-158">用來偵聽來自用戶端的永久性共用物件模型（PSOM）連線。</span><span class="sxs-lookup"><span data-stu-id="351fc-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-159">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-160">Lync Server Web 會議相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-161">8058</span><span class="sxs-lookup"><span data-stu-id="351fc-161">8058</span></span></p></td>
<td><p><span data-ttu-id="351fc-162">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-163">用來從 Live Meeting 用戶端和舊版的 Lync Server，偵聽永久共用物件模型（PSOM）連線。</span><span class="sxs-lookup"><span data-stu-id="351fc-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-164">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-165">Lync Server 音訊/視訊會議服務</span><span class="sxs-lookup"><span data-stu-id="351fc-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-166">5063</span><span class="sxs-lookup"><span data-stu-id="351fc-166">5063</span></span></p></td>
<td><p><span data-ttu-id="351fc-167">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-168">用於音訊/視頻（A/V）會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-169">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-170">Lync Server 音訊/視訊會議服務</span><span class="sxs-lookup"><span data-stu-id="351fc-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="351fc-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="351fc-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="351fc-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-173">用於視訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="351fc-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-174">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-175">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-176">80</span><span class="sxs-lookup"><span data-stu-id="351fc-176">80</span></span></p></td>
<td><p><span data-ttu-id="351fc-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="351fc-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="351fc-178">用於從前端伺服器到網路伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url），在未使用 HTTPS 時進行通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-179">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-180">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-181">443</span><span class="sxs-lookup"><span data-stu-id="351fc-181">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-182">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="351fc-183">用來從前端伺服器與網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）進行通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-184">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-185">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-186">8080</span><span class="sxs-lookup"><span data-stu-id="351fc-186">8080</span></span></p></td>
<td><p><span data-ttu-id="351fc-187">TCP 與 HTTP</span><span class="sxs-lookup"><span data-stu-id="351fc-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="351fc-188">供外部存取的網頁元件使用。</span><span class="sxs-lookup"><span data-stu-id="351fc-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-189">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-190">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="351fc-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="351fc-191">4443</span><span class="sxs-lookup"><span data-stu-id="351fc-191">4443</span></span></p></td>
<td><p><span data-ttu-id="351fc-192">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="351fc-193">HTTPS （從反向 Proxy）與 HTTPS 前端端池通訊，以進行自動探索登入。</span><span class="sxs-lookup"><span data-stu-id="351fc-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-194">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-195">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="351fc-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="351fc-196">8060</span><span class="sxs-lookup"><span data-stu-id="351fc-196">8060</span></span></p></td>
<td><p><span data-ttu-id="351fc-197">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-198">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-199">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="351fc-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="351fc-200">8061</span><span class="sxs-lookup"><span data-stu-id="351fc-200">8061</span></span></p></td>
<td><p><span data-ttu-id="351fc-201">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-202">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-203">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="351fc-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="351fc-204">5086</span><span class="sxs-lookup"><span data-stu-id="351fc-204">5086</span></span></p></td>
<td><p><span data-ttu-id="351fc-205">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-206">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="351fc-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-207">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-208">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="351fc-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="351fc-209">5087</span><span class="sxs-lookup"><span data-stu-id="351fc-209">5087</span></span></p></td>
<td><p><span data-ttu-id="351fc-210">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-211">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="351fc-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-212">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-213">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="351fc-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="351fc-214">443</span><span class="sxs-lookup"><span data-stu-id="351fc-214">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-215">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-216">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-217">Lync Server 會議助理服務（電話撥入式會議）</span><span class="sxs-lookup"><span data-stu-id="351fc-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="351fc-218">5064</span><span class="sxs-lookup"><span data-stu-id="351fc-218">5064</span></span></p></td>
<td><p><span data-ttu-id="351fc-219">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-220">用於電話撥入式會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-221">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-222">Lync Server 會議助理服務（電話撥入式會議）</span><span class="sxs-lookup"><span data-stu-id="351fc-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="351fc-223">5072</span><span class="sxs-lookup"><span data-stu-id="351fc-223">5072</span></span></p></td>
<td><p><span data-ttu-id="351fc-224">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-225">用於接聽的傳入 SIP 要求（撥入會議）。</span><span class="sxs-lookup"><span data-stu-id="351fc-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-226">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-227">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-228">5070</span><span class="sxs-lookup"><span data-stu-id="351fc-228">5070</span></span></p></td>
<td><p><span data-ttu-id="351fc-229">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-230">供中繼伺服器用來將前端伺服器的傳入要求傳送到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-231">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-232">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-233">5067</span><span class="sxs-lookup"><span data-stu-id="351fc-233">5067</span></span></p></td>
<td><p><span data-ttu-id="351fc-234">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-235">用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-236">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-237">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-238">5068</span><span class="sxs-lookup"><span data-stu-id="351fc-238">5068</span></span></p></td>
<td><p><span data-ttu-id="351fc-239">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-240">用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-241">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-242">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-243">5081</span><span class="sxs-lookup"><span data-stu-id="351fc-243">5081</span></span></p></td>
<td><p><span data-ttu-id="351fc-244">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-245">用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-246">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-247">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-248">5082</span><span class="sxs-lookup"><span data-stu-id="351fc-248">5082</span></span></p></td>
<td><p><span data-ttu-id="351fc-249">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-250">用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-251">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-252">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="351fc-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-253">5065</span><span class="sxs-lookup"><span data-stu-id="351fc-253">5065</span></span></p></td>
<td><p><span data-ttu-id="351fc-254">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-255">用於應用程式共用的傳入 SIP 偵聽要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-256">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-257">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="351fc-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="351fc-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="351fc-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="351fc-259">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-260">用來共用應用程式的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="351fc-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-261">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-262">Lync Server 會議宣告服務</span><span class="sxs-lookup"><span data-stu-id="351fc-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="351fc-263">5073</span><span class="sxs-lookup"><span data-stu-id="351fc-263">5073</span></span></p></td>
<td><p><span data-ttu-id="351fc-264">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-265">用於 Lync Server 會議宣告服務的傳入 SIP 要求（也就是電話撥入式會議）。</span><span class="sxs-lookup"><span data-stu-id="351fc-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-266">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-267">Lync Server 通話寄存服務</span><span class="sxs-lookup"><span data-stu-id="351fc-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="351fc-268">5075</span><span class="sxs-lookup"><span data-stu-id="351fc-268">5075</span></span></p></td>
<td><p><span data-ttu-id="351fc-269">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-270">用於來電寄存應用程式的內送 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-271">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-272">Lync Server 音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="351fc-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="351fc-273">5076</span><span class="sxs-lookup"><span data-stu-id="351fc-273">5076</span></span></p></td>
<td><p><span data-ttu-id="351fc-274">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-275">用於音訊測試服務的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-276">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-277">不適用</span><span class="sxs-lookup"><span data-stu-id="351fc-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="351fc-278">5066</span><span class="sxs-lookup"><span data-stu-id="351fc-278">5066</span></span></p></td>
<td><p><span data-ttu-id="351fc-279">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-280">用於輸出增強型9-1-1 （E9-1-1）閘道。</span><span class="sxs-lookup"><span data-stu-id="351fc-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-281">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-282">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="351fc-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="351fc-283">5071</span><span class="sxs-lookup"><span data-stu-id="351fc-283">5071</span></span></p></td>
<td><p><span data-ttu-id="351fc-284">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-285">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-286">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-287">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="351fc-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="351fc-288">8404</span><span class="sxs-lookup"><span data-stu-id="351fc-288">8404</span></span></p></td>
<td><p><span data-ttu-id="351fc-289">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-290">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-291">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-292">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="351fc-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="351fc-293">5080</span><span class="sxs-lookup"><span data-stu-id="351fc-293">5080</span></span></p></td>
<td><p><span data-ttu-id="351fc-294">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-295">用於由頻寬原則服務為 A/V 邊緣開啟流量的呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="351fc-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-296">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-297">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="351fc-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="351fc-298">448</span><span class="sxs-lookup"><span data-stu-id="351fc-298">448</span></span></p></td>
<td><p><span data-ttu-id="351fc-299">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-300">用於 Lync Server 頻寬策略服務的呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="351fc-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-301">中央管理儲存所在的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="351fc-302">Lync Server 主版複製程式代理服務</span><span class="sxs-lookup"><span data-stu-id="351fc-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="351fc-303">445</span><span class="sxs-lookup"><span data-stu-id="351fc-303">445</span></span></p></td>
<td><p><span data-ttu-id="351fc-304">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-305">用來將配置資料從中央管理存儲推送到執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-306">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-307">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="351fc-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="351fc-308">1434</span><span class="sxs-lookup"><span data-stu-id="351fc-308">1434</span></span></p></td>
<td><p><span data-ttu-id="351fc-309">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="351fc-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-310">本機 SQL Server 實例中的中央管理儲存在本機複製複本的 SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="351fc-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-311">所有內部伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-312">各種各樣</span><span class="sxs-lookup"><span data-stu-id="351fc-312">Various</span></span></p></td>
<td><p><span data-ttu-id="351fc-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="351fc-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="351fc-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="351fc-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-315">在所有內部伺服器上，音訊會議所用的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="351fc-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="351fc-316">是由所有終止音訊的伺服器所使用：前端伺服器（適用于 Lync Server 會議助理服務、Lync Server 會議宣告服務，以及 Lync server 音訊/視訊會議服務）及中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-317">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="351fc-318">443</span><span class="sxs-lookup"><span data-stu-id="351fc-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="351fc-319">由 Lync Server 2013 用來連線到 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-320">控制器</span><span class="sxs-lookup"><span data-stu-id="351fc-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="351fc-321">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-322">5060</span><span class="sxs-lookup"><span data-stu-id="351fc-322">5060</span></span></p></td>
<td><p><span data-ttu-id="351fc-323">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-324">您也可以選擇將靜態路由用於受信任的服務，例如遠端通話控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="351fc-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-325">控制器</span><span class="sxs-lookup"><span data-stu-id="351fc-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="351fc-326">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-327">444</span><span class="sxs-lookup"><span data-stu-id="351fc-327">444</span></span></p></td>
<td><p><span data-ttu-id="351fc-328">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-328">HTTPS</span></span></p>
<p><span data-ttu-id="351fc-329">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-330">前端與控制器之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="351fc-331">此外，用戶端憑證發佈（到前端伺服器）或驗證用戶端憑證是否已發佈。</span><span class="sxs-lookup"><span data-stu-id="351fc-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-332">控制器</span><span class="sxs-lookup"><span data-stu-id="351fc-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="351fc-333">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-334">80</span><span class="sxs-lookup"><span data-stu-id="351fc-334">80</span></span></p></td>
<td><p><span data-ttu-id="351fc-335">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-336">用於從董事到網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）的初始通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="351fc-337">在 [標準] 操作中，會使用埠443和通訊協定類型 TCP，切換到 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="351fc-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-338">控制器</span><span class="sxs-lookup"><span data-stu-id="351fc-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="351fc-339">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="351fc-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="351fc-340">443</span><span class="sxs-lookup"><span data-stu-id="351fc-340">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-341">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="351fc-342">用於從控制器到網頁伺服器陣列 Fqdn （IIS 網頁元件所用的 Url）的通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-343">控制器</span><span class="sxs-lookup"><span data-stu-id="351fc-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="351fc-344">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="351fc-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="351fc-345">5061</span><span class="sxs-lookup"><span data-stu-id="351fc-345">5061</span></span></p></td>
<td><p><span data-ttu-id="351fc-346">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-347">用於伺服器與用戶端連線之間的內部通訊。</span><span class="sxs-lookup"><span data-stu-id="351fc-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-348">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-349">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-350">5070</span><span class="sxs-lookup"><span data-stu-id="351fc-350">5070</span></span></p></td>
<td><p><span data-ttu-id="351fc-351">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-352">由中繼伺服器用於來自前端伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-353">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-354">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-355">5067</span><span class="sxs-lookup"><span data-stu-id="351fc-355">5067</span></span></p></td>
<td><p><span data-ttu-id="351fc-356">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-357">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-358">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-359">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-360">5068</span><span class="sxs-lookup"><span data-stu-id="351fc-360">5068</span></span></p></td>
<td><p><span data-ttu-id="351fc-361">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-362">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-363">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="351fc-364">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="351fc-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="351fc-365">5070</span><span class="sxs-lookup"><span data-stu-id="351fc-365">5070</span></span></p></td>
<td><p><span data-ttu-id="351fc-366">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-367">用於來自前端伺服器的 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="351fc-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-368">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-369">持續聊天 SIP</span><span class="sxs-lookup"><span data-stu-id="351fc-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="351fc-370">5041</span><span class="sxs-lookup"><span data-stu-id="351fc-370">5041</span></span></p></td>
<td><p><span data-ttu-id="351fc-371">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-372">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-373">持續聊天 Windows Communication Foundation （WCF）</span><span class="sxs-lookup"><span data-stu-id="351fc-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="351fc-374">881</span><span class="sxs-lookup"><span data-stu-id="351fc-374">881</span></span></p></td>
<td><p><span data-ttu-id="351fc-375">TCP （TLS）和 TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-376">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="351fc-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="351fc-377">持續聊天檔案傳輸服務</span><span class="sxs-lookup"><span data-stu-id="351fc-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="351fc-378">443</span><span class="sxs-lookup"><span data-stu-id="351fc-378">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-379">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="351fc-380">某些遠端呼叫控制案例需要在前端伺服器或控制器與 PBX 之間建立 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="351fc-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="351fc-381">雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，這會將 RCC 線路伺服器 FQDN 與前端伺服器或控制器用來連接 PBX 系統的 TCP 埠產生關聯。</span><span class="sxs-lookup"><span data-stu-id="351fc-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="351fc-382">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351fc-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="351fc-383">針對只使用硬體負載平衡的池（而非 DNS 負載平衡），下表顯示需要開啟硬體負載平衡器的埠。</span><span class="sxs-lookup"><span data-stu-id="351fc-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="351fc-384">硬體負載平衡器埠（如果只使用硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="351fc-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351fc-385">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-385">Load Balancer</span></span></th>
<th><span data-ttu-id="351fc-386">通道</span><span class="sxs-lookup"><span data-stu-id="351fc-386">Port</span></span></th>
<th><span data-ttu-id="351fc-387">通訊協定</span><span class="sxs-lookup"><span data-stu-id="351fc-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351fc-388">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-389">5061</span><span class="sxs-lookup"><span data-stu-id="351fc-389">5061</span></span></p></td>
<td><p><span data-ttu-id="351fc-390">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-391">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-392">444</span><span class="sxs-lookup"><span data-stu-id="351fc-392">444</span></span></p></td>
<td><p><span data-ttu-id="351fc-393">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-394">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-395">135</span><span class="sxs-lookup"><span data-stu-id="351fc-395">135</span></span></p></td>
<td><p><span data-ttu-id="351fc-396">DCOM 與遠端程式通話（RPC）</span><span class="sxs-lookup"><span data-stu-id="351fc-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-397">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-398">80</span><span class="sxs-lookup"><span data-stu-id="351fc-398">80</span></span></p></td>
<td><p><span data-ttu-id="351fc-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="351fc-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-400">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-401">8080</span><span class="sxs-lookup"><span data-stu-id="351fc-401">8080</span></span></p></td>
<td><p><span data-ttu-id="351fc-402">從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</span><span class="sxs-lookup"><span data-stu-id="351fc-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-403">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-404">443</span><span class="sxs-lookup"><span data-stu-id="351fc-404">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-405">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-406">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-407">4443</span><span class="sxs-lookup"><span data-stu-id="351fc-407">4443</span></span></p></td>
<td><p><span data-ttu-id="351fc-408">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="351fc-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-409">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-410">5072</span><span class="sxs-lookup"><span data-stu-id="351fc-410">5072</span></span></p></td>
<td><p><span data-ttu-id="351fc-411">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-412">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-413">5073</span><span class="sxs-lookup"><span data-stu-id="351fc-413">5073</span></span></p></td>
<td><p><span data-ttu-id="351fc-414">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-415">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-416">5075</span><span class="sxs-lookup"><span data-stu-id="351fc-416">5075</span></span></p></td>
<td><p><span data-ttu-id="351fc-417">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-418">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-419">5076</span><span class="sxs-lookup"><span data-stu-id="351fc-419">5076</span></span></p></td>
<td><p><span data-ttu-id="351fc-420">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-421">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-422">5071</span><span class="sxs-lookup"><span data-stu-id="351fc-422">5071</span></span></p></td>
<td><p><span data-ttu-id="351fc-423">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-424">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-425">5080</span><span class="sxs-lookup"><span data-stu-id="351fc-425">5080</span></span></p></td>
<td><p><span data-ttu-id="351fc-426">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-427">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-428">448</span><span class="sxs-lookup"><span data-stu-id="351fc-428">448</span></span></p></td>
<td><p><span data-ttu-id="351fc-429">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-430">中繼伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-431">5070</span><span class="sxs-lookup"><span data-stu-id="351fc-431">5070</span></span></p></td>
<td><p><span data-ttu-id="351fc-432">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-433">前端伺服器負載平衡器（如果該池也會執行轉送伺服器）</span><span class="sxs-lookup"><span data-stu-id="351fc-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="351fc-434">5070</span><span class="sxs-lookup"><span data-stu-id="351fc-434">5070</span></span></p></td>
<td><p><span data-ttu-id="351fc-435">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-436">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-437">443</span><span class="sxs-lookup"><span data-stu-id="351fc-437">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-438">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-439">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-440">444</span><span class="sxs-lookup"><span data-stu-id="351fc-440">444</span></span></p></td>
<td><p><span data-ttu-id="351fc-441">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-442">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-443">5061</span><span class="sxs-lookup"><span data-stu-id="351fc-443">5061</span></span></p></td>
<td><p><span data-ttu-id="351fc-444">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-445">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-446">4443</span><span class="sxs-lookup"><span data-stu-id="351fc-446">4443</span></span></p></td>
<td><p><span data-ttu-id="351fc-447">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="351fc-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="351fc-448">您的前端池和使用 DNS 負載平衡的控制器池也必須部署硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="351fc-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="351fc-449">下表顯示在這些硬體負載平衡器上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="351fc-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="351fc-450">使用 DNS 負載平衡的硬體負載平衡器埠</span><span class="sxs-lookup"><span data-stu-id="351fc-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351fc-451">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-451">Load Balancer</span></span></th>
<th><span data-ttu-id="351fc-452">通道</span><span class="sxs-lookup"><span data-stu-id="351fc-452">Port</span></span></th>
<th><span data-ttu-id="351fc-453">通訊協定</span><span class="sxs-lookup"><span data-stu-id="351fc-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351fc-454">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-455">80</span><span class="sxs-lookup"><span data-stu-id="351fc-455">80</span></span></p></td>
<td><p><span data-ttu-id="351fc-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="351fc-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-457">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-458">443</span><span class="sxs-lookup"><span data-stu-id="351fc-458">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-459">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-460">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-461">8080</span><span class="sxs-lookup"><span data-stu-id="351fc-461">8080</span></span></p></td>
<td><p><span data-ttu-id="351fc-462">從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</span><span class="sxs-lookup"><span data-stu-id="351fc-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-463">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-464">4443</span><span class="sxs-lookup"><span data-stu-id="351fc-464">4443</span></span></p></td>
<td><p><span data-ttu-id="351fc-465">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="351fc-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-466">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-467">443</span><span class="sxs-lookup"><span data-stu-id="351fc-467">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-468">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="351fc-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-469">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="351fc-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="351fc-470">4443</span><span class="sxs-lookup"><span data-stu-id="351fc-470">4443</span></span></p></td>
<td><p><span data-ttu-id="351fc-471">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="351fc-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="351fc-472">所需的用戶端埠</span><span class="sxs-lookup"><span data-stu-id="351fc-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="351fc-473">元件</span><span class="sxs-lookup"><span data-stu-id="351fc-473">Component</span></span></th>
<th><span data-ttu-id="351fc-474">通道</span><span class="sxs-lookup"><span data-stu-id="351fc-474">Port</span></span></th>
<th><span data-ttu-id="351fc-475">通訊協定</span><span class="sxs-lookup"><span data-stu-id="351fc-475">Protocol</span></span></th>
<th><span data-ttu-id="351fc-476">筆記</span><span class="sxs-lookup"><span data-stu-id="351fc-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="351fc-477">台</span><span class="sxs-lookup"><span data-stu-id="351fc-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-478">67/68</span><span class="sxs-lookup"><span data-stu-id="351fc-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="351fc-479">動態</span><span class="sxs-lookup"><span data-stu-id="351fc-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-480">由 Lync Server 用來尋找註冊機 FQDN （也就是如果 DNS SRV 失敗且沒有設定手動設定）。</span><span class="sxs-lookup"><span data-stu-id="351fc-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-481">台</span><span class="sxs-lookup"><span data-stu-id="351fc-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-482">443</span><span class="sxs-lookup"><span data-stu-id="351fc-482">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-483">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-484">用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="351fc-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-485">台</span><span class="sxs-lookup"><span data-stu-id="351fc-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-486">443</span><span class="sxs-lookup"><span data-stu-id="351fc-486">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-487">TCP （PSOM/TLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-488">用於外部使用者存取網路會議會話。</span><span class="sxs-lookup"><span data-stu-id="351fc-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-489">台</span><span class="sxs-lookup"><span data-stu-id="351fc-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-490">443</span><span class="sxs-lookup"><span data-stu-id="351fc-490">443</span></span></p></td>
<td><p><span data-ttu-id="351fc-491">TCP （STUN/MSTURN）</span><span class="sxs-lookup"><span data-stu-id="351fc-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="351fc-492">供外部使用者存取 A/V 會話及媒體（TCP）</span><span class="sxs-lookup"><span data-stu-id="351fc-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-493">台</span><span class="sxs-lookup"><span data-stu-id="351fc-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-494">3478</span><span class="sxs-lookup"><span data-stu-id="351fc-494">3478</span></span></p></td>
<td><p><span data-ttu-id="351fc-495">UDP （STUN/MSTURN）</span><span class="sxs-lookup"><span data-stu-id="351fc-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="351fc-496">供外部使用者存取 A/V 會話及媒體（UDP）</span><span class="sxs-lookup"><span data-stu-id="351fc-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-497">台</span><span class="sxs-lookup"><span data-stu-id="351fc-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-498">5061</span><span class="sxs-lookup"><span data-stu-id="351fc-498">5061</span></span></p></td>
<td><p><span data-ttu-id="351fc-499">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="351fc-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="351fc-500">用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="351fc-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-501">台</span><span class="sxs-lookup"><span data-stu-id="351fc-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="351fc-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="351fc-503">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-504">用於 Lync 用戶端與舊版用戶端之間的檔案傳輸（Microsoft Office 通訊伺服器 2007 R2 的用戶端、Microsoft Office 通訊伺服器2007，以及即時通訊伺服器2005）。</span><span class="sxs-lookup"><span data-stu-id="351fc-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-505">台</span><span class="sxs-lookup"><span data-stu-id="351fc-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="351fc-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="351fc-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="351fc-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-508">音訊埠範圍（所需的最小20個埠）</span><span class="sxs-lookup"><span data-stu-id="351fc-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-509">台</span><span class="sxs-lookup"><span data-stu-id="351fc-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="351fc-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="351fc-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="351fc-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="351fc-512">影片埠範圍（需要20個埠的最小值）。</span><span class="sxs-lookup"><span data-stu-id="351fc-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-513">台</span><span class="sxs-lookup"><span data-stu-id="351fc-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="351fc-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="351fc-515">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-516">對等檔案傳輸（適用于會議檔案傳輸，用戶端使用 PSOM）。</span><span class="sxs-lookup"><span data-stu-id="351fc-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="351fc-517">台</span><span class="sxs-lookup"><span data-stu-id="351fc-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="351fc-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="351fc-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="351fc-519">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="351fc-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-520">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="351fc-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="351fc-521">Aastra 6721ip 常見區域電話</span><span class="sxs-lookup"><span data-stu-id="351fc-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="351fc-522">Aastra 6725ip phone</span><span class="sxs-lookup"><span data-stu-id="351fc-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="351fc-523">HP 4110 IP Phone （通用區域電話）</span><span class="sxs-lookup"><span data-stu-id="351fc-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="351fc-524">HP 4120 IP Phone （辦公桌電話）</span><span class="sxs-lookup"><span data-stu-id="351fc-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="351fc-525">Polycom CX500 IP 常見區域電話</span><span class="sxs-lookup"><span data-stu-id="351fc-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="351fc-526">Polycom CX600 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="351fc-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="351fc-527">Polycom CX700 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="351fc-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="351fc-528">Polycom CX3000 IP 會議電話</span><span class="sxs-lookup"><span data-stu-id="351fc-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="351fc-529">67/68</span><span class="sxs-lookup"><span data-stu-id="351fc-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="351fc-530">動態</span><span class="sxs-lookup"><span data-stu-id="351fc-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="351fc-531">由所列的裝置使用，以尋找 Lync 伺服器憑證、資源調配 FQDN 和註冊機 FQDN。</span><span class="sxs-lookup"><span data-stu-id="351fc-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="351fc-532">**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet （ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 參數）。</span><span class="sxs-lookup"><span data-stu-id="351fc-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="351fc-533">Lync 用戶端的設定程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="351fc-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="351fc-534">在用戶端必須遍歷組織的防火牆（例如，任何外部通訊或其他組織託管的會議）的情況下，對於外部使用者存取所用的埠，都是必要的。</span><span class="sxs-lookup"><span data-stu-id="351fc-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

