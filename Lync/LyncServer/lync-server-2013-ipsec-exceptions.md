---
title: Lync Server 2013 IPsec 例外狀況
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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="48d35-102">Lync Server 2013 中的 IPsec 例外狀況</span><span class="sxs-lookup"><span data-stu-id="48d35-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48d35-103">_**主題上次修改日期：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="48d35-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="48d35-104">針對網際網路通訊協定安全性（IPsec）（請參閱已部署的 IETF RFC 4301-4309）商業網路，必須停用用於傳送音訊、影片和全景影片的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="48d35-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="48d35-105">建議因需要避免由於 IPsec 協商而分配媒體埠的任何延遲。</span><span class="sxs-lookup"><span data-stu-id="48d35-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="48d35-106">下表說明建議的 IPsec 例外狀況設定。</span><span class="sxs-lookup"><span data-stu-id="48d35-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="48d35-107">建議的 IPsec 例外狀況</span><span class="sxs-lookup"><span data-stu-id="48d35-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="48d35-108">規則名稱</span><span class="sxs-lookup"><span data-stu-id="48d35-108">Rule name</span></span></th>
<th><span data-ttu-id="48d35-109">來源 IP</span><span class="sxs-lookup"><span data-stu-id="48d35-109">Source IP</span></span></th>
<th><span data-ttu-id="48d35-110">目的地 IP</span><span class="sxs-lookup"><span data-stu-id="48d35-110">Destination IP</span></span></th>
<th><span data-ttu-id="48d35-111">通訊協定</span><span class="sxs-lookup"><span data-stu-id="48d35-111">Protocol</span></span></th>
<th><span data-ttu-id="48d35-112">來源埠</span><span class="sxs-lookup"><span data-stu-id="48d35-112">Source port</span></span></th>
<th><span data-ttu-id="48d35-113">目的地埠</span><span class="sxs-lookup"><span data-stu-id="48d35-113">Destination port</span></span></th>
<th><span data-ttu-id="48d35-114">驗證需求</span><span class="sxs-lookup"><span data-stu-id="48d35-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d35-115">A/V 邊緣伺服器內部入站</span><span class="sxs-lookup"><span data-stu-id="48d35-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-116">每</span><span class="sxs-lookup"><span data-stu-id="48d35-116">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-117">A/V 邊緣伺服器內部</span><span class="sxs-lookup"><span data-stu-id="48d35-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="48d35-118">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-119">每</span><span class="sxs-lookup"><span data-stu-id="48d35-119">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-120">每</span><span class="sxs-lookup"><span data-stu-id="48d35-120">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-121">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-122">A/V 邊緣伺服器外部輸入</span><span class="sxs-lookup"><span data-stu-id="48d35-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-123">每</span><span class="sxs-lookup"><span data-stu-id="48d35-123">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-124">A/V 邊緣伺服器外部</span><span class="sxs-lookup"><span data-stu-id="48d35-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="48d35-125">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-126">每</span><span class="sxs-lookup"><span data-stu-id="48d35-126">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-127">每</span><span class="sxs-lookup"><span data-stu-id="48d35-127">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-128">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-129">A/V 邊緣伺服器內部出站</span><span class="sxs-lookup"><span data-stu-id="48d35-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-130">A/V 邊緣伺服器內部</span><span class="sxs-lookup"><span data-stu-id="48d35-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="48d35-131">每</span><span class="sxs-lookup"><span data-stu-id="48d35-131">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-133">每</span><span class="sxs-lookup"><span data-stu-id="48d35-133">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-134">每</span><span class="sxs-lookup"><span data-stu-id="48d35-134">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-135">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-136">A/V 邊緣伺服器外部輸出</span><span class="sxs-lookup"><span data-stu-id="48d35-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-137">A/V 邊緣伺服器外部</span><span class="sxs-lookup"><span data-stu-id="48d35-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="48d35-138">每</span><span class="sxs-lookup"><span data-stu-id="48d35-138">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-139">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-140">每</span><span class="sxs-lookup"><span data-stu-id="48d35-140">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-141">每</span><span class="sxs-lookup"><span data-stu-id="48d35-141">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-142">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-143">中繼伺服器入站</span><span class="sxs-lookup"><span data-stu-id="48d35-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-144">每</span><span class="sxs-lookup"><span data-stu-id="48d35-144">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-145">仲介</span><span class="sxs-lookup"><span data-stu-id="48d35-145">Mediation</span></span></p>
<p><span data-ttu-id="48d35-146">伺服器（s）</span><span class="sxs-lookup"><span data-stu-id="48d35-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="48d35-147">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-148">每</span><span class="sxs-lookup"><span data-stu-id="48d35-148">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-149">每</span><span class="sxs-lookup"><span data-stu-id="48d35-149">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-150">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-151">轉送伺服器出站</span><span class="sxs-lookup"><span data-stu-id="48d35-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-152">仲介</span><span class="sxs-lookup"><span data-stu-id="48d35-152">Mediation</span></span></p>
<p><span data-ttu-id="48d35-153">伺服器（s）</span><span class="sxs-lookup"><span data-stu-id="48d35-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="48d35-154">每</span><span class="sxs-lookup"><span data-stu-id="48d35-154">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-155">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-156">每</span><span class="sxs-lookup"><span data-stu-id="48d35-156">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-157">每</span><span class="sxs-lookup"><span data-stu-id="48d35-157">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-158">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-159">會議助理入站</span><span class="sxs-lookup"><span data-stu-id="48d35-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-160">每</span><span class="sxs-lookup"><span data-stu-id="48d35-160">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-161">運行會議助理的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="48d35-162">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-163">每</span><span class="sxs-lookup"><span data-stu-id="48d35-163">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-164">每</span><span class="sxs-lookup"><span data-stu-id="48d35-164">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-165">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-166">會議助理出站</span><span class="sxs-lookup"><span data-stu-id="48d35-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-167">運行會議助理的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="48d35-168">每</span><span class="sxs-lookup"><span data-stu-id="48d35-168">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-169">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-170">每</span><span class="sxs-lookup"><span data-stu-id="48d35-170">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-171">每</span><span class="sxs-lookup"><span data-stu-id="48d35-171">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-172">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-173">A/V 會議入站</span><span class="sxs-lookup"><span data-stu-id="48d35-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-174">每</span><span class="sxs-lookup"><span data-stu-id="48d35-174">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-175">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="48d35-176">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-177">每</span><span class="sxs-lookup"><span data-stu-id="48d35-177">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-178">每</span><span class="sxs-lookup"><span data-stu-id="48d35-178">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-179">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-180">A/V 會議輸出</span><span class="sxs-lookup"><span data-stu-id="48d35-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-181">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="48d35-182">每</span><span class="sxs-lookup"><span data-stu-id="48d35-182">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-183">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-184">每</span><span class="sxs-lookup"><span data-stu-id="48d35-184">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-185">每</span><span class="sxs-lookup"><span data-stu-id="48d35-185">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-186">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-187">Exchange 入站</span><span class="sxs-lookup"><span data-stu-id="48d35-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-188">每</span><span class="sxs-lookup"><span data-stu-id="48d35-188">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-189">Exchange 整合通訊</span><span class="sxs-lookup"><span data-stu-id="48d35-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="48d35-190">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-191">每</span><span class="sxs-lookup"><span data-stu-id="48d35-191">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-192">每</span><span class="sxs-lookup"><span data-stu-id="48d35-192">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-193">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-194">應用程式共用伺服器入站</span><span class="sxs-lookup"><span data-stu-id="48d35-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-195">每</span><span class="sxs-lookup"><span data-stu-id="48d35-195">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-196">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="48d35-197">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="48d35-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-198">每</span><span class="sxs-lookup"><span data-stu-id="48d35-198">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-199">每</span><span class="sxs-lookup"><span data-stu-id="48d35-199">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-200">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-201">應用程式共用伺服器出站</span><span class="sxs-lookup"><span data-stu-id="48d35-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-202">應用程式共用伺服器</span><span class="sxs-lookup"><span data-stu-id="48d35-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="48d35-203">每</span><span class="sxs-lookup"><span data-stu-id="48d35-203">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-204">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="48d35-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-205">每</span><span class="sxs-lookup"><span data-stu-id="48d35-205">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-206">每</span><span class="sxs-lookup"><span data-stu-id="48d35-206">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-207">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d35-208">Exchange 輸出</span><span class="sxs-lookup"><span data-stu-id="48d35-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="48d35-209">Exchange 整合通訊</span><span class="sxs-lookup"><span data-stu-id="48d35-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="48d35-210">每</span><span class="sxs-lookup"><span data-stu-id="48d35-210">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-211">UDP 與 TCP</span><span class="sxs-lookup"><span data-stu-id="48d35-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="48d35-212">每</span><span class="sxs-lookup"><span data-stu-id="48d35-212">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-213">每</span><span class="sxs-lookup"><span data-stu-id="48d35-213">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-214">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d35-215">台</span><span class="sxs-lookup"><span data-stu-id="48d35-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="48d35-216">每</span><span class="sxs-lookup"><span data-stu-id="48d35-216">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-217">每</span><span class="sxs-lookup"><span data-stu-id="48d35-217">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-218">UDP-IN</span><span class="sxs-lookup"><span data-stu-id="48d35-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="48d35-219">指定的媒體埠範圍</span><span class="sxs-lookup"><span data-stu-id="48d35-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="48d35-220">每</span><span class="sxs-lookup"><span data-stu-id="48d35-220">Any</span></span></p></td>
<td><p><span data-ttu-id="48d35-221">不要驗證</span><span class="sxs-lookup"><span data-stu-id="48d35-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

