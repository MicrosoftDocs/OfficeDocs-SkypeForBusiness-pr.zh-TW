---
title: 連接埠摘要-SIP，XMPP 同盟及 public instant messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2512b49f9e0bcdc092354a5f43cb234c7e4d5445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="a1302-102">連接埠摘要-SIP，XMPP 同盟和公用立即訊息在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1302-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1302-103">_**上次修改主題：** 2013年-03-15_</span><span class="sxs-lookup"><span data-stu-id="a1302-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="a1302-104">Microsoft Lync Server 2013、 Lync Server 2010 與 Office Communications Server 同盟的連接埠、 通訊協定和防火牆需求都是類似於已部署的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="a1302-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="a1302-105">用戶端起始與 Access Edge service 通訊，透過 TLS/SIP/TCP 443。</span><span class="sxs-lookup"><span data-stu-id="a1302-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="a1302-106">不過，同盟協力廠商將會引發 Access Edge service 通訊透過 MTLS/SIP/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="a1302-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="a1302-107">若要設定防火牆連接埠和通訊協定支援公用立即訊息連線必要，請先注意 SIP/MTLS/TCP 5061 是雙向帳戶中的公用 IM 提供者的連絡人能夠連絡 Lync 用戶端，或連絡公用 IM 連絡人的 Lync。</span><span class="sxs-lookup"><span data-stu-id="a1302-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="a1302-108">Windows Live Messenger 可以參與音訊/視訊通訊與 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a1302-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="a1302-109">此帳戶，您通常會有支援外部使用者的 Lync 用戶端防火牆上非常類似防火牆連接埠和通訊協定設定。</span><span class="sxs-lookup"><span data-stu-id="a1302-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a1302-110">多個曾經 Lync 是功能強大的工具，可將跨組織及與個人世界各地的連線。</span><span class="sxs-lookup"><span data-stu-id="a1302-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="a1302-111">與 Windows Live Messenger 同盟需要任何其他的使用者/裝置的授權超過 Lync 標準用戶端存取授權 (CAL)。</span><span class="sxs-lookup"><span data-stu-id="a1302-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="a1302-112">Skype 同盟會新增至這份清單，讓 Lync 使用者可達到數百個數百萬的人員 IM 與語音。</span><span class="sxs-lookup"><span data-stu-id="a1302-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="a1302-113">同盟與 Messenger 用戶端連絡人最終會將正式在 2013 年 3 月 15 日，但不包括在中國大陸。</span><span class="sxs-lookup"><span data-stu-id="a1302-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="a1302-114">Skype 會變成先前用信差同盟用戶端的同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="a1302-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="a1302-115">連接埠和通訊協定可延伸訊息與顯示狀態通訊協定 (XMPP) proxy 部署 Edge Server 上定義允許的 XMPP 同盟協力廠商的通訊的 Edge server，並以 XMPP 也允許來自您的 Edge Server 的通訊同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="a1302-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="a1302-116">內部向防火牆從前端伺服器或前端集區到 Edge Server 或 Edge 集區上也定義規則。</span><span class="sxs-lookup"><span data-stu-id="a1302-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="a1302-117">防火牆摘要-SIP 同盟</span><span class="sxs-lookup"><span data-stu-id="a1302-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1302-118">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a1302-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1302-119">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-119">Source IP address</span></span></th>
<th><span data-ttu-id="a1302-120">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-120">Destination IP address</span></span></th>
<th><span data-ttu-id="a1302-121">附註</span><span class="sxs-lookup"><span data-stu-id="a1302-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1302-122">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1302-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1302-123">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1302-124">任何</span><span class="sxs-lookup"><span data-stu-id="a1302-124">Any</span></span></p></td>
<td><p><span data-ttu-id="a1302-125">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="a1302-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a1302-126">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="a1302-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1302-127">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a1302-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1302-128">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-128">Source IP address</span></span></th>
<th><span data-ttu-id="a1302-129">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-129">Destination IP address</span></span></th>
<th><span data-ttu-id="a1302-130">附註</span><span class="sxs-lookup"><span data-stu-id="a1302-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1302-131">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1302-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1302-132">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="a1302-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a1302-133">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-134">使用 SIP 的同盟和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="a1302-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1302-135">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1302-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1302-136">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-137">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="a1302-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a1302-138">使用 SIP 的同盟和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="a1302-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1302-139">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1302-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1302-140">用戶端</span><span class="sxs-lookup"><span data-stu-id="a1302-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="a1302-141">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-142">外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="a1302-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1302-143">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a1302-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a1302-144">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-145">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="a1302-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a1302-146">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="a1302-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1302-147">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1302-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1302-148">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-149">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="a1302-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a1302-150">所需的 Windows Live Messenger 與公用 IM 進行連線。</span><span class="sxs-lookup"><span data-stu-id="a1302-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1302-151">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1302-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1302-152">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="a1302-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a1302-153">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="a1302-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="a1302-154">所需的 Windows Live Messenger 與公用 IM 進行連線。</span><span class="sxs-lookup"><span data-stu-id="a1302-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="a1302-155">防火牆摘要-Extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="a1302-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1302-156">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a1302-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1302-157">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="a1302-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="a1302-158">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="a1302-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a1302-159">註解</span><span class="sxs-lookup"><span data-stu-id="a1302-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1302-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a1302-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a1302-161">任何</span><span class="sxs-lookup"><span data-stu-id="a1302-161">Any</span></span></p></td>
<td><p><span data-ttu-id="a1302-162">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a1302-163">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="a1302-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a1302-164">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="a1302-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1302-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a1302-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a1302-166">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a1302-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a1302-167">任何</span><span class="sxs-lookup"><span data-stu-id="a1302-167">Any</span></span></p></td>
<td><p><span data-ttu-id="a1302-168">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="a1302-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a1302-169">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="a1302-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1302-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="a1302-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="a1302-171">任何</span><span class="sxs-lookup"><span data-stu-id="a1302-171">Any</span></span></p></td>
<td><p><span data-ttu-id="a1302-172">內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="a1302-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="a1302-173">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道至 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a1302-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1302-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a1302-174">See Also</span></span>


[<span data-ttu-id="a1302-175">Lync Server 2013 中的外部使用者存取的案例</span><span class="sxs-lookup"><span data-stu-id="a1302-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="a1302-176">決定外部 A / V 防火牆和連接埠需求 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1302-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="a1302-177">管理 Lync Server 2013 中的 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="a1302-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

