---
title: Lync Server 2013： DNS 摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532120"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="2aa69-102">Lync Server 2013 中的 DNS 摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="2aa69-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa69-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2aa69-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2aa69-104">對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。</span><span class="sxs-lookup"><span data-stu-id="2aa69-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="2aa69-105">此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="2aa69-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="2aa69-106">如需 Lync 2013 DNS 需求的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2aa69-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="2aa69-107">如需設定如何設定 Lync 2013 用戶端自動設定的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「自動設定沒有分割的大腦 dns」一節。</span><span class="sxs-lookup"><span data-stu-id="2aa69-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="2aa69-108">下表包含用以支援單一合併 Edge 拓撲 (如單一合併 Edge 拓撲圖表中所示) 所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="2aa69-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="2aa69-109">請注意，只有在自動設定 Lync 2013 用戶端時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="2aa69-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="2aa69-110">如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="2aa69-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="2aa69-111">重要： Edge Server 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="2aa69-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="2aa69-112">若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="2aa69-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="2aa69-113">例如，如調整式合併 edge 案例中的調整式合併 Edge 案例中所示，在 [Lync Server 2013 中使用 NAT 透過私人 IP 位址進行 DNS 負載平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)，預設閘道會指向外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="2aa69-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="2aa69-114">您可以在每部 Edge Server 中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2aa69-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="2aa69-115">**網路介面卡 1 - 節點 1 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="2aa69-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="2aa69-116">已指派 172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="2aa69-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="2aa69-117">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="2aa69-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="2aa69-118">確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="2aa69-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2aa69-119">**網路介面卡 1 - 節點 2 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="2aa69-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="2aa69-120">已指派 172.25.33.11 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="2aa69-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="2aa69-121">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="2aa69-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="2aa69-122">確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="2aa69-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2aa69-123">**網路介面卡 2 - 節點 1 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="2aa69-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="2aa69-124">已指派三個私人 IP 位址給此網路介面卡，例如 10.45.16.10 用於 Access Edge、10.45.16.20 用於 Web Conferencing Edge、10.45.16.30 用於 AV Edge。</span><span class="sxs-lookup"><span data-stu-id="2aa69-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2aa69-p104">將單一 IP 位址用於所有三個 Edge 服務介面是可行的，但不建議這麼做。雖然這樣會儲存 IP 位址，但每個服務需要不同的連接埠號碼。預設連接埠號碼為 443/TCP，可確保大部分遠端防火牆都允許該流量。將連接埠值變更為 (例如) 5061/TCP (用於 Access Edge)、444/TCP (用於 Web Conferencing Edge) 及 443/TCP (用於 AV Edge)，可能會導致遠端使用者發生問題，保護他們的防火牆不允許透過 5061/TCP 及 444/TCP 傳輸的流量。此外，由於可以在 IP 位址上進行篩選，因此三個不同的 IP 位址會讓疑難排解較為容易。</span><span class="sxs-lookup"><span data-stu-id="2aa69-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="2aa69-130">Access Edge 公用 IP 位址為主要位址，其預設閘道設為整合式路由器 (10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="2aa69-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="2aa69-131">Web Conferencing 和 A/V Edge 私人 IP 位址是 Windows Server 的 [本機區域連線內容]\*\*\*\* 之 [網際網路通訊協定第 4 版 (TCP/IPv4)]\*\*\*\* 和 [網際網路通訊協定第 6 版 (TCP/IPv6)]\*\*\*\* 內容之 [進階]\*\*\*\* 區段中的其他 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2aa69-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="2aa69-132">**網路介面卡 2 - 節點 2 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="2aa69-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="2aa69-133">已指派三個私人 IP 位址給此網路介面卡，例如 10.45.16.11 用於 Access Edge、10.45.16.21 用於 Web Conferencing Edge、10.45.16.31 用於 AV Edge。</span><span class="sxs-lookup"><span data-stu-id="2aa69-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="2aa69-134">Access Edge 公用 IP 位址為主要位址，其預設閘道設為整合式路由器 (10.45.16.1)。</span><span class="sxs-lookup"><span data-stu-id="2aa69-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="2aa69-135">Web Conferencing 和 A/V Edge 私人 IP 位址是 Windows Server 的 [本機區域連線內容]\*\*\*\* 之 [網際網路通訊協定第 4 版 (TCP/IPv4)]\*\*\*\* 和 [網際網路通訊協定第 6 版 (TCP/IPv6)]\*\*\*\* 內容之 [進階]\*\*\*\* 區段中的其他 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2aa69-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2aa69-136">設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。</span><span class="sxs-lookup"><span data-stu-id="2aa69-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="2aa69-137">另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="2aa69-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="2aa69-138">此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。</span><span class="sxs-lookup"><span data-stu-id="2aa69-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="2aa69-139">經過調整再合併的 Edge 所需之 DNS 記錄，DNS 使用 NAT 與私人 IP 位址進行負載平衡 (範例)</span><span class="sxs-lookup"><span data-stu-id="2aa69-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aa69-140">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="2aa69-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2aa69-141">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="2aa69-142">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="2aa69-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="2aa69-143">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="2aa69-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-146">131.107.155.10 及 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="2aa69-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="2aa69-147">針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複 Access Edge 外部介面 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="2aa69-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa69-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-150">131.107.155.20 及 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="2aa69-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="2aa69-151">Web Conferencing Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="2aa69-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-154">131.107.155.30 及 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="2aa69-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="2aa69-155">A/V Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="2aa69-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa69-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="2aa69-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="2aa69-157">_sip _sip._tls .com</span><span class="sxs-lookup"><span data-stu-id="2aa69-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-159">Access Edge 外部介面。</span><span class="sxs-lookup"><span data-stu-id="2aa69-159">Access Edge external interface.</span></span> <span data-ttu-id="2aa69-160">自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。</span><span class="sxs-lookup"><span data-stu-id="2aa69-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="2aa69-161">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="2aa69-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="2aa69-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="2aa69-163">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="2aa69-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-p107">SIP Access Edge 外部介面。DNS 自動探索同盟協力廠商 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 所需。請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="2aa69-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa69-168">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2aa69-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2aa69-170">172.25.33.10 及 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="2aa69-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="2aa69-171">合併的 Edge 內部介面</span><span class="sxs-lookup"><span data-stu-id="2aa69-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="2aa69-172">進行同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aa69-173">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="2aa69-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2aa69-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="2aa69-174">FQDN</span></span></th>
<th><span data-ttu-id="2aa69-175">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="2aa69-176">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="2aa69-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-177">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="2aa69-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="2aa69-178">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="2aa69-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-180">SIP Access Edge 外部介面。DNS 自動探索同盟至其他潛在同盟協力廠商 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 所需。請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="2aa69-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2aa69-181">行動性及推播通知結算所需要此 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="2aa69-182">DNS 摘要 - Public Instant Messaging Connectivity</span><span class="sxs-lookup"><span data-stu-id="2aa69-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aa69-183">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="2aa69-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2aa69-184">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="2aa69-185">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="2aa69-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="2aa69-186">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="2aa69-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-189">Access Edge service 介面</span><span class="sxs-lookup"><span data-stu-id="2aa69-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="2aa69-190">針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複 Access Edge 外部介面 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="2aa69-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="2aa69-191">可延伸訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="2aa69-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aa69-192">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="2aa69-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2aa69-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="2aa69-193">FQDN</span></span></th>
<th><span data-ttu-id="2aa69-194">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="2aa69-195">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="2aa69-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa69-196">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="2aa69-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="2aa69-197">_xmpp-server._tcp .com</span><span class="sxs-lookup"><span data-stu-id="2aa69-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2aa69-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2aa69-199">Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="2aa69-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="2aa69-200">您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="2aa69-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="2aa69-201">如需其他詳細資料，請參閱另 <strong>請</strong> 參閱主題</span><span class="sxs-lookup"><span data-stu-id="2aa69-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa69-202">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="2aa69-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2aa69-203">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="2aa69-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="2aa69-204">Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2aa69-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="2aa69-205">指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="2aa69-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="2aa69-206">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="2aa69-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

