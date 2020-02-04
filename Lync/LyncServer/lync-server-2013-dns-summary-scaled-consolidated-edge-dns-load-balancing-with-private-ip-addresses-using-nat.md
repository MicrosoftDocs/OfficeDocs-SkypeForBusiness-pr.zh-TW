---
title: Lync Server 2013：DNS 摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)
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
ms.openlocfilehash: 6a7836a8d9ce998a8de9185de7aeb12eb088f190
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="1941d-102">Lync Server 2013 中的 DNS 摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="1941d-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1941d-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1941d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1941d-104">對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。</span><span class="sxs-lookup"><span data-stu-id="1941d-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="1941d-105">此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。</span><span class="sxs-lookup"><span data-stu-id="1941d-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="1941d-106">如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1941d-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1941d-107">如需有關設定 Lync 2013 用戶端的自動設定的詳細資料，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分割大腦 dns）一節。</span><span class="sxs-lookup"><span data-stu-id="1941d-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1941d-108">下表包含支援單一合併邊緣拓朴圖中所顯示之單一整合邊緣拓朴所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="1941d-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="1941d-109">請注意，只有在自動設定 Lync 2013 用戶端時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="1941d-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="1941d-110">如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的記錄。</span><span class="sxs-lookup"><span data-stu-id="1941d-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="1941d-111">重要： Edge 伺服器網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="1941d-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="1941d-112">若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="1941d-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="1941d-113">例如，如您在使用 Lync Server 2013 中的縮放的合併邊緣案例中所示[，在 Lync Server 中使用 NAT 進行 DNS 負載平衡](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)，預設閘道會指向外部防火牆。</span><span class="sxs-lookup"><span data-stu-id="1941d-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="1941d-114">您可以在每個邊緣伺服器中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1941d-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="1941d-115">**網路介面卡 1-節點1（內部介面）**</span><span class="sxs-lookup"><span data-stu-id="1941d-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1941d-116">已指派172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="1941d-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="1941d-117">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1941d-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1941d-118">請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="1941d-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1941d-119">**網路介面卡 1-節點2（內部介面）**</span><span class="sxs-lookup"><span data-stu-id="1941d-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1941d-120">已指派172.25.33.11 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="1941d-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="1941d-121">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="1941d-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1941d-122">請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="1941d-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1941d-123">**網路介面卡2節點1（外部介面）**</span><span class="sxs-lookup"><span data-stu-id="1941d-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="1941d-124">系統會將三個私人 IP 位址指派給這個網路介面卡，例如10.45.16.10 存取邊緣、10.45.16.20 網頁會議邊緣，以及 AV 邊緣的10.45.16.30。</span><span class="sxs-lookup"><span data-stu-id="1941d-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1941d-125">如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1941d-125">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="1941d-126">雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="1941d-126">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="1941d-127">預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。</span><span class="sxs-lookup"><span data-stu-id="1941d-127">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="1941d-128">若要將埠值變更為（例如）存取邊緣的 5061/TCP，對於網路會議邊緣的 444/tcp，以及 AV 邊緣的 443/TCP，可能會導致遠端使用者發生問題，使得其背後的防火牆無法透過 5061/TCP 與 444/TCP 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="1941d-128">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="1941d-129">此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1941d-129">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="1941d-130">[存取邊緣公用 IP 位址] 是主要的，且 [預設閘道] 已設定為整合的路由器（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="1941d-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="1941d-131">[Web 會議] 和 [A/V 邊緣私人 IP 位址] 是在 Windows **Server 中的 [** **網際網路通訊協定版本4（tcp/IPv4）** ] 和 [ **internet 通訊協定版本6（tcp/IPv6）** ] 屬性的 [**高級**] 區段中的其他 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1941d-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="1941d-132">**網路介面卡2節點2（外部介面）**</span><span class="sxs-lookup"><span data-stu-id="1941d-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="1941d-133">系統會將三個私人 IP 位址指派給這個網路介面卡，例如10.45.16.11 存取邊緣、10.45.16.21 網頁會議邊緣，以及 AV 邊緣的10.45.16.31。</span><span class="sxs-lookup"><span data-stu-id="1941d-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="1941d-134">[存取邊緣公用 IP 位址] 是主要的，且 [預設閘道] 已設定為整合的路由器（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="1941d-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="1941d-135">[Web 會議] 和 [A/V 邊緣私人 IP 位址] 是在 Windows **Server 中的 [** **網際網路通訊協定版本4（tcp/IPv4）** ] 和 [ **internet 通訊協定版本6（tcp/IPv6）** ] 屬性的 [**高級**] 區段中的其他 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1941d-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1941d-136">將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="1941d-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="1941d-137">另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。</span><span class="sxs-lookup"><span data-stu-id="1941d-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="1941d-138">此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料</span><span class="sxs-lookup"><span data-stu-id="1941d-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="1941d-139">使用 NAT 來調整合並邊緣所需的 DNS 記錄、使用 NAT 的私人 IP 位址進行 DNS 負載平衡（範例）</span><span class="sxs-lookup"><span data-stu-id="1941d-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1941d-140">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="1941d-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1941d-141">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1941d-142">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="1941d-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1941d-143">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="1941d-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1941d-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-146">131.107.155.10 和131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="1941d-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="1941d-147">在已啟用 Lync 功能的使用者的情況中，對於所有 SIP 網域，都必須重複使用 [存取邊緣外部介面]</span><span class="sxs-lookup"><span data-stu-id="1941d-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1941d-148">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-150">131.107.155.20 和131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="1941d-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="1941d-151">網路會議 Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="1941d-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1941d-152">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-154">131.107.155.30 和131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="1941d-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="1941d-155">A/V 邊緣外部介面</span><span class="sxs-lookup"><span data-stu-id="1941d-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1941d-156">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="1941d-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="1941d-157">_sip. _tls. .com</span><span class="sxs-lookup"><span data-stu-id="1941d-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-159">[存取邊緣外部介面]。</span><span class="sxs-lookup"><span data-stu-id="1941d-159">Access Edge external interface.</span></span> <span data-ttu-id="1941d-160">需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。</span><span class="sxs-lookup"><span data-stu-id="1941d-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="1941d-161">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="1941d-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1941d-162">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1941d-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1941d-163">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="1941d-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-165">SIP 存取邊緣外部介面。</span><span class="sxs-lookup"><span data-stu-id="1941d-165">SIP Access Edge external interface.</span></span> <span data-ttu-id="1941d-166">自動 DNS 發現聯盟夥伴的必要（稱為「允許 SIP 網域」（在舊版發行中稱為「增強聯盟」）。</span><span class="sxs-lookup"><span data-stu-id="1941d-166">Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="1941d-167">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="1941d-167">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1941d-168">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1941d-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1941d-170">172.25.33.10 和172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="1941d-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="1941d-171">整合的邊緣內部介面</span><span class="sxs-lookup"><span data-stu-id="1941d-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="1941d-172">同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1941d-173">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="1941d-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1941d-174">稱</span><span class="sxs-lookup"><span data-stu-id="1941d-174">FQDN</span></span></th>
<th><span data-ttu-id="1941d-175">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1941d-176">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="1941d-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1941d-177">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1941d-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1941d-178">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="1941d-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-180">SIP 存取邊緣外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="1941d-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1941d-181">行動與推播通知結算所需要這個 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="1941d-182">DNS 摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="1941d-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1941d-183">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="1941d-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1941d-184">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1941d-185">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="1941d-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1941d-186">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="1941d-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1941d-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-189">存取邊緣服務介面</span><span class="sxs-lookup"><span data-stu-id="1941d-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="1941d-190">在已啟用 Lync 功能的使用者的情況中，對於所有 SIP 網域，都必須重複使用 [存取邊緣外部介面]</span><span class="sxs-lookup"><span data-stu-id="1941d-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1941d-191">可擴展訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="1941d-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1941d-192">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="1941d-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1941d-193">稱</span><span class="sxs-lookup"><span data-stu-id="1941d-193">FQDN</span></span></th>
<th><span data-ttu-id="1941d-194">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1941d-195">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="1941d-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1941d-196">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="1941d-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="1941d-197">_xmpp-_tcp. .com</span><span class="sxs-lookup"><span data-stu-id="1941d-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1941d-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1941d-199">XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="1941d-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="1941d-200">您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="1941d-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="1941d-201">如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</span><span class="sxs-lookup"><span data-stu-id="1941d-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1941d-202">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1941d-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1941d-203">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="1941d-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="1941d-204">Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="1941d-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="1941d-205">指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="1941d-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="1941d-206">通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="1941d-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

