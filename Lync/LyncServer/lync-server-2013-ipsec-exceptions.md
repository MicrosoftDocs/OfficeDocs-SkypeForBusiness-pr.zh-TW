---
title: Lync Server 2013 IPsec 例外狀況
description: Lync Server 2013 IPsec 例外狀況。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574999"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="76177-103">Lync Server 2013 中的 IPsec 例外狀況</span><span class="sxs-lookup"><span data-stu-id="76177-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76177-104">_**主題上次修改日期：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="76177-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="76177-p101">對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="76177-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="76177-107">下表說明建議採用的 IPSec 例外設定。</span><span class="sxs-lookup"><span data-stu-id="76177-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="76177-108">建議的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="76177-108">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76177-109">規則名稱</span><span class="sxs-lookup"><span data-stu-id="76177-109">Rule name</span></span></th>
<th><span data-ttu-id="76177-110">來源 IP</span><span class="sxs-lookup"><span data-stu-id="76177-110">Source IP</span></span></th>
<th><span data-ttu-id="76177-111">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="76177-111">Destination IP</span></span></th>
<th><span data-ttu-id="76177-112">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="76177-112">Protocol</span></span></th>
<th><span data-ttu-id="76177-113">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="76177-113">Source port</span></span></th>
<th><span data-ttu-id="76177-114">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="76177-114">Destination port</span></span></th>
<th><span data-ttu-id="76177-115">驗證需求</span><span class="sxs-lookup"><span data-stu-id="76177-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76177-116">A/V Edge Server (輸入的內部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-117">任何</span><span class="sxs-lookup"><span data-stu-id="76177-117">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-118">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="76177-119">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-120">任何</span><span class="sxs-lookup"><span data-stu-id="76177-120">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-121">任何</span><span class="sxs-lookup"><span data-stu-id="76177-121">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-122">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-123">A/V Edge Server (輸入的外部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-124">任何</span><span class="sxs-lookup"><span data-stu-id="76177-124">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-125">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="76177-126">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-127">任何</span><span class="sxs-lookup"><span data-stu-id="76177-127">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-128">任何</span><span class="sxs-lookup"><span data-stu-id="76177-128">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-129">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-130">A/V Edge Server (輸出的內部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-131">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="76177-132">任何</span><span class="sxs-lookup"><span data-stu-id="76177-132">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-133">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="76177-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-134">任何</span><span class="sxs-lookup"><span data-stu-id="76177-134">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-135">任何</span><span class="sxs-lookup"><span data-stu-id="76177-135">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-136">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-137">A/V Edge Server (輸出的外部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-138">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="76177-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="76177-139">任何</span><span class="sxs-lookup"><span data-stu-id="76177-139">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-140">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-141">任何</span><span class="sxs-lookup"><span data-stu-id="76177-141">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-142">任何</span><span class="sxs-lookup"><span data-stu-id="76177-142">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-143">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-144">中繼伺服器 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="76177-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-145">任何</span><span class="sxs-lookup"><span data-stu-id="76177-145">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-146">調解</span><span class="sxs-lookup"><span data-stu-id="76177-146">Mediation</span></span></p>
<p><span data-ttu-id="76177-147">伺服器 (s) </span><span class="sxs-lookup"><span data-stu-id="76177-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="76177-148">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-149">任何</span><span class="sxs-lookup"><span data-stu-id="76177-149">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-150">任何</span><span class="sxs-lookup"><span data-stu-id="76177-150">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-151">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-152">中繼伺服器 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="76177-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-153">調解</span><span class="sxs-lookup"><span data-stu-id="76177-153">Mediation</span></span></p>
<p><span data-ttu-id="76177-154">伺服器 (s) </span><span class="sxs-lookup"><span data-stu-id="76177-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="76177-155">任何</span><span class="sxs-lookup"><span data-stu-id="76177-155">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-156">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-157">任何</span><span class="sxs-lookup"><span data-stu-id="76177-157">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-158">任何</span><span class="sxs-lookup"><span data-stu-id="76177-158">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-159">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-160">會議服務員 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="76177-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-161">任何</span><span class="sxs-lookup"><span data-stu-id="76177-161">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-162">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="76177-163">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-164">任何</span><span class="sxs-lookup"><span data-stu-id="76177-164">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-165">任何</span><span class="sxs-lookup"><span data-stu-id="76177-165">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-166">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-167">會議服務員 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="76177-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-168">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="76177-169">任何</span><span class="sxs-lookup"><span data-stu-id="76177-169">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-170">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-171">任何</span><span class="sxs-lookup"><span data-stu-id="76177-171">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-172">任何</span><span class="sxs-lookup"><span data-stu-id="76177-172">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-173">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-174">A/V 會議 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="76177-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-175">任何</span><span class="sxs-lookup"><span data-stu-id="76177-175">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-176">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="76177-177">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-178">任何</span><span class="sxs-lookup"><span data-stu-id="76177-178">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-179">任何</span><span class="sxs-lookup"><span data-stu-id="76177-179">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-180">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-181">A/V 會議 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="76177-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-182">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="76177-183">任何</span><span class="sxs-lookup"><span data-stu-id="76177-183">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-184">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-185">任何</span><span class="sxs-lookup"><span data-stu-id="76177-185">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-186">任何</span><span class="sxs-lookup"><span data-stu-id="76177-186">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-187">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-188">Exchange (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="76177-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-189">任何</span><span class="sxs-lookup"><span data-stu-id="76177-189">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-190">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="76177-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="76177-191">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-192">任何</span><span class="sxs-lookup"><span data-stu-id="76177-192">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-193">任何</span><span class="sxs-lookup"><span data-stu-id="76177-193">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-194">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-195">應用程式共用伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="76177-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="76177-196">任何</span><span class="sxs-lookup"><span data-stu-id="76177-196">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-197">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="76177-198">TCP</span><span class="sxs-lookup"><span data-stu-id="76177-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-199">任何</span><span class="sxs-lookup"><span data-stu-id="76177-199">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-200">任何</span><span class="sxs-lookup"><span data-stu-id="76177-200">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-201">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-202">應用程式共用伺服器輸出</span><span class="sxs-lookup"><span data-stu-id="76177-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-203">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="76177-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="76177-204">任何</span><span class="sxs-lookup"><span data-stu-id="76177-204">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-205">TCP</span><span class="sxs-lookup"><span data-stu-id="76177-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-206">任何</span><span class="sxs-lookup"><span data-stu-id="76177-206">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-207">任何</span><span class="sxs-lookup"><span data-stu-id="76177-207">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-208">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76177-209">Exchange (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="76177-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="76177-210">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="76177-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="76177-211">任何</span><span class="sxs-lookup"><span data-stu-id="76177-211">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-212">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="76177-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="76177-213">任何</span><span class="sxs-lookup"><span data-stu-id="76177-213">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-214">任何</span><span class="sxs-lookup"><span data-stu-id="76177-214">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-215">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76177-216">用戶端</span><span class="sxs-lookup"><span data-stu-id="76177-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="76177-217">任何</span><span class="sxs-lookup"><span data-stu-id="76177-217">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-218">任何</span><span class="sxs-lookup"><span data-stu-id="76177-218">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-219">Udp</span><span class="sxs-lookup"><span data-stu-id="76177-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="76177-220">指定的媒體連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="76177-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="76177-221">任何</span><span class="sxs-lookup"><span data-stu-id="76177-221">Any</span></span></p></td>
<td><p><span data-ttu-id="76177-222">不要驗證</span><span class="sxs-lookup"><span data-stu-id="76177-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

