---
title: Lync Server 2013：前端集區的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="7b736-102">Lync Server 2013 中前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="7b736-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b736-103">_**主題上次修改日期：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="7b736-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="7b736-104">若要成功完成此程式，您必須以網域管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="7b736-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="7b736-105">您必須先設定必要的網域名稱系統（DNS）記錄，才能在拓撲建立程式中發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="7b736-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="7b736-106">此外，Lync Server 2013 部署的設定中所用的一些完整功能變數名稱（Fqdn）是邏輯和非物理伺服器 Fqdn，因此在發佈之前，必須先進行額外的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="7b736-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7b736-107">Lync Server 2013 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="7b736-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="7b736-108">例如，支援名為<STRONG>contoso. local</STRONG>的根網域的林，但不支援名為<STRONG>local</STRONG>的根網域。</span><span class="sxs-lookup"><span data-stu-id="7b736-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="7b736-109">如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「使用單標籤 DNS 名稱設定 Windows 網域的相關資訊，"at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>。</span><span class="sxs-lookup"><span data-stu-id="7b736-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7b736-110">您指定的名稱必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="7b736-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="7b736-111">根據預設，未加入網域之電腦的電腦名稱稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b736-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7b736-112">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="7b736-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7b736-113">在指派執行 Lync Server、Edge 伺服器和池的伺服器 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。</span><span class="sxs-lookup"><span data-stu-id="7b736-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="7b736-114">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="7b736-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="7b736-115">外部 DNS 和公用憑證授權單位（Ca）通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。</span><span class="sxs-lookup"><span data-stu-id="7b736-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="7b736-116">在部署之後，在執行拓撲之後，請確定已建立下列 Active Directory 和 DNS 記錄（如您對特定功能的需求）：</span><span class="sxs-lookup"><span data-stu-id="7b736-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="7b736-117">將存在於拓撲中的每個伺服器角色，都會發佈為 Active Directory 物件（將電腦加入網域即可完成此作業）。</span><span class="sxs-lookup"><span data-stu-id="7b736-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="7b736-118">每個伺服器都有一個 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="7b736-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="7b736-119">如果您打算針對\_sipinternaltls\_tcp 形式的用戶端使用自動登入，則每個 SIP 網域都存在 DNS SRV 記錄。\<SIP 網域\>。</span><span class="sxs-lookup"><span data-stu-id="7b736-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="7b736-120">如果您將使用手動設定用戶端，則不需要此記錄。</span><span class="sxs-lookup"><span data-stu-id="7b736-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="7b736-121">針對每個已設定的簡單 URL 的 DNS A 記錄，其中通常有四個： [開會]、[撥入]、[lwa] 和 [排程]。</span><span class="sxs-lookup"><span data-stu-id="7b736-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="7b736-122">此外，系統管理員簡單的 URL 是使用 Lync Server 2013 [控制台] 的特殊 URL。</span><span class="sxs-lookup"><span data-stu-id="7b736-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="7b736-123">運行 SQL Server 的伺服器必須加入網域，並可由拓撲建立程式發佈的電腦來使用。</span><span class="sxs-lookup"><span data-stu-id="7b736-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="7b736-124">下表會遵循 [規劃] 區段中所提供的參考體系結構。</span><span class="sxs-lookup"><span data-stu-id="7b736-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="7b736-125">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7b736-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="7b736-126">前端池所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="7b736-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b736-127">位置</span><span class="sxs-lookup"><span data-stu-id="7b736-127">Location</span></span></th>
<th><span data-ttu-id="7b736-128">類型</span><span class="sxs-lookup"><span data-stu-id="7b736-128">Type</span></span></th>
<th><span data-ttu-id="7b736-129">稱</span><span class="sxs-lookup"><span data-stu-id="7b736-129">FQDN</span></span></th>
<th><span data-ttu-id="7b736-130">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="7b736-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b736-131">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-132">A</span><span class="sxs-lookup"><span data-stu-id="7b736-132">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b736-134">Pool01 （DNS 負載平衡）。</span><span class="sxs-lookup"><span data-stu-id="7b736-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="7b736-135">需要一個 DNS A 記錄，以取得池中每個前端伺服器的 IP 位址，並對應到 [池 FQDN]。</span><span class="sxs-lookup"><span data-stu-id="7b736-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-136">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-137">A</span><span class="sxs-lookup"><span data-stu-id="7b736-137">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b736-139">Pool01 （硬體負載平衡器的虛擬 IP （VIP））。</span><span class="sxs-lookup"><span data-stu-id="7b736-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-140">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-141">A</span><span class="sxs-lookup"><span data-stu-id="7b736-141">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="7b736-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="7b736-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="7b736-145">…</span><span class="sxs-lookup"><span data-stu-id="7b736-145"></span></span></p></td>
<td><p><span data-ttu-id="7b736-146">Pool01 前端伺服器（節點1）。</span><span class="sxs-lookup"><span data-stu-id="7b736-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="7b736-147">Pool01 前端伺服器（節點2）。</span><span class="sxs-lookup"><span data-stu-id="7b736-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="7b736-148">Pool01 前端伺服器（節點3）。</span><span class="sxs-lookup"><span data-stu-id="7b736-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="7b736-149">…</span><span class="sxs-lookup"><span data-stu-id="7b736-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-150">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-151">A</span><span class="sxs-lookup"><span data-stu-id="7b736-151">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b736-153">Pool01 前端伺服器（節點2）。</span><span class="sxs-lookup"><span data-stu-id="7b736-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-154">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-155">A</span><span class="sxs-lookup"><span data-stu-id="7b736-155">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b736-157">用戶端到伺服器網站流量的 Pool01 （VIP）。</span><span class="sxs-lookup"><span data-stu-id="7b736-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-158">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-159">A</span><span class="sxs-lookup"><span data-stu-id="7b736-159">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="7b736-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="7b736-161">Pool01 運行 SQL Server 2008 R2 的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="7b736-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-162">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-163">A</span><span class="sxs-lookup"><span data-stu-id="7b736-163">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-165">對於 Lync Phone Edition 是必要的，或自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="7b736-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="7b736-166">在任何情況下都不需要。</span><span class="sxs-lookup"><span data-stu-id="7b736-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-167">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-168">A</span><span class="sxs-lookup"><span data-stu-id="7b736-168">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7b736-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-170">假設第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="7b736-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="7b736-171">Lync Phone Edition 所需、自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="7b736-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="7b736-172">在任何情況下都不需要。</span><span class="sxs-lookup"><span data-stu-id="7b736-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-173">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-174">A</span><span class="sxs-lookup"><span data-stu-id="7b736-174">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-176">在內部發佈的電話撥入式會議（如果已安裝，則為 Director）回應簡單的 URL 查詢的簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="7b736-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-177">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-178">A</span><span class="sxs-lookup"><span data-stu-id="7b736-178">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-180">在內部發佈的會議的簡單 URL-前端伺服器（或已安裝的控制器）會回應簡單的 URL 查詢。</span><span class="sxs-lookup"><span data-stu-id="7b736-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-181">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-182">A</span><span class="sxs-lookup"><span data-stu-id="7b736-182">A</span></span></p></td>
<td><p><span data-ttu-id="7b736-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="7b736-184">管理員</span><span class="sxs-lookup"><span data-stu-id="7b736-184">admin</span></span></p></td>
<td><p><span data-ttu-id="7b736-185">選擇性記錄、Lync Server 2013 [控制台] 的簡單 URL （如果已安裝，則為 [控制器]）回應簡單的 URL 查詢。</span><span class="sxs-lookup"><span data-stu-id="7b736-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="7b736-186">建議僅限主機名稱（無功能變數名稱）。</span><span class="sxs-lookup"><span data-stu-id="7b736-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b736-187">VIP = 硬體載入平衡器的虛擬 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7b736-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="7b736-188">前端池的 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="7b736-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b736-189">位置</span><span class="sxs-lookup"><span data-stu-id="7b736-189">Location</span></span></th>
<th><span data-ttu-id="7b736-190">類型</span><span class="sxs-lookup"><span data-stu-id="7b736-190">Type</span></span></th>
<th><span data-ttu-id="7b736-191">稱</span><span class="sxs-lookup"><span data-stu-id="7b736-191">FQDN</span></span></th>
<th><span data-ttu-id="7b736-192">目標 FQDN</span><span class="sxs-lookup"><span data-stu-id="7b736-192">Target FQDN</span></span></th>
<th><span data-ttu-id="7b736-193">通道</span><span class="sxs-lookup"><span data-stu-id="7b736-193">Port</span></span></th>
<th><span data-ttu-id="7b736-194">地圖/批註</span><span class="sxs-lookup"><span data-stu-id="7b736-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b736-195">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-196">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="7b736-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="7b736-197">_sipinternaltls. _tcp. .com</span><span class="sxs-lookup"><span data-stu-id="7b736-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-199">5061</span><span class="sxs-lookup"><span data-stu-id="7b736-199">5061</span></span></p></td>
<td><p><span data-ttu-id="7b736-200">自動將 Lync 2013 用戶端設定為內部工作所需。</span><span class="sxs-lookup"><span data-stu-id="7b736-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b736-201">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-202">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="7b736-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="7b736-203">_sipinternaltls _tcp .com</span><span class="sxs-lookup"><span data-stu-id="7b736-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7b736-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-205">5061</span><span class="sxs-lookup"><span data-stu-id="7b736-205">5061</span></span></p></td>
<td><p><span data-ttu-id="7b736-206">自動將 Lync 2013 用戶端設定為內部工作所需。</span><span class="sxs-lookup"><span data-stu-id="7b736-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b736-207">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="7b736-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="7b736-208">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="7b736-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="7b736-209">_ntp. _udp. .com</span><span class="sxs-lookup"><span data-stu-id="7b736-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b736-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7b736-211">123</span><span class="sxs-lookup"><span data-stu-id="7b736-211">123</span></span></p></td>
<td><p><span data-ttu-id="7b736-212">運行 Lync Phone Edition 之裝置所需的網路時間協定（NTP）來源。</span><span class="sxs-lookup"><span data-stu-id="7b736-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="7b736-213">在內部，這應該指向網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="7b736-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="7b736-214">如果未定義網網域控制站，則會嘗試使用 NTP 伺服器 time.windows.com。</span><span class="sxs-lookup"><span data-stu-id="7b736-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

