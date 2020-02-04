---
title: DNS 摘要 - 單一合併 Edge (利用公用 IP 位址)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3578bc7b1668bf8cb2268ed079e558e1cf1761
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="c4a5b-102">Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (利用公用 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="c4a5b-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4a5b-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="c4a5b-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="c4a5b-104">對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="c4a5b-105">此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="c4a5b-106">如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="c4a5b-107">如需有關執行 Lync 2013 之用戶端的自動設定的詳細資料（如果未設定 split 大腦 DNS），請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分裂</span><span class="sxs-lookup"><span data-stu-id="c4a5b-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="c4a5b-108">下表包含支援單一合併邊緣拓朴圖中所顯示之單一整合邊緣拓朴所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="c4a5b-109">請注意，只有 Lync 2013 和 Lync 2010 用戶端自動進行設定時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="c4a5b-110">如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的自動設定記錄。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="c4a5b-111">重要： Edge 伺服器網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="c4a5b-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="c4a5b-112">若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="c4a5b-113">例如，如單一整合邊緣拓朴中的公用 IP 位址圖所示，使用[Lync Server 2013 中的公用 ip 位址](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)，預設閘道會指向網際網路周邊或可提供公用 ip 位址的防火牆中的外部路由器。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="c4a5b-114">Edge 伺服器介面的網路關聯是路由關聯，而不是 NAT 關聯。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="c4a5b-115">您可以在 Edge 伺服器中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4a5b-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="c4a5b-116">**網路介面卡1（內部介面）**</span><span class="sxs-lookup"><span data-stu-id="c4a5b-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="c4a5b-117">已指派172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="c4a5b-118">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="c4a5b-119">請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="c4a5b-120">**網路介面卡2（外部介面）**</span><span class="sxs-lookup"><span data-stu-id="c4a5b-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="c4a5b-121">系統會將三個公用 IP 位址指派給這個網路介面卡，例如131.107.155.10 存取邊緣、131.107.155.20 網頁會議邊緣，以及 AV 邊緣的131.107.155.30。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="c4a5b-122">如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="c4a5b-123">雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="c4a5b-124">預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="c4a5b-125">若要將埠值變更為（例如）存取邊緣的 5061/TCP，對於網路會議邊緣的 444/tcp，以及 AV 邊緣的 443/TCP，可能會導致遠端使用者發生問題，使得其背後的防火牆無法透過 5061/TCP 與 444/TCP 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="c4a5b-126">此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="c4a5b-127">[存取邊緣公用 IP 位址] 是主要的，且 [預設閘道] 已設定為公用路由器（131.107.155.1）。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="c4a5b-128">[Web 會議] 和 [A/V 邊緣公用 IP 位址] 是在 Windows **Server 中的 [** **網際網路通訊協定版本4（tcp/IPv4）** ] 和 [ **internet 通訊協定版本6（tcp/IPv6）** ] 屬性的 [**高級**] 區段中的其他 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="c4a5b-129">將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="c4a5b-130">另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="c4a5b-131">此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料</span><span class="sxs-lookup"><span data-stu-id="c4a5b-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="c4a5b-132">使用公用 IP 位址的單一合併邊緣所需的 DNS 記錄（範例）</span><span class="sxs-lookup"><span data-stu-id="c4a5b-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a5b-133">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="c4a5b-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c4a5b-134">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="c4a5b-135">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="c4a5b-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="c4a5b-136">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="c4a5b-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a5b-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c4a5b-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="c4a5b-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-140">在已啟用 Lync 功能的使用者的情況中，對於所有 SIP 網域，都必須重複使用 [存取邊緣外部介面]</span><span class="sxs-lookup"><span data-stu-id="c4a5b-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a5b-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c4a5b-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="c4a5b-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-144">網路會議 Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="c4a5b-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a5b-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c4a5b-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="c4a5b-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-148">A/V 邊緣外部介面</span><span class="sxs-lookup"><span data-stu-id="c4a5b-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a5b-149">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="c4a5b-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-150">_sip. _tls. .com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-152">[存取邊緣外部介面]。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-152">Access Edge external interface.</span></span> <span data-ttu-id="c4a5b-153">需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="c4a5b-154">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4a5b-155">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="c4a5b-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-156">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-158">需要 SIP 存取邊緣外部介面，才能自動 DNS 發現聯盟夥伴（稱為「允許 SIP 網域」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="c4a5b-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a5b-159">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c4a5b-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4a5b-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="c4a5b-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-162">整合的邊緣內部介面</span><span class="sxs-lookup"><span data-stu-id="c4a5b-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="c4a5b-163">如上表所列的記錄會以<EM>.net</EM>副檔名或<EM>.com</EM>副檔名顯示，以強調您不使用分割大腦 DNS 時所需駐留的區域。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="c4a5b-164">如果您使用的是分割大腦 DNS，所有記錄都將位於同一個區域中，唯一的區別就是它們是否在內部或外部版本中。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="c4a5b-165">如需詳細資訊，請參閱<A href="lync-server-2013-determine-dns-requirements.md">決定 Lync Server 2013 的 DNS 需求</A>中的「分割大腦 DNS」。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="c4a5b-166">同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a5b-167">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="c4a5b-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c4a5b-168">稱</span><span class="sxs-lookup"><span data-stu-id="c4a5b-168">FQDN</span></span></th>
<th><span data-ttu-id="c4a5b-169">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="c4a5b-170">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="c4a5b-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a5b-171">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="c4a5b-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-172">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-174">SIP 存取邊緣外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="c4a5b-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="c4a5b-175">行動與推播通知結算所需要這個 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c4a5b-176">可擴展訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="c4a5b-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4a5b-177">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="c4a5b-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c4a5b-178">稱</span><span class="sxs-lookup"><span data-stu-id="c4a5b-178">FQDN</span></span></th>
<th><span data-ttu-id="c4a5b-179">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="c4a5b-180">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="c4a5b-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4a5b-181">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="c4a5b-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-182">_xmpp-_tcp. .com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4a5b-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-184">XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="c4a5b-185">您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="c4a5b-186">如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</span><span class="sxs-lookup"><span data-stu-id="c4a5b-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4a5b-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c4a5b-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-188">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="c4a5b-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-189">Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="c4a5b-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="c4a5b-190">指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="c4a5b-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="c4a5b-191">通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="c4a5b-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

