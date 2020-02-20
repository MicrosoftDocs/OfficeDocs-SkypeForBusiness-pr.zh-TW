---
title: 'Lync Server 2013: IP 位址類型概觀'
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
ms.openlocfilehash: 975aa4a81b4e44cc20fdbfda946f901610a1b484
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="74634-102">Lync Server 2013 的 IP 位址類型概觀</span><span class="sxs-lookup"><span data-stu-id="74634-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74634-103">_**上次修改主題：** 2013年-01-29_</span><span class="sxs-lookup"><span data-stu-id="74634-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="74634-104">在 Lync Server 2013 中設定 IP 位址時，您會有三個選項。</span><span class="sxs-lookup"><span data-stu-id="74634-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="74634-105">您可以設定 Lync Server 2013 到支援 IP 版本 4 (IPv4)，唯一 IP 第 6 版 (IPv6)，或兩者的組合 （又稱為*雙重堆疊*）。</span><span class="sxs-lookup"><span data-stu-id="74634-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="74634-106">有幾個問題，考慮每種類型的設定：</span><span class="sxs-lookup"><span data-stu-id="74634-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="74634-107">**僅限 IPv4**   建立 IPv6，因為在世界用盡 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="74634-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="74634-108">最後，全球，但這次完全支援 IPv6，許多公司和您的企業可能需要與通訊的裝置還不支援 IPv6，並可能不適用於一些時間。</span><span class="sxs-lookup"><span data-stu-id="74634-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="74634-109">僅 IPv4 的設定有助於確保您實作可以與彼此大多數現有裝置的 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="74634-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="74634-110">**僅限 IPv6**   反之，完整的 IPv6 實作在這個階段中，將排除的通訊與許多現有裝置。</span><span class="sxs-lookup"><span data-stu-id="74634-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="74634-111">**雙重堆疊**   雙重堆疊是獲 IPv4 與 IPv6 位址的網路。</span><span class="sxs-lookup"><span data-stu-id="74634-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="74634-112">Lync Server 2013 中支援此組態，因為在大多數情況下從完整 IPv4 轉換為完整 IPv6 會花幾年。</span><span class="sxs-lookup"><span data-stu-id="74634-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="74634-113">下列各節概述這三種組態之各種 Lync Server 功能之間的相容性。</span><span class="sxs-lookup"><span data-stu-id="74634-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74634-114">使用 IPv6 的用戶端或伺服器設定只支援僅供實驗室或驗證之用。</span><span class="sxs-lookup"><span data-stu-id="74634-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="74634-115">在實際執行部署中不支援 IPv6 唯一組態。</span><span class="sxs-lookup"><span data-stu-id="74634-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="74634-116">用戶端登錄</span><span class="sxs-lookup"><span data-stu-id="74634-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74634-117">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="74634-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="74634-118">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="74634-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74634-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-122">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-123">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-125">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-126">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-127">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-130">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="74634-133">端對端用戶端</span><span class="sxs-lookup"><span data-stu-id="74634-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="74634-134">對等通訊包含音訊、 音訊/視訊、 應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="74634-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="74634-135">這兩種用戶端已成功註冊後，支援下列的組合。</span><span class="sxs-lookup"><span data-stu-id="74634-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74634-136">用戶端端點 1</span><span class="sxs-lookup"><span data-stu-id="74634-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="74634-137">用戶端端點 2</span><span class="sxs-lookup"><span data-stu-id="74634-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74634-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-141">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-142">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-143">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-145">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="74634-148">會議</span><span class="sxs-lookup"><span data-stu-id="74634-148">Conferencing</span></span>

<span data-ttu-id="74634-149">會議包含音訊/視訊、 應用程式共用，以及資料共同作業 （白板與檔案共用）。</span><span class="sxs-lookup"><span data-stu-id="74634-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74634-150">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="74634-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="74634-151">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="74634-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74634-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-155">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-156">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-158">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-159">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-160">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-163">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="74634-166">中繼伺服器 PSTN</span><span class="sxs-lookup"><span data-stu-id="74634-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="74634-167">Lync Server 2013 不支援媒體旁路的公用交換的電話網路 (PSTN) 通話如果流量是透過 IPv6 的介面。</span><span class="sxs-lookup"><span data-stu-id="74634-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="74634-168">如果需要媒體旁路，我們建議的 PSTN 閘道設為 IPv4。</span><span class="sxs-lookup"><span data-stu-id="74634-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74634-169">主要介面 \*</span><span class="sxs-lookup"><span data-stu-id="74634-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="74634-170">PSTN 介面 （中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="74634-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="74634-171">PSTN 閘道設定</span><span class="sxs-lookup"><span data-stu-id="74634-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74634-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-173">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-175">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-176">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-178">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-179">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74634-181">\*主要介面是與 Lync Server 元件進行通訊的介面。</span><span class="sxs-lookup"><span data-stu-id="74634-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="74634-182">遠端使用者對等通訊</span><span class="sxs-lookup"><span data-stu-id="74634-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="74634-183">與遠端使用者的對等通訊包含立即訊息、 音訊/視訊、 應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="74634-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74634-184">遠端使用者網路</span><span class="sxs-lookup"><span data-stu-id="74634-184">Remote user network</span></span></th>
<th><span data-ttu-id="74634-185">Edge server (外部 edge)</span><span class="sxs-lookup"><span data-stu-id="74634-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74634-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="74634-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-188">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="74634-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-190">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="74634-191">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-193">雙重堆疊</span><span class="sxs-lookup"><span data-stu-id="74634-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="74634-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="74634-196">前端集區與 Edge 集區組態</span><span class="sxs-lookup"><span data-stu-id="74634-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="74634-197">下表顯示的前端伺服器集區和內部 Edge Server 集區的支援矩陣。</span><span class="sxs-lookup"><span data-stu-id="74634-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="74634-198">前端集區與 Edge 集區 (內部 Edge) 矩陣</span><span class="sxs-lookup"><span data-stu-id="74634-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="74634-199"><strong>Edge 集區： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="74634-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-200"><strong>Edge 集區： 雙重堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="74634-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-201"><strong>Edge 集區： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="74634-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-202"><strong>前端集區： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="74634-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-203">是</span><span class="sxs-lookup"><span data-stu-id="74634-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-204">是</span><span class="sxs-lookup"><span data-stu-id="74634-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-205">否</span><span class="sxs-lookup"><span data-stu-id="74634-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-206"><strong>前端集區： 雙重堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="74634-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-207">是</span><span class="sxs-lookup"><span data-stu-id="74634-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-208">是</span><span class="sxs-lookup"><span data-stu-id="74634-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-209">否</span><span class="sxs-lookup"><span data-stu-id="74634-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-210"><strong>前端集區： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="74634-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-211">否</span><span class="sxs-lookup"><span data-stu-id="74634-211">No</span></span></p></td>
<td><p><span data-ttu-id="74634-212">否</span><span class="sxs-lookup"><span data-stu-id="74634-212">No</span></span></p></td>
<td><p><span data-ttu-id="74634-213">是\*</span><span class="sxs-lookup"><span data-stu-id="74634-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74634-214">\*使用此組合僅在實驗室環境中。</span><span class="sxs-lookup"><span data-stu-id="74634-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="74634-215">下表是內部和外部 edge 介面的支援組合矩陣。</span><span class="sxs-lookup"><span data-stu-id="74634-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="74634-216">Edge 集區 (內部 Edge) 與 Edge 集區 (外部 Edge) 矩陣</span><span class="sxs-lookup"><span data-stu-id="74634-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="74634-217"><strong>Edge 集區 (外部 Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="74634-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-218"><strong>Edge 集區 (外部 Edge): 雙重堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="74634-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-219"><strong>Edge 集區 (外部 Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="74634-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-220"><strong>Edge 集區 (內部 Edge): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="74634-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-221">是</span><span class="sxs-lookup"><span data-stu-id="74634-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-222">是</span><span class="sxs-lookup"><span data-stu-id="74634-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-223">否</span><span class="sxs-lookup"><span data-stu-id="74634-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74634-224"><strong>Edge 集區 (內部 Edge): 雙重堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="74634-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-225">否</span><span class="sxs-lookup"><span data-stu-id="74634-225">No</span></span></p></td>
<td><p><span data-ttu-id="74634-226">是</span><span class="sxs-lookup"><span data-stu-id="74634-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="74634-227">否</span><span class="sxs-lookup"><span data-stu-id="74634-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74634-228"><strong>Edge 集區 (內部 Edge): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="74634-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="74634-229">否</span><span class="sxs-lookup"><span data-stu-id="74634-229">No</span></span></p></td>
<td><p><span data-ttu-id="74634-230">否</span><span class="sxs-lookup"><span data-stu-id="74634-230">No</span></span></p></td>
<td><p><span data-ttu-id="74634-231">是\*</span><span class="sxs-lookup"><span data-stu-id="74634-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74634-232">\*使用此組合僅在實驗室環境中。</span><span class="sxs-lookup"><span data-stu-id="74634-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="74634-233">進階 Enterprise Voice 支援 IPv6</span><span class="sxs-lookup"><span data-stu-id="74634-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="74634-234">部署，包括通話許可控制 (CAC)、 增強型 9-1-1 (E9-1-1) 或媒體旁路必須設定為 IPv4 僅或雙重堆疊實作。</span><span class="sxs-lookup"><span data-stu-id="74634-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74634-235">在雙重堆疊部署中，即使使用 IPv6，Lync 用戶端連線至 Lync Server Lync 將盡可能對應適當的 IPv4 位址，以支援 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="74634-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="74634-236">不支援透過 IPv6 位址的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="74634-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="74634-237">Exchange 整合通訊 (UM) 不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="74634-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="74634-238">對於 Exchange UM，請務必 DNS 解析不會傳回 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="74634-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="74634-239">來電傳送至語音信箱時，使用 IPv6 將導致失敗。</span><span class="sxs-lookup"><span data-stu-id="74634-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="74634-240">其他 Lync Server 2013 支援的 IPv6 功能</span><span class="sxs-lookup"><span data-stu-id="74634-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="74634-241">除了的功能和元件先前所述，Lync Server 2013 支援 IPv6 的下列功能：</span><span class="sxs-lookup"><span data-stu-id="74634-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="74634-242">**常設聊天室**</span><span class="sxs-lookup"><span data-stu-id="74634-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="74634-243">您使用拓撲產生器設定 IPv6 的常設聊天室。</span><span class="sxs-lookup"><span data-stu-id="74634-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="74634-244">如需設定常設聊天室的詳細資訊，請參閱 < Deploying Persistent Chat Server 文件。</span><span class="sxs-lookup"><span data-stu-id="74634-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="74634-245">**品質經驗 (QoE) 與詳細通話記錄 (CDR) 報告**</span><span class="sxs-lookup"><span data-stu-id="74634-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="74634-246">監控報告包含的 IP 位址是儲存在監控伺服器資料庫中，是否的 IPv4 或 IPv6。</span><span class="sxs-lookup"><span data-stu-id="74634-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

