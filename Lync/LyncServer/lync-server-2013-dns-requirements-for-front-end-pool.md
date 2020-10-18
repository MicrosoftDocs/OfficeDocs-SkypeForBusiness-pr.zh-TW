---
title: Lync Server 2013：前端集區的 DNS 需求
description: Lync Server 2013：前端集區的 DNS 需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574329"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="539ff-103">Lync Server 2013 中前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="539ff-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="539ff-104">_**主題上次修改日期：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="539ff-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="539ff-105">若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="539ff-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="539ff-106">在 [拓撲產生器] 中發佈拓撲之前，您必須先設定必要的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="539ff-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="539ff-107">此外，Lync Server 2013 部署的設定中所用的部分完整功能變數名稱 (Fqdn) 是邏輯和非實體伺服器的 Fqdn，所以在發佈之前必須先進行其他 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="539ff-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="539ff-108">Lync Server 2013 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="539ff-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="539ff-109">例如，根網域名稱為 <STRONG>contoso.local</STRONG> 的樹系是受支援的，名為 <STRONG>local</STRONG> 的根網域則不受支援。</span><span class="sxs-lookup"><span data-stu-id="539ff-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="539ff-110">如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「如何針對具有單一標籤 DNS 名稱的網域設定 Windows」的相關資訊，請參閱<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp 3052&kbid = 300684</A>。</span><span class="sxs-lookup"><span data-stu-id="539ff-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="539ff-111">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="539ff-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="539ff-112">根據預設，未加入網域的電腦，其電腦名稱是簡稱，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="539ff-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="539ff-113">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="539ff-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="539ff-114">在指派執行 Lync Server、Edge server 及集區的伺服器 Fqdn 時，<STRONG>只能使用標準字元</STRONG> (包括 A–Z、-Z、0–9和連字號) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="539ff-115">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="539ff-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="539ff-116">當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用憑證授權單位 (CA) 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="539ff-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="539ff-117">在部署拓撲之後執行拓撲之後，請確定下列 Active Directory 和 DNS 記錄會根據您的特定功能的需求而建立 (。) ：</span><span class="sxs-lookup"><span data-stu-id="539ff-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="539ff-118">將存在於拓撲中的每個伺服器角色都會發佈為 Active Directory 物件 (將電腦加入網域，就能完成此) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="539ff-119">每個伺服器都存在 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="539ff-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="539ff-120">如果您打算對 \_ sipinternaltls tcp 格式的用戶端使用自動登入，則每個 SIP 網域都會存在 DNS SRV 記錄。 \_ \<SIP domain\></span><span class="sxs-lookup"><span data-stu-id="539ff-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="539ff-121">如果您將對用戶端使用手動設定，則不需要此記錄。</span><span class="sxs-lookup"><span data-stu-id="539ff-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="539ff-122">每個已設定簡單 URL 的 DNS A 記錄通常有四種：meet、dialin、lwa 及 scheduler。</span><span class="sxs-lookup"><span data-stu-id="539ff-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="539ff-123">此外，您還可以使用系統管理員簡易 URL，這是 access Lync Server 2013 控制台的特殊 URL。</span><span class="sxs-lookup"><span data-stu-id="539ff-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="539ff-124">執行 SQL Server 的伺服器必須加入網域，並可由拓撲產生器發佈的電腦存取。</span><span class="sxs-lookup"><span data-stu-id="539ff-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="539ff-125">下表追蹤規劃章節中呈現的參考架構。</span><span class="sxs-lookup"><span data-stu-id="539ff-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="539ff-126">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="539ff-127">前端集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="539ff-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="539ff-128">位置</span><span class="sxs-lookup"><span data-stu-id="539ff-128">Location</span></span></th>
<th><span data-ttu-id="539ff-129">類型</span><span class="sxs-lookup"><span data-stu-id="539ff-129">Type</span></span></th>
<th><span data-ttu-id="539ff-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="539ff-130">FQDN</span></span></th>
<th><span data-ttu-id="539ff-131">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="539ff-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="539ff-132">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-133">A</span><span class="sxs-lookup"><span data-stu-id="539ff-133">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="539ff-135">Pool01 (DNS 負載平衡)。</span><span class="sxs-lookup"><span data-stu-id="539ff-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="539ff-136">需要集區中每一部前端伺服器之 IP 位址的 DNS A 記錄，對應至集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="539ff-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-137">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-138">A</span><span class="sxs-lookup"><span data-stu-id="539ff-138">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="539ff-140">Pool01 (硬體負載平衡器的虛擬 IP (VIP))。</span><span class="sxs-lookup"><span data-stu-id="539ff-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-141">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-142">A</span><span class="sxs-lookup"><span data-stu-id="539ff-142">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="539ff-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="539ff-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="539ff-146">…</span><span class="sxs-lookup"><span data-stu-id="539ff-146">…</span></span></p></td>
<td><p><span data-ttu-id="539ff-147">Pool01 前端伺服器 (節點 1) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="539ff-148">Pool01 前端伺服器 (節點 2) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="539ff-149">Pool01 前端伺服器 (節點 3) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="539ff-150">…</span><span class="sxs-lookup"><span data-stu-id="539ff-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-151">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-152">A</span><span class="sxs-lookup"><span data-stu-id="539ff-152">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="539ff-154">Pool01 前端伺服器 (節點 2) 。</span><span class="sxs-lookup"><span data-stu-id="539ff-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-155">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-156">A</span><span class="sxs-lookup"><span data-stu-id="539ff-156">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="539ff-158">用戶端到伺服器 Web 流量的 Pool01 (VIP)。</span><span class="sxs-lookup"><span data-stu-id="539ff-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-159">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-160">A</span><span class="sxs-lookup"><span data-stu-id="539ff-160">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="539ff-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="539ff-162">Pool01 執行 SQL Server 2008 R2 的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="539ff-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-163">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-164">A</span><span class="sxs-lookup"><span data-stu-id="539ff-164">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-166">對於 Lync Phone Edition 是必要的，或自動登入沒有 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="539ff-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="539ff-167">並非所有情況下都需要此種記錄。</span><span class="sxs-lookup"><span data-stu-id="539ff-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-168">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-169">A</span><span class="sxs-lookup"><span data-stu-id="539ff-169">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="539ff-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-171">假設第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="539ff-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="539ff-172">對於 Lync Phone Edition 是必要的，自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="539ff-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="539ff-173">並非所有情況下都需要此種記錄。</span><span class="sxs-lookup"><span data-stu-id="539ff-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-174">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-175">A</span><span class="sxs-lookup"><span data-stu-id="539ff-175">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-177">內部發佈的撥入式會議的簡易 URL –前端伺服器 (或 Director （如果已安裝) 會回應簡易 URL 查詢）。</span><span class="sxs-lookup"><span data-stu-id="539ff-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-178">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-179">A</span><span class="sxs-lookup"><span data-stu-id="539ff-179">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-181">在內部發佈之會議的簡易 URL –前端伺服器 (或 Director （如果已安裝）) 會回應簡易 URL 查詢。</span><span class="sxs-lookup"><span data-stu-id="539ff-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-182">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-183">A</span><span class="sxs-lookup"><span data-stu-id="539ff-183">A</span></span></p></td>
<td><p><span data-ttu-id="539ff-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="539ff-185">管理</span><span class="sxs-lookup"><span data-stu-id="539ff-185">admin</span></span></p></td>
<td><p><span data-ttu-id="539ff-186">選用的記錄，Lync Server 2013 控制台的簡易 URL 發行于內部-前端伺服器 (或 Director （如果已安裝) 會回應簡易 URL 查詢）。</span><span class="sxs-lookup"><span data-stu-id="539ff-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="539ff-187">建議僅使用主機名稱 (沒有網域名稱)。</span><span class="sxs-lookup"><span data-stu-id="539ff-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="539ff-188">VIP = 硬體負載平衡器的虛擬 IP 位址</span><span class="sxs-lookup"><span data-stu-id="539ff-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="539ff-189">前端集區的 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="539ff-189">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="539ff-190">位置</span><span class="sxs-lookup"><span data-stu-id="539ff-190">Location</span></span></th>
<th><span data-ttu-id="539ff-191">類型</span><span class="sxs-lookup"><span data-stu-id="539ff-191">Type</span></span></th>
<th><span data-ttu-id="539ff-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="539ff-192">FQDN</span></span></th>
<th><span data-ttu-id="539ff-193">目標 FQDN</span><span class="sxs-lookup"><span data-stu-id="539ff-193">Target FQDN</span></span></th>
<th><span data-ttu-id="539ff-194">連接埠</span><span class="sxs-lookup"><span data-stu-id="539ff-194">Port</span></span></th>
<th><span data-ttu-id="539ff-195">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="539ff-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="539ff-196">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-197">SRV</span><span class="sxs-lookup"><span data-stu-id="539ff-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="539ff-198">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="539ff-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-200">5061</span><span class="sxs-lookup"><span data-stu-id="539ff-200">5061</span></span></p></td>
<td><p><span data-ttu-id="539ff-201">自動設定 Lync 2013 用戶端以供內部運作時所需。</span><span class="sxs-lookup"><span data-stu-id="539ff-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="539ff-202">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-203">SRV</span><span class="sxs-lookup"><span data-stu-id="539ff-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="539ff-204">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="539ff-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="539ff-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-206">5061</span><span class="sxs-lookup"><span data-stu-id="539ff-206">5061</span></span></p></td>
<td><p><span data-ttu-id="539ff-207">自動設定 Lync 2013 用戶端以供內部運作時所需。</span><span class="sxs-lookup"><span data-stu-id="539ff-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="539ff-208">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="539ff-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="539ff-209">SRV</span><span class="sxs-lookup"><span data-stu-id="539ff-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="539ff-210">_ntp _ntp._udp .com</span><span class="sxs-lookup"><span data-stu-id="539ff-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ff-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="539ff-212">123</span><span class="sxs-lookup"><span data-stu-id="539ff-212">123</span></span></p></td>
<td><p><span data-ttu-id="539ff-213">執行 Lync Phone Edition 之裝置所需的網路時間通訊協定 (NTP) 來源。</span><span class="sxs-lookup"><span data-stu-id="539ff-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="539ff-214">在內部，此記錄應指向網域控制站。</span><span class="sxs-lookup"><span data-stu-id="539ff-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="539ff-215">如果未定義網域控制站，則會嘗試使用 NTP 伺服器 time.windows.com。</span><span class="sxs-lookup"><span data-stu-id="539ff-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

