---
title: Lync Server 2013：判斷外部 A/V 防火牆和埠需求
description: Lync Server 2013：判斷外部 A/V 防火牆和埠需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550929"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="ccdea-103">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="ccdea-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccdea-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ccdea-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ccdea-105">Audio/Video (A/V) 通訊可能是複雜的。</span><span class="sxs-lookup"><span data-stu-id="ccdea-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="ccdea-106">因為 A/V 所使用的通訊協定性質，以及用戶端和伺服器使用通訊協定的方式，所以特殊區段會保證用戶端與伺服器版本之間的差異。</span><span class="sxs-lookup"><span data-stu-id="ccdea-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="ccdea-107">使用下列 A/V 防火牆及埠表來判斷防火牆需求和要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="ccdea-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="ccdea-108">接著檢閱網路位址轉譯 (NAT) 術語，因為 NAT 可透過許多方式實作。</span><span class="sxs-lookup"><span data-stu-id="ccdea-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="ccdea-109">如需防火牆埠設定的詳細範例，請參閱 [Lync Server 2013 中的外部使用者存取案例案例](lync-server-2013-scenarios-for-external-user-access.md)中的參考架構。</span><span class="sxs-lookup"><span data-stu-id="ccdea-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="ccdea-110">Audio/Video 和媒體流量中的 UDP 和 TCP 一般通訊協定用法</span><span class="sxs-lookup"><span data-stu-id="ccdea-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccdea-111">Audio/Video 傳輸</span><span class="sxs-lookup"><span data-stu-id="ccdea-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="ccdea-112">Usage</span><span class="sxs-lookup"><span data-stu-id="ccdea-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccdea-113">Udp</span><span class="sxs-lookup"><span data-stu-id="ccdea-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="ccdea-114">音訊和影片的慣用傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="ccdea-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccdea-115">TCP</span><span class="sxs-lookup"><span data-stu-id="ccdea-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="ccdea-116">音訊和影片的 Fallback transport layer 通訊協定</span><span class="sxs-lookup"><span data-stu-id="ccdea-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="ccdea-117">Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的應用程式共用所需的傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="ccdea-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="ccdea-118">Lync Server 2010 和 Lync Server 2013 的檔案傳輸所需的傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="ccdea-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="ccdea-119">外部使用者存取的外部 A/V 防火牆連接埠需求</span><span class="sxs-lookup"><span data-stu-id="ccdea-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="ccdea-120">外部 (和內部) SIP 和會議介面的防火牆埠需求，不論您的用戶端版本為何，或是同盟協力廠商的版本，都是一致的。</span><span class="sxs-lookup"><span data-stu-id="ccdea-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="ccdea-121">A/V Edge 外部介面則不同。</span><span class="sxs-lookup"><span data-stu-id="ccdea-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="ccdea-122">若要使用 Office 通訊伺服器2007的同盟，A/V Edge service 需要外部防火牆規則允許 RTP/TCP 和 RTP/UDP 的50000到59999埠範圍中的流量，以流向這兩個方向。</span><span class="sxs-lookup"><span data-stu-id="ccdea-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="ccdea-123">上表假設 Lync Server 2013 是主要同盟協力廠商，且設定為與所列的其他其中一個同盟夥伴類型通訊。</span><span class="sxs-lookup"><span data-stu-id="ccdea-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="ccdea-124">設定 Audio/Video 的埠範圍 50000 59999 必須考慮，埠範圍會包含用於與同盟協力廠商通訊的來源埠。</span><span class="sxs-lookup"><span data-stu-id="ccdea-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="ccdea-125">詳細資訊，請考慮從同盟協力廠商發起通訊。</span><span class="sxs-lookup"><span data-stu-id="ccdea-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="ccdea-126">從 50000 59999 範圍中 A/V Edge service 埠的通訊，會連線至夥伴的 A/V Edge service 所期望的埠 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="ccdea-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="ccdea-127">相反地，對您 A/V Edge service 埠 TCP 443 的輸入流量，其來源埠為 50000-59999。</span><span class="sxs-lookup"><span data-stu-id="ccdea-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="ccdea-128">防火牆管理的不同防火牆和原則可能只需要設定目的地規則，也可能需要設定來源和目的地。</span><span class="sxs-lookup"><span data-stu-id="ccdea-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="ccdea-129">如果您的需求只適用于目的地埠，則 Audio/Video 需求如下：</span><span class="sxs-lookup"><span data-stu-id="ccdea-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccdea-130">來源 IP</span><span class="sxs-lookup"><span data-stu-id="ccdea-130">Source IP</span></span></th>
<th><span data-ttu-id="ccdea-131">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="ccdea-131">Destination IP</span></span></th>
<th><span data-ttu-id="ccdea-132">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="ccdea-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccdea-133">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-134">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="ccdea-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccdea-136">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-137">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-137">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ccdea-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccdea-139">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-139">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-140">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="ccdea-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccdea-142">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-142">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-143">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ccdea-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ccdea-145">如果您的原則同時需要輸入和輸出防火牆規則定義，Audio/Video 需求如下：</span><span class="sxs-lookup"><span data-stu-id="ccdea-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccdea-146">來源 IP</span><span class="sxs-lookup"><span data-stu-id="ccdea-146">Source IP</span></span></th>
<th><span data-ttu-id="ccdea-147">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="ccdea-147">Destination IP</span></span></th>
<th><span data-ttu-id="ccdea-148">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="ccdea-148">Source Port</span></span></th>
<th><span data-ttu-id="ccdea-149">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="ccdea-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccdea-150">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-151">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-151">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-152">TCP 50000 59999</span><span class="sxs-lookup"><span data-stu-id="ccdea-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ccdea-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="ccdea-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccdea-154">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-155">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-155">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ccdea-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="ccdea-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ccdea-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccdea-158">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-159">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-160">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="ccdea-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccdea-162">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-162">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-163">A/V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="ccdea-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ccdea-164">任何</span><span class="sxs-lookup"><span data-stu-id="ccdea-164">Any</span></span></p></td>
<td><p><span data-ttu-id="ccdea-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ccdea-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="ccdea-166">Microsoft Office 通訊伺服器2007需要稍有不同的設定。</span><span class="sxs-lookup"><span data-stu-id="ccdea-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="ccdea-167">59999的 TCP 和 UDP 埠範圍必須是開啟的輸入和輸出。</span><span class="sxs-lookup"><span data-stu-id="ccdea-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="ccdea-168">這項需求只適用于 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="ccdea-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="ccdea-169">Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000 59999 開啟輸出。</span><span class="sxs-lookup"><span data-stu-id="ccdea-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="ccdea-170">Edge service 的 NAT 需求</span><span class="sxs-lookup"><span data-stu-id="ccdea-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="ccdea-171">如果您選擇為 Edge service 設定不可路由的私人 IP 位址，則適用下列 NAT 需求：</span><span class="sxs-lookup"><span data-stu-id="ccdea-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="ccdea-172">NAT 只可搭配使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="ccdea-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="ccdea-173">NAT 不支援硬體負載平衡 (HLB) Edge 拓撲。</span><span class="sxs-lookup"><span data-stu-id="ccdea-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="ccdea-174">NAT 只可用於外部 Edge 介面。</span><span class="sxs-lookup"><span data-stu-id="ccdea-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="ccdea-175">在內部 Edge 介面上不支援 NAT。</span><span class="sxs-lookup"><span data-stu-id="ccdea-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="ccdea-176">NAT 必須對稱傳入和傳出的流量。</span><span class="sxs-lookup"><span data-stu-id="ccdea-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="ccdea-177">對於來自網際網路的流量，NAT 必須將 A/V Edge service 之已啟用 NAT 的公用 IP 位址的目的地 IP 位址變更為其外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="ccdea-178">來源 IP 位址必須保持不變，因此 A/V Edge service 可以找出最佳的媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="ccdea-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="ccdea-179">例如，在下圖的輸入方向中，公用 IP 位址131.107.155.30 已變更為外部 (私人) IP 位址10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="ccdea-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="ccdea-180">來源 IP 位址保持不變。</span><span class="sxs-lookup"><span data-stu-id="ccdea-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="ccdea-181">若要從 A/V Edge service 到網際網路的流量，NAT 必須將來源 IP 位址從 A/V Edge service 的外部 IP 位址變更為已啟用 NAT 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="ccdea-182">例如，在下圖的輸出方向上，外部 (私人) IP 位址10.45.16.10 已變更為公用 IP 位址131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="ccdea-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="ccdea-183">**下圖顯示 NAT 如何變更輸入流量的目的地 IP 位址，以及輸出流量的來源 IP 位址。**</span><span class="sxs-lookup"><span data-stu-id="ccdea-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="ccdea-184">![變更目的地/來源 IP 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 IP 位址")</span><span class="sxs-lookup"><span data-stu-id="ccdea-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="ccdea-185">重點為：</span><span class="sxs-lookup"><span data-stu-id="ccdea-185">The key points are:</span></span>

  - <span data-ttu-id="ccdea-186">輸入至執行 A/V Edge service 之伺服器的流量，來源 IP 位址不會變更，但目的地 IP 位址會從131.107.155.30 變更為10.45.16.10 的轉譯後的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="ccdea-187">從執行 A/V Edge service 的伺服器輸出到工作站的流量，來源 IP 位址會從伺服器的公用 IP 位址變更為執行 A/V Edge service 之伺服器的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="ccdea-188">目的地 IP 會保留工作站的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="ccdea-189">當封包保留第一個 NAT 裝置輸出後，NAT 裝置上的規則會將執行 A/V Edge service 外部介面 IP 位址 (10.45.16.10) 的伺服器來源 IP 位址變更為 (131.107.155.30) 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ccdea-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

