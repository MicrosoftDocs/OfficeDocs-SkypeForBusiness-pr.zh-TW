---
title: Lync Server 2013：內部伺服器的埠和通訊協定
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
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="eb191-102">Lync Server 2013 內部伺服器的埠和通訊協定</span><span class="sxs-lookup"><span data-stu-id="eb191-102">Ports and protocols for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb191-103">_**主題上次修改日期：** 2016-04-06_</span><span class="sxs-lookup"><span data-stu-id="eb191-103">_**Topic Last Modified:** 2016-04-06_</span></span>

<span data-ttu-id="eb191-104">本節摘要說明伺服器、負載平衡器和 Lync Server 部署中的用戶端所使用的埠和通訊協定。</span><span class="sxs-lookup"><span data-stu-id="eb191-104">This section summarizes the ports and protocols used by servers, load balancers, and clients in a Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb191-105">當 Lync 與 Communicator 用戶端參與單一通訊時，通常稱為對等。</span><span class="sxs-lookup"><span data-stu-id="eb191-105">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="eb191-106">從技術角度來看，兩個用戶端都是以單一交談的方式進行通訊，中間是中間的立即訊息 multipoint 控制項單位（IMMCU）。</span><span class="sxs-lookup"><span data-stu-id="eb191-106">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="eb191-107">IMMCU 是前端伺服器的元件。</span><span class="sxs-lookup"><span data-stu-id="eb191-107">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="eb191-108">將 IMMCU 放在所需的通訊工作流程中，即可允許通話詳細資料錄製，以及前端伺服器所能啟用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="eb191-108">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="eb191-109">通訊來自用戶端上的動態來源埠到前端伺服器埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性）。</span><span class="sxs-lookup"><span data-stu-id="eb191-109">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="eb191-110">透過設計、對等通訊（以及多方 IM），只有當 Lync Server 與 IMMCU 處於作用中且可用時，才可以使用。</span><span class="sxs-lookup"><span data-stu-id="eb191-110">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="eb191-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="eb191-111">Port and Protocol Details</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb191-112">在伺服器上啟動 Lync Server services 之前，Windows 防火牆必須執行，因為 Lync Server 在防火牆中開啟必要的埠。</span><span class="sxs-lookup"><span data-stu-id="eb191-112">Windows Firewall must be running before you start the Lync Server services on a server, because that is when Lync Server opens the required ports in the firewall.</span></span>



</div>

<span data-ttu-id="eb191-113">如需有關 edge 元件防火牆設定的詳細資料，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb191-113">For details about firewall configuration for edge components, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

<span data-ttu-id="eb191-114">下表列出每個內部伺服器角色上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="eb191-114">The following table lists the ports that need to be open on each internal server role.</span></span>

### <a name="required-server-ports-by-server-role"></a><span data-ttu-id="eb191-115">所需的伺服器埠（依伺服器角色）</span><span class="sxs-lookup"><span data-stu-id="eb191-115">Required Server Ports (by Server Role)</span></span>

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
<th><span data-ttu-id="eb191-116">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="eb191-116">Server role</span></span></th>
<th><span data-ttu-id="eb191-117">服務名稱</span><span class="sxs-lookup"><span data-stu-id="eb191-117">Service name</span></span></th>
<th><span data-ttu-id="eb191-118">通道</span><span class="sxs-lookup"><span data-stu-id="eb191-118">Port</span></span></th>
<th><span data-ttu-id="eb191-119">通訊協定</span><span class="sxs-lookup"><span data-stu-id="eb191-119">Protocol</span></span></th>
<th><span data-ttu-id="eb191-120">筆記</span><span class="sxs-lookup"><span data-stu-id="eb191-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb191-121">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-121">All Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-122">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="eb191-122">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="eb191-123">1434</span><span class="sxs-lookup"><span data-stu-id="eb191-123">1434</span></span></p></td>
<td><p><span data-ttu-id="eb191-124">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="eb191-124">UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-125">中央管理儲存資料庫的本機複製複本的 SQL 瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="eb191-125">SQL Browser for the local replicated copy of the Central Management Store database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-126">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-126">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-127">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-127">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-128">5060</span><span class="sxs-lookup"><span data-stu-id="eb191-128">5060</span></span></p></td>
<td><p><span data-ttu-id="eb191-129">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-129">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-130">您也可以選擇將標準版伺服器與前端伺服器（例如遠端通話控制伺服器）的靜態路由使用。</span><span class="sxs-lookup"><span data-stu-id="eb191-130">Optionally used by Standard Edition servers and Front End Servers for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-131">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-131">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-132">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-132">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-133">5061</span><span class="sxs-lookup"><span data-stu-id="eb191-133">5061</span></span></p></td>
<td><p><span data-ttu-id="eb191-134">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-134">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-135">由標準版伺服器和前端池使用，可用於伺服器與用戶端（MTLS）之間的所有內部 SIP 通訊，以及前端伺服器與中繼伺服器（MTLS）之間的 SIP 通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-135">Used by Standard Edition servers and Front End pools for all internal SIP communications between servers (MTLS), for SIP communications between Server and Client (TLS) and for SIP communications between Front End Servers and Mediation Servers (MTLS).</span></span> <span data-ttu-id="eb191-136">也用於與監控伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-136">Also used for communications with Monitoring Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-137">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-137">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-138">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-138">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-139">444</span><span class="sxs-lookup"><span data-stu-id="eb191-139">444</span></span></p></td>
<td><p><span data-ttu-id="eb191-140">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-140">HTTPS</span></span></p>
<p><span data-ttu-id="eb191-141">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-141">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-142">用於焦點（管理會議狀態的 Lync 伺服器元件）與個別伺服器之間的 HTTPS 通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-142">Used for HTTPS communication between the Focus (the Lync Server component that manages conference state) and the individual servers.</span></span></p>
<p><span data-ttu-id="eb191-143">此埠也用於 Survivable 分支裝置與前端伺服器之間的 TCP 通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-143">This port is also used for TCP communication between Survivable Branch Appliances and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-144">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-144">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-145">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-145">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-146">135</span><span class="sxs-lookup"><span data-stu-id="eb191-146">135</span></span></p></td>
<td><p><span data-ttu-id="eb191-147">DCOM 與遠端程式通話（RPC）</span><span class="sxs-lookup"><span data-stu-id="eb191-147">DCOM and remote procedure call (RPC)</span></span></p></td>
<td><p><span data-ttu-id="eb191-148">用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製程式同步處理和通訊錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="eb191-148">Used for DCOM based operations such as Moving Users, User Replicator Synchronization, and Address Book Synchronization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-149">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-149">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-150">Lync Server IM 會議服務</span><span class="sxs-lookup"><span data-stu-id="eb191-150">Lync Server IM Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-151">5062</span><span class="sxs-lookup"><span data-stu-id="eb191-151">5062</span></span></p></td>
<td><p><span data-ttu-id="eb191-152">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-152">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-153">用於立即訊息（IM）會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-153">Used for incoming SIP requests for instant messaging (IM) conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-154">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-154">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-155">Lync Server Web 會議服務</span><span class="sxs-lookup"><span data-stu-id="eb191-155">Lync Server Web Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-156">8057</span><span class="sxs-lookup"><span data-stu-id="eb191-156">8057</span></span></p></td>
<td><p><span data-ttu-id="eb191-157">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-157">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-158">用來偵聽來自用戶端的永久性共用物件模型（PSOM）連線。</span><span class="sxs-lookup"><span data-stu-id="eb191-158">Used to listen for Persistent Shared Object Model (PSOM) connections from client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-159">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-159">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-160">Lync Server Web 會議相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-160">Lync Server Web Conferencing Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-161">8058</span><span class="sxs-lookup"><span data-stu-id="eb191-161">8058</span></span></p></td>
<td><p><span data-ttu-id="eb191-162">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-162">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-163">用來從 Live Meeting 用戶端和舊版的 Lync Server，偵聽永久共用物件模型（PSOM）連線。</span><span class="sxs-lookup"><span data-stu-id="eb191-163">Used to listen for Persistent Shared Object Model (PSOM) connections from the Live Meeting client and previous versions of Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-164">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-164">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-165">Lync Server 音訊/視訊會議服務</span><span class="sxs-lookup"><span data-stu-id="eb191-165">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-166">5063</span><span class="sxs-lookup"><span data-stu-id="eb191-166">5063</span></span></p></td>
<td><p><span data-ttu-id="eb191-167">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-167">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-168">用於音訊/視頻（A/V）會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-168">Used for incoming SIP requests for audio/video (A/V) conferencing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-169">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-169">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-170">Lync Server 音訊/視訊會議服務</span><span class="sxs-lookup"><span data-stu-id="eb191-170">Lync Server Audio/Video Conferencing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-171">57501-65535</span><span class="sxs-lookup"><span data-stu-id="eb191-171">57501-65535</span></span></p></td>
<td><p><span data-ttu-id="eb191-172">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="eb191-172">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-173">用於視訊會議的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="eb191-173">Media port range used for video conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-174">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-174">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-175">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-175">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-176">80</span><span class="sxs-lookup"><span data-stu-id="eb191-176">80</span></span></p></td>
<td><p><span data-ttu-id="eb191-177">HTTP</span><span class="sxs-lookup"><span data-stu-id="eb191-177">HTTP</span></span></p></td>
<td><p><span data-ttu-id="eb191-178">用於從前端伺服器到網路伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url），在未使用 HTTPS 時進行通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-178">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components) when HTTPS is not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-179">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-179">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-180">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-180">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-181">443</span><span class="sxs-lookup"><span data-stu-id="eb191-181">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-182">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-182">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="eb191-183">用來從前端伺服器與網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）進行通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-183">Used for communication from Front End Servers to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-184">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-184">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-185">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-185">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-186">8080</span><span class="sxs-lookup"><span data-stu-id="eb191-186">8080</span></span></p></td>
<td><p><span data-ttu-id="eb191-187">TCP 與 HTTP</span><span class="sxs-lookup"><span data-stu-id="eb191-187">TCP and HTTP</span></span></p></td>
<td><p><span data-ttu-id="eb191-188">供外部存取的網頁元件使用。</span><span class="sxs-lookup"><span data-stu-id="eb191-188">Used by web components for external access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-189">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-189">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-190">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="eb191-190">Web server component</span></span></p></td>
<td><p><span data-ttu-id="eb191-191">4443</span><span class="sxs-lookup"><span data-stu-id="eb191-191">4443</span></span></p></td>
<td><p><span data-ttu-id="eb191-192">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-192">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="eb191-193">HTTPS （從反向 Proxy）與 HTTPS 前端端池通訊，以進行自動探索登入。</span><span class="sxs-lookup"><span data-stu-id="eb191-193">HTTPS (from Reverse Proxy) and HTTPS Front End inter-pool communications for Autodiscover sign-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-194">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-194">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-195">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="eb191-195">Web server component</span></span></p></td>
<td><p><span data-ttu-id="eb191-196">8060</span><span class="sxs-lookup"><span data-stu-id="eb191-196">8060</span></span></p></td>
<td><p><span data-ttu-id="eb191-197">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-197">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-198">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-198">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-199">Web 服務器元件</span><span class="sxs-lookup"><span data-stu-id="eb191-199">Web server component</span></span></p></td>
<td><p><span data-ttu-id="eb191-200">8061</span><span class="sxs-lookup"><span data-stu-id="eb191-200">8061</span></span></p></td>
<td><p><span data-ttu-id="eb191-201">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-201">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-202">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-202">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-203">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="eb191-203">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="eb191-204">5086</span><span class="sxs-lookup"><span data-stu-id="eb191-204">5086</span></span></p></td>
<td><p><span data-ttu-id="eb191-205">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-205">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-206">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="eb191-206">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-207">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-207">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-208">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="eb191-208">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="eb191-209">5087</span><span class="sxs-lookup"><span data-stu-id="eb191-209">5087</span></span></p></td>
<td><p><span data-ttu-id="eb191-210">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-210">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-211">行動服務內部程式使用的 SIP 埠</span><span class="sxs-lookup"><span data-stu-id="eb191-211">SIP port used by Mobility Services internal processes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-212">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-212">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-213">行動服務元件</span><span class="sxs-lookup"><span data-stu-id="eb191-213">Mobility Services component</span></span></p></td>
<td><p><span data-ttu-id="eb191-214">443</span><span class="sxs-lookup"><span data-stu-id="eb191-214">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-215">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-215">HTTPS</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-216">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-216">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-217">Lync Server 會議助理服務（電話撥入式會議）</span><span class="sxs-lookup"><span data-stu-id="eb191-217">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="eb191-218">5064</span><span class="sxs-lookup"><span data-stu-id="eb191-218">5064</span></span></p></td>
<td><p><span data-ttu-id="eb191-219">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-219">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-220">用於電話撥入式會議的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-220">Used for incoming SIP requests for dial-in conferencing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-221">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-221">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-222">Lync Server 會議助理服務（電話撥入式會議）</span><span class="sxs-lookup"><span data-stu-id="eb191-222">Lync Server Conferencing Attendant service (dial-in conferencing)</span></span></p></td>
<td><p><span data-ttu-id="eb191-223">5072</span><span class="sxs-lookup"><span data-stu-id="eb191-223">5072</span></span></p></td>
<td><p><span data-ttu-id="eb191-224">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-224">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-225">用於接聽的傳入 SIP 要求（撥入會議）。</span><span class="sxs-lookup"><span data-stu-id="eb191-225">Used for incoming SIP requests for Attendant (dial in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-226">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-226">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-227">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-227">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-228">5070</span><span class="sxs-lookup"><span data-stu-id="eb191-228">5070</span></span></p></td>
<td><p><span data-ttu-id="eb191-229">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-229">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-230">供中繼伺服器用來將前端伺服器的傳入要求傳送到中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-230">Used by the Mediation Server for incoming requests from the Front End Server to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-231">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-231">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-232">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-232">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-233">5067</span><span class="sxs-lookup"><span data-stu-id="eb191-233">5067</span></span></p></td>
<td><p><span data-ttu-id="eb191-234">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-234">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-235">用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-235">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-236">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-236">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-237">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-237">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-238">5068</span><span class="sxs-lookup"><span data-stu-id="eb191-238">5068</span></span></p></td>
<td><p><span data-ttu-id="eb191-239">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-239">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-240">用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-240">Used for incoming SIP requests from the PSTN gateway to the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-241">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-241">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-242">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-242">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-243">5081</span><span class="sxs-lookup"><span data-stu-id="eb191-243">5081</span></span></p></td>
<td><p><span data-ttu-id="eb191-244">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-244">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-245">用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-245">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-246">同時執行 Collocated 轉送伺服器的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-246">Front End Servers that also run a Collocated Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-247">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-247">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-248">5082</span><span class="sxs-lookup"><span data-stu-id="eb191-248">5082</span></span></p></td>
<td><p><span data-ttu-id="eb191-249">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-249">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-250">用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-250">Used for outgoing SIP requests from the Mediation Server to the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-251">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-251">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-252">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="eb191-252">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-253">5065</span><span class="sxs-lookup"><span data-stu-id="eb191-253">5065</span></span></p></td>
<td><p><span data-ttu-id="eb191-254">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-254">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-255">用於應用程式共用的傳入 SIP 偵聽要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-255">Used for incoming SIP listening requests for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-256">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-256">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-257">Lync Server 應用程式共用服務</span><span class="sxs-lookup"><span data-stu-id="eb191-257">Lync Server Application Sharing service</span></span></p></td>
<td><p><span data-ttu-id="eb191-258">49152-65535</span><span class="sxs-lookup"><span data-stu-id="eb191-258">49152-65535</span></span></p></td>
<td><p><span data-ttu-id="eb191-259">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-259">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-260">用來共用應用程式的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="eb191-260">Media port range used for application sharing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-261">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-261">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-262">Lync Server 會議宣告服務</span><span class="sxs-lookup"><span data-stu-id="eb191-262">Lync Server Conferencing Announcement service</span></span></p></td>
<td><p><span data-ttu-id="eb191-263">5073</span><span class="sxs-lookup"><span data-stu-id="eb191-263">5073</span></span></p></td>
<td><p><span data-ttu-id="eb191-264">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-264">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-265">用於 Lync Server 會議宣告服務的傳入 SIP 要求（也就是電話撥入式會議）。</span><span class="sxs-lookup"><span data-stu-id="eb191-265">Used for incoming SIP requests for the Lync Server Conferencing Announcement service (that is, for dial-in conferencing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-266">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-266">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-267">Lync Server 通話寄存服務</span><span class="sxs-lookup"><span data-stu-id="eb191-267">Lync Server Call Park service</span></span></p></td>
<td><p><span data-ttu-id="eb191-268">5075</span><span class="sxs-lookup"><span data-stu-id="eb191-268">5075</span></span></p></td>
<td><p><span data-ttu-id="eb191-269">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-269">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-270">用於來電寄存應用程式的內送 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-270">Used for incoming SIP requests for the Call Park application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-271">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-271">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-272">Lync Server 音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="eb191-272">Lync Server Audio Test service</span></span></p></td>
<td><p><span data-ttu-id="eb191-273">5076</span><span class="sxs-lookup"><span data-stu-id="eb191-273">5076</span></span></p></td>
<td><p><span data-ttu-id="eb191-274">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-274">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-275">用於音訊測試服務的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-275">Used for incoming SIP requests for the Audio Test service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-276">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-276">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-277">不適用</span><span class="sxs-lookup"><span data-stu-id="eb191-277">Not applicable</span></span></p></td>
<td><p><span data-ttu-id="eb191-278">5066</span><span class="sxs-lookup"><span data-stu-id="eb191-278">5066</span></span></p></td>
<td><p><span data-ttu-id="eb191-279">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-279">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-280">用於輸出增強型9-1-1 （E9-1-1）閘道。</span><span class="sxs-lookup"><span data-stu-id="eb191-280">Used for outbound Enhanced 9-1-1 (E9-1-1) gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-281">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-281">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-282">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="eb191-282">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="eb191-283">5071</span><span class="sxs-lookup"><span data-stu-id="eb191-283">5071</span></span></p></td>
<td><p><span data-ttu-id="eb191-284">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-284">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-285">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-285">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-286">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-286">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-287">Lync Server 回應群組服務</span><span class="sxs-lookup"><span data-stu-id="eb191-287">Lync Server Response Group service</span></span></p></td>
<td><p><span data-ttu-id="eb191-288">8404</span><span class="sxs-lookup"><span data-stu-id="eb191-288">8404</span></span></p></td>
<td><p><span data-ttu-id="eb191-289">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-289">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-290">用於回應群組應用程式的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-290">Used for incoming SIP requests for the Response Group application.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-291">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-291">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-292">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="eb191-292">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="eb191-293">5080</span><span class="sxs-lookup"><span data-stu-id="eb191-293">5080</span></span></p></td>
<td><p><span data-ttu-id="eb191-294">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-294">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-295">用於由頻寬原則服務為 A/V 邊緣開啟流量的呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="eb191-295">Used for call admission control by the Bandwidth Policy service for A/V Edge TURN traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-296">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-296">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-297">Lync Server 頻寬原則服務</span><span class="sxs-lookup"><span data-stu-id="eb191-297">Lync Server Bandwidth Policy Service</span></span></p></td>
<td><p><span data-ttu-id="eb191-298">448</span><span class="sxs-lookup"><span data-stu-id="eb191-298">448</span></span></p></td>
<td><p><span data-ttu-id="eb191-299">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-299">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-300">用於 Lync Server 頻寬策略服務的呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="eb191-300">Used for call admission control by the Lync Server Bandwidth Policy Service.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-301">中央管理儲存所在的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-301">Front End Servers where the Central Management store resides</span></span></p></td>
<td><p><span data-ttu-id="eb191-302">Lync Server 主版複製程式代理服務</span><span class="sxs-lookup"><span data-stu-id="eb191-302">Lync Server Master Replicator Agent service</span></span></p></td>
<td><p><span data-ttu-id="eb191-303">445</span><span class="sxs-lookup"><span data-stu-id="eb191-303">445</span></span></p></td>
<td><p><span data-ttu-id="eb191-304">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-304">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-305">用來將配置資料從中央管理存儲推送到執行 Lync Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-305">Used to push configuration data from the Central Management store to servers running Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-306">所有伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-306">All Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-307">SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="eb191-307">SQL Browser</span></span></p></td>
<td><p><span data-ttu-id="eb191-308">1434</span><span class="sxs-lookup"><span data-stu-id="eb191-308">1434</span></span></p></td>
<td><p><span data-ttu-id="eb191-309">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="eb191-309">UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-310">本機 SQL Server 實例中的中央管理儲存在本機複製複本的 SQL 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="eb191-310">SQL Browser for local replicated copy of Central Management store data in local SQL Server instance</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-311">所有內部伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-311">All internal servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-312">各種各樣</span><span class="sxs-lookup"><span data-stu-id="eb191-312">Various</span></span></p></td>
<td><p><span data-ttu-id="eb191-313">49152-57500</span><span class="sxs-lookup"><span data-stu-id="eb191-313">49152-57500</span></span></p></td>
<td><p><span data-ttu-id="eb191-314">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="eb191-314">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-315">在所有內部伺服器上，音訊會議所用的媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="eb191-315">Media port range used for audio conferencing on all internal servers.</span></span> <span data-ttu-id="eb191-316">是由所有終止音訊的伺服器所使用：前端伺服器（適用于 Lync Server 會議助理服務、Lync Server 會議宣告服務，以及 Lync server 音訊/視訊會議服務）及中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-316">Used by all servers that terminate audio: Front End Servers (for Lync Server Conferencing Attendant service, Lync Server Conferencing Announcement service, and Lync Server Audio/Video Conferencing service), and Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-317">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-317">Office Web Apps Servers</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb191-318">443</span><span class="sxs-lookup"><span data-stu-id="eb191-318">443</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eb191-319">由 Lync Server 2013 用來連線到 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-319">Used by Lync Server 2013 to connect to Office Web Apps Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-320">控制器</span><span class="sxs-lookup"><span data-stu-id="eb191-320">Directors</span></span></p></td>
<td><p><span data-ttu-id="eb191-321">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-321">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-322">5060</span><span class="sxs-lookup"><span data-stu-id="eb191-322">5060</span></span></p></td>
<td><p><span data-ttu-id="eb191-323">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-323">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-324">您也可以選擇將靜態路由用於受信任的服務，例如遠端通話控制伺服器。</span><span class="sxs-lookup"><span data-stu-id="eb191-324">Optionally used for static routes to trusted services, such as remote call control servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-325">控制器</span><span class="sxs-lookup"><span data-stu-id="eb191-325">Directors</span></span></p></td>
<td><p><span data-ttu-id="eb191-326">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-326">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-327">444</span><span class="sxs-lookup"><span data-stu-id="eb191-327">444</span></span></p></td>
<td><p><span data-ttu-id="eb191-328">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-328">HTTPS</span></span></p>
<p><span data-ttu-id="eb191-329">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-329">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-330">前端與控制器之間的伺服器間通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-330">Inter-server communication between Front End and Director.</span></span> <span data-ttu-id="eb191-331">此外，用戶端憑證發佈（到前端伺服器）或驗證用戶端憑證是否已發佈。</span><span class="sxs-lookup"><span data-stu-id="eb191-331">Additionally, client certificate publish (to Front End Servers) or validate if the client certificate has already been published.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-332">控制器</span><span class="sxs-lookup"><span data-stu-id="eb191-332">Directors</span></span></p></td>
<td><p><span data-ttu-id="eb191-333">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-333">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-334">80</span><span class="sxs-lookup"><span data-stu-id="eb191-334">80</span></span></p></td>
<td><p><span data-ttu-id="eb191-335">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-335">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-336">用於從董事到網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）的初始通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-336">Used for initial communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span> <span data-ttu-id="eb191-337">在 [標準] 操作中，會使用埠443和通訊協定類型 TCP，切換到 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="eb191-337">In normal operation, will switch to HTTPS traffic, using port 443 and protocol type TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-338">控制器</span><span class="sxs-lookup"><span data-stu-id="eb191-338">Directors</span></span></p></td>
<td><p><span data-ttu-id="eb191-339">Lync Server Web 相容性服務</span><span class="sxs-lookup"><span data-stu-id="eb191-339">Lync Server Web Compatibility service</span></span></p></td>
<td><p><span data-ttu-id="eb191-340">443</span><span class="sxs-lookup"><span data-stu-id="eb191-340">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-341">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-341">HTTPS</span></span></p></td>
<td><p><span data-ttu-id="eb191-342">用於從控制器到網頁伺服器陣列 Fqdn （IIS 網頁元件所用的 Url）的通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-342">Used for communication from Directors to the web farm FQDNs (the URLs used by IIS web components).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-343">控制器</span><span class="sxs-lookup"><span data-stu-id="eb191-343">Directors</span></span></p></td>
<td><p><span data-ttu-id="eb191-344">Lync Server 前端服務</span><span class="sxs-lookup"><span data-stu-id="eb191-344">Lync Server Front-End service</span></span></p></td>
<td><p><span data-ttu-id="eb191-345">5061</span><span class="sxs-lookup"><span data-stu-id="eb191-345">5061</span></span></p></td>
<td><p><span data-ttu-id="eb191-346">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-346">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-347">用於伺服器與用戶端連線之間的內部通訊。</span><span class="sxs-lookup"><span data-stu-id="eb191-347">Used for internal communications between servers and for client connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-348">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-348">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-349">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-349">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-350">5070</span><span class="sxs-lookup"><span data-stu-id="eb191-350">5070</span></span></p></td>
<td><p><span data-ttu-id="eb191-351">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-351">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-352">由中繼伺服器用於來自前端伺服器的傳入要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-352">Used by the Mediation Server for incoming requests from the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-353">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-353">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-354">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-354">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-355">5067</span><span class="sxs-lookup"><span data-stu-id="eb191-355">5067</span></span></p></td>
<td><p><span data-ttu-id="eb191-356">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-356">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-357">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-357">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-358">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-358">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-359">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-359">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-360">5068</span><span class="sxs-lookup"><span data-stu-id="eb191-360">5068</span></span></p></td>
<td><p><span data-ttu-id="eb191-361">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-361">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-362">用於來自 PSTN 閘道的傳入 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-362">Used for incoming SIP requests from the PSTN gateway.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-363">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-363">Mediation Servers</span></span></p></td>
<td><p><span data-ttu-id="eb191-364">Lync Server 轉送服務</span><span class="sxs-lookup"><span data-stu-id="eb191-364">Lync Server Mediation service</span></span></p></td>
<td><p><span data-ttu-id="eb191-365">5070</span><span class="sxs-lookup"><span data-stu-id="eb191-365">5070</span></span></p></td>
<td><p><span data-ttu-id="eb191-366">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-366">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-367">用於來自前端伺服器的 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="eb191-367">Used for SIP requests from the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-368">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-368">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-369">持續聊天 SIP</span><span class="sxs-lookup"><span data-stu-id="eb191-369">Persistent Chat SIP</span></span></p></td>
<td><p><span data-ttu-id="eb191-370">5041</span><span class="sxs-lookup"><span data-stu-id="eb191-370">5041</span></span></p></td>
<td><p><span data-ttu-id="eb191-371">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-371">TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-372">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-372">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-373">持續聊天 Windows Communication Foundation （WCF）</span><span class="sxs-lookup"><span data-stu-id="eb191-373">Persistent Chat Windows Communication Foundation (WCF)</span></span></p></td>
<td><p><span data-ttu-id="eb191-374">881</span><span class="sxs-lookup"><span data-stu-id="eb191-374">881</span></span></p></td>
<td><p><span data-ttu-id="eb191-375">TCP （TLS）和 TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-375">TCP (TLS) and TCP (MTLS)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-376">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="eb191-376">Persistent Chat Front End Server</span></span></p></td>
<td><p><span data-ttu-id="eb191-377">持續聊天檔案傳輸服務</span><span class="sxs-lookup"><span data-stu-id="eb191-377">Persistent Chat File Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="eb191-378">443</span><span class="sxs-lookup"><span data-stu-id="eb191-378">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-379">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-379">TCP (TLS)</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="eb191-380">某些遠端呼叫控制案例需要在前端伺服器或控制器與 PBX 之間建立 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="eb191-380">Some remote call control scenarios require a TCP connection between the Front End Server or Director and the PBX.</span></span> <span data-ttu-id="eb191-381">雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，這會將 RCC 線路伺服器 FQDN 與前端伺服器或控制器用來連接 PBX 系統的 TCP 埠產生關聯。</span><span class="sxs-lookup"><span data-stu-id="eb191-381">Although Lync Server no longer uses TCP port 5060, during remote call control deployment you create a trusted server configuration, which associates the RCC Line Server FQDN with the TCP port that the Front End Server or Director will use to connect to the PBX system.</span></span> <span data-ttu-id="eb191-382">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb191-382">For details, see the <STRONG>CsTrustedApplicationComputer</STRONG> cmdlet in the Lync Server Management Shell documentation.</span></span>



</div>

<span data-ttu-id="eb191-383">針對只使用硬體負載平衡的池（而非 DNS 負載平衡），下表顯示需要開啟硬體負載平衡器的埠。</span><span class="sxs-lookup"><span data-stu-id="eb191-383">For your pools that use only hardware load balancing (not DNS load balancing), the following table shows the ports that need to open the hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a><span data-ttu-id="eb191-384">硬體負載平衡器埠（如果只使用硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="eb191-384">Hardware Load Balancer Ports if Using Only Hardware Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb191-385">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-385">Load Balancer</span></span></th>
<th><span data-ttu-id="eb191-386">通道</span><span class="sxs-lookup"><span data-stu-id="eb191-386">Port</span></span></th>
<th><span data-ttu-id="eb191-387">通訊協定</span><span class="sxs-lookup"><span data-stu-id="eb191-387">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb191-388">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-388">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-389">5061</span><span class="sxs-lookup"><span data-stu-id="eb191-389">5061</span></span></p></td>
<td><p><span data-ttu-id="eb191-390">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-390">TCP (TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-391">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-391">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-392">444</span><span class="sxs-lookup"><span data-stu-id="eb191-392">444</span></span></p></td>
<td><p><span data-ttu-id="eb191-393">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-393">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-394">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-394">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-395">135</span><span class="sxs-lookup"><span data-stu-id="eb191-395">135</span></span></p></td>
<td><p><span data-ttu-id="eb191-396">DCOM 與遠端程式通話（RPC）</span><span class="sxs-lookup"><span data-stu-id="eb191-396">DCOM and remote procedure call (RPC)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-397">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-397">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-398">80</span><span class="sxs-lookup"><span data-stu-id="eb191-398">80</span></span></p></td>
<td><p><span data-ttu-id="eb191-399">HTTP</span><span class="sxs-lookup"><span data-stu-id="eb191-399">HTTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-400">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-400">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-401">8080</span><span class="sxs-lookup"><span data-stu-id="eb191-401">8080</span></span></p></td>
<td><p><span data-ttu-id="eb191-402">從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</span><span class="sxs-lookup"><span data-stu-id="eb191-402">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-403">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-403">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-404">443</span><span class="sxs-lookup"><span data-stu-id="eb191-404">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-405">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-405">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-406">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-406">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-407">4443</span><span class="sxs-lookup"><span data-stu-id="eb191-407">4443</span></span></p></td>
<td><p><span data-ttu-id="eb191-408">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="eb191-408">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-409">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-409">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-410">5072</span><span class="sxs-lookup"><span data-stu-id="eb191-410">5072</span></span></p></td>
<td><p><span data-ttu-id="eb191-411">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-411">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-412">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-412">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-413">5073</span><span class="sxs-lookup"><span data-stu-id="eb191-413">5073</span></span></p></td>
<td><p><span data-ttu-id="eb191-414">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-414">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-415">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-415">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-416">5075</span><span class="sxs-lookup"><span data-stu-id="eb191-416">5075</span></span></p></td>
<td><p><span data-ttu-id="eb191-417">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-417">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-418">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-418">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-419">5076</span><span class="sxs-lookup"><span data-stu-id="eb191-419">5076</span></span></p></td>
<td><p><span data-ttu-id="eb191-420">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-420">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-421">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-421">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-422">5071</span><span class="sxs-lookup"><span data-stu-id="eb191-422">5071</span></span></p></td>
<td><p><span data-ttu-id="eb191-423">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-423">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-424">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-424">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-425">5080</span><span class="sxs-lookup"><span data-stu-id="eb191-425">5080</span></span></p></td>
<td><p><span data-ttu-id="eb191-426">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-426">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-427">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-427">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-428">448</span><span class="sxs-lookup"><span data-stu-id="eb191-428">448</span></span></p></td>
<td><p><span data-ttu-id="eb191-429">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-429">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-430">中繼伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-430">Mediation Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-431">5070</span><span class="sxs-lookup"><span data-stu-id="eb191-431">5070</span></span></p></td>
<td><p><span data-ttu-id="eb191-432">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-432">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-433">前端伺服器負載平衡器（如果該池也會執行轉送伺服器）</span><span class="sxs-lookup"><span data-stu-id="eb191-433">Front End Server load balancer (if the pool also runs Mediation Server)</span></span></p></td>
<td><p><span data-ttu-id="eb191-434">5070</span><span class="sxs-lookup"><span data-stu-id="eb191-434">5070</span></span></p></td>
<td><p><span data-ttu-id="eb191-435">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-435">TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-436">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-436">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-437">443</span><span class="sxs-lookup"><span data-stu-id="eb191-437">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-438">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-438">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-439">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-439">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-440">444</span><span class="sxs-lookup"><span data-stu-id="eb191-440">444</span></span></p></td>
<td><p><span data-ttu-id="eb191-441">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-441">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-442">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-442">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-443">5061</span><span class="sxs-lookup"><span data-stu-id="eb191-443">5061</span></span></p></td>
<td><p><span data-ttu-id="eb191-444">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-444">TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-445">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-445">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-446">4443</span><span class="sxs-lookup"><span data-stu-id="eb191-446">4443</span></span></p></td>
<td><p><span data-ttu-id="eb191-447">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="eb191-447">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb191-448">您的前端池和使用 DNS 負載平衡的控制器池也必須部署硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="eb191-448">Your Front End pools and Director pools that use DNS load balancing also must have a hardware load balancer deployed.</span></span> <span data-ttu-id="eb191-449">下表顯示在這些硬體負載平衡器上需要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="eb191-449">The following table shows the ports that need to be open on these hardware load balancers.</span></span>

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a><span data-ttu-id="eb191-450">使用 DNS 負載平衡的硬體負載平衡器埠</span><span class="sxs-lookup"><span data-stu-id="eb191-450">Hardware Load Balancer Ports if Using DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb191-451">負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-451">Load Balancer</span></span></th>
<th><span data-ttu-id="eb191-452">通道</span><span class="sxs-lookup"><span data-stu-id="eb191-452">Port</span></span></th>
<th><span data-ttu-id="eb191-453">通訊協定</span><span class="sxs-lookup"><span data-stu-id="eb191-453">Protocol</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb191-454">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-454">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-455">80</span><span class="sxs-lookup"><span data-stu-id="eb191-455">80</span></span></p></td>
<td><p><span data-ttu-id="eb191-456">HTTP</span><span class="sxs-lookup"><span data-stu-id="eb191-456">HTTP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-457">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-457">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-458">443</span><span class="sxs-lookup"><span data-stu-id="eb191-458">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-459">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-459">HTTPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-460">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-460">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-461">8080</span><span class="sxs-lookup"><span data-stu-id="eb191-461">8080</span></span></p></td>
<td><p><span data-ttu-id="eb191-462">從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</span><span class="sxs-lookup"><span data-stu-id="eb191-462">TCP - Client and device retrieval of root certificate from Front End Server – clients and devices authenticated by NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-463">前端伺服器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-463">Front End Server load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-464">4443</span><span class="sxs-lookup"><span data-stu-id="eb191-464">4443</span></span></p></td>
<td><p><span data-ttu-id="eb191-465">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="eb191-465">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-466">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-466">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-467">443</span><span class="sxs-lookup"><span data-stu-id="eb191-467">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-468">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="eb191-468">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-469">控制器負載平衡器</span><span class="sxs-lookup"><span data-stu-id="eb191-469">Director load balancer</span></span></p></td>
<td><p><span data-ttu-id="eb191-470">4443</span><span class="sxs-lookup"><span data-stu-id="eb191-470">4443</span></span></p></td>
<td><p><span data-ttu-id="eb191-471">HTTPS （從反向 proxy）</span><span class="sxs-lookup"><span data-stu-id="eb191-471">HTTPS (from reverse proxy)</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a><span data-ttu-id="eb191-472">所需的用戶端埠</span><span class="sxs-lookup"><span data-stu-id="eb191-472">Required Client Ports</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb191-473">元件</span><span class="sxs-lookup"><span data-stu-id="eb191-473">Component</span></span></th>
<th><span data-ttu-id="eb191-474">通道</span><span class="sxs-lookup"><span data-stu-id="eb191-474">Port</span></span></th>
<th><span data-ttu-id="eb191-475">通訊協定</span><span class="sxs-lookup"><span data-stu-id="eb191-475">Protocol</span></span></th>
<th><span data-ttu-id="eb191-476">筆記</span><span class="sxs-lookup"><span data-stu-id="eb191-476">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb191-477">台</span><span class="sxs-lookup"><span data-stu-id="eb191-477">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-478">67/68</span><span class="sxs-lookup"><span data-stu-id="eb191-478">67/68</span></span></p></td>
<td><p><span data-ttu-id="eb191-479">動態</span><span class="sxs-lookup"><span data-stu-id="eb191-479">DHCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-480">由 Lync Server 用來尋找註冊機 FQDN （也就是如果 DNS SRV 失敗且沒有設定手動設定）。</span><span class="sxs-lookup"><span data-stu-id="eb191-480">Used by Lync Server to find the Registrar FQDN (that is, if DNS SRV fails and manual settings are not configured).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-481">台</span><span class="sxs-lookup"><span data-stu-id="eb191-481">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-482">443</span><span class="sxs-lookup"><span data-stu-id="eb191-482">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-483">TCP （TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-483">TCP (TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-484">用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="eb191-484">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-485">台</span><span class="sxs-lookup"><span data-stu-id="eb191-485">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-486">443</span><span class="sxs-lookup"><span data-stu-id="eb191-486">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-487">TCP （PSOM/TLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-487">TCP (PSOM/TLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-488">用於外部使用者存取網路會議會話。</span><span class="sxs-lookup"><span data-stu-id="eb191-488">Used for external user access to web conferencing sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-489">台</span><span class="sxs-lookup"><span data-stu-id="eb191-489">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-490">443</span><span class="sxs-lookup"><span data-stu-id="eb191-490">443</span></span></p></td>
<td><p><span data-ttu-id="eb191-491">TCP （STUN/MSTURN）</span><span class="sxs-lookup"><span data-stu-id="eb191-491">TCP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="eb191-492">供外部使用者存取 A/V 會話及媒體（TCP）</span><span class="sxs-lookup"><span data-stu-id="eb191-492">Used for external user access to A/V sessions and media (TCP)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-493">台</span><span class="sxs-lookup"><span data-stu-id="eb191-493">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-494">3478</span><span class="sxs-lookup"><span data-stu-id="eb191-494">3478</span></span></p></td>
<td><p><span data-ttu-id="eb191-495">UDP （STUN/MSTURN）</span><span class="sxs-lookup"><span data-stu-id="eb191-495">UDP (STUN/MSTURN)</span></span></p></td>
<td><p><span data-ttu-id="eb191-496">供外部使用者存取 A/V 會話及媒體（UDP）</span><span class="sxs-lookup"><span data-stu-id="eb191-496">Used for external user access to A/V sessions and media (UDP)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-497">台</span><span class="sxs-lookup"><span data-stu-id="eb191-497">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-498">5061</span><span class="sxs-lookup"><span data-stu-id="eb191-498">5061</span></span></p></td>
<td><p><span data-ttu-id="eb191-499">TCP （MTLS）</span><span class="sxs-lookup"><span data-stu-id="eb191-499">TCP (MTLS)</span></span></p></td>
<td><p><span data-ttu-id="eb191-500">用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="eb191-500">Used for client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-501">台</span><span class="sxs-lookup"><span data-stu-id="eb191-501">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-502">6891-6901</span><span class="sxs-lookup"><span data-stu-id="eb191-502">6891-6901</span></span></p></td>
<td><p><span data-ttu-id="eb191-503">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-503">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-504">用於 Lync 用戶端與舊版用戶端之間的檔案傳輸（Microsoft Office 通訊伺服器 2007 R2 的用戶端、Microsoft Office 通訊伺服器2007，以及即時通訊伺服器2005）。</span><span class="sxs-lookup"><span data-stu-id="eb191-504">Used for file transfer between Lync clients and previous clients (clients of Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007, and Live Communications Server 2005).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-505">台</span><span class="sxs-lookup"><span data-stu-id="eb191-505">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-506">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="eb191-506">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="eb191-507">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="eb191-507">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-508">音訊埠範圍（所需的最小20個埠）</span><span class="sxs-lookup"><span data-stu-id="eb191-508">Audio port range (minimum of 20 ports required)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-509">台</span><span class="sxs-lookup"><span data-stu-id="eb191-509">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-510">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="eb191-510">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="eb191-511">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="eb191-511">TCP/UDP</span></span></p></td>
<td><p><span data-ttu-id="eb191-512">影片埠範圍（需要20個埠的最小值）。</span><span class="sxs-lookup"><span data-stu-id="eb191-512">Video port range (minimum of 20 ports required).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-513">台</span><span class="sxs-lookup"><span data-stu-id="eb191-513">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-514">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="eb191-514">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="eb191-515">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-515">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-516">對等檔案傳輸（適用于會議檔案傳輸，用戶端使用 PSOM）。</span><span class="sxs-lookup"><span data-stu-id="eb191-516">Peer-to-peer file transfer (for conferencing file transfer, clients use PSOM).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb191-517">台</span><span class="sxs-lookup"><span data-stu-id="eb191-517">Clients</span></span></p></td>
<td><p><span data-ttu-id="eb191-518">1024-65535 \*</span><span class="sxs-lookup"><span data-stu-id="eb191-518">1024-65535 \*</span></span></p></td>
<td><p><span data-ttu-id="eb191-519">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="eb191-519">TCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-520">應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="eb191-520">Application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb191-521">Aastra 6721ip 常見區域電話</span><span class="sxs-lookup"><span data-stu-id="eb191-521">Aastra 6721ip common area phone</span></span></p>
<p><span data-ttu-id="eb191-522">Aastra 6725ip phone</span><span class="sxs-lookup"><span data-stu-id="eb191-522">Aastra 6725ip desk phone</span></span></p>
<p><span data-ttu-id="eb191-523">HP 4110 IP Phone （通用區域電話）</span><span class="sxs-lookup"><span data-stu-id="eb191-523">HP 4110 IP Phone (common area phone)</span></span></p>
<p><span data-ttu-id="eb191-524">HP 4120 IP Phone （辦公桌電話）</span><span class="sxs-lookup"><span data-stu-id="eb191-524">HP 4120 IP Phone (desk phone)</span></span></p>
<p><span data-ttu-id="eb191-525">Polycom CX500 IP 常見區域電話</span><span class="sxs-lookup"><span data-stu-id="eb191-525">Polycom CX500 IP common area phone</span></span></p>
<p><span data-ttu-id="eb191-526">Polycom CX600 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="eb191-526">Polycom CX600 IP desk phone</span></span></p>
<p><span data-ttu-id="eb191-527">Polycom CX700 IP 電話機</span><span class="sxs-lookup"><span data-stu-id="eb191-527">Polycom CX700 IP desk phone</span></span></p>
<p><span data-ttu-id="eb191-528">Polycom CX3000 IP 會議電話</span><span class="sxs-lookup"><span data-stu-id="eb191-528">Polycom CX3000 IP conference phone</span></span></p></td>
<td><p><span data-ttu-id="eb191-529">67/68</span><span class="sxs-lookup"><span data-stu-id="eb191-529">67/68</span></span></p></td>
<td><p><span data-ttu-id="eb191-530">動態</span><span class="sxs-lookup"><span data-stu-id="eb191-530">DHCP</span></span></p></td>
<td><p><span data-ttu-id="eb191-531">由所列的裝置使用，以尋找 Lync 伺服器憑證、資源調配 FQDN 和註冊機 FQDN。</span><span class="sxs-lookup"><span data-stu-id="eb191-531">Used by the listed devices to find the Lync Server certificate, provisioning FQDN, and Registrar FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eb191-532">**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet （ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 參數）。</span><span class="sxs-lookup"><span data-stu-id="eb191-532">**\*** To configure specific ports for these media types, use the CsConferencingConfiguration cmdlet (ClientMediaPortRangeEnabled, ClientMediaPort, and ClientMediaPortRange parameters).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb191-533">Lync 用戶端的設定程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。</span><span class="sxs-lookup"><span data-stu-id="eb191-533">The set programs for Lync clients automatically create the required operating-system firewall exceptions on the client computer.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="eb191-534">在用戶端必須遍歷組織的防火牆（例如，任何外部通訊或其他組織託管的會議）的情況下，對於外部使用者存取所用的埠，都是必要的。</span><span class="sxs-lookup"><span data-stu-id="eb191-534">The ports that are used for external user access are required for any scenario in which the client must traverse the organization’s firewall (for example, any external communications or meetings hosted by other organizations).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

