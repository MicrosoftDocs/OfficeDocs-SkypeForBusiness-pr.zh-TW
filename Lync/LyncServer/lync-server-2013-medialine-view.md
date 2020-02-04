---
title: Lync Server 2013： MediaLine view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="5a3bb-102">Lync Server 2013 中的 [MediaLine] 視圖</span><span class="sxs-lookup"><span data-stu-id="5a3bb-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a3bb-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5a3bb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5a3bb-104">[MediaLine] 視圖會儲存資料庫中每個媒體線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="5a3bb-105">一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="5a3bb-106">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個影片媒體線;不過，如果使用會議裝置或使用圖庫視圖，該會話可能會包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="5a3bb-107">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a3bb-108">左欄</span><span class="sxs-lookup"><span data-stu-id="5a3bb-108">Column</span></span></th>
<th><span data-ttu-id="5a3bb-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="5a3bb-109">Data Type</span></span></th>
<th><span data-ttu-id="5a3bb-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="5a3bb-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="5a3bb-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5a3bb-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="5a3bb-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-115">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-115">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-116">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="5a3bb-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-118">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3bb-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-119">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5a3bb-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-121">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-121">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-122">針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="5a3bb-123">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5a3bb-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-125">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-125">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-126">針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="5a3bb-127">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-128">安全性</span><span class="sxs-lookup"><span data-stu-id="5a3bb-128">Security</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-129">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3bb-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-130">安全設定檔正在使用中。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-130">Security profile in use.</span></span> <span data-ttu-id="5a3bb-131">0為 [無]，1為 SRTP，2為 V1。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-132">傳輸</span><span class="sxs-lookup"><span data-stu-id="5a3bb-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-133">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3bb-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-134">傳輸類型。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-134">Transport type.</span></span> <span data-ttu-id="5a3bb-135">0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-137">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-138">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-138">IP address of the caller.</span></span> <span data-ttu-id="5a3bb-139">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="5a3bb-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-141">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-141">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-142">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="5a3bb-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-144">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-144">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-145">指出來電者是否在組織網路內。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="5a3bb-146">1表示呼叫者是在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="5a3bb-147">0代表呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="5a3bb-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-149">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-150">呼叫者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-152">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-153">呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="5a3bb-154">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5a3bb-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-156">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-156">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-157">呼叫者使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-159">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-160">由 A/V 邊緣服務報告的呼叫者 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="5a3bb-161">此位址可能會與 CallerIPAddr （例如，如果用戶端位於 NAT 之後）不同。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5a3bb-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-163">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-164">來電者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="5a3bb-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-166">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-167">來電者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5a3bb-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-169">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-170">來電者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5a3bb-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-172">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-173">來電者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="5a3bb-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-175">Varchar （256</span><span class="sxs-lookup"><span data-stu-id="5a3bb-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-176">呼叫者的 Wifi 驅動程式描述。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="5a3bb-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-178">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-179">呼叫者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="5a3bb-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-181">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-182">呼叫者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-182">Details of caller’s network connection.</span></span> <span data-ttu-id="5a3bb-183">如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="5a3bb-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-185">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-186">呼叫者 WiFi 連線所使用的基本服務組識別元。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="5a3bb-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-188">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-188">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-189">指出呼叫者是否已經由虛擬專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="5a3bb-190">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-192">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-193">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-193">IP address of the callee.</span></span> <span data-ttu-id="5a3bb-194">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="5a3bb-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-196">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-196">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-197">被呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="5a3bb-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-199">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-199">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-200">指出被呼叫者是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="5a3bb-201">1代表被呼叫者是在商業網路內，0代表被呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="5a3bb-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-203">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-204">被呼叫者使用的網路介面 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-206">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-207">被呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="5a3bb-208">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5a3bb-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-210">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-210">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-211">在被呼叫者所使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="5a3bb-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-213">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-214">被呼叫者的 IP 位址，由 A/V 邊緣服務所報告。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="5a3bb-215">此位址可能會與 CalleeIPAddr （例如，如果用戶端位於 NAT 之後）不同。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5a3bb-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-217">var （50）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-218">被呼叫者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="5a3bb-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-220">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-221">被呼叫者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5a3bb-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-223">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-224">被呼叫者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5a3bb-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-226">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-227">被呼叫者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="5a3bb-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-229">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-230">被呼叫者的 Wifi 驅動程式描述。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="5a3bb-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-232">Varchar （256</span><span class="sxs-lookup"><span data-stu-id="5a3bb-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-233">被呼叫者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="5a3bb-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-235">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-236">被呼叫者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-236">Details of callee’s network connection.</span></span> <span data-ttu-id="5a3bb-237">如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="5a3bb-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-239">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-240">被呼叫者的 WiFi 連線所使用的基本服務組識別元。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="5a3bb-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-242">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-242">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-243">指出被呼叫者是否已經由虛擬私人網路絡進行連線。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="5a3bb-244">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="5a3bb-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-246">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-247">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="5a3bb-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-249">int</span><span class="sxs-lookup"><span data-stu-id="5a3bb-249">int</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-250">這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="5a3bb-251">您應該不要將它與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="5a3bb-252">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="5a3bb-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-254">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="5a3bb-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-255">強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="5a3bb-256">它描述頻寬限制的來源（例如，「原則伺服器」、「轉換伺服器」或「模態」）。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-257">呼叫</span><span class="sxs-lookup"><span data-stu-id="5a3bb-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-258">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-258">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-259">指出來自來電者的統計資料是否已收到;1為 [是]，0為 [否]。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-260">方</span><span class="sxs-lookup"><span data-stu-id="5a3bb-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-261">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-261">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-262">指出是否已收到來自呼叫接收器的指標;1為 [是]，0為 [否]。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="5a3bb-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-264">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-264">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-265">指出報告是用於通話的一部分還是完全通話。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="5a3bb-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-267">稍微</span><span class="sxs-lookup"><span data-stu-id="5a3bb-267">bit</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-268">指出通話是分類為不佳通話（1），或作為良好通話（0）。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a3bb-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="5a3bb-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-270">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3bb-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-271">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a3bb-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="5a3bb-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-273">Tinyint</span><span class="sxs-lookup"><span data-stu-id="5a3bb-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5a3bb-274">指示使用者是否使用 ICE 通訊協定（網際網路連線建立）與網路連線。</span><span class="sxs-lookup"><span data-stu-id="5a3bb-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

