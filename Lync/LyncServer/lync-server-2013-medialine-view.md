---
title: Lync Server 2013： MediaLine view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="3fbe9-102">Lync Server 2013 中的 [MediaLine] 視圖</span><span class="sxs-lookup"><span data-stu-id="3fbe9-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fbe9-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3fbe9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3fbe9-104">[MediaLine] 視圖會儲存資料庫中每個媒體線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="3fbe9-105">一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="3fbe9-106">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個影片媒體線;不過，如果使用會議裝置或使用圖庫視圖，該會話可能會包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="3fbe9-107">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fbe9-108">左欄</span><span class="sxs-lookup"><span data-stu-id="3fbe9-108">Column</span></span></th>
<th><span data-ttu-id="3fbe9-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="3fbe9-109">Data Type</span></span></th>
<th><span data-ttu-id="3fbe9-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3fbe9-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="3fbe9-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3fbe9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="3fbe9-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-115">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-115">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-116">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="3fbe9-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-118">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3fbe9-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-119">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3fbe9-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-121">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-121">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-122">針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="3fbe9-123">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="3fbe9-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-125">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-125">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-126">針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="3fbe9-127">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-128">安全性</span><span class="sxs-lookup"><span data-stu-id="3fbe9-128">Security</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-129">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3fbe9-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-130">安全設定檔正在使用中。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-130">Security profile in use.</span></span> <span data-ttu-id="3fbe9-131">0為 [無]，1為 SRTP，2為 V1。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-132">傳輸</span><span class="sxs-lookup"><span data-stu-id="3fbe9-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-133">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3fbe9-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-134">傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-134">Transport type.</span></span> <span data-ttu-id="3fbe9-135">0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-137">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-138">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-138">IP address of the caller.</span></span> <span data-ttu-id="3fbe9-139">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="3fbe9-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-141">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-141">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-142">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="3fbe9-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-144">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-144">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-145">指出來電者是否在組織網路內。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="3fbe9-146">1表示呼叫者是在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="3fbe9-147">0代表呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="3fbe9-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-149">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-150">呼叫者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-152">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-153">呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="3fbe9-154">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3fbe9-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-156">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-156">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-157">呼叫者使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-159">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-160">由 A/V 邊緣服務報告的呼叫者 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3fbe9-161">此位址可能會與 CallerIPAddr （例如，如果用戶端位於 NAT 之後）不同。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3fbe9-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-163">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-164">來電者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="3fbe9-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-166">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-167">來電者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3fbe9-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-169">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-170">來電者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3fbe9-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-172">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-173">來電者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3fbe9-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-175">Varchar （256</span><span class="sxs-lookup"><span data-stu-id="3fbe9-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-176">呼叫者的 Wifi 驅動程式描述。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3fbe9-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-178">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-179">呼叫者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3fbe9-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-181">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-182">呼叫者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-182">Details of caller’s network connection.</span></span> <span data-ttu-id="3fbe9-183">如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="3fbe9-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-185">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-186">呼叫者 WiFi 連線所使用的基本服務組識別元。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="3fbe9-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-188">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-188">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-189">指出呼叫者是否已經由虛擬專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="3fbe9-190">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-192">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-193">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-193">IP address of the callee.</span></span> <span data-ttu-id="3fbe9-194">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="3fbe9-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-196">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-196">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-197">被呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="3fbe9-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-199">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-199">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-200">指出被呼叫者是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="3fbe9-201">1代表被呼叫者是在商業網路內，0代表被呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="3fbe9-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-203">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-204">被呼叫者使用的網路介面 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-206">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-207">被呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="3fbe9-208">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="3fbe9-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-210">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-210">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-211">在被呼叫者所使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="3fbe9-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-213">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-214">被呼叫者的 IP 位址，由 A/V 邊緣服務所報告。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="3fbe9-215">此位址可能會與 CalleeIPAddr （例如，如果用戶端位於 NAT 之後）不同。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="3fbe9-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-217">var （50）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-218">被呼叫者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="3fbe9-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-220">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-221">被呼叫者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="3fbe9-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-223">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-224">被呼叫者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="3fbe9-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-226">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-227">被呼叫者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="3fbe9-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-229">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-230">被呼叫者的 Wifi 驅動程式描述。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="3fbe9-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-232">Varchar （256</span><span class="sxs-lookup"><span data-stu-id="3fbe9-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-233">被呼叫者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="3fbe9-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-235">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-236">被呼叫者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-236">Details of callee’s network connection.</span></span> <span data-ttu-id="3fbe9-237">如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="3fbe9-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-239">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-240">被呼叫者的 WiFi 連線所使用的基本服務組識別元。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="3fbe9-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-242">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-242">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-243">指出被呼叫者是否已經由虛擬私人網路絡進行連線。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="3fbe9-244">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="3fbe9-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-246">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-247">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="3fbe9-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-249">int</span><span class="sxs-lookup"><span data-stu-id="3fbe9-249">int</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-250">這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="3fbe9-251">您應該不要將它與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="3fbe9-252">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="3fbe9-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-254">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3fbe9-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-255">強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="3fbe9-256">它描述頻寬限制的來源（例如，「原則伺服器」、「轉換伺服器」或「模態」）。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-257">呼叫</span><span class="sxs-lookup"><span data-stu-id="3fbe9-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-258">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-258">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-259">指出來自來電者的統計資料是否已收到;1為 [是]，0為 [否]。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-260">方</span><span class="sxs-lookup"><span data-stu-id="3fbe9-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-261">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-261">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-262">指出是否已收到來自呼叫接收器的指標;1為 [是]，0為 [否]。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="3fbe9-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-264">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-264">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-265">指出報告是用於通話的一部分還是完全通話。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="3fbe9-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-267">稍微</span><span class="sxs-lookup"><span data-stu-id="3fbe9-267">bit</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-268">指出通話是分類為不佳通話（1），或作為良好通話（0）。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fbe9-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3fbe9-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-270">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3fbe9-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-271">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fbe9-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="3fbe9-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-273">Tinyint</span><span class="sxs-lookup"><span data-stu-id="3fbe9-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3fbe9-274">指示使用者是否使用 ICE 通訊協定（網際網路連線建立）與網路連線。</span><span class="sxs-lookup"><span data-stu-id="3fbe9-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

