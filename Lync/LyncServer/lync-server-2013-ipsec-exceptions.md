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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="5eaa1-102">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="5eaa1-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eaa1-103">_**主題上次修改日期：** 2012 年 06 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="5eaa1-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="5eaa1-p101">對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="5eaa1-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="5eaa1-106">下表說明建議採用的 IPSec 例外設定。</span><span class="sxs-lookup"><span data-stu-id="5eaa1-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="5eaa1-107">建議的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="5eaa1-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="5eaa1-108">規則名稱</span><span class="sxs-lookup"><span data-stu-id="5eaa1-108">Rule name</span></span></th>
<th><span data-ttu-id="5eaa1-109">來源 IP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-109">Source IP</span></span></th>
<th><span data-ttu-id="5eaa1-110">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-110">Destination IP</span></span></th>
<th><span data-ttu-id="5eaa1-111">Protocol (通訊協定)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-111">Protocol</span></span></th>
<th><span data-ttu-id="5eaa1-112">來源連接埠</span><span class="sxs-lookup"><span data-stu-id="5eaa1-112">Source port</span></span></th>
<th><span data-ttu-id="5eaa1-113">目的地連接埠</span><span class="sxs-lookup"><span data-stu-id="5eaa1-113">Destination port</span></span></th>
<th><span data-ttu-id="5eaa1-114">驗證需求</span><span class="sxs-lookup"><span data-stu-id="5eaa1-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-115">A/V Edge Server (輸入的內部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-116">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-116">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-117">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-118">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-119">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-119">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-120">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-120">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-121">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-122">A/V Edge Server (輸入的外部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-123">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-123">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-124">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-125">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-126">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-126">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-127">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-127">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-128">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-129">A/V Edge Server (輸出的內部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-130">A/V Edge Server (內部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-131">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-131">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-133">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-133">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-134">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-134">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-135">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-136">A/V Edge Server (輸出的外部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-137">A/V Edge Server (外部流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-138">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-138">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-139">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-140">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-140">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-141">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-141">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-142">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-143">中繼伺服器 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-144">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-144">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-145">中繼</span><span class="sxs-lookup"><span data-stu-id="5eaa1-145">Mediation</span></span></p>
<p><span data-ttu-id="5eaa1-146">伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-147">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-148">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-148">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-149">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-149">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-150">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-151">中繼伺服器 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-152">中繼</span><span class="sxs-lookup"><span data-stu-id="5eaa1-152">Mediation</span></span></p>
<p><span data-ttu-id="5eaa1-153">伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-154">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-154">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-155">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-156">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-156">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-157">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-157">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-158">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-159">會議服務員 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-160">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-160">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-161">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-162">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-163">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-163">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-164">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-164">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-165">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-166">會議服務員 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-167">執行會議服務員的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-168">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-168">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-169">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-170">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-170">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-171">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-171">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-172">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-173">A/V 會議 (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-174">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-174">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-175">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-176">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-177">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-177">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-178">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-178">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-179">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-180">A/V 會議 (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-181">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-182">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-182">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-183">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-184">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-184">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-185">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-185">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-186">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-187">Exchange (輸入流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-188">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-188">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-189">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="5eaa1-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-190">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-191">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-191">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-192">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-192">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-193">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-194">應用程式共用伺服器輸入</span><span class="sxs-lookup"><span data-stu-id="5eaa1-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-195">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-195">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-196">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-197">TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-198">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-198">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-199">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-199">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-200">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-201">應用程式共用伺服器輸出</span><span class="sxs-lookup"><span data-stu-id="5eaa1-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-202">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="5eaa1-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-203">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-203">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-204">TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-205">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-205">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-206">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-206">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-207">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eaa1-208">Exchange (輸出流量)</span><span class="sxs-lookup"><span data-stu-id="5eaa1-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-209">Exchange Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="5eaa1-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-210">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-210">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-211">UDP 和 TCP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-212">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-212">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-213">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-213">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-214">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eaa1-215">用戶端</span><span class="sxs-lookup"><span data-stu-id="5eaa1-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-216">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-216">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-217">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-217">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-218">UDP</span><span class="sxs-lookup"><span data-stu-id="5eaa1-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-219">指定的媒體連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="5eaa1-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-220">任何</span><span class="sxs-lookup"><span data-stu-id="5eaa1-220">Any</span></span></p></td>
<td><p><span data-ttu-id="5eaa1-221">不要驗證</span><span class="sxs-lookup"><span data-stu-id="5eaa1-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

