---
title: Lync Server 2013： 決定外部 A / V 防火牆和連接埠需求
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
ms.openlocfilehash: f28e1f18a0d2f2d51e835332d6abc8c67905d647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="4fa6b-102">決定外部 A / V 防火牆和連接埠需求 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fa6b-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fa6b-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="4fa6b-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4fa6b-104">音訊/視訊 (A / V) 通訊可能的複數。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="4fa6b-105">因使用中的通訊協定的本質 / V，以及如何用戶端和伺服器使用的通訊協定，特殊] 區段中已獲得保證來說明用戶端及伺服器版本之間的差異。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="4fa6b-106">使用下列的 A / V 防火牆和連接埠表格至判斷防火牆需求，以及哪些若要開啟 [連接埠。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="4fa6b-107">接著檢閱網路位址轉譯 (NAT) 術語，因為 NAT 可透過許多方式實作。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="4fa6b-108">防火牆連接埠設定的詳細範例，請參閱參考架構中[的 Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="4fa6b-109">UDP 和 TCP 音訊/視訊和媒體流量的一般通訊協定使用量</span><span class="sxs-lookup"><span data-stu-id="4fa6b-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fa6b-110">音訊/視訊傳輸</span><span class="sxs-lookup"><span data-stu-id="4fa6b-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="4fa6b-111">Usage</span><span class="sxs-lookup"><span data-stu-id="4fa6b-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa6b-112">UDP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-113">音訊及視訊的慣用的傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="4fa6b-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa6b-114">TCP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-115">音訊及視訊的後援傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="4fa6b-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="4fa6b-116">共用 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 的應用程式需要傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="4fa6b-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="4fa6b-117">檔案傳輸時必須使用 Lync Server 2010 和 Lync Server 2013 需要傳輸層通訊協定</span><span class="sxs-lookup"><span data-stu-id="4fa6b-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="4fa6b-118">外部使用者存取的外部 A/V 防火牆連接埠需求</span><span class="sxs-lookup"><span data-stu-id="4fa6b-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="4fa6b-119">外部 （及內部） 的防火牆連接埠需求 SIP 和會議的介面是一致的無論您的用戶端的版本或同盟協力廠商的版本。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="4fa6b-120">A/V Edge 外部介面則不同。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="4fa6b-121">同盟與 Office Communications Server 2007，A / V Edge 服務需要外部防火牆規則，允許透過 59,999 流向兩個方向的連接埠範圍 50000 中的 RTP/TCP 和 RTP/UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="4fa6b-122">上表假設 Lync Server 2013 是主要的同盟協力廠商，而且正在設定與其他同盟協力廠商類型所列的其中一個通訊。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="4fa6b-123">設定音訊/視訊連接埠範圍 50000-59999 的必須考慮到的連接埠範圍將包含通訊對同盟協力廠商來源的連接埠。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="4fa6b-124">在詳細資料，請考慮通訊會起始從同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="4fa6b-125">通訊從 A / V Edge service 連接埠 50000-59999 範圍中的會連線到預期的連接埠 TCP 443 的合作夥伴的 A / V Edge service。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="4fa6b-126">相反地，輸入流量 A/V Edge service 連接埠 TCP 443 會有 50000-59，999 介於來源連接埠。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="4fa6b-127">不同的防火牆和防火牆管理的原則可能需要只目的地規則進行的設定，或他們可能需要來源和目的地，以進行設定。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="4fa6b-128">如果您的需求適用於僅目的地連接埠，音訊/視訊需求︰</span><span class="sxs-lookup"><span data-stu-id="4fa6b-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fa6b-129">來源 IP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-129">Source IP</span></span></th>
<th><span data-ttu-id="4fa6b-130">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-130">Destination IP</span></span></th>
<th><span data-ttu-id="4fa6b-131">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="4fa6b-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa6b-132">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-133">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4fa6b-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa6b-135">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-136">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-136">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4fa6b-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fa6b-138">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-139">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4fa6b-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa6b-141">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-142">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4fa6b-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4fa6b-144">如果您的原則需要兩個輸入和輸出的防火牆規則定義，音訊/視訊需求︰</span><span class="sxs-lookup"><span data-stu-id="4fa6b-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fa6b-145">來源 IP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-145">Source IP</span></span></th>
<th><span data-ttu-id="4fa6b-146">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="4fa6b-146">Destination IP</span></span></th>
<th><span data-ttu-id="4fa6b-147">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="4fa6b-147">Source Port</span></span></th>
<th><span data-ttu-id="4fa6b-148">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="4fa6b-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fa6b-149">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-150">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-151">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="4fa6b-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4fa6b-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa6b-153">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-154">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4fa6b-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4fa6b-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fa6b-157">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-158">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-159">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-159">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4fa6b-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fa6b-161">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-162">A / V Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="4fa6b-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-163">任何</span><span class="sxs-lookup"><span data-stu-id="4fa6b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="4fa6b-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4fa6b-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="4fa6b-165">Microsoft Office Communications Server 2007 需要稍有不同的設定。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="4fa6b-166">輸入和輸出，則必須開啟 50000-59999 的 TCP 及 UDP 連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="4fa6b-167">僅適用於 Office Communicator 2007 是這項要求。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="4fa6b-168">Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 只需要 TCP 範圍 50000-59999 開放輸出。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="4fa6b-169">Edge service 的 NAT 需求</span><span class="sxs-lookup"><span data-stu-id="4fa6b-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="4fa6b-170">如果您選擇設定 Edge service 的非路由傳送私人 IP 位址，適用下列 NAT 需求：</span><span class="sxs-lookup"><span data-stu-id="4fa6b-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="4fa6b-171">NAT 只可以搭配 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="4fa6b-172">NAT 不支援使用硬體負載平衡 (HLB) Edge 拓撲。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="4fa6b-173">只能在外部 Edge 介面 NAT。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="4fa6b-174">內部 Edge 介面不支援 NAT。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="4fa6b-175">NAT 必須對稱的內送和外寄流量。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="4fa6b-176">來自網際網路的流量，NAT 必須變更的目的地 IP 位址從啟用 NAT 的公用 IP 位址的 A / V Edge service 為外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="4fa6b-177">來源 IP 位址必須保持不變，以便在 A / V Edge service 可以找出最佳的媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="4fa6b-178">例如，以在下圖中輸入的方向，公用 IP 位址 131.107.155.30 已變更為外部 （私人） IP 位址 10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="4fa6b-179">來源 IP 位址將維持不變。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="4fa6b-180">流量從 A / V Edge service 至網際網路，NAT 必須變更來源 IP 位址從外部 IP 位址的 A / V Edge service 為啟用 NAT 的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="4fa6b-181">例如，在下圖中的輸出方向，外部 （私人） IP 位址 10.45.16.10 已變更為公用 IP 位址 131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="4fa6b-182">**下圖顯示如何 NAT 變更輸入流量的目的地 IP 位址和輸出流量的來源 IP 位址。**</span><span class="sxs-lookup"><span data-stu-id="4fa6b-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="4fa6b-183">![變更目的地/來源 IP 位址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "變更目的地/來源 IP 位址")</span><span class="sxs-lookup"><span data-stu-id="4fa6b-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="4fa6b-184">重點為：</span><span class="sxs-lookup"><span data-stu-id="4fa6b-184">The key points are:</span></span>

  - <span data-ttu-id="4fa6b-185">是輸入到伺服器執行 A / V Edge service 為來源 IP 位址不會變更的流量，但目的地 IP 位址從 131.107.155.30 變更要翻譯的 IP 位址 10.45.16.10。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="4fa6b-186">會從執行 A server 輸出的流量 / V Edge service 回到工作站、 來源 IP 位址從伺服器的公用 IP 位址變更為公用 IP 位址的伺服器執行 A / V Edge service。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="4fa6b-187">目的地 ip 位址會維持工作站的公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="4fa6b-188">NAT 裝置上的規則封包離開的第一個 NAT 裝置輸出之後，變更來源 IP 位址的伺服器執行 A / V Edge service 為公用 IP 位址 (131.107.155.30) 的外部介面 IP 位址 (10.45.16.10)。</span><span class="sxs-lookup"><span data-stu-id="4fa6b-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

