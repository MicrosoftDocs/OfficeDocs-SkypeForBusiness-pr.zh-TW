---
title: Lync Server 2013：IP 位址類型概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="7320a-102">Lync Server 2013 的 IP 位址類型概觀</span><span class="sxs-lookup"><span data-stu-id="7320a-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7320a-103">_**主題上次修改日期：** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="7320a-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="7320a-104">在 Lync Server 2013 中設定 IP 位址時，有三個選項可供您選擇。</span><span class="sxs-lookup"><span data-stu-id="7320a-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="7320a-105">您可以設定 Lync Server 2013，只支援 IP 版本4（IPv4）、僅限 IP 版本6（IPv6），或兩者的組合（稱為*雙堆疊*）。</span><span class="sxs-lookup"><span data-stu-id="7320a-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="7320a-106">每個類型的設定都要考慮幾個問題：</span><span class="sxs-lookup"><span data-stu-id="7320a-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="7320a-107">\*\*\*\*    已建立僅 ipv4 IPv6，因為世界的 ipv4 位址不在正常運作。</span><span class="sxs-lookup"><span data-stu-id="7320a-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="7320a-108">我們最終會在全球完全支援 IPv6，但在這段時間，您企業可能需要與之通訊的許多公司和裝置都不支援 IPv6，而且可能不需要一段時間。</span><span class="sxs-lookup"><span data-stu-id="7320a-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="7320a-109">僅提供 IPv4 的設定將有助於確保您的 Lync 伺服器實現可以與大多數現有的裝置通訊。</span><span class="sxs-lookup"><span data-stu-id="7320a-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="7320a-110">**僅 ipv6 相反**   ，目前的完整 ipv6 實現會排除與許多現有裝置的通訊。</span><span class="sxs-lookup"><span data-stu-id="7320a-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="7320a-111">**雙堆疊**   雙堆疊是啟用 IPv4 和 IPv6 位址的網路。</span><span class="sxs-lookup"><span data-stu-id="7320a-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="7320a-112">Lync Server 2013 支援此設定，因為在大多數情況下，從完整 IPv4 轉換到完整 IPv6 時，將需要幾年的時間。</span><span class="sxs-lookup"><span data-stu-id="7320a-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="7320a-113">下列各節概述各種 Lync Server 功能在這三種設定中的相容性。</span><span class="sxs-lookup"><span data-stu-id="7320a-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7320a-114">只有在 lab 或驗證目的中，才支援僅含 IPv6 的用戶端或伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="7320a-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="7320a-115">生產部署中不支援僅限 IPv6 的配置。</span><span class="sxs-lookup"><span data-stu-id="7320a-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="7320a-116">用戶端註冊</span><span class="sxs-lookup"><span data-stu-id="7320a-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7320a-117">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="7320a-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="7320a-118">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="7320a-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7320a-119">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-120">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-121">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-122">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-123">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-124">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-125">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-126">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-127">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-130">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="7320a-133">對等用戶端</span><span class="sxs-lookup"><span data-stu-id="7320a-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="7320a-134">對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="7320a-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="7320a-135">在兩個用戶端都成功註冊之後，就支援下列組合。</span><span class="sxs-lookup"><span data-stu-id="7320a-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7320a-136">用戶端端點1</span><span class="sxs-lookup"><span data-stu-id="7320a-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="7320a-137">用戶端端點2</span><span class="sxs-lookup"><span data-stu-id="7320a-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7320a-138">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-139">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-140">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-141">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-142">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-143">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-145">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="7320a-148">會議</span><span class="sxs-lookup"><span data-stu-id="7320a-148">Conferencing</span></span>

<span data-ttu-id="7320a-149">會議包括音訊/視頻、應用程式共用和資料共同作業（whiteboarding 與檔案共用）。</span><span class="sxs-lookup"><span data-stu-id="7320a-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7320a-150">用戶端端點網路</span><span class="sxs-lookup"><span data-stu-id="7320a-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="7320a-151">伺服器網路</span><span class="sxs-lookup"><span data-stu-id="7320a-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7320a-152">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-153">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-154">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-155">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-156">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-157">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-158">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-159">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-160">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-163">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="7320a-166">中繼伺服器/PSTN</span><span class="sxs-lookup"><span data-stu-id="7320a-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="7320a-167">如果通信量是透過 IPv6 介面，Lync Server 2013 不支援公用交換電話網絡（PSTN）通話的媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7320a-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="7320a-168">如果需要媒體旁路，建議 PSTN 閘道設定為 IPv4。</span><span class="sxs-lookup"><span data-stu-id="7320a-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7320a-169">主要介面 \*</span><span class="sxs-lookup"><span data-stu-id="7320a-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="7320a-170">PSTN 介面（在中繼伺服器上）</span><span class="sxs-lookup"><span data-stu-id="7320a-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="7320a-171">PSTN 閘道設定</span><span class="sxs-lookup"><span data-stu-id="7320a-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7320a-172">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-173">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-174">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-175">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-176">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-177">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-178">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-179">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7320a-181">\*主要介面是與 Lync 伺服器元件進行通訊的介面。</span><span class="sxs-lookup"><span data-stu-id="7320a-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="7320a-182">遠端使用者對等通訊</span><span class="sxs-lookup"><span data-stu-id="7320a-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="7320a-183">與遠端使用者進行對等通訊時，包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="7320a-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7320a-184">遠端使用者網路</span><span class="sxs-lookup"><span data-stu-id="7320a-184">Remote user network</span></span></th>
<th><span data-ttu-id="7320a-185">Edge 伺服器（外部邊緣）</span><span class="sxs-lookup"><span data-stu-id="7320a-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7320a-186">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="7320a-187">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-188">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-189">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="7320a-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-190">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="7320a-191">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-193">雙堆疊</span><span class="sxs-lookup"><span data-stu-id="7320a-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="7320a-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="7320a-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="7320a-196">前臺端池和邊緣池設定</span><span class="sxs-lookup"><span data-stu-id="7320a-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="7320a-197">下表顯示前端伺服器池與內部邊緣伺服器池之間的支援矩陣。</span><span class="sxs-lookup"><span data-stu-id="7320a-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="7320a-198">前端池與邊緣池（內部邊緣）矩陣</span><span class="sxs-lookup"><span data-stu-id="7320a-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="7320a-199"><strong>Edge 池： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-200"><strong>Edge 池：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-201"><strong>Edge 池： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-202"><strong>前端池： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-203">是</span><span class="sxs-lookup"><span data-stu-id="7320a-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-204">是</span><span class="sxs-lookup"><span data-stu-id="7320a-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-205">否</span><span class="sxs-lookup"><span data-stu-id="7320a-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-206"><strong>前部端池：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-207">是</span><span class="sxs-lookup"><span data-stu-id="7320a-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-208">是</span><span class="sxs-lookup"><span data-stu-id="7320a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-209">否</span><span class="sxs-lookup"><span data-stu-id="7320a-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-210"><strong>前臺端池： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-211">否</span><span class="sxs-lookup"><span data-stu-id="7320a-211">No</span></span></p></td>
<td><p><span data-ttu-id="7320a-212">否</span><span class="sxs-lookup"><span data-stu-id="7320a-212">No</span></span></p></td>
<td><p><span data-ttu-id="7320a-213">否</span><span class="sxs-lookup"><span data-stu-id="7320a-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7320a-214">\*僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="7320a-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="7320a-215">下表是支援的內部和外部邊緣介面組合的矩陣。</span><span class="sxs-lookup"><span data-stu-id="7320a-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="7320a-216">Edge 池（內部邊緣）與邊緣池（外部邊緣）矩陣</span><span class="sxs-lookup"><span data-stu-id="7320a-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="7320a-217"><strong>Edge 池（外部邊緣）： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-218"><strong>Edge 池（外部邊緣）：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-219"><strong>Edge 池（外部邊緣）： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-220"><strong>Edge 池（內部邊緣）： IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-221">是</span><span class="sxs-lookup"><span data-stu-id="7320a-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-222">是</span><span class="sxs-lookup"><span data-stu-id="7320a-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-223">否</span><span class="sxs-lookup"><span data-stu-id="7320a-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7320a-224"><strong>Edge 池（內部邊緣）：雙堆疊</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-225">否</span><span class="sxs-lookup"><span data-stu-id="7320a-225">No</span></span></p></td>
<td><p><span data-ttu-id="7320a-226">是</span><span class="sxs-lookup"><span data-stu-id="7320a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="7320a-227">否</span><span class="sxs-lookup"><span data-stu-id="7320a-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7320a-228"><strong>Edge 池（內部邊緣）： IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="7320a-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="7320a-229">否</span><span class="sxs-lookup"><span data-stu-id="7320a-229">No</span></span></p></td>
<td><p><span data-ttu-id="7320a-230">否</span><span class="sxs-lookup"><span data-stu-id="7320a-230">No</span></span></p></td>
<td><p><span data-ttu-id="7320a-231">否</span><span class="sxs-lookup"><span data-stu-id="7320a-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7320a-232">\*僅在實驗室環境中使用此組合。</span><span class="sxs-lookup"><span data-stu-id="7320a-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="7320a-233">針對 IPv6 的高級企業語音支援</span><span class="sxs-lookup"><span data-stu-id="7320a-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="7320a-234">包括 [呼叫許可控制（CAC）]、[增強9-1-1 （E9-1）] 或 [媒體旁路] 的部署，必須設定為僅使用 IPv4 或雙堆疊式實現。</span><span class="sxs-lookup"><span data-stu-id="7320a-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7320a-235">在雙堆疊式部署中，即使 Lync 用戶端使用 IPv6 連線至 Lync Server，Lync 也會盡最佳努力，將適當的 IPv4 位址對應至支援 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="7320a-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="7320a-236">不支援含 IPv6 位址的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="7320a-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="7320a-237">Exchange 整合通訊（UM）不支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="7320a-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="7320a-238">針對 Exchange UM，請確定 DNS 解析沒有傳回 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="7320a-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="7320a-239">使用 IPv6 可能會在來電傳送至語音信箱時造成失敗。</span><span class="sxs-lookup"><span data-stu-id="7320a-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="7320a-240">其他適用于 IPv6 的 Lync Server 2013 功能支援</span><span class="sxs-lookup"><span data-stu-id="7320a-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="7320a-241">除了先前提及的功能和元件之外，Lync Server 2013 還支援 IPv6 以執行下列功能：</span><span class="sxs-lookup"><span data-stu-id="7320a-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="7320a-242">**常設聊天室**</span><span class="sxs-lookup"><span data-stu-id="7320a-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="7320a-243">您可以使用拓撲建立器，將 IPv6 設定成持續聊天。</span><span class="sxs-lookup"><span data-stu-id="7320a-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="7320a-244">如需有關設定持續聊天的詳細資訊，請參閱部署持久聊天伺服器檔。</span><span class="sxs-lookup"><span data-stu-id="7320a-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="7320a-245">**經驗品質（QoE）和通話詳細資料錄製（CDR）報告**</span><span class="sxs-lookup"><span data-stu-id="7320a-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="7320a-246">無論是 IPv4 或 IPv6 類型，監視報告都包含儲存在監視伺服器資料庫的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7320a-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

