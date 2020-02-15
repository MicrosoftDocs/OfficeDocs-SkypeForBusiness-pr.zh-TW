---
title: Lync Server 2013 IPsec 例外
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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="2a44b-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="2a44b-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a44b-103">_**主題上次修改日期：** 2012 年 06 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="2a44b-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="2a44b-p101">對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="2a44b-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="2a44b-106">下表說明建議採用的 IPSec 例外設定。</span><span class="sxs-lookup"><span data-stu-id="2a44b-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="2a44b-107">建議的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="2a44b-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="2a44b-108">規則名稱</span><span class="sxs-lookup"><span data-stu-id="2a44b-108">Rule name</span></span></th>
<th><span data-ttu-id="2a44b-109">來源 IP</span><span class="sxs-lookup"><span data-stu-id="2a44b-109">Source IP</span></span></th>
<th><span data-ttu-id="2a44b-110">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="2a44b-110">Destination IP</span></span></th>
<th><span data-ttu-id="2a44b-111">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="2a44b-111">Protocol</span></span></th>
<th><span data-ttu-id="2a44b-112">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="2a44b-112">Source port</span></span></th>
<th><span data-ttu-id="2a44b-113">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="2a44b-113">Destination port</span></span></th>
<th><span data-ttu-id="2a44b-114">驗證需求</span><span class="sxs-lookup"><span data-stu-id="2a44b-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-115">A/V Edge Server (輸入的內部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-116">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-116">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-117">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="2a44b-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-119">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-119">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-120">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-120">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-121">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-122">A/V Edge Server (輸入的外部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-123">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-123">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-124">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="2a44b-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-126">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-127">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-127">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-128">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-129">A/V Edge Server (輸出的內部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-130">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="2a44b-131">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-131">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-133">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-133">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-134">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-135">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-136">A/V Edge Server (輸出的外部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-137">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="2a44b-138">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-140">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-140">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-141">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-142">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-143">中繼伺服器 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-144">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-144">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-145">中繼</span><span class="sxs-lookup"><span data-stu-id="2a44b-145">Mediation</span></span></p>
<p><span data-ttu-id="2a44b-146">伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="2a44b-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-148">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-148">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-149">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-150">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-151">中繼伺服器 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-152">中繼</span><span class="sxs-lookup"><span data-stu-id="2a44b-152">Mediation</span></span></p>
<p><span data-ttu-id="2a44b-153">伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="2a44b-154">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-156">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-156">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-157">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-157">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-158">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-159">會議服務員 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-160">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-160">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-161">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="2a44b-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-163">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-164">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-164">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-165">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-166">會議服務員 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-167">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="2a44b-168">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-168">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-170">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-171">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-171">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-172">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-173">A/V 會議 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-174">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-175">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a44b-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-177">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-177">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-178">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-179">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-180">A/V 會議 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-181">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="2a44b-182">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-184">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-184">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-185">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-185">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-186">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-187">Exchange (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-188">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-188">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="2a44b-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="2a44b-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-191">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-191">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-192">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-192">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-193">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-194">應用程式共用伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="2a44b-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-195">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-195">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-196">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="2a44b-197">TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-198">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-198">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-199">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-200">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-201">應用程式共用伺服器輸出</span><span class="sxs-lookup"><span data-stu-id="2a44b-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-202">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="2a44b-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="2a44b-203">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-203">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-204">TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-205">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-205">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-206">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-206">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-207">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a44b-208">Exchange (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="2a44b-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="2a44b-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="2a44b-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="2a44b-210">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-210">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="2a44b-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-212">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-212">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-213">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-213">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-214">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a44b-215">用戶端</span><span class="sxs-lookup"><span data-stu-id="2a44b-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="2a44b-216">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-216">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-217">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-217">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-218">UDP</span><span class="sxs-lookup"><span data-stu-id="2a44b-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="2a44b-219">指定的媒體連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="2a44b-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="2a44b-220">任何</span><span class="sxs-lookup"><span data-stu-id="2a44b-220">Any</span></span></p></td>
<td><p><span data-ttu-id="2a44b-221">不要驗證</span><span class="sxs-lookup"><span data-stu-id="2a44b-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

