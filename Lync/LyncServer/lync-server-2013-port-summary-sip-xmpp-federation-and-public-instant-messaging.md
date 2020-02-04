---
title: 埠摘要-SIP、XMPP 同盟及公用立即訊息
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
ms.openlocfilehash: 3ae19fb2477f61c0e408ebad3a8abf97fb75b9c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e3704-102">埠摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="e3704-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3704-103">_**主題上次修改日期：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="e3704-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="e3704-104">使用 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行聯盟的埠、通訊協定和防火牆需求與已部署的 Edge 伺服器類似。</span><span class="sxs-lookup"><span data-stu-id="e3704-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="e3704-105">用戶端以 TLS/SIP/TCP 443 的存取邊緣服務啟動通訊。</span><span class="sxs-lookup"><span data-stu-id="e3704-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="e3704-106">但是，同盟夥伴會啟動與整個 MTLS/SIP/TCP 5061 的存取邊緣服務的通訊。</span><span class="sxs-lookup"><span data-stu-id="e3704-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="e3704-107">若要針對支援公用立即訊息連線的埠和通訊協定設定您的防火牆，請先注意，SIP/MTLS/TCP 5061 是雙向的，以將公用 IM 提供者的連絡人連線到 Lync 用戶端，或是 Lync 與公用 IM 連絡人聯繫。</span><span class="sxs-lookup"><span data-stu-id="e3704-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="e3704-108">Windows Live Messenger 可以使用 Lync 用戶端參與音訊/視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="e3704-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="e3704-109">這個帳戶是您在防火牆上通常會有的類似防火牆埠和通訊協定設定，以支援 Lync 用戶端作為外部使用者。</span><span class="sxs-lookup"><span data-stu-id="e3704-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e3704-110">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="e3704-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e3704-111">與 Windows Live Messenger 的同盟不需要在 Lync 標準用戶端存取授權（CAL）之外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="e3704-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="e3704-112">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="e3704-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="e3704-113">與 Messenger 用戶端連絡人的同盟將于2013年3月15日正式結束，除了中國大陸以外。</span><span class="sxs-lookup"><span data-stu-id="e3704-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="e3704-114">Skype 將成為先前使用 Messenger 之聯盟使用者的同盟用戶端。</span><span class="sxs-lookup"><span data-stu-id="e3704-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="e3704-115">針對在 Edge 伺服器部署的可擴展訊息和目前狀態通訊協定（XMPP） proxy 所定義的埠和通訊協定，允許從 XMPP 聯盟夥伴傳送到 Edge 伺服器，也可讓您從邊緣伺服器與 XMPP 進行通訊。聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="e3704-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="e3704-116">您也可以在內部防火牆上，從前端伺服器或頂層端池中，在邊緣伺服器或 Edge 池中定義規則。</span><span class="sxs-lookup"><span data-stu-id="e3704-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="e3704-117">防火牆摘要-SIP 同盟</span><span class="sxs-lookup"><span data-stu-id="e3704-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3704-118">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="e3704-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e3704-119">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-119">Source IP address</span></span></th>
<th><span data-ttu-id="e3704-120">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-120">Destination IP address</span></span></th>
<th><span data-ttu-id="e3704-121">筆記</span><span class="sxs-lookup"><span data-stu-id="e3704-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3704-122">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e3704-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e3704-123">存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e3704-124">每</span><span class="sxs-lookup"><span data-stu-id="e3704-124">Any</span></span></p></td>
<td><p><span data-ttu-id="e3704-125">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e3704-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e3704-126">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="e3704-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3704-127">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="e3704-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e3704-128">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-128">Source IP address</span></span></th>
<th><span data-ttu-id="e3704-129">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-129">Destination IP address</span></span></th>
<th><span data-ttu-id="e3704-130">筆記</span><span class="sxs-lookup"><span data-stu-id="e3704-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3704-131">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e3704-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e3704-132">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="e3704-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e3704-133">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-134">針對使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e3704-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3704-135">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e3704-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e3704-136">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-137">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="e3704-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e3704-138">針對使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e3704-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3704-139">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e3704-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e3704-140">台</span><span class="sxs-lookup"><span data-stu-id="e3704-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="e3704-141">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-142">供外部使用者存取的用戶端到伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="e3704-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3704-143">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e3704-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e3704-144">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-145">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e3704-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e3704-146">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="e3704-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3704-147">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e3704-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e3704-148">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-149">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e3704-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e3704-150">對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</span><span class="sxs-lookup"><span data-stu-id="e3704-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3704-151">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e3704-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e3704-152">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e3704-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e3704-153">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e3704-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e3704-154">對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</span><span class="sxs-lookup"><span data-stu-id="e3704-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="e3704-155">防火牆摘要-可擴展的訊息和目前狀態通訊協定（XMPP）</span><span class="sxs-lookup"><span data-stu-id="e3704-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3704-156">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="e3704-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e3704-157">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="e3704-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="e3704-158">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="e3704-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e3704-159">批註</span><span class="sxs-lookup"><span data-stu-id="e3704-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3704-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e3704-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e3704-161">每</span><span class="sxs-lookup"><span data-stu-id="e3704-161">Any</span></span></p></td>
<td><p><span data-ttu-id="e3704-162">Access Edge 服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e3704-163">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="e3704-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e3704-164">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="e3704-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3704-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e3704-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e3704-166">Access Edge 服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e3704-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e3704-167">每</span><span class="sxs-lookup"><span data-stu-id="e3704-167">Any</span></span></p></td>
<td><p><span data-ttu-id="e3704-168">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="e3704-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e3704-169">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="e3704-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3704-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="e3704-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="e3704-171">每</span><span class="sxs-lookup"><span data-stu-id="e3704-171">Any</span></span></p></td>
<td><p><span data-ttu-id="e3704-172">內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="e3704-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e3704-173">從前端伺服器或頂層池的 XMPP 閘道到 Edge 伺服器的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="e3704-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3704-174">請參閱</span><span class="sxs-lookup"><span data-stu-id="e3704-174">See Also</span></span>


[<span data-ttu-id="e3704-175">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="e3704-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e3704-176">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="e3704-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="e3704-177">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="e3704-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

