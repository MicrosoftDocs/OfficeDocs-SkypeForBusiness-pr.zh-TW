---
title: Lync Server 2013： DNS 摘要-調整式合併 edge （利用公用 IP 位址進行 DNS 負載平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaa466792de1adcd3d048c946c7b36803fbaab63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501300"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="01020-102">Lync Server 2013 中的 DNS 摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="01020-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01020-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="01020-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="01020-104">對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。</span><span class="sxs-lookup"><span data-stu-id="01020-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="01020-105">此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="01020-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="01020-106">如需 Lync 2013 DNS 需求的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01020-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="01020-107">如需設定如何設定 Lync 2013 用戶端自動設定的詳細資訊，請參閱 [決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「自動設定沒有分割的大腦 dns」一節。</span><span class="sxs-lookup"><span data-stu-id="01020-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="01020-108">下表包含用以支援單一合併 Edge 拓撲 (如單一合併 Edge 拓撲圖表中所示) 所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="01020-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="01020-109">請注意，只有在自動設定 Lync 2013 用戶端時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="01020-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="01020-110">如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="01020-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="01020-111">重要： Edge Server 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="01020-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="01020-112">若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="01020-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="01020-113">例如，如調整式合併 edge 案例中的調整式合併 Edge 案例中所示，在 [Lync Server 2013 中使用公用 IP 位址進行 DNS 負載平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) ，預設閘道會指向外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="01020-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="01020-114">您可以在每部 Edge Server 中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01020-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="01020-115">**網路介面卡 1 - 節點 1 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="01020-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="01020-116">已指派 172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="01020-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="01020-117">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="01020-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="01020-118">確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="01020-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="01020-119">**網路介面卡 1 - 節點 2 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="01020-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="01020-120">已指派 172.25.33.11 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="01020-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="01020-121">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="01020-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="01020-122">確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="01020-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="01020-123">**網路介面卡 2 - 節點 1 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="01020-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="01020-124">三個私人 IP 位址會指派給此網路介面卡，例如131.107.155.10 用於 Access Edge service、131.107.155.20 for Web 會議 Edge service、131.107.155.30 for A/V Edge service。</span><span class="sxs-lookup"><span data-stu-id="01020-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="01020-125">Access Edge service 公用 IP 位址為主要位址，且其預設閘道設定為公用路由器 (131.107.155.1) 。</span><span class="sxs-lookup"><span data-stu-id="01020-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="01020-126">Web 會議 Edge service 和 A/V Edge service 私人 IP 位址是在 [**網際網路通訊協定第4版**的屬性] 的 [**高級**] 區段中的其他 IP 位址 (TCP/IPv4) 及**網際網路通訊協定第6版** (TCP/IPv6 Windows Server 中的**局域連線屬性**。</span><span class="sxs-lookup"><span data-stu-id="01020-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="01020-127">將單一 IP 位址用於所有三個 Edge 服務介面是可行的，但不建議這麼做。</span><span class="sxs-lookup"><span data-stu-id="01020-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="01020-128">雖然這樣會儲存 IP 位址，但每個服務需要不同的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="01020-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="01020-129">預設連接埠號碼為 443/TCP，可確保大部分遠端防火牆都允許該流量。</span><span class="sxs-lookup"><span data-stu-id="01020-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="01020-130">將埠值變更為 (例如，Access Edge service 的) 5061/tcp; A/V Edge service 的 Web 會議 Edge service 和443/TCP 的 444/TCP）可能會為遠端使用者造成問題，但這些使用者在其背後的防火牆不允許流量超過 5061/TCP 和 444/TCP。</span><span class="sxs-lookup"><span data-stu-id="01020-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="01020-131">此外，由於可以在 IP 位址上進行篩選，因此三個不同的 IP 位址會讓疑難排解較為容易。</span><span class="sxs-lookup"><span data-stu-id="01020-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="01020-132">**網路介面卡 2 - 節點 2 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="01020-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="01020-133">三個私人 IP 位址會指派給此網路介面卡，例如131.107.155.11 用於 Access Edge service、131.107.155.21 for Web 會議 Edge service、131.107.155.31 for A/V Edge service。</span><span class="sxs-lookup"><span data-stu-id="01020-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="01020-134">Access Edge service 公用 IP 位址為主要位址，且其預設閘道設定為公用路由器 (131.107.155.1) 。</span><span class="sxs-lookup"><span data-stu-id="01020-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="01020-135">Web 會議 Edge service 和 A/V Edge service 私人 IP 位址是在 [**網際網路通訊協定第4版**的屬性] 的 [**高級**] 區段中的其他 IP 位址 (TCP/IPv4) 及**網際網路通訊協定第6版** (TCP/IPv6 Windows Server 中的**局域連線屬性**。</span><span class="sxs-lookup"><span data-stu-id="01020-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="01020-136">設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。</span><span class="sxs-lookup"><span data-stu-id="01020-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="01020-137">另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="01020-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="01020-138">此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。</span><span class="sxs-lookup"><span data-stu-id="01020-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="01020-139">調整式合併 Edge （透過公用 IP 位址進行 DNS 負載平衡）所需的 DNS 記錄 (範例) </span><span class="sxs-lookup"><span data-stu-id="01020-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01020-140">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="01020-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01020-141">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="01020-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="01020-142">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="01020-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="01020-143">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="01020-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01020-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01020-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01020-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-146">131.107.155.10 及 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="01020-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="01020-147">Access Edge service 外部介面 (Contoso) 針對所有具有 Lync 啟用使用者的 SIP 網域，依需要重複</span><span class="sxs-lookup"><span data-stu-id="01020-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01020-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01020-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01020-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-150">131.107.155.20 及 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="01020-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="01020-151">Web 會議 Edge service 外部介面</span><span class="sxs-lookup"><span data-stu-id="01020-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01020-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01020-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01020-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-154">131.107.155.30 及 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="01020-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="01020-155">A/V Edge service 外部介面</span><span class="sxs-lookup"><span data-stu-id="01020-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01020-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="01020-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="01020-157">_sip _sip._tls .com</span><span class="sxs-lookup"><span data-stu-id="01020-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-159">Access Edge service 外部介面。</span><span class="sxs-lookup"><span data-stu-id="01020-159">Access Edge service external interface.</span></span> <span data-ttu-id="01020-160">自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。</span><span class="sxs-lookup"><span data-stu-id="01020-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="01020-161">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="01020-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01020-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="01020-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="01020-163">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="01020-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-165">「Access Edge service」的自動 DNS 探索（稱為「允許的 SIP 網域」）所需的外部介面，稱為「允許的 SIP 網域」 (稱為「增強型同盟」) 。</span><span class="sxs-lookup"><span data-stu-id="01020-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="01020-166">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="01020-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01020-167">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01020-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01020-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="01020-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="01020-169">172.25.33.10 及 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="01020-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="01020-170">合併的 Edge 內部介面</span><span class="sxs-lookup"><span data-stu-id="01020-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="01020-171">進行同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="01020-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01020-172">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="01020-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01020-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="01020-173">FQDN</span></span></th>
<th><span data-ttu-id="01020-174">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="01020-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01020-175">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="01020-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01020-176">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="01020-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="01020-177">_sipfederationtls _sipfederationtls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="01020-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-179">SIP Access Edge service 外部介面，可自動將同盟的 DNS 探索至其他潛在同盟協力廠商，也稱為「允許的 SIP 網域」 (在舊版版本) 中稱為「增強型同盟」。</span><span class="sxs-lookup"><span data-stu-id="01020-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="01020-180">針對具有啟用 Lync 功能之使用者的所有 SIP 網域和使用推播通知服務或 Apple Push Notification 服務的 Microsoft Lync 行動用戶端，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="01020-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="01020-181">可延伸訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="01020-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01020-182">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="01020-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01020-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="01020-183">FQDN</span></span></th>
<th><span data-ttu-id="01020-184">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="01020-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01020-185">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="01020-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01020-186">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="01020-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="01020-187">_xmpp-server._tcp .com</span><span class="sxs-lookup"><span data-stu-id="01020-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01020-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01020-189">Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="01020-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="01020-190">您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="01020-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="01020-191">如需其他詳細資料，請參閱另 <strong>請</strong> 參閱主題</span><span class="sxs-lookup"><span data-stu-id="01020-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01020-192">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01020-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01020-193">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="01020-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="01020-194">Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="01020-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="01020-195">指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="01020-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="01020-196">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="01020-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

