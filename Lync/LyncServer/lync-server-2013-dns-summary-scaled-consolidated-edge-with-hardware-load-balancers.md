---
title: DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="20aa8-102">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (利用硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="20aa8-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20aa8-103">_**主題上次修改日期：** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="20aa8-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="20aa8-104">對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。</span><span class="sxs-lookup"><span data-stu-id="20aa8-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="20aa8-105">此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。</span><span class="sxs-lookup"><span data-stu-id="20aa8-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="20aa8-106">如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20aa8-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="20aa8-107">如需有關設定 Lync 2013 用戶端的自動設定的詳細資料，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分割大腦 dns）一節。</span><span class="sxs-lookup"><span data-stu-id="20aa8-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="20aa8-108">下表包含支援經過調整的合併邊緣拓朴（硬體負載平衡）圖所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="20aa8-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="20aa8-109">請注意，只有 Lync 用戶端的自動設定需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="20aa8-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="20aa8-110">如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="20aa8-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="20aa8-111">重要： Edge 伺服器網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="20aa8-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="20aa8-112">若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="20aa8-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="20aa8-113">例如，如在 Lync Server 2013 中以縮放的合併邊緣案例中所示，在[使用硬體負載平衡器調整合並邊緣](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)的情況圖中，預設閘道會指向外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="20aa8-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="20aa8-114">您可以在每個邊緣伺服器中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20aa8-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="20aa8-115">**網路介面卡1（內部介面）**</span><span class="sxs-lookup"><span data-stu-id="20aa8-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="20aa8-116">已指派172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="20aa8-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="20aa8-117">沒有預設閘道。</span><span class="sxs-lookup"><span data-stu-id="20aa8-117">No default gateway.</span></span>
    
    <span data-ttu-id="20aa8-118">請確定有來自網路的路由，包含 Edge 伺服器內部介面至任何包含 Lync Server 用戶端或執行 Lync Server 之伺服器的網路（例如從172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="20aa8-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="20aa8-119">**網路介面卡2（外部介面）**</span><span class="sxs-lookup"><span data-stu-id="20aa8-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="20aa8-120">系統會將三個公用 IP 位址指派給這個網路介面卡，例如 131.107.155.10 [存取邊緣服務]，131.107.155.20 [網路會議 Edge 服務]，131.107.155.30 提供 A/V 邊緣服務。</span><span class="sxs-lookup"><span data-stu-id="20aa8-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="20aa8-121">指派給 Edge 伺服器實際外部網路介面的 IP 位址，可能會視您選擇的硬體負載平衡器而定。</span><span class="sxs-lookup"><span data-stu-id="20aa8-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="20aa8-122">請參閱硬體負載平衡器的相關檔，瞭解實際的 IP 位址需求。</span><span class="sxs-lookup"><span data-stu-id="20aa8-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="20aa8-123">如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="20aa8-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="20aa8-124">雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="20aa8-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="20aa8-125">預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。</span><span class="sxs-lookup"><span data-stu-id="20aa8-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="20aa8-126">將埠值變更為（例如） [存取邊緣] 服務的 [5061/TCP]、[網路會議邊緣] 服務的 [444/tcp] 和 [A/V 邊緣] 服務的 443/TCP，可能會導致遠端使用者發生問題，而這些使用者的防火牆不允許使用 5061/TCP 和 444/TCP 的流量。</span><span class="sxs-lookup"><span data-stu-id="20aa8-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="20aa8-127">此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="20aa8-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="20aa8-128">[存取邊緣服務 IP 位址] 是主要的，預設閘道設定為 [面向網際網路的路由器] （131.107.155.1）。</span><span class="sxs-lookup"><span data-stu-id="20aa8-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="20aa8-129">Web 會議 Edge 服務和 A/V 邊緣服務 IP 位址是副。</span><span class="sxs-lookup"><span data-stu-id="20aa8-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="20aa8-130">將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="20aa8-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="20aa8-131">另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。</span><span class="sxs-lookup"><span data-stu-id="20aa8-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="20aa8-132">此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料</span><span class="sxs-lookup"><span data-stu-id="20aa8-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="20aa8-133">已調整的合併邊緣所需的 DNS 記錄，以及硬體負載平衡（範例）</span><span class="sxs-lookup"><span data-stu-id="20aa8-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20aa8-134">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="20aa8-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="20aa8-135">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="20aa8-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="20aa8-136">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="20aa8-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="20aa8-137">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="20aa8-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20aa8-138">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="20aa8-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="20aa8-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20aa8-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="20aa8-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="20aa8-141">Access Edge 服務外部介面（Contoso）。</span><span class="sxs-lookup"><span data-stu-id="20aa8-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="20aa8-142">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="20aa8-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20aa8-143">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="20aa8-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="20aa8-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20aa8-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="20aa8-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="20aa8-146">網路會議 Edge 服務外部介面</span><span class="sxs-lookup"><span data-stu-id="20aa8-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20aa8-147">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="20aa8-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="20aa8-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20aa8-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="20aa8-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="20aa8-150">A/V 邊緣服務外部介面</span><span class="sxs-lookup"><span data-stu-id="20aa8-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20aa8-151">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="20aa8-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="20aa8-152">_sip. _tls. .com</span><span class="sxs-lookup"><span data-stu-id="20aa8-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20aa8-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-154">Access Edge 服務外部介面。</span><span class="sxs-lookup"><span data-stu-id="20aa8-154">Access Edge service external interface.</span></span> <span data-ttu-id="20aa8-155">需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。</span><span class="sxs-lookup"><span data-stu-id="20aa8-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="20aa8-156">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="20aa8-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20aa8-157">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="20aa8-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="20aa8-158">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="20aa8-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20aa8-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20aa8-160">SIP 存取邊緣服務外部介面需要聯盟夥伴的自動 DNS 探索（稱為「允許 SIP 網域」（在舊版發行中稱為「已允許 SIP 網域」）。</span><span class="sxs-lookup"><span data-stu-id="20aa8-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="20aa8-161">在已啟用 Lync 功能的使用者以及使用推播通知服務或 Apple 推播通知服務的 Microsoft Lync 行動用戶端的情況下，對所有 SIP 網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="20aa8-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20aa8-162">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="20aa8-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="20aa8-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="20aa8-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="20aa8-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="20aa8-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="20aa8-165">整合的邊緣內部介面</span><span class="sxs-lookup"><span data-stu-id="20aa8-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

