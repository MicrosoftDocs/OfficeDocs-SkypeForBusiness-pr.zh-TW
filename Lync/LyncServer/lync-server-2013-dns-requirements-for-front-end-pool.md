---
title: Lync Server 2013：前端集區的 DNS 需求
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
ms.openlocfilehash: eff0ab4c6ee2f6582c8274345c15af681d242561
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532170"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="bca5c-102">Lync Server 2013 中前端集區的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="bca5c-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bca5c-103">_**主題上次修改日期：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="bca5c-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="bca5c-104">若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="bca5c-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="bca5c-105">在 [拓撲產生器] 中發佈拓撲之前，您必須先設定必要的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="bca5c-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="bca5c-106">此外，Lync Server 2013 部署的設定中所用的部分完整功能變數名稱 (Fqdn) 是邏輯和非實體伺服器的 Fqdn，所以在發佈之前必須先進行其他 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="bca5c-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="bca5c-107">Lync Server 2013 不支援單一標示的網域。</span><span class="sxs-lookup"><span data-stu-id="bca5c-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="bca5c-108">例如，根網域名稱為 <STRONG>contoso.local</STRONG> 的樹系是受支援的，名為 <STRONG>local</STRONG> 的根網域則不受支援。</span><span class="sxs-lookup"><span data-stu-id="bca5c-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="bca5c-109">如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「如何針對具有單一標籤 DNS 名稱的網域設定 Windows」的相關資訊，請參閱<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp 3052&kbid = 300684</A>。</span><span class="sxs-lookup"><span data-stu-id="bca5c-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bca5c-110">您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。</span><span class="sxs-lookup"><span data-stu-id="bca5c-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="bca5c-111">根據預設，未加入網域的電腦，其電腦名稱是簡稱，而不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bca5c-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="bca5c-112">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="bca5c-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="bca5c-113">在指派執行 Lync Server、Edge server 及集區的伺服器 Fqdn 時，<STRONG>只能使用標準字元</STRONG> (包括 A–Z、-Z、0–9和連字號) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="bca5c-114">請勿使用 Unicode 字元或底線。</span><span class="sxs-lookup"><span data-stu-id="bca5c-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="bca5c-115">當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用憑證授權單位 (CA) 通常不支援在 FQDN 中使用非標準字元。</span><span class="sxs-lookup"><span data-stu-id="bca5c-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="bca5c-116">在部署拓撲之後執行拓撲之後，請確定下列 Active Directory 和 DNS 記錄會根據您的特定功能的需求而建立 (。) ：</span><span class="sxs-lookup"><span data-stu-id="bca5c-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="bca5c-117">將存在於拓撲中的每個伺服器角色都會發佈為 Active Directory 物件 (將電腦加入網域，就能完成此) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="bca5c-118">每個伺服器都存在 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="bca5c-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="bca5c-119">如果您打算對 \_ sipinternaltls tcp 格式的用戶端使用自動登入，則每個 SIP 網域都會存在 DNS SRV 記錄。 \_ \<SIP domain\></span><span class="sxs-lookup"><span data-stu-id="bca5c-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="bca5c-120">如果您將對用戶端使用手動設定，則不需要此記錄。</span><span class="sxs-lookup"><span data-stu-id="bca5c-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="bca5c-121">每個已設定簡單 URL 的 DNS A 記錄通常有四種：meet、dialin、lwa 及 scheduler。</span><span class="sxs-lookup"><span data-stu-id="bca5c-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="bca5c-122">此外，您還可以使用系統管理員簡易 URL，這是 access Lync Server 2013 控制台的特殊 URL。</span><span class="sxs-lookup"><span data-stu-id="bca5c-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="bca5c-123">執行 SQL Server 的伺服器必須加入網域，並可由拓撲產生器發佈的電腦存取。</span><span class="sxs-lookup"><span data-stu-id="bca5c-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="bca5c-124">下表追蹤規劃章節中呈現的參考架構。</span><span class="sxs-lookup"><span data-stu-id="bca5c-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="bca5c-125">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="bca5c-126">前端集區所需的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="bca5c-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bca5c-127">位置</span><span class="sxs-lookup"><span data-stu-id="bca5c-127">Location</span></span></th>
<th><span data-ttu-id="bca5c-128">類型</span><span class="sxs-lookup"><span data-stu-id="bca5c-128">Type</span></span></th>
<th><span data-ttu-id="bca5c-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="bca5c-129">FQDN</span></span></th>
<th><span data-ttu-id="bca5c-130">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="bca5c-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-131">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-132">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-132">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bca5c-134">Pool01 (DNS 負載平衡)。</span><span class="sxs-lookup"><span data-stu-id="bca5c-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="bca5c-135">需要集區中每一部前端伺服器之 IP 位址的 DNS A 記錄，對應至集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bca5c-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-136">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-137">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-137">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bca5c-139">Pool01 (硬體負載平衡器的虛擬 IP (VIP))。</span><span class="sxs-lookup"><span data-stu-id="bca5c-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-140">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-141">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-141">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="bca5c-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="bca5c-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="bca5c-145">…</span><span class="sxs-lookup"><span data-stu-id="bca5c-145">…</span></span></p></td>
<td><p><span data-ttu-id="bca5c-146">Pool01 前端伺服器 (節點 1) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="bca5c-147">Pool01 前端伺服器 (節點 2) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="bca5c-148">Pool01 前端伺服器 (節點 3) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="bca5c-149">…</span><span class="sxs-lookup"><span data-stu-id="bca5c-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-150">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-151">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-151">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bca5c-153">Pool01 前端伺服器 (節點 2) 。</span><span class="sxs-lookup"><span data-stu-id="bca5c-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-154">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-155">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-155">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bca5c-157">用戶端到伺服器 Web 流量的 Pool01 (VIP)。</span><span class="sxs-lookup"><span data-stu-id="bca5c-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-158">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-159">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-159">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bca5c-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="bca5c-161">Pool01 執行 SQL Server 2008 R2 的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="bca5c-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-162">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-163">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-163">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-165">對於 Lync Phone Edition 是必要的，或自動登入沒有 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="bca5c-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="bca5c-166">並非所有情況下都需要此種記錄。</span><span class="sxs-lookup"><span data-stu-id="bca5c-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-167">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-168">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-168">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-170">假設第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="bca5c-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="bca5c-171">對於 Lync Phone Edition 是必要的，自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。</span><span class="sxs-lookup"><span data-stu-id="bca5c-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="bca5c-172">並非所有情況下都需要此種記錄。</span><span class="sxs-lookup"><span data-stu-id="bca5c-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-173">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-174">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-174">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-176">內部發佈的撥入式會議的簡易 URL –前端伺服器 (或 Director （如果已安裝) 會回應簡易 URL 查詢）。</span><span class="sxs-lookup"><span data-stu-id="bca5c-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-177">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-178">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-178">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-180">在內部發佈之會議的簡易 URL –前端伺服器 (或 Director （如果已安裝）) 會回應簡易 URL 查詢。</span><span class="sxs-lookup"><span data-stu-id="bca5c-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-181">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-182">A</span><span class="sxs-lookup"><span data-stu-id="bca5c-182">A</span></span></p></td>
<td><p><span data-ttu-id="bca5c-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="bca5c-184">管理</span><span class="sxs-lookup"><span data-stu-id="bca5c-184">admin</span></span></p></td>
<td><p><span data-ttu-id="bca5c-185">選用的記錄，Lync Server 2013 控制台的簡易 URL 發行于內部-前端伺服器 (或 Director （如果已安裝) 會回應簡易 URL 查詢）。</span><span class="sxs-lookup"><span data-stu-id="bca5c-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="bca5c-186">建議僅使用主機名稱 (沒有網域名稱)。</span><span class="sxs-lookup"><span data-stu-id="bca5c-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bca5c-187">VIP = 硬體負載平衡器的虛擬 IP 位址</span><span class="sxs-lookup"><span data-stu-id="bca5c-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="bca5c-188">前端集區的 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="bca5c-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="bca5c-189">位置</span><span class="sxs-lookup"><span data-stu-id="bca5c-189">Location</span></span></th>
<th><span data-ttu-id="bca5c-190">類型</span><span class="sxs-lookup"><span data-stu-id="bca5c-190">Type</span></span></th>
<th><span data-ttu-id="bca5c-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="bca5c-191">FQDN</span></span></th>
<th><span data-ttu-id="bca5c-192">目標 FQDN</span><span class="sxs-lookup"><span data-stu-id="bca5c-192">Target FQDN</span></span></th>
<th><span data-ttu-id="bca5c-193">連接埠</span><span class="sxs-lookup"><span data-stu-id="bca5c-193">Port</span></span></th>
<th><span data-ttu-id="bca5c-194">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="bca5c-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-195">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-196">SRV</span><span class="sxs-lookup"><span data-stu-id="bca5c-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="bca5c-197">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="bca5c-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-199">5061</span><span class="sxs-lookup"><span data-stu-id="bca5c-199">5061</span></span></p></td>
<td><p><span data-ttu-id="bca5c-200">自動設定 Lync 2013 用戶端以供內部運作時所需。</span><span class="sxs-lookup"><span data-stu-id="bca5c-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bca5c-201">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-202">SRV</span><span class="sxs-lookup"><span data-stu-id="bca5c-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="bca5c-203">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="bca5c-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-205">5061</span><span class="sxs-lookup"><span data-stu-id="bca5c-205">5061</span></span></p></td>
<td><p><span data-ttu-id="bca5c-206">自動設定 Lync 2013 用戶端以供內部運作時所需。</span><span class="sxs-lookup"><span data-stu-id="bca5c-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bca5c-207">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="bca5c-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="bca5c-208">SRV</span><span class="sxs-lookup"><span data-stu-id="bca5c-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="bca5c-209">_ntp _ntp._udp .com</span><span class="sxs-lookup"><span data-stu-id="bca5c-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bca5c-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bca5c-211">123</span><span class="sxs-lookup"><span data-stu-id="bca5c-211">123</span></span></p></td>
<td><p><span data-ttu-id="bca5c-212">執行 Lync Phone Edition 之裝置所需的網路時間通訊協定 (NTP) 來源。</span><span class="sxs-lookup"><span data-stu-id="bca5c-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="bca5c-213">在內部，此記錄應指向網域控制站。</span><span class="sxs-lookup"><span data-stu-id="bca5c-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="bca5c-214">如果未定義網域控制站，則會嘗試使用 NTP 伺服器 time.windows.com。</span><span class="sxs-lookup"><span data-stu-id="bca5c-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

