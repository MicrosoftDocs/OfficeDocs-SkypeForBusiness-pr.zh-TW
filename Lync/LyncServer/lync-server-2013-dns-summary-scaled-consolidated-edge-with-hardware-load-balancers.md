---
title: 使用硬體負載平衡器的 DNS 摘要-調整式合併 edge
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
ms.openlocfilehash: f5847a43c6d07cf188c97cd8de6a47dfb83e1468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501280"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="01f7c-102">Lync Server 2013 中的 DNS 摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="01f7c-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f7c-103">_**主題上次修改日期：** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="01f7c-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="01f7c-104">對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。</span><span class="sxs-lookup"><span data-stu-id="01f7c-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="01f7c-105">此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="01f7c-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="01f7c-106">如需 Lync 2013 DNS 需求的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01f7c-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="01f7c-107">如需設定如何設定 Lync 2013 用戶端自動設定的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「自動設定沒有分割的大腦 dns」一節。</span><span class="sxs-lookup"><span data-stu-id="01f7c-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="01f7c-108">下表包含支援調整式合併 Edge 拓撲 (硬體負載平衡) 圖所需之 DNS 記錄的摘要。</span><span class="sxs-lookup"><span data-stu-id="01f7c-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="01f7c-109">請注意，只有 Lync 用戶端的自動設定需要某些 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="01f7c-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="01f7c-110">如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="01f7c-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="01f7c-111">重要： Edge Server 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="01f7c-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="01f7c-112">若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="01f7c-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="01f7c-113">例如，在 [調整式合併 edge 案例] 中，在 [Lync Server 2013 中使用硬體負載平衡器調整](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)式合併 edge 案例中所顯示的預設閘道會指向外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="01f7c-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="01f7c-114">您可以在每一部 Edge Server 中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01f7c-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="01f7c-115">**網路介面卡 1 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="01f7c-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="01f7c-116">已指派 172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="01f7c-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="01f7c-117">無預設閘道。</span><span class="sxs-lookup"><span data-stu-id="01f7c-117">No default gateway.</span></span>
    
    <span data-ttu-id="01f7c-118">請確定有從包含 Edge Server 內部介面的網路到包含 Lync Server 用戶端或執行 Lync Server 之伺服器的任何網路的路由 (例如，從172.25.33.0 到 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="01f7c-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="01f7c-119">**網路介面卡 2 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="01f7c-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="01f7c-120">三個公用 IP 位址會指派給此網路介面卡，例如131.107.155.10 用於 Access Edge service、131.107.155.20 for Web 會議 Edge service、131.107.155.30 for A/V Edge service。</span><span class="sxs-lookup"><span data-stu-id="01f7c-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="01f7c-121">指派給 Edge Server 實際外部網路介面的 IP 位址，可能取決於您所選擇的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="01f7c-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="01f7c-122">請參閱硬體負載平衡器的檔，以瞭解實際的 IP 位址需求。</span><span class="sxs-lookup"><span data-stu-id="01f7c-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="01f7c-123">將單一 IP 位址用於所有三個 Edge 服務介面是可行的，但不建議這麼做。</span><span class="sxs-lookup"><span data-stu-id="01f7c-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="01f7c-124">雖然這樣會儲存 IP 位址，但每個服務需要不同的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="01f7c-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="01f7c-125">預設連接埠號碼為 443/TCP，可確保大部分遠端防火牆都允許該流量。</span><span class="sxs-lookup"><span data-stu-id="01f7c-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="01f7c-126">將埠值變更為 (例如，Access Edge service 的) 5061/tcp; A/V Edge service 的 Web 會議 Edge service 和443/TCP 的 444/TCP）可能會為遠端使用者造成問題，但這些使用者在其背後的防火牆不允許流量超過 5061/TCP 和 444/TCP。</span><span class="sxs-lookup"><span data-stu-id="01f7c-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="01f7c-127">此外，由於可以在 IP 位址上進行篩選，因此三個不同的 IP 位址會讓疑難排解較為容易。</span><span class="sxs-lookup"><span data-stu-id="01f7c-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="01f7c-128">Access Edge service 的 IP 位址為主要位址，且預設閘道設定為網際網路對向路由器 (131.107.155.1) 。</span><span class="sxs-lookup"><span data-stu-id="01f7c-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="01f7c-129">Web 會議 Edge service 和 A/V Edge service IP 位址次要。</span><span class="sxs-lookup"><span data-stu-id="01f7c-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="01f7c-130">設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。</span><span class="sxs-lookup"><span data-stu-id="01f7c-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="01f7c-131">另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="01f7c-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="01f7c-132">此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。</span><span class="sxs-lookup"><span data-stu-id="01f7c-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="01f7c-133">調整式合併 Edge （硬體負載平衡 (範例）所需的 DNS 記錄) </span><span class="sxs-lookup"><span data-stu-id="01f7c-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f7c-134">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="01f7c-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01f7c-135">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="01f7c-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="01f7c-136">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="01f7c-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="01f7c-137">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="01f7c-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f7c-138">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01f7c-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01f7c-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f7c-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="01f7c-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="01f7c-141">Access Edge service 外部介面 (Contoso) 。</span><span class="sxs-lookup"><span data-stu-id="01f7c-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="01f7c-142">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="01f7c-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f7c-143">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01f7c-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01f7c-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f7c-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="01f7c-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="01f7c-146">Web 會議 Edge service 外部介面</span><span class="sxs-lookup"><span data-stu-id="01f7c-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01f7c-147">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01f7c-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01f7c-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f7c-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="01f7c-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="01f7c-150">A/V Edge service 外部介面</span><span class="sxs-lookup"><span data-stu-id="01f7c-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f7c-151">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="01f7c-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="01f7c-152">_sip _sip._tls .com</span><span class="sxs-lookup"><span data-stu-id="01f7c-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f7c-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-154">Access Edge service 外部介面。</span><span class="sxs-lookup"><span data-stu-id="01f7c-154">Access Edge service external interface.</span></span> <span data-ttu-id="01f7c-155">自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。</span><span class="sxs-lookup"><span data-stu-id="01f7c-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="01f7c-156">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="01f7c-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01f7c-157">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="01f7c-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="01f7c-158">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="01f7c-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f7c-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f7c-160">需要 SIP Access Edge service 外部介面，以供同盟協力廠商（稱為「允許的 SIP 網域」）自動探索，但在先前版本) 中稱為「增強型同盟」 (。</span><span class="sxs-lookup"><span data-stu-id="01f7c-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="01f7c-161">針對具有啟用 Lync 功能之使用者的所有 SIP 網域和使用推播通知服務或 Apple Push Notification 服務的 Microsoft Lync 行動用戶端，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="01f7c-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f7c-162">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01f7c-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01f7c-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="01f7c-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="01f7c-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="01f7c-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="01f7c-165">合併 Edge 內部介面</span><span class="sxs-lookup"><span data-stu-id="01f7c-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

