---
title: Lync Server 2013：決定外部 A/V 防火牆和連接埠需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="3e462-102">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="3e462-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e462-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="3e462-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="3e462-104">音訊/視頻（A/V）通訊可能是一個複雜的。</span><span class="sxs-lookup"><span data-stu-id="3e462-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="3e462-105">因為在 A/V 中使用的通訊協定以及用戶端和伺服器如何使用通訊協定，所以有一個特殊的章節可保證說明用戶端與伺服器版本之間的差異。</span><span class="sxs-lookup"><span data-stu-id="3e462-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="3e462-106">使用下列 A/V 防火牆和埠表來判斷防火牆需求和要開啟的埠。</span><span class="sxs-lookup"><span data-stu-id="3e462-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="3e462-107">然後，請查看網路位址轉譯（NAT）術語，因為 NAT 可以用許多不同的方式來實現。</span><span class="sxs-lookup"><span data-stu-id="3e462-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="3e462-108">如需防火牆埠設定的詳細範例，請參閱[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)中的參考體系結構。</span><span class="sxs-lookup"><span data-stu-id="3e462-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="3e462-109">音訊/視頻和媒體流量中的 UDP 與 TCP 的一般通訊協定用法</span><span class="sxs-lookup"><span data-stu-id="3e462-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e462-110">音訊/視頻傳輸</span><span class="sxs-lookup"><span data-stu-id="3e462-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="3e462-111">用法</span><span class="sxs-lookup"><span data-stu-id="3e462-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e462-112">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="3e462-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="3e462-113">音訊與影片的首選傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="3e462-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e462-114">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="3e462-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="3e462-115">音訊與影片的回退傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="3e462-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="3e462-116">Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 適用的應用程式共用所需的傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="3e462-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="3e462-117">將檔案傳輸至 Lync Server 2010 和 Lync Server 2013 所需的傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="3e462-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="3e462-118">外部使用者存取的外部 A/V 防火牆埠需求</span><span class="sxs-lookup"><span data-stu-id="3e462-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="3e462-119">不論用戶端的版本或同盟夥伴版本為何，外部（以及內部） SIP 與會議介面的防火牆埠需求都是一致的。</span><span class="sxs-lookup"><span data-stu-id="3e462-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="3e462-120">音訊/視頻邊緣外部介面也不是如此。</span><span class="sxs-lookup"><span data-stu-id="3e462-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="3e462-121">針對使用 Office 通訊伺服器2007的同盟，A/V Edge 服務需要外部防火牆規則，才能在50000至59999埠範圍中啟用 RTP/TCP 和 RTP/UDP 流量，以雙向流動。</span><span class="sxs-lookup"><span data-stu-id="3e462-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="3e462-122">上表假設 Lync Server 2013 是主要同盟夥伴，且正在設定為與列出的其他其中一個聯盟夥伴類型進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3e462-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="3e462-123">將音訊/視訊連接埠範圍設定為 50000-59999，必須考慮埠範圍將包含與同盟夥伴通訊的來源埠。</span><span class="sxs-lookup"><span data-stu-id="3e462-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="3e462-124">在詳細資料中，請考慮從同盟合作夥伴開始進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3e462-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="3e462-125">來自 50000 59999 範圍中的 A/V 邊緣服務埠的通訊，會連線到合作夥伴的 A/V 邊緣服務的預期埠 TCP 443。</span><span class="sxs-lookup"><span data-stu-id="3e462-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="3e462-126">相反地，到 A/V 邊緣服務埠 TCP 443 的入站流量將會有 50000 59999 的來源埠。</span><span class="sxs-lookup"><span data-stu-id="3e462-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="3e462-127">防火牆管理的不同防火牆與原則可能只需要設定目的地規則，或者可能需要設定來源和目的地。</span><span class="sxs-lookup"><span data-stu-id="3e462-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="3e462-128">如果您的需求只適用于目的地埠，音訊/視頻需求如下：</span><span class="sxs-lookup"><span data-stu-id="3e462-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e462-129">來源 IP</span><span class="sxs-lookup"><span data-stu-id="3e462-129">Source IP</span></span></th>
<th><span data-ttu-id="3e462-130">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="3e462-130">Destination IP</span></span></th>
<th><span data-ttu-id="3e462-131">目的地埠</span><span class="sxs-lookup"><span data-stu-id="3e462-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e462-132">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-133">每</span><span class="sxs-lookup"><span data-stu-id="3e462-133">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e462-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e462-135">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-136">每</span><span class="sxs-lookup"><span data-stu-id="3e462-136">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="3e462-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e462-138">每</span><span class="sxs-lookup"><span data-stu-id="3e462-138">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-139">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e462-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e462-141">每</span><span class="sxs-lookup"><span data-stu-id="3e462-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-142">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="3e462-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3e462-144">如果您的原則需要輸入和輸出防火牆規則定義，音訊/視頻需求如下：</span><span class="sxs-lookup"><span data-stu-id="3e462-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e462-145">來源 IP</span><span class="sxs-lookup"><span data-stu-id="3e462-145">Source IP</span></span></th>
<th><span data-ttu-id="3e462-146">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="3e462-146">Destination IP</span></span></th>
<th><span data-ttu-id="3e462-147">來源埠</span><span class="sxs-lookup"><span data-stu-id="3e462-147">Source Port</span></span></th>
<th><span data-ttu-id="3e462-148">目的地埠</span><span class="sxs-lookup"><span data-stu-id="3e462-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e462-149">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-150">每</span><span class="sxs-lookup"><span data-stu-id="3e462-150">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-151">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="3e462-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3e462-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e462-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e462-153">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-154">每</span><span class="sxs-lookup"><span data-stu-id="3e462-154">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="3e462-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="3e462-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="3e462-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e462-157">每</span><span class="sxs-lookup"><span data-stu-id="3e462-157">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-158">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-159">每</span><span class="sxs-lookup"><span data-stu-id="3e462-159">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="3e462-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e462-161">每</span><span class="sxs-lookup"><span data-stu-id="3e462-161">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-162">A/V 邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="3e462-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="3e462-163">每</span><span class="sxs-lookup"><span data-stu-id="3e462-163">Any</span></span></p></td>
<td><p><span data-ttu-id="3e462-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="3e462-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e462-165">Microsoft Office 通訊伺服器2007需要稍有不同的配置。</span><span class="sxs-lookup"><span data-stu-id="3e462-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="3e462-166">TCP 和 UDP 埠範圍為 50000-59999 必須開啟入站和出站。</span><span class="sxs-lookup"><span data-stu-id="3e462-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="3e462-167">這個需求只適用于 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="3e462-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="3e462-168">Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000-59999 開啟輸出。</span><span class="sxs-lookup"><span data-stu-id="3e462-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="3e462-169">Edge 服務的 NAT 需求</span><span class="sxs-lookup"><span data-stu-id="3e462-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="3e462-170">如果您選擇針對 Edge 服務設定無法路由的私人 IP 位址，則適用下列 NAT 需求：</span><span class="sxs-lookup"><span data-stu-id="3e462-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="3e462-171">NAT 只能與 DNS 負載平衡搭配使用。</span><span class="sxs-lookup"><span data-stu-id="3e462-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="3e462-172">NAT 在硬體負載平衡（HLB）邊緣拓撲中不受支援。</span><span class="sxs-lookup"><span data-stu-id="3e462-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="3e462-173">NAT 只能在外部邊緣介面上使用。</span><span class="sxs-lookup"><span data-stu-id="3e462-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="3e462-174">內部邊緣介面不支援 NAT。</span><span class="sxs-lookup"><span data-stu-id="3e462-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="3e462-175">NAT 必須針對內送和外寄流量進行對稱。</span><span class="sxs-lookup"><span data-stu-id="3e462-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="3e462-176">對於來自網際網路的流量，NAT 必須將目的地 IP 位址從 A/V 邊緣服務的 NAT 啟用公用 IP 位址變更為其外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e462-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="3e462-177">來源 IP 位址必須保持不變，因此 A/V Edge 服務可以找到最佳媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="3e462-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="3e462-178">例如，在下圖中的入站方向上，公用 IP 位址131.107.155.30 已變更為外部（私人） IP 位址10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="3e462-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="3e462-179">來源 IP 位址仍保持不變。</span><span class="sxs-lookup"><span data-stu-id="3e462-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="3e462-180">對於從 A/V 邊緣服務到網際網路的流量，NAT 必須將來源 IP 位址從 A/V 邊緣服務的外部 IP 位址變更為啟用 NAT 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e462-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="3e462-181">例如，在下圖中的輸出方向上，外部（私人） IP 位址10.45.16.10 已變更為公用 IP 位址131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="3e462-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="3e462-182">**下圖顯示 NAT 如何變更入站流量的目的地 IP 位址，以及輸出流量的來源 IP 位址。**</span><span class="sxs-lookup"><span data-stu-id="3e462-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="3e462-183">![變更目的地/來源 ip 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 ip 位址")</span><span class="sxs-lookup"><span data-stu-id="3e462-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="3e462-184">重點如下：</span><span class="sxs-lookup"><span data-stu-id="3e462-184">The key points are:</span></span>

  - <span data-ttu-id="3e462-185">入站至執行 A/V 邊緣服務之伺服器的流量，來源 IP 位址不會變更，但目的地 IP 位址會從131.107.155.30 變更為10.45.16.10 的已翻譯 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e462-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="3e462-186">來源 IP 位址從伺服器的公用 IP 位址變更為執行 A/V 邊緣服務之伺服器的公用 IP 位址的流量（從伺服器的公用 IP 位址到工作站）。</span><span class="sxs-lookup"><span data-stu-id="3e462-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="3e462-187">目的地 IP 仍是工作站的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3e462-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="3e462-188">在資料包離開第一個 NAT 裝置的輸出之後，NAT 裝置上的規則會將執行 A/V 邊緣服務外部介面 IP 位址（10.45.16.10）的伺服器來源 IP 位址變更為其公用 IP 位址（131.107.155.30）。</span><span class="sxs-lookup"><span data-stu-id="3e462-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

