---
title: Lync Server 2013：選擇拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="9acbc-102">在 Lync Server 2013 中選擇拓撲</span><span class="sxs-lookup"><span data-stu-id="9acbc-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="9acbc-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9acbc-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9acbc-104">當您選擇拓撲時，可以使用下列支援的拓撲選項之一：</span><span class="sxs-lookup"><span data-stu-id="9acbc-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9acbc-105">除非另有說明，否則如果您有 Microsoft Lync Server 2010 的使用經驗，您可以在這裡找到這些指南，主要是不變的。</span><span class="sxs-lookup"><span data-stu-id="9acbc-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="9acbc-106">Lync Server 2013 中的單一合併 Edge (利用私人 IP 位址及 NAT)</span><span class="sxs-lookup"><span data-stu-id="9acbc-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="9acbc-107">Lync Server 2013 中的單一合併 Edge (利用公用 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9acbc-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="9acbc-108">Lync Server 2013 中的調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="9acbc-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="9acbc-109">Lync Server 2013 中的調整式合併 Edge (透過公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="9acbc-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="9acbc-110">Lync Server 2013 中含硬體負載平衡器的調整式合併 Edge</span><span class="sxs-lookup"><span data-stu-id="9acbc-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="9acbc-111">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="9acbc-112">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="9acbc-113">下表摘要列出支援的 Microsoft Lync Server 2013 拓撲結構所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="9acbc-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="9acbc-114">欄標題指出特定邊緣設定選項可用的功能。</span><span class="sxs-lookup"><span data-stu-id="9acbc-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="9acbc-115">使用 [調整邊緣（DNS 負載平衡）] 選項做為範例，您可以看到它支援高可用性，可以使用無法路由的私人 IP 位址（使用 NAT），或指派給 Edge 外部介面的路由公用 IP 位址，並減少成本，因為硬體負載平衡器不是必要的。</span><span class="sxs-lookup"><span data-stu-id="9acbc-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="9acbc-116">DNS 負載平衡支援的邊緣容錯移轉案例為 Lync 到 Lync 點對點會話、Lync 會議會話、Lync 對 PSTN 會話和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9acbc-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="9acbc-117">無法從 DNS 負載平衡獲益的邊緣容錯移轉案例是針對遠端使用者交換整合訊息（UM）（在 Exchange 2010 SP1 之前）、公用立即訊息（IM）連線以及與執行 Office 通訊的伺服器的同盟伺服器.</span><span class="sxs-lookup"><span data-stu-id="9acbc-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="9acbc-118">Edge 伺服器拓撲選項摘要</span><span class="sxs-lookup"><span data-stu-id="9acbc-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="9acbc-119">拓撲</span><span class="sxs-lookup"><span data-stu-id="9acbc-119">Topology</span></span></th>
<th><span data-ttu-id="9acbc-120">高可用性</span><span class="sxs-lookup"><span data-stu-id="9acbc-120">High availability</span></span></th>
<th><span data-ttu-id="9acbc-121">在 Edge 池中，外部邊緣伺服器所需的其他 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="9acbc-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="9acbc-122">Lync 對 Lync 會話的邊緣容錯移轉</span><span class="sxs-lookup"><span data-stu-id="9acbc-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="9acbc-123">Lync to Lync EUM/PIC/OCS 同盟會話的邊緣容錯移轉</span><span class="sxs-lookup"><span data-stu-id="9acbc-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-124">使用 NAT 的單一邊緣</span><span class="sxs-lookup"><span data-stu-id="9acbc-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="9acbc-125">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-125">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-126">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-126">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-127">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-127">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-128">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-129">使用公用 IP 的單一邊緣</span><span class="sxs-lookup"><span data-stu-id="9acbc-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="9acbc-130">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-130">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-131">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-131">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-132">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-132">No</span></span></p></td>
<td><p><span data-ttu-id="9acbc-133">否</span><span class="sxs-lookup"><span data-stu-id="9acbc-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-134">使用 NAT 調整邊緣（DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="9acbc-135">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-136">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-137">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-138">使用公用 IP 進行縮放的邊緣（DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="9acbc-139">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-140">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-141">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-142">已縮放的邊緣硬體負載平衡</span><span class="sxs-lookup"><span data-stu-id="9acbc-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="9acbc-143">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-144">否（每個 VIP 一個 DNS A 記錄）</span><span class="sxs-lookup"><span data-stu-id="9acbc-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="9acbc-145">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="9acbc-146">是</span><span class="sxs-lookup"><span data-stu-id="9acbc-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9acbc-147">**\***[DNS 負載平衡] 不提供公用立即訊息（IM）連線的容錯移轉與執行 Office 通訊伺服器的伺服器的同盟。</span><span class="sxs-lookup"><span data-stu-id="9acbc-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="9acbc-148">Exchange UM （遠端使用者）使用 DNS 負載平衡的容錯移轉需要 Exchange Server 2010 SP1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9acbc-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="9acbc-149">單一邊緣與縮放邊緣（DNS 負載平衡）拓撲可以使用：</span><span class="sxs-lookup"><span data-stu-id="9acbc-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="9acbc-150">可路由的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9acbc-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="9acbc-151">如果使用對稱網路位址轉譯（NAT），則無法路由的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9acbc-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="9acbc-152">如果您使用的是公用 IP 位址或私人 IP 位址與 NAT，您仍會根據拓撲建立器中的設定選項，使用相同數量的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9acbc-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="9acbc-153">您可以將 Edge 伺服器設定為使用單一 IP 位址，每個服務都有不同的埠，或針對每個服務使用不同的 IP 位址，但使用相同的埠（預設為 TCP 443）。</span><span class="sxs-lookup"><span data-stu-id="9acbc-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="9acbc-154">如果您決定將無法路由的私人 IP 位址與 NAT 搭配使用：</span><span class="sxs-lookup"><span data-stu-id="9acbc-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="9acbc-155">您必須在所有三個外部介面上使用可路由的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9acbc-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="9acbc-156">您必須為內送和外寄通訊設定對稱 NAT</span><span class="sxs-lookup"><span data-stu-id="9acbc-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="9acbc-157">已縮放的邊緣（硬體負載平衡）拓朴必須使用公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9acbc-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="9acbc-158">Lync Server 2013 支援在路由器或防火牆後面放置 Access、Web 會議和 A/V 邊緣外部介面，以針對單一和縮放的合併邊緣伺服器拓撲執行網路位址轉譯（NAT）。</span><span class="sxs-lookup"><span data-stu-id="9acbc-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="9acbc-159">針對所有 Edge 外部介面使用 NAT，需要使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="9acbc-160">與使用硬體負載平衡器相比，使用不含 NAT 的 DNS 負載平衡可讓您減少邊緣池中每個邊緣伺服器的公用 IP 位址數量，如下列清單所述：</span><span class="sxs-lookup"><span data-stu-id="9acbc-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="9acbc-161">Lync Server 2013 縮放的合併邊緣（DNS 負載平衡）需要在 Edge 池中的每個 Edge 伺服器都有三個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9acbc-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="9acbc-162">Lync Server 2013 縮放的合併邊緣（硬體負載平衡）需要三個負載平衡器虛擬 IP 位址的公用 IP 位址（一次需求不會隨著更多邊緣伺服器新增到池中而增加）加上三個公用 IP 位址。在池中的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9acbc-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="9acbc-163">已調整合並邊緣的 IP 位址需求（每個角色的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9acbc-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9acbc-164">每個池的邊緣伺服器數</span><span class="sxs-lookup"><span data-stu-id="9acbc-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="9acbc-165">Lync Server 2013 的必要 IP 位址數量（DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="9acbc-166">Lync Server 2013 的必要 IP 位址數量（硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-167">2</span><span class="sxs-lookup"><span data-stu-id="9acbc-167">2</span></span></p></td>
<td><p><span data-ttu-id="9acbc-168">6</span><span class="sxs-lookup"><span data-stu-id="9acbc-168">6</span></span></p></td>
<td><p><span data-ttu-id="9acbc-169">3（每個 VIP 1） + 6</span><span class="sxs-lookup"><span data-stu-id="9acbc-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-170">3</span><span class="sxs-lookup"><span data-stu-id="9acbc-170">3</span></span></p></td>
<td><p><span data-ttu-id="9acbc-171">9</span><span class="sxs-lookup"><span data-stu-id="9acbc-171">9</span></span></p></td>
<td><p><span data-ttu-id="9acbc-172">3（每個 VIP 1 個） + 9</span><span class="sxs-lookup"><span data-stu-id="9acbc-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-173">4</span><span class="sxs-lookup"><span data-stu-id="9acbc-173">4</span></span></p></td>
<td><p><span data-ttu-id="9acbc-174">之間</span><span class="sxs-lookup"><span data-stu-id="9acbc-174">12</span></span></p></td>
<td><p><span data-ttu-id="9acbc-175">3（每個 VIP 1） + 12</span><span class="sxs-lookup"><span data-stu-id="9acbc-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-176">500</span><span class="sxs-lookup"><span data-stu-id="9acbc-176">5</span></span></p></td>
<td><p><span data-ttu-id="9acbc-177">工資</span><span class="sxs-lookup"><span data-stu-id="9acbc-177">15</span></span></p></td>
<td><p><span data-ttu-id="9acbc-178">3（每個 VIP 1） + 15</span><span class="sxs-lookup"><span data-stu-id="9acbc-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="9acbc-179">已調整合並邊緣的 IP 位址需求（適用于所有角色的單一 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9acbc-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9acbc-180">每個池的邊緣伺服器數</span><span class="sxs-lookup"><span data-stu-id="9acbc-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="9acbc-181">Lync Server 2013 的必要 IP 位址數量（DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="9acbc-182">Lync Server 2013 的必要 IP 位址數量（硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="9acbc-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-183">2</span><span class="sxs-lookup"><span data-stu-id="9acbc-183">2</span></span></p></td>
<td><p><span data-ttu-id="9acbc-184">2</span><span class="sxs-lookup"><span data-stu-id="9acbc-184">2</span></span></p></td>
<td><p><span data-ttu-id="9acbc-185">1（每個 VIP 1 個） + 2</span><span class="sxs-lookup"><span data-stu-id="9acbc-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-186">3</span><span class="sxs-lookup"><span data-stu-id="9acbc-186">3</span></span></p></td>
<td><p><span data-ttu-id="9acbc-187">3</span><span class="sxs-lookup"><span data-stu-id="9acbc-187">3</span></span></p></td>
<td><p><span data-ttu-id="9acbc-188">1（每個 VIP 1 個） + 3</span><span class="sxs-lookup"><span data-stu-id="9acbc-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9acbc-189">4</span><span class="sxs-lookup"><span data-stu-id="9acbc-189">4</span></span></p></td>
<td><p><span data-ttu-id="9acbc-190">4</span><span class="sxs-lookup"><span data-stu-id="9acbc-190">4</span></span></p></td>
<td><p><span data-ttu-id="9acbc-191">1（每個 VIP 1 個） + 4</span><span class="sxs-lookup"><span data-stu-id="9acbc-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9acbc-192">500</span><span class="sxs-lookup"><span data-stu-id="9acbc-192">5</span></span></p></td>
<td><p><span data-ttu-id="9acbc-193">500</span><span class="sxs-lookup"><span data-stu-id="9acbc-193">5</span></span></p></td>
<td><p><span data-ttu-id="9acbc-194">1（每個 VIP 1 個） + 5</span><span class="sxs-lookup"><span data-stu-id="9acbc-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9acbc-195">拓撲選擇的主要決策點有高可用性和負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="9acbc-196">高可用性需求可能會影響負載平衡決策。</span><span class="sxs-lookup"><span data-stu-id="9acbc-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="9acbc-197">**高可用性**  如果您需要高可用性，請在池中部署至少兩個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9acbc-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="9acbc-198">單一邊緣池最多可支援十二台邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9acbc-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="9acbc-199">如果需要更多容量，您可以部署多個 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="9acbc-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="9acbc-200">一般來說，指定使用者基礎的10% 將需要外部存取。</span><span class="sxs-lookup"><span data-stu-id="9acbc-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="9acbc-201">拓撲建立器可讓您在單一邊緣池中設定最多20台邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9acbc-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="9acbc-202">在池中經過測試和支援的最大 Edge 伺服器數為十二個，而拓撲產生器允許大於十二的數位，不應該在單一邊緣池中，解釋為超過12個邊緣伺服器的默示支援。</span><span class="sxs-lookup"><span data-stu-id="9acbc-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="9acbc-203">**硬體負載平衡**  在針對 Edge 外部介面使用可公開路由的 IP 位址時，在 Lync Server 2013 Edge 伺服器上支援負載平衡的硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="9acbc-204">例如，您可以在下列任何一種應用程式需要容錯移轉的情況下使用這個方法：</span><span class="sxs-lookup"><span data-stu-id="9acbc-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="9acbc-205">公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9acbc-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="9acbc-206">與執行 Microsoft Office 通訊伺服器2007或 Microsoft Office 通訊伺服器 2007 R2 的公司同盟</span><span class="sxs-lookup"><span data-stu-id="9acbc-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="9acbc-207">外部存取 Exchange 2007 整合通訊（UM）或 Exchange 2010 UM</span><span class="sxs-lookup"><span data-stu-id="9acbc-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="9acbc-208">Exchange UM 支援 Exchange 2010 SP1 及更新版本的 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="9acbc-209">這三個應用程式將會繼續運作，但它們不是 DNS 負載平衡感知，而且只會連接到池中的第一個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="9acbc-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="9acbc-210">如果該伺服器無法使用，連接就會失敗。</span><span class="sxs-lookup"><span data-stu-id="9acbc-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="9acbc-211">例如，如果在池中部署多個邊緣伺服器來處理同盟流量負載，則只有一個訪問 proxy 會在其他人空閒時實際接收流量。</span><span class="sxs-lookup"><span data-stu-id="9acbc-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9acbc-212">如果您是使用 Lync Server 2010 和 Microsoft Office 365 與公司進行聯盟，則建議使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9acbc-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="9acbc-213">請注意，如果大多數聯盟夥伴都使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2，就會有顯著的效能影響。</span><span class="sxs-lookup"><span data-stu-id="9acbc-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="9acbc-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="9acbc-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

