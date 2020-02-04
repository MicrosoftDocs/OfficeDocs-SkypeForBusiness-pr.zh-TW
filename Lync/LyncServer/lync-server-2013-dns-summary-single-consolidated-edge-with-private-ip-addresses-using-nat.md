---
title: DNS 摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3276219fb4c2227cde75cf9a5d3a47616c03336d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="f9aae-102">Lync Server 2013 中的 DNS 摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="f9aae-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9aae-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="f9aae-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="f9aae-104">對 Lync Server 2013 進行遠端存取的 DNS 記錄需求與憑證和埠的遠端存取是相當直接的。</span><span class="sxs-lookup"><span data-stu-id="f9aae-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="f9aae-105">此外，許多記錄都是選擇性的，視您如何設定執行 Lync 2013 的用戶端以及是否啟用同盟而定。</span><span class="sxs-lookup"><span data-stu-id="f9aae-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="f9aae-106">如需有關 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9aae-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f9aae-107">如需有關執行 Lync 2013 之用戶端的自動設定的詳細資料（如果未設定 split 大腦 DNS），請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)（不含分裂</span><span class="sxs-lookup"><span data-stu-id="f9aae-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f9aae-108">下表包含支援單一合併邊緣拓朴圖中所顯示之單一整合邊緣拓朴所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="f9aae-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="f9aae-109">請注意，只有 Lync 2013 和 Lync 2010 用戶端自動進行設定時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="f9aae-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="f9aae-110">如果您打算使用群組原則物件（Gpo）來設定 Lync 用戶端，則不需要相關聯的自動設定記錄。</span><span class="sxs-lookup"><span data-stu-id="f9aae-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="f9aae-111">重要： Edge 伺服器網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="f9aae-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="f9aae-112">若要避免路由問題，請確認 Edge 伺服器中至少有兩個網路介面卡，且 [預設閘道] 只在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="f9aae-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="f9aae-113">例如，如單一整合邊緣拓朴中，在[Lync Server 2013 中有私人 IP 位址和 NAT](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)的單一合併邊緣拓撲圖所示，預設閘道會指向外部防火牆（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="f9aae-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="f9aae-114">您可以在 Edge 伺服器中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9aae-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="f9aae-115">**網路介面卡1（內部介面）**</span><span class="sxs-lookup"><span data-stu-id="f9aae-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="f9aae-116">已指派172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="f9aae-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="f9aae-117">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="f9aae-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="f9aae-118">請確定您的網路有一個路由，其中包含邊緣內部介面到任何網路，包括執行 Lync Server 2013 或 Lync Server 2013 用戶端的伺服器（例如從172.25.33.0 到192.168.10.0）。</span><span class="sxs-lookup"><span data-stu-id="f9aae-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="f9aae-119">**網路介面卡2（外部介面）**</span><span class="sxs-lookup"><span data-stu-id="f9aae-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="f9aae-120">系統會將三個私人 IP 位址指派給這個網路介面卡，例如10.45.16.10 存取邊緣、10.45.16.20 網頁會議邊緣、AV 邊緣10.45.16.30</span><span class="sxs-lookup"><span data-stu-id="f9aae-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f9aae-121">如果不建議這樣做，您可以針對所有三個邊緣服務介面使用單一 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f9aae-121">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="f9aae-122">雖然這會儲存 IP 位址，但是它需要每個服務有不同的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="f9aae-122">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="f9aae-123">預設埠號碼為 443/TCP，可確保大多數的遠端防火牆都能允許流量。</span><span class="sxs-lookup"><span data-stu-id="f9aae-123">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="f9aae-124">若要將埠值變更為（例如）存取邊緣的 5061/TCP，對於網路會議邊緣的 444/tcp，以及 AV 邊緣的 443/TCP，可能會導致遠端使用者發生問題，使得其背後的防火牆無法透過 5061/TCP 與 444/TCP 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f9aae-124">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="f9aae-125">此外，三個不同的 IP 位址可讓疑難排解變得更容易，因為能夠篩選 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f9aae-125">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="f9aae-126">存取邊緣 IP 位址是主要，且預設閘道設定為整合路由器（10.45.16.1）。</span><span class="sxs-lookup"><span data-stu-id="f9aae-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="f9aae-127">[Web 會議] 和 [A/V 邊緣 IP 位址-次要]。</span><span class="sxs-lookup"><span data-stu-id="f9aae-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f9aae-128">將 Edge 伺服器設定成兩個網路介面卡是其中一個選項。</span><span class="sxs-lookup"><span data-stu-id="f9aae-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="f9aae-129">另一個選項是將一個網路介面卡用於內部端，而將三個網路介面卡用於邊緣伺服器的外部端。</span><span class="sxs-lookup"><span data-stu-id="f9aae-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="f9aae-130">此選項的主要優點是每 Edge 伺服器服務有一個獨特的網路介面卡，而且在需要疑難排解時也可能更簡明地收集資料</span><span class="sxs-lookup"><span data-stu-id="f9aae-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="f9aae-131">使用 NAT （範例）使用私人 IP 位址的單一合併邊緣所需的 DNS 記錄（範例）</span><span class="sxs-lookup"><span data-stu-id="f9aae-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9aae-132">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="f9aae-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9aae-133">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f9aae-134">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="f9aae-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f9aae-135">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="f9aae-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9aae-136">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9aae-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9aae-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="f9aae-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="f9aae-139">在已啟用 Lync 功能的使用者的情況中，對於所有 SIP 網域，都必須重複使用 [存取邊緣外部介面]</span><span class="sxs-lookup"><span data-stu-id="f9aae-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aae-140">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9aae-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9aae-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="f9aae-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="f9aae-143">網路會議 Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="f9aae-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9aae-144">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9aae-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9aae-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="f9aae-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="f9aae-147">A/V 邊緣外部介面</span><span class="sxs-lookup"><span data-stu-id="f9aae-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aae-148">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="f9aae-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="f9aae-149">_sip. _tls. .com</span><span class="sxs-lookup"><span data-stu-id="f9aae-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-151">[存取邊緣外部介面]。</span><span class="sxs-lookup"><span data-stu-id="f9aae-151">Access Edge external interface.</span></span> <span data-ttu-id="f9aae-152">需要自動設定 Lync 2013 和 Lync 2010 用戶端才能在外部作業。</span><span class="sxs-lookup"><span data-stu-id="f9aae-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="f9aae-153">在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="f9aae-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9aae-154">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f9aae-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f9aae-155">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="f9aae-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-157">需要 SIP 存取邊緣外部介面，才能自動 DNS 發現聯盟夥伴（稱為「允許 SIP 網域」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="f9aae-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aae-158">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9aae-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9aae-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9aae-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9aae-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="f9aae-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="f9aae-161">整合的邊緣內部介面</span><span class="sxs-lookup"><span data-stu-id="f9aae-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="f9aae-162">如上表所列的記錄會以<EM>.net</EM>副檔名或<EM>.com</EM>副檔名顯示，以強調您不使用分割大腦 DNS 時所需駐留的區域。</span><span class="sxs-lookup"><span data-stu-id="f9aae-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="f9aae-163">如果您使用的是分割大腦 DNS，所有記錄都將位於同一個<EM>.com</EM>區域中，唯一的區別就是它們位於內部或外部 DNS 區域版本中。</span><span class="sxs-lookup"><span data-stu-id="f9aae-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="f9aae-164">如需詳細資訊，請參閱<A href="lync-server-2013-determine-dns-requirements.md">決定 Lync Server 2013 的 DNS 需求</A>中的「分割大腦 DNS」。</span><span class="sxs-lookup"><span data-stu-id="f9aae-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="f9aae-165">同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9aae-166">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="f9aae-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9aae-167">稱</span><span class="sxs-lookup"><span data-stu-id="f9aae-167">FQDN</span></span></th>
<th><span data-ttu-id="f9aae-168">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f9aae-169">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="f9aae-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9aae-170">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f9aae-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f9aae-171">_sipfederationtls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="f9aae-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-173">SIP 存取邊緣外部介面需要將同盟自動 DNS 探索到其他潛在的同盟夥伴，且稱為「允許的 SIP 網域」（在先前的版本中稱為「增強聯盟」）。在已啟用 Lync 功能的使用者的情況中，針對所有 SIP 網域重複上述動作</span><span class="sxs-lookup"><span data-stu-id="f9aae-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f9aae-174">行動與推播通知結算所需要這個 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f9aae-175">可擴展訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="f9aae-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9aae-176">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="f9aae-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9aae-177">稱</span><span class="sxs-lookup"><span data-stu-id="f9aae-177">FQDN</span></span></th>
<th><span data-ttu-id="f9aae-178">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f9aae-179">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="f9aae-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9aae-180">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="f9aae-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="f9aae-181">_xmpp-_tcp. .com</span><span class="sxs-lookup"><span data-stu-id="f9aae-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9aae-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9aae-183">XMPP [存取邊緣服務] 或 [Edge] 池中的 [proxy 外部介面]。在已啟用 Lync 功能的使用者中，針對所有內部 SIP 網域重複上述步驟，可透過全域原則、使用者所處的網站原則，或套用使用者原則來設定外部存取原則。啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9aae-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="f9aae-184">您也必須在 XMPP 聯盟夥伴原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="f9aae-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="f9aae-185">如需其他詳細資料，請參閱另<strong>請</strong>參閱中的主題</span><span class="sxs-lookup"><span data-stu-id="f9aae-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9aae-186">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9aae-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9aae-187">xmpp.contoso.com （例如）</span><span class="sxs-lookup"><span data-stu-id="f9aae-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="f9aae-188">Edge 伺服器或邊緣池託管 XMPP proxy 的存取邊緣服務的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f9aae-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="f9aae-189">指向託管 XMPP proxy 服務的存取邊緣服務或 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="f9aae-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="f9aae-190">通常，您所建立的 SRV 記錄會指向這個主機（A 或 AAAA）記錄</span><span class="sxs-lookup"><span data-stu-id="f9aae-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

