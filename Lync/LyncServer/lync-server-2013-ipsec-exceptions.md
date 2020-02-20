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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="3140d-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="3140d-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3140d-103">_**主題上次修改日期：** 2012 年 06 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="3140d-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="3140d-p101">對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="3140d-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="3140d-106">下表說明建議採用的 IPSec 例外設定。</span><span class="sxs-lookup"><span data-stu-id="3140d-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="3140d-107">建議的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="3140d-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="3140d-108">規則名稱</span><span class="sxs-lookup"><span data-stu-id="3140d-108">Rule name</span></span></th>
<th><span data-ttu-id="3140d-109">來源 IP</span><span class="sxs-lookup"><span data-stu-id="3140d-109">Source IP</span></span></th>
<th><span data-ttu-id="3140d-110">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="3140d-110">Destination IP</span></span></th>
<th><span data-ttu-id="3140d-111">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="3140d-111">Protocol</span></span></th>
<th><span data-ttu-id="3140d-112">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="3140d-112">Source port</span></span></th>
<th><span data-ttu-id="3140d-113">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="3140d-113">Destination port</span></span></th>
<th><span data-ttu-id="3140d-114">驗證需求</span><span class="sxs-lookup"><span data-stu-id="3140d-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3140d-115">A/V Edge Server (輸入的內部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-116">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-116">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-117">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="3140d-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-119">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-119">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-120">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-120">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-121">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-122">A/V Edge Server (輸入的外部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-123">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-123">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-124">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="3140d-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-126">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-126">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-127">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-127">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-128">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-129">A/V Edge Server (輸出的內部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-130">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="3140d-131">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-133">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-133">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-134">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-135">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-136">A/V Edge Server (輸出的外部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-137">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="3140d-138">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-138">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-140">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-140">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-141">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-142">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-143">中繼伺服器 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-144">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-144">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-145">中繼</span><span class="sxs-lookup"><span data-stu-id="3140d-145">Mediation</span></span></p>
<p><span data-ttu-id="3140d-146">伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="3140d-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-148">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-148">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-149">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-149">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-150">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-151">中繼伺服器 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-152">中繼</span><span class="sxs-lookup"><span data-stu-id="3140d-152">Mediation</span></span></p>
<p><span data-ttu-id="3140d-153">伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="3140d-154">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-154">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-156">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-156">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-157">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-157">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-158">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-159">會議服務員 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-160">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-160">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-161">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="3140d-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-163">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-163">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-164">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-164">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-165">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-166">會議服務員 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-167">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="3140d-168">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-168">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-170">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-170">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-171">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-171">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-172">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-173">A/V 會議 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-174">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-174">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-175">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3140d-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-177">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-177">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-178">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-178">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-179">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-180">A/V 會議 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-181">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3140d-182">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-182">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-184">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-184">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-185">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-185">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-186">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-187">Exchange (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-188">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-188">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="3140d-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="3140d-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-191">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-191">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-192">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-192">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-193">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-194">應用程式共用伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="3140d-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-195">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-195">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-196">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="3140d-197">TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-198">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-198">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-199">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-199">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-200">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-201">應用程式共用伺服器輸出</span><span class="sxs-lookup"><span data-stu-id="3140d-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-202">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="3140d-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="3140d-203">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-203">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-204">TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-205">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-205">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-206">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-206">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-207">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3140d-208">Exchange (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="3140d-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="3140d-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="3140d-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="3140d-210">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-210">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="3140d-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="3140d-212">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-212">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-213">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-213">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-214">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3140d-215">用戶端</span><span class="sxs-lookup"><span data-stu-id="3140d-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="3140d-216">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-216">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-217">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-217">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-218">UDP</span><span class="sxs-lookup"><span data-stu-id="3140d-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="3140d-219">指定的媒體連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="3140d-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="3140d-220">任何</span><span class="sxs-lookup"><span data-stu-id="3140d-220">Any</span></span></p></td>
<td><p><span data-ttu-id="3140d-221">不要驗證</span><span class="sxs-lookup"><span data-stu-id="3140d-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

