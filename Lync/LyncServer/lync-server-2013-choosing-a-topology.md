---
title: Lync Server 2013：選擇拓撲
description: Lync Server 2013：選擇拓撲。
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
ms.openlocfilehash: 01ded739c3c5e4e0bd8c0f25f3f0fe8ff1f350b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549679"
---
# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="57221-103">在 Lync Server 2013 中選擇拓撲</span><span class="sxs-lookup"><span data-stu-id="57221-103">Choosing a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="57221-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="57221-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="57221-105">選擇拓撲後，可以使用下列其中一個支援的拓撲選項：</span><span class="sxs-lookup"><span data-stu-id="57221-105">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="57221-106">除非另有說明，否則，如果您有 Microsoft Lync Server 2010 的經驗，您會發現這裡的指南基本上沒有變化。</span><span class="sxs-lookup"><span data-stu-id="57221-106">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="57221-107">Lync Server 2013 中的單一合併 edge （利用私人 IP 位址及 NAT）</span><span class="sxs-lookup"><span data-stu-id="57221-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="57221-108">Lync Server 2013 中的單一合併 edge （使用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="57221-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="57221-109">Lync Server 2013 中的調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="57221-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="57221-110">Lync Server 2013 中的調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="57221-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="57221-111">Lync Server 2013 中的調整式合併 edge （搭配硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="57221-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="57221-p101">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="57221-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="57221-114">下表摘要列出支援的 Microsoft Lync Server 2013 拓撲的可用功能。</span><span class="sxs-lookup"><span data-stu-id="57221-114">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="57221-115">欄標題表示某特定 Edge 設定選項可用的功能。</span><span class="sxs-lookup"><span data-stu-id="57221-115">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="57221-116">以調整式 Edge (DNS 負載平衡) 選項為例，您可以看到它支援高可用性，可使用指派給 Edge 外部介面之無法經路由傳送的私人 IP 位址 (搭配 NAT) 或可路由公用 IP 位址，由於不需要硬體負載平衡器因此可以降低成本。</span><span class="sxs-lookup"><span data-stu-id="57221-116">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="57221-117">DNS 負載平衡支援的 Edge 容錯移轉案例是 Lync-to-Lync 點對點會話、Lync 會議會話、Lync to PSTN 會話、Office 365 和 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="57221-117">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions, Office 365, and Microsoft 365.</span></span> <span data-ttu-id="57221-118">無法從 DNS 負載平衡受益的 Edge 容錯移轉案例是針對遠端使用者 Exchange 整合通訊 (UM)  (在 Exchange 2010 SP1) 之前，公用立即訊息 (IM) 連線，以及與執行 Office 通訊伺服器的伺服器同盟。</span><span class="sxs-lookup"><span data-stu-id="57221-118">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="57221-119">Edge Server 拓撲選項摘要</span><span class="sxs-lookup"><span data-stu-id="57221-119">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="57221-120">拓撲</span><span class="sxs-lookup"><span data-stu-id="57221-120">Topology</span></span></th>
<th><span data-ttu-id="57221-121">高可用性</span><span class="sxs-lookup"><span data-stu-id="57221-121">High availability</span></span></th>
<th><span data-ttu-id="57221-122">Edge 集區中的外部 Edge Server 都需要額外的 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="57221-122">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="57221-123">Lync-to-Lync 會話的 Edge 容錯移轉</span><span class="sxs-lookup"><span data-stu-id="57221-123">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="57221-124">Lync-to-Lync EUM/PIC/OCS 同盟會話的 Edge 容錯移轉</span><span class="sxs-lookup"><span data-stu-id="57221-124">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57221-125">使用 NAT 的單一 Edge</span><span class="sxs-lookup"><span data-stu-id="57221-125">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="57221-126">否</span><span class="sxs-lookup"><span data-stu-id="57221-126">No</span></span></p></td>
<td><p><span data-ttu-id="57221-127">否</span><span class="sxs-lookup"><span data-stu-id="57221-127">No</span></span></p></td>
<td><p><span data-ttu-id="57221-128">否</span><span class="sxs-lookup"><span data-stu-id="57221-128">No</span></span></p></td>
<td><p><span data-ttu-id="57221-129">否</span><span class="sxs-lookup"><span data-stu-id="57221-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-130">使用公用 IP 的單一 Edge</span><span class="sxs-lookup"><span data-stu-id="57221-130">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="57221-131">否</span><span class="sxs-lookup"><span data-stu-id="57221-131">No</span></span></p></td>
<td><p><span data-ttu-id="57221-132">否</span><span class="sxs-lookup"><span data-stu-id="57221-132">No</span></span></p></td>
<td><p><span data-ttu-id="57221-133">否</span><span class="sxs-lookup"><span data-stu-id="57221-133">No</span></span></p></td>
<td><p><span data-ttu-id="57221-134">否</span><span class="sxs-lookup"><span data-stu-id="57221-134">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57221-135">使用 NAT 的調整式 Edge (DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="57221-135">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="57221-136">是</span><span class="sxs-lookup"><span data-stu-id="57221-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-137">是</span><span class="sxs-lookup"><span data-stu-id="57221-137">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-138">是</span><span class="sxs-lookup"><span data-stu-id="57221-138">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-139">使用公用 IP 的調整式 Edge (DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="57221-139">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="57221-140">是</span><span class="sxs-lookup"><span data-stu-id="57221-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-141">是</span><span class="sxs-lookup"><span data-stu-id="57221-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-142">是</span><span class="sxs-lookup"><span data-stu-id="57221-142">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57221-143">調整式 Edge 硬體 (負載平衡)</span><span class="sxs-lookup"><span data-stu-id="57221-143">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="57221-144">是</span><span class="sxs-lookup"><span data-stu-id="57221-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-145">否 (每個 VIP 各一個 DNS A 記錄)</span><span class="sxs-lookup"><span data-stu-id="57221-145">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="57221-146">是</span><span class="sxs-lookup"><span data-stu-id="57221-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="57221-147">是</span><span class="sxs-lookup"><span data-stu-id="57221-147">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57221-148">**\*** 無法使用 DNS 負載平衡，針對公用立即訊息 (IM) 連線，以及與執行 Office 通訊伺服器之伺服器的同盟的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="57221-148">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="57221-149">Exchange UM (遠端使用者) 容錯移轉使用 DNS 負載平衡，需要 Exchange Server 2010 SP1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="57221-149">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="57221-150">單一 Edge 和調整式的 Edge (DNS 負載平衡) 拓撲可以使用：</span><span class="sxs-lookup"><span data-stu-id="57221-150">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="57221-151">可路由公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="57221-151">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="57221-152">在使用對稱網路位址轉譯 (NAT) 時，無法路由的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="57221-152">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="57221-153">如果您使用與 NAT 的公用 IP 位址或私人 IP 位址，您仍會根據拓撲產生器中的設定選擇，使用相同數目的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="57221-153">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="57221-154">您可以設定 Edge Server 使用單一 IP 位址，每個服務使用不同的埠，或為每個服務使用不同的 IP 位址，但依預設，TCP 443) 使用相同的埠 (。</span><span class="sxs-lookup"><span data-stu-id="57221-154">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="57221-155">如果您決定使用與 NAT 的非路由私人 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="57221-155">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="57221-156">您必須在所有三個外部介面上使用可路由傳送的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="57221-156">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="57221-157">您必須為輸入和輸出流量設定對稱的 NAT</span><span class="sxs-lookup"><span data-stu-id="57221-157">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="57221-158">調整式 Edge (硬體負載平衡) 拓撲必須使用公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="57221-158">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="57221-159">Lync Server 2013 支援將 Access、Web 會議和 A/V Edge 外部介面放在路由器或防火牆後面，該路由器或防火牆可對單一及調整式合併 Edge Server 拓撲執行網路位址轉譯 (NAT) 。</span><span class="sxs-lookup"><span data-stu-id="57221-159">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="57221-p106">若要將 NAT 用於所有 Edge 外部介面，需要使用 DNS 負載平衡。和使用硬體負載平衡相比，透過使用 DNS 負載平衡而不使用 NAT，可讓您減少 Edge 集區中每個 Edge Server 的公用 IP 位址數目，如下列清單中所述：</span><span class="sxs-lookup"><span data-stu-id="57221-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="57221-162">Lync Server 2013 調整式合併 Edge (DNS 負載平衡) 針對 Edge 集區中的每個 Edge Server 需要三個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="57221-162">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="57221-163">Lync Server 2013 調整式合併 Edge (硬體負載平衡) 需要三個公用 IP 位址用於負載平衡器的虛擬 IP 位址 (一次，當增加集區的 Edge Server) 外加集區中每 Edge Server 的三個公用 IP 位址時，不會增加。</span><span class="sxs-lookup"><span data-stu-id="57221-163">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="57221-164">調整式合併 Edge 的 IP 位址需求 (每個角色一個 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="57221-164">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57221-165">每個集區的 Edge Server 數目</span><span class="sxs-lookup"><span data-stu-id="57221-165">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="57221-166">Lync Server 2013 (的 DNS 負載平衡) 所需的 IP 位址數目</span><span class="sxs-lookup"><span data-stu-id="57221-166">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="57221-167">Lync Server 2013 (硬體負載平衡) 所需的 IP 位址數目</span><span class="sxs-lookup"><span data-stu-id="57221-167">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57221-168">第</span><span class="sxs-lookup"><span data-stu-id="57221-168">2</span></span></p></td>
<td><p><span data-ttu-id="57221-169">6 </span><span class="sxs-lookup"><span data-stu-id="57221-169">6</span></span></p></td>
<td><p><span data-ttu-id="57221-170">3 (每個 VIP 各 1 個) + 6</span><span class="sxs-lookup"><span data-stu-id="57221-170">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-171">個</span><span class="sxs-lookup"><span data-stu-id="57221-171">3</span></span></p></td>
<td><p><span data-ttu-id="57221-172">9 </span><span class="sxs-lookup"><span data-stu-id="57221-172">9</span></span></p></td>
<td><p><span data-ttu-id="57221-173">3 (每個 VIP 各 1 個) + 9</span><span class="sxs-lookup"><span data-stu-id="57221-173">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57221-174">4 </span><span class="sxs-lookup"><span data-stu-id="57221-174">4</span></span></p></td>
<td><p><span data-ttu-id="57221-175">12 </span><span class="sxs-lookup"><span data-stu-id="57221-175">12</span></span></p></td>
<td><p><span data-ttu-id="57221-176">3 (每個 VIP 各 1 個) + 12</span><span class="sxs-lookup"><span data-stu-id="57221-176">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-177">5 </span><span class="sxs-lookup"><span data-stu-id="57221-177">5</span></span></p></td>
<td><p><span data-ttu-id="57221-178">15 </span><span class="sxs-lookup"><span data-stu-id="57221-178">15</span></span></p></td>
<td><p><span data-ttu-id="57221-179">3 (每個 VIP 各 1 個) + 15</span><span class="sxs-lookup"><span data-stu-id="57221-179">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="57221-180">調整式合併 Edge 的 IP 位址需求 (所有角色都使用單一 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="57221-180">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57221-181">每個集區的 Edge Server 數目</span><span class="sxs-lookup"><span data-stu-id="57221-181">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="57221-182">Lync Server 2013 (的 DNS 負載平衡) 所需的 IP 位址數目</span><span class="sxs-lookup"><span data-stu-id="57221-182">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="57221-183">Lync Server 2013 (硬體負載平衡) 所需的 IP 位址數目</span><span class="sxs-lookup"><span data-stu-id="57221-183">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57221-184">第</span><span class="sxs-lookup"><span data-stu-id="57221-184">2</span></span></p></td>
<td><p><span data-ttu-id="57221-185">第</span><span class="sxs-lookup"><span data-stu-id="57221-185">2</span></span></p></td>
<td><p><span data-ttu-id="57221-186">1 (每個 VIP 各 1 個) + 2</span><span class="sxs-lookup"><span data-stu-id="57221-186">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-187">個</span><span class="sxs-lookup"><span data-stu-id="57221-187">3</span></span></p></td>
<td><p><span data-ttu-id="57221-188">個</span><span class="sxs-lookup"><span data-stu-id="57221-188">3</span></span></p></td>
<td><p><span data-ttu-id="57221-189">1 (每個 VIP 各 1 個) + 3</span><span class="sxs-lookup"><span data-stu-id="57221-189">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57221-190">4 </span><span class="sxs-lookup"><span data-stu-id="57221-190">4</span></span></p></td>
<td><p><span data-ttu-id="57221-191">4 </span><span class="sxs-lookup"><span data-stu-id="57221-191">4</span></span></p></td>
<td><p><span data-ttu-id="57221-192">1 (每個 VIP 各 1 個) + 4</span><span class="sxs-lookup"><span data-stu-id="57221-192">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57221-193">5 </span><span class="sxs-lookup"><span data-stu-id="57221-193">5</span></span></p></td>
<td><p><span data-ttu-id="57221-194">5 </span><span class="sxs-lookup"><span data-stu-id="57221-194">5</span></span></p></td>
<td><p><span data-ttu-id="57221-195">1 (每個 VIP 各 1 個) + 5</span><span class="sxs-lookup"><span data-stu-id="57221-195">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57221-p107">拓撲選項的主要決策點是高可用性和負載平衡。高可用性的需求條件會影響負載平衡的決策。</span><span class="sxs-lookup"><span data-stu-id="57221-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="57221-198">**高可用性**   如果您需要高可用性，請在集區中至少部署兩部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="57221-198">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="57221-199">單一 Edge 集區可支援最多十二部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="57221-199">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="57221-200">如果您需要更多容量，請部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="57221-200">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="57221-201">一般而言，10% 的使用者人數需要外部存取。</span><span class="sxs-lookup"><span data-stu-id="57221-201">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="57221-202">拓撲產生器可讓您在單一 Edge 集區中設定最多二十部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="57221-202">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="57221-203">在集區中已測試及支援的 Edge Server 數目上限為12，拓撲產生器允許大於12的數位，不應該對單一 Edge 集區中的十二部以上伺服器進行默示的支援。</span><span class="sxs-lookup"><span data-stu-id="57221-203">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="57221-204">**硬體負載平衡**   在使用可公開路由的 Edge 外部介面的 IP 位址時，可支援負載平衡 Lync Server 2013 Edge server 的硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="57221-204">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="57221-205">例如，在下列任一應用程式中需要容錯移轉時，就可使用此方法：</span><span class="sxs-lookup"><span data-stu-id="57221-205">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="57221-206">公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="57221-206">Public IM connectivity</span></span>
    
      - <span data-ttu-id="57221-207">與執行 Microsoft Office 通訊伺服器2007或 Microsoft Office 通訊伺服器 2007 R2 之公司的同盟</span><span class="sxs-lookup"><span data-stu-id="57221-207">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="57221-208">外部存取至 Exchange 2007 Unified Messaging (UM) 或 Exchange 2010 UM</span><span class="sxs-lookup"><span data-stu-id="57221-208">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="57221-209">Exchange 2010 SP1 和更新的 DNS 負載平衡支援 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="57221-209">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="57221-p111">這三種應用程式都能繼續運作，但不會感知 DNS 負載平衡，只會連接至集區中第一個 Edge Server。如果該伺服器無法使用，連線就會失敗。例如，如果在集區中部署多個 Edge Server 用來處理同盟流量負載，實際上只有一個 Access Proxy 會收到流量，而其他伺服器都閒置中。</span><span class="sxs-lookup"><span data-stu-id="57221-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="57221-213">如果您要與使用 Lync Server 2010 和 Office 365 或 Microsoft 365 的公司進行同盟，則建議使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="57221-213">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Office 365 or Microsoft 365.</span></span> <span data-ttu-id="57221-214">請注意，如果大多數同盟協力廠商使用 Office 通訊伺服器2007或 Office 通訊伺服器 2007 R2，對效能有顯著影響。</span><span class="sxs-lookup"><span data-stu-id="57221-214">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="57221-215"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="57221-215"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

