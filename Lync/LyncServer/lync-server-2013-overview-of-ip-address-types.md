---
title: Lync Server 2013： IP 位址類型的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9663f7ee8b57ceba27e1a1892c30bb92a1c86ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521000"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="116c7-102">Lync Server 2013 的 IP 位址類型概述</span><span class="sxs-lookup"><span data-stu-id="116c7-102">Overview of IP address types for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="116c7-103">_**主題上次修改日期：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="116c7-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="116c7-104">在 Lync Server 2013 中設定 IP 位址時，您有三個選項。</span><span class="sxs-lookup"><span data-stu-id="116c7-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="116c7-105">您可以將 Lync Server 2013 設定為僅支援 IP 版本 4 (IPv4) 、只有 IP 版本 6 (IPv6) ，或是兩種 (（稱為 *雙重堆疊*) ）的組合。</span><span class="sxs-lookup"><span data-stu-id="116c7-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="116c7-106">每種類型的設定都有幾個考慮事項：</span><span class="sxs-lookup"><span data-stu-id="116c7-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="116c7-107">**僅 IPv4**    因為世界用完了 IPv4 位址，所以已建立 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="116c7-108">最後，我們會完全支援全球的 IPv6，但目前，您的企業可能需要與其通訊的許多公司和裝置都不支援 IPv6，而且可能不是一段時間。</span><span class="sxs-lookup"><span data-stu-id="116c7-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="116c7-109">僅限 IPv4 的設定會協助確保您的 Lync Server 實施可以與大多數的現有裝置進行通訊。</span><span class="sxs-lookup"><span data-stu-id="116c7-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="116c7-110">**僅 IPv6**    相反地，完整的 IPv6 的實施方式，會排除與許多現有裝置的通訊。</span><span class="sxs-lookup"><span data-stu-id="116c7-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="116c7-111">**雙重堆疊**    雙堆疊是一種同時啟用 IPv4 和 IPv6 位址的網路。</span><span class="sxs-lookup"><span data-stu-id="116c7-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="116c7-112">Lync Server 2013 支援此設定，因為在大多數情況下，從完整 IPv4 轉換為完整 IPv6 會需要數年。</span><span class="sxs-lookup"><span data-stu-id="116c7-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="116c7-113">下列各節將說明各種 Lync Server 功能的這三個設定之間的相容性。</span><span class="sxs-lookup"><span data-stu-id="116c7-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="116c7-114">只有實驗室或驗證目的才支援用戶端或伺服器設定只支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="116c7-115">在實際執行部署中，不支援只有設定 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="116c7-116">用戶端註冊</span><span class="sxs-lookup"><span data-stu-id="116c7-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116c7-117">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="116c7-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="116c7-118">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="116c7-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116c7-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-122">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-123">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-125">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-126">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-127">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-130">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="116c7-133">Peer-to-Peer 用戶端</span><span class="sxs-lookup"><span data-stu-id="116c7-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="116c7-134">對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="116c7-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="116c7-135">這兩個用戶端都成功註冊後，支援下列組合。</span><span class="sxs-lookup"><span data-stu-id="116c7-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116c7-136">用戶端端點1</span><span class="sxs-lookup"><span data-stu-id="116c7-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="116c7-137">用戶端端點2</span><span class="sxs-lookup"><span data-stu-id="116c7-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116c7-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-141">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-142">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-143">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-145">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="116c7-148">會議</span><span class="sxs-lookup"><span data-stu-id="116c7-148">Conferencing</span></span>

<span data-ttu-id="116c7-149">會議包含音訊/視頻、應用程式共用，以及資料共同作業 (白板和檔案共用) 。</span><span class="sxs-lookup"><span data-stu-id="116c7-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116c7-150">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="116c7-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="116c7-151">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="116c7-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116c7-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-155">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-156">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-158">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-159">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-160">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-163">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="116c7-166">轉送伺服器/PSTN</span><span class="sxs-lookup"><span data-stu-id="116c7-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="116c7-167">Lync Server 2013 不支援公用交換電話網路 (PSTN) 通話的媒體旁路，如果流量是透過 IPv6 介面。</span><span class="sxs-lookup"><span data-stu-id="116c7-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="116c7-168">如果需要媒體旁路，建議將 PSTN 閘道設定為 IPv4。</span><span class="sxs-lookup"><span data-stu-id="116c7-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116c7-169">主要介面 \*</span><span class="sxs-lookup"><span data-stu-id="116c7-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="116c7-170">轉送伺服器上的 PSTN 介面 () </span><span class="sxs-lookup"><span data-stu-id="116c7-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="116c7-171">PSTN 閘道設定</span><span class="sxs-lookup"><span data-stu-id="116c7-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116c7-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-173">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-175">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-176">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-178">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-179">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116c7-181">\* 主要介面是與 Lync Server 元件通訊的介面。</span><span class="sxs-lookup"><span data-stu-id="116c7-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="116c7-182">遠端使用者 Peer-to-Peer 通訊</span><span class="sxs-lookup"><span data-stu-id="116c7-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="116c7-183">與遠端使用者的對等通訊包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="116c7-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="116c7-184">遠端使用者網路</span><span class="sxs-lookup"><span data-stu-id="116c7-184">Remote user network</span></span></th>
<th><span data-ttu-id="116c7-185">Edge server (外部 edge) </span><span class="sxs-lookup"><span data-stu-id="116c7-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="116c7-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="116c7-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-188">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="116c7-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-190">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="116c7-191">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-193">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="116c7-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="116c7-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="116c7-196">前端集區和 Edge 集區設定</span><span class="sxs-lookup"><span data-stu-id="116c7-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="116c7-197">下表顯示前端伺服器集區和內部 Edge Server 集區之間的支援矩陣。</span><span class="sxs-lookup"><span data-stu-id="116c7-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="116c7-198">前端集區和 Edge 集區 (內部 Edge) 矩陣</span><span class="sxs-lookup"><span data-stu-id="116c7-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="116c7-199"><strong>Edge 集區： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-200"><strong>Edge 集區：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-201"><strong>Edge 集區： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-202"><strong>前端集區： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-203">是</span><span class="sxs-lookup"><span data-stu-id="116c7-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-204">是</span><span class="sxs-lookup"><span data-stu-id="116c7-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-205">否</span><span class="sxs-lookup"><span data-stu-id="116c7-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-206"><strong>前端集區：雙棧</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-207">是</span><span class="sxs-lookup"><span data-stu-id="116c7-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-208">是</span><span class="sxs-lookup"><span data-stu-id="116c7-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-209">否</span><span class="sxs-lookup"><span data-stu-id="116c7-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-210"><strong>前端集區： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-211">否</span><span class="sxs-lookup"><span data-stu-id="116c7-211">No</span></span></p></td>
<td><p><span data-ttu-id="116c7-212">否</span><span class="sxs-lookup"><span data-stu-id="116c7-212">No</span></span></p></td>
<td><p><span data-ttu-id="116c7-213">是\*</span><span class="sxs-lookup"><span data-stu-id="116c7-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116c7-214">\* 僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="116c7-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="116c7-215">下表是支援的內部和外部 edge 介面組合的矩陣。</span><span class="sxs-lookup"><span data-stu-id="116c7-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="116c7-216">Edge 集區 (內部 Edge) 和 Edge 集區 (外部 Edge) 矩陣</span><span class="sxs-lookup"><span data-stu-id="116c7-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="116c7-217"><strong>Edge 集區 (外部 Edge) ： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-218"><strong>Edge 集區 (外部 Edge) ：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-219"><strong>Edge 集區 (外部 Edge) ： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-220"><strong>Edge 集區 (內部 Edge) ： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-221">是</span><span class="sxs-lookup"><span data-stu-id="116c7-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-222">是</span><span class="sxs-lookup"><span data-stu-id="116c7-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-223">否</span><span class="sxs-lookup"><span data-stu-id="116c7-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="116c7-224"><strong>Edge 集區 (內部 Edge) ：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-225">否</span><span class="sxs-lookup"><span data-stu-id="116c7-225">No</span></span></p></td>
<td><p><span data-ttu-id="116c7-226">是</span><span class="sxs-lookup"><span data-stu-id="116c7-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="116c7-227">否</span><span class="sxs-lookup"><span data-stu-id="116c7-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="116c7-228"><strong>Edge 集區 (內部 Edge) ： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="116c7-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="116c7-229">否</span><span class="sxs-lookup"><span data-stu-id="116c7-229">No</span></span></p></td>
<td><p><span data-ttu-id="116c7-230">否</span><span class="sxs-lookup"><span data-stu-id="116c7-230">No</span></span></p></td>
<td><p><span data-ttu-id="116c7-231">是\*</span><span class="sxs-lookup"><span data-stu-id="116c7-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="116c7-232">\* 僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="116c7-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="116c7-233">IPv6 的高級 Enterprise 語音支援</span><span class="sxs-lookup"><span data-stu-id="116c7-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="116c7-234">包含通話許可控制的部署 (CAC) 、增強型 9-1-1 (E9-1-1) 或媒體旁路，都必須設定為 IPv4 或雙堆疊式的執行。</span><span class="sxs-lookup"><span data-stu-id="116c7-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="116c7-235">在雙堆疊部署中，即使 Lync 用戶端使用 IPv6 連接至 Lync 伺服器，Lync 也會盡力對應適當的 IPv4 位址，以支援 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="116c7-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="116c7-236">不支援使用 IPv6 位址的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="116c7-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="116c7-237">Exchange 整合通訊 (UM) 不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="116c7-238">若為 Exchange UM，請確定 DNS 解析不會傳回 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="116c7-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="116c7-239">在來電傳送至語音信箱時，使用 IPv6 可能會造成失敗。</span><span class="sxs-lookup"><span data-stu-id="116c7-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="116c7-240">其他 Lync Server 2013 功能支援 IPv6</span><span class="sxs-lookup"><span data-stu-id="116c7-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="116c7-241">除了先前所述的功能和元件，Lync Server 2013 還支援下列功能的 IPv6：</span><span class="sxs-lookup"><span data-stu-id="116c7-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="116c7-242">**常設聊天室**</span><span class="sxs-lookup"><span data-stu-id="116c7-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="116c7-243">您可以使用拓撲產生器，設定持續聊天的 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="116c7-244">如需設定持續性聊天的詳細資訊，請參閱部署 Persistent Chat Server 檔。</span><span class="sxs-lookup"><span data-stu-id="116c7-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="116c7-245">**經驗品質 (QoE) 和詳細通話記錄 (CDR) 報告**</span><span class="sxs-lookup"><span data-stu-id="116c7-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="116c7-246">監控報告包含的 IP 位址會儲存在監控伺服器資料庫中，不論其類型是 IPv4 還是 IPv6。</span><span class="sxs-lookup"><span data-stu-id="116c7-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

