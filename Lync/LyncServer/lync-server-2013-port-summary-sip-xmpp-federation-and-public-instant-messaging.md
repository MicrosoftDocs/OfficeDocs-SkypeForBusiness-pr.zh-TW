---
title: 埠摘要-SIP、XMPP 同盟和公用立即訊息
description: 埠摘要-SIP、XMPP 同盟和公用立即訊息。
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
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566352"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="34e7e-103">Lync Server 2013 中的埠摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="34e7e-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e7e-104">_**主題上次修改日期：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="34e7e-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="34e7e-105">與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器同盟相關的埠、通訊協定及防火牆需求，類似于已部署的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="34e7e-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="34e7e-106">用戶端會透過 TLS/SIP/TCP 443，與 Access Edge service 發起通訊。</span><span class="sxs-lookup"><span data-stu-id="34e7e-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="34e7e-107">同盟合作夥伴但是會透過 MTLS/SIP/TCP 5061，發起與 Access Edge service 的通訊。</span><span class="sxs-lookup"><span data-stu-id="34e7e-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="34e7e-108">若要為您的防火牆設定支援公用立即訊息連線所需的埠和通訊協定，請先注意 SIP/MTLS/TCP 5061 是雙向的，可讓公用 IM 提供者中的連絡人能夠聯繫 Lync 用戶端，或與 Lync 聯繫以取得公用 IM 連絡人。</span><span class="sxs-lookup"><span data-stu-id="34e7e-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="34e7e-109">Windows Live Messenger 可以與 Lync 用戶端參與音訊/視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="34e7e-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="34e7e-110">這會針對一般具有防火牆的防火牆埠和通訊協定設定，以支援 Lync 用戶端的外部使用者使用。</span><span class="sxs-lookup"><span data-stu-id="34e7e-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="34e7e-111">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="34e7e-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="34e7e-112">與 Windows Live Messenger 的同盟除了 Lync Standard Client Access License (CAL) 之外，不需要額外的使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="34e7e-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="34e7e-113">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="34e7e-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="34e7e-114">與 Messenger 用戶端連絡人的同盟會在2013年3月15日（中國大陸除外）正式結束。</span><span class="sxs-lookup"><span data-stu-id="34e7e-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="34e7e-115">Skype 會成為先前使用信使的同盟使用者的同盟用戶端。</span><span class="sxs-lookup"><span data-stu-id="34e7e-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="34e7e-116">在 Edge Server 上部署的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy 所定義的埠和通訊協定，允許從 XMPP 同盟協力廠商到 Edge Server 的通訊，也允許從 Edge Server 到 XMPP 同盟合作夥伴的通訊。</span><span class="sxs-lookup"><span data-stu-id="34e7e-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="34e7e-117">規則也會定義在內部的防火牆上，從前端伺服器或前端集區到 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="34e7e-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="34e7e-118">防火牆摘要-SIP 同盟</span><span class="sxs-lookup"><span data-stu-id="34e7e-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34e7e-119">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="34e7e-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="34e7e-120">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-120">Source IP address</span></span></th>
<th><span data-ttu-id="34e7e-121">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-121">Destination IP address</span></span></th>
<th><span data-ttu-id="34e7e-122">注意事項</span><span class="sxs-lookup"><span data-stu-id="34e7e-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-123">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="34e7e-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="34e7e-124">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="34e7e-125">任何</span><span class="sxs-lookup"><span data-stu-id="34e7e-125">Any</span></span></p></td>
<td><p><span data-ttu-id="34e7e-126">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="34e7e-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="34e7e-127">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="34e7e-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34e7e-128">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="34e7e-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="34e7e-129">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-129">Source IP address</span></span></th>
<th><span data-ttu-id="34e7e-130">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-130">Destination IP address</span></span></th>
<th><span data-ttu-id="34e7e-131">注意事項</span><span class="sxs-lookup"><span data-stu-id="34e7e-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-132">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="34e7e-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="34e7e-133">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="34e7e-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="34e7e-134">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-135">適用于使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="34e7e-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e7e-136">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="34e7e-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="34e7e-137">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-138">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="34e7e-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="34e7e-139">適用于使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="34e7e-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-140">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="34e7e-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="34e7e-141">用戶端</span><span class="sxs-lookup"><span data-stu-id="34e7e-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="34e7e-142">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-143">外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="34e7e-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e7e-144">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="34e7e-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="34e7e-145">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-146">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="34e7e-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="34e7e-147">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="34e7e-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="34e7e-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="34e7e-149">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-150">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="34e7e-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="34e7e-151">使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</span><span class="sxs-lookup"><span data-stu-id="34e7e-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e7e-152">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="34e7e-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="34e7e-153">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="34e7e-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="34e7e-154">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="34e7e-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="34e7e-155">使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</span><span class="sxs-lookup"><span data-stu-id="34e7e-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="34e7e-156">防火牆摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) </span><span class="sxs-lookup"><span data-stu-id="34e7e-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34e7e-157">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="34e7e-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="34e7e-158">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="34e7e-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="34e7e-159">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="34e7e-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="34e7e-160">註解</span><span class="sxs-lookup"><span data-stu-id="34e7e-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="34e7e-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="34e7e-162">任何</span><span class="sxs-lookup"><span data-stu-id="34e7e-162">Any</span></span></p></td>
<td><p><span data-ttu-id="34e7e-163">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="34e7e-164">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="34e7e-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="34e7e-165">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="34e7e-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e7e-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="34e7e-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="34e7e-167">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="34e7e-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="34e7e-168">任何</span><span class="sxs-lookup"><span data-stu-id="34e7e-168">Any</span></span></p></td>
<td><p><span data-ttu-id="34e7e-169">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="34e7e-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="34e7e-170">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="34e7e-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e7e-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="34e7e-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="34e7e-172">任何</span><span class="sxs-lookup"><span data-stu-id="34e7e-172">Any</span></span></p></td>
<td><p><span data-ttu-id="34e7e-173">內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="34e7e-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="34e7e-174">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="34e7e-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34e7e-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34e7e-175">See Also</span></span>


[<span data-ttu-id="34e7e-176">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="34e7e-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="34e7e-177">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="34e7e-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="34e7e-178">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="34e7e-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

