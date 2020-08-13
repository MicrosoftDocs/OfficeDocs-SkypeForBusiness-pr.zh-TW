---
title: DNS 摘要-單一合併 edge （利用公用 IP 位址）
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
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="98529-102">Lync Server 2013 中的 DNS 摘要-單一合併 edge （利用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="98529-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98529-103">_**主題上次修改日期：** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="98529-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="98529-104">對 Lync Server 2013 的遠端存取的 DNS 記錄需求，與憑證及埠的遠端存取非常直接。</span><span class="sxs-lookup"><span data-stu-id="98529-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="98529-105">此外，許多記錄是選用的，取決於如何設定執行 Lync 2013 的用戶端，以及是否啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="98529-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="98529-106">如需 Lync 2013 DNS 需求的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98529-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="98529-107">如需有關執行 Lync 2013 之用戶端自動設定的詳細資訊，請參閱[決定 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)中的「沒有 Split-Brain DNS 的自動設定」。</span><span class="sxs-lookup"><span data-stu-id="98529-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="98529-108">下表包含用以支援單一合併 Edge 拓撲 (如單一合併 Edge 拓撲圖表中所示) 所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="98529-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="98529-109">請注意，只有在自動設定 Lync 2013 和 Lync 2010 用戶端時，才需要特定的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="98529-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="98529-110">如果您打算使用群組原則物件 (Gpo) 設定 Lync 用戶端，則不需要關聯的自動設定記錄。</span><span class="sxs-lookup"><span data-stu-id="98529-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="98529-111">重要： Edge Server 網路介面卡需求</span><span class="sxs-lookup"><span data-stu-id="98529-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="98529-112">若要避免路由問題，請確認 Edge Server 中至少有兩個網路介面卡，且預設閘道只會在與外部介面相關聯的網路介面卡上設定。</span><span class="sxs-lookup"><span data-stu-id="98529-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="98529-113">例如，在[Lync Server 2013 的單一合併](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)edge 拓撲中，如使用公用 ip 位址的單一合併 edge 拓撲，使用公用 ip 位址的單一合併 edge 拓撲，預設閘道會指向您網際網路周邊或防火牆上的外部路由器，可提供公用 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="98529-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="98529-114">Edge Server 介面的網路關聯性是路由關聯，而不是 NAT 關聯。</span><span class="sxs-lookup"><span data-stu-id="98529-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="98529-115">您可以在 Edge Server 中設定兩個網路介面卡，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98529-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="98529-116">**網路介面卡 1 (內部介面)**</span><span class="sxs-lookup"><span data-stu-id="98529-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="98529-117">已指派 172.25.33.10 的內部介面。</span><span class="sxs-lookup"><span data-stu-id="98529-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="98529-118">未定義預設閘道。</span><span class="sxs-lookup"><span data-stu-id="98529-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="98529-119">確定有從包含 Edge 內部介面的網路，路由傳送至任何包含執行 Lync Server 2013 或 Lync Server 2013 用戶端之伺服器的網路 (例如，從172.25.33.0 至 192.168.10.0) 。</span><span class="sxs-lookup"><span data-stu-id="98529-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="98529-120">**網路介面卡 2 (外部介面)**</span><span class="sxs-lookup"><span data-stu-id="98529-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="98529-121">將三個公開 IP 位址指派給這個網路介面卡，例如，131.107.155.10 指派給 Access Edge、131.107.155.20 指派給 Web Conferencing Edge，而 131.107.155.30 指派給 AV Edge。</span><span class="sxs-lookup"><span data-stu-id="98529-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="98529-p104">對於所有三個 Edge 服務介面使用相同的 IP 位址，不過不建議這麼做。雖然這確實能夠節省 IP 位址，不過對於各個服務仍然需要不同的連接埠編號。預設的連接埠編號是 443/TCP，這能夠確保大多數遠端防火牆將允許流量。例如，將連接埠值變更為 5061/TCP (Access Edge)、 444/TCP (Web Conferencing Edge) 和 443/TCP (AV Edge)，可能導致遠端使用者發生問題，以致其使用的防火牆埠不允許透過 5061/TCP 和 444/TCP 的流量。此外，由於能夠篩選 IP 位址，所以三個不同的 IP 位址比較容易進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="98529-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="98529-127">Access Edge 公開 IP 位址為主要位址，且其預設閘道將設為公開路由器 (131.107.155.1)。</span><span class="sxs-lookup"><span data-stu-id="98529-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="98529-128">Web 會議和 A/V Edge 公開 IP 位址是 Windows Server 的**本機區域連線內容**中**網際網路協定第 4 版 (TCP/IPv4)** 和**網際網路通訊協定第 6 版(TCP/IPv6)** 所出現的**進階**區段中額外的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="98529-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="98529-129">設定具有兩個網路介面卡的 Edge Server 是兩個選項之一。</span><span class="sxs-lookup"><span data-stu-id="98529-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="98529-130">另一種方法是針對 Edge Server 的外部端，使用一個網路介面卡作為內部端和三個網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="98529-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="98529-131">此選項的主要優點是，每個 Edge Server 服務都有不同的網路介面卡，而且在進行疑難排解時，可能會有更簡明的資料收集方式。</span><span class="sxs-lookup"><span data-stu-id="98529-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="98529-132">含有公開 IP 位址的單一合併 Edge 所需的 DNS 記錄 (範例)</span><span class="sxs-lookup"><span data-stu-id="98529-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98529-133">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="98529-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="98529-134">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="98529-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="98529-135">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="98529-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="98529-136">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="98529-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98529-137">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="98529-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98529-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="98529-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="98529-140">Access Edge 外部介面 (Contoso) 對於存在 Lync 啟用的使用者在其中的所有 SIP 網路進行必要的重複</span><span class="sxs-lookup"><span data-stu-id="98529-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98529-141">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="98529-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98529-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="98529-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="98529-144">Web Conferencing Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="98529-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98529-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="98529-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98529-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="98529-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="98529-148">A/V Edge 外部介面</span><span class="sxs-lookup"><span data-stu-id="98529-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98529-149">外部 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="98529-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="98529-150">_sip _tls .com</span><span class="sxs-lookup"><span data-stu-id="98529-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-152">Access Edge 外部介面。</span><span class="sxs-lookup"><span data-stu-id="98529-152">Access Edge external interface.</span></span> <span data-ttu-id="98529-153">自動設定 Lync 2013 和 Lync 2010 用戶端時必須執行，以供外部工作。</span><span class="sxs-lookup"><span data-stu-id="98529-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="98529-154">請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="98529-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98529-155">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="98529-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="98529-156">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="98529-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-158">DNS 自動探索同盟合作夥伴 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 需要 SIP Access Edge 外部介面。對於存在 Lync 啟用的使用者在其中的所有 SIP 網路必須重複</span><span class="sxs-lookup"><span data-stu-id="98529-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98529-159">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="98529-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98529-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="98529-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="98529-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="98529-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="98529-162">合併 Edge 內部介面</span><span class="sxs-lookup"><span data-stu-id="98529-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="98529-163">上表所列記錄內含 <EM>.net</EM> 延伸網址或 <EM>.com</EM> 延伸網址，以強調在您未使用 split-brain DNS 時這些項目應該歸屬的區域。</span><span class="sxs-lookup"><span data-stu-id="98529-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="98529-164">如果您使用 split-brain DNS，則所有記錄將位於相同區域，唯一區別在於該記錄的版本 (內部或外部)。</span><span class="sxs-lookup"><span data-stu-id="98529-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="98529-165">如需詳細資訊，請參閱<A href="lync-server-2013-determine-dns-requirements.md">決定 Lync Server 2013 的 dns 需求</A>中的「Split-Brain DNS」。</span><span class="sxs-lookup"><span data-stu-id="98529-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="98529-166">進行同盟所需的記錄</span><span class="sxs-lookup"><span data-stu-id="98529-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98529-167">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="98529-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="98529-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="98529-168">FQDN</span></span></th>
<th><span data-ttu-id="98529-169">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="98529-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="98529-170">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="98529-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98529-171">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="98529-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="98529-172">_sipfederationtls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="98529-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-174">SIP Access Edge 外部介面。DNS 自動探索同盟至其他潛在同盟協力廠商 (亦稱為「允許的 SIP 網域」，先前版本稱為增強型同盟) 所需。請針對具有啟用 Lync 功能之使用者的所有 SIP 網域，依需要重複。</span><span class="sxs-lookup"><span data-stu-id="98529-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="98529-175">行動性及推播通知結算所需要此 SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="98529-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="98529-176">可延伸訊息和目前狀態通訊協定的 DNS 摘要</span><span class="sxs-lookup"><span data-stu-id="98529-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98529-177">位置/類型/埠</span><span class="sxs-lookup"><span data-stu-id="98529-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="98529-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="98529-178">FQDN</span></span></th>
<th><span data-ttu-id="98529-179">IP 位址/FQDN 主機記錄</span><span class="sxs-lookup"><span data-stu-id="98529-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="98529-180">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="98529-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98529-181">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="98529-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="98529-182">_xmpp-_tcp .com</span><span class="sxs-lookup"><span data-stu-id="98529-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98529-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98529-184">Access Edge service 或 Edge 集區上的 XMPP proxy 外部介面。針對所有內部 SIP 網域，針對所有內部 SIP 網域，依需要重複此步驟：透過全域原則、使用者所在的網站原則，或套用到啟用 Lync 功能之使用者的使用者原則，可透過外部存取原則的設定允許與 XMPP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="98529-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="98529-185">您也必須在 XMPP 同盟協力廠商原則中設定允許的 XMPP 網域。</span><span class="sxs-lookup"><span data-stu-id="98529-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="98529-186">如需其他詳細資料，請參閱另<strong>請</strong>參閱主題</span><span class="sxs-lookup"><span data-stu-id="98529-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98529-187">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="98529-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98529-188">xmpp.contoso.com (範例)</span><span class="sxs-lookup"><span data-stu-id="98529-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="98529-189">Edge Server 或 Edge 集區上主控 XMPP proxy 的 Access Edge service 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="98529-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="98529-190">指向主控 XMPP proxy 服務的 Access Edge service 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="98529-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="98529-191">一般而言，您建立的 SRV 記錄會指向此主機 (A 或 AAAA) 記錄</span><span class="sxs-lookup"><span data-stu-id="98529-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

