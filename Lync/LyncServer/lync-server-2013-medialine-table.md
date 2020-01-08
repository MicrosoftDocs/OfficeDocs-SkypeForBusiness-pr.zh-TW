---
title: Lync Server 2013：MediaLine 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="71f4a-102">Lync Server 2013 中的 MediaLine 表格</span><span class="sxs-lookup"><span data-stu-id="71f4a-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f4a-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="71f4a-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="71f4a-104">每個記錄代表一個媒體線。</span><span class="sxs-lookup"><span data-stu-id="71f4a-104">Each record represents one media line.</span></span> <span data-ttu-id="71f4a-105">（一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="71f4a-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="71f4a-106">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個視頻媒體線，但如果是使用會議裝置或使用了圖庫視圖，該會話可能包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="71f4a-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71f4a-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="71f4a-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="71f4a-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="71f4a-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="71f4a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="71f4a-113">首選</span><span class="sxs-lookup"><span data-stu-id="71f4a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="71f4a-114"><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="71f4a-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-116">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-116">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-117">首選</span><span class="sxs-lookup"><span data-stu-id="71f4a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="71f4a-118"><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="71f4a-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71f4a-121">首選</span><span class="sxs-lookup"><span data-stu-id="71f4a-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="71f4a-122">0為主要音訊，1為主要影片，2為全景影片，3為應用程式/桌面共用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="71f4a-123">這個標籤在單一會話中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="71f4a-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-125">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-126">此欄存在，但在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="71f4a-127">在 CallerConnectivityICE 和 CalleeConnectivityICE 欄中，會捕獲針對媒體線使用之連線性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="71f4a-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-129">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-130">有關在 bits 標誌中描述的互動式連接建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="71f4a-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="71f4a-131">如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-133">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-134">與 CallerIceWarningFlags 相同，但在被呼叫方端的那一側。</span><span class="sxs-lookup"><span data-stu-id="71f4a-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="71f4a-135">如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-136"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-137">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-138">使用中的安全性設定檔。</span><span class="sxs-lookup"><span data-stu-id="71f4a-138">The security profile in use.</span></span> <span data-ttu-id="71f4a-139">0為 [無]，1為 SRTP，2為 V1。</span><span class="sxs-lookup"><span data-stu-id="71f4a-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-140"><strong>傳輸</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-141">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-142">0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="71f4a-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-144">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-144">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-145">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-146">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-146">IP Address of the caller.</span></span> <span data-ttu-id="71f4a-147">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-149">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-150">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="71f4a-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-152">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-152">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-153"> 外</span><span class="sxs-lookup"><span data-stu-id="71f4a-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-154">來電者的子網。</span><span class="sxs-lookup"><span data-stu-id="71f4a-154">The subnet of the caller.</span></span> <span data-ttu-id="71f4a-155">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-157">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-158">1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="71f4a-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-160">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-160">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-161">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-162">來電者的 mac 位址，從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-164">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-164">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-165">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-166">呼叫者使用的 Lync Server A/V 邊緣服務 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="71f4a-167">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-169">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-170">呼叫者在 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="71f4a-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-172">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-172">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-173">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-174">呼叫者使用的擷取裝置。</span><span class="sxs-lookup"><span data-stu-id="71f4a-174">Capture device used by the caller.</span></span> <span data-ttu-id="71f4a-175">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-177">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-177">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-178">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-179">由呼叫者使用的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="71f4a-179">Render device used by caller.</span></span> <span data-ttu-id="71f4a-180">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-182">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-182">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-183">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-184">呼叫者的捕獲裝置驅動程式（從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-186">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-186">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-187">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-188">呼叫者轉譯裝置的驅動程式，從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-190">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71f4a-191">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-192">指出呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="71f4a-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="71f4a-193">值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。</span><span class="sxs-lookup"><span data-stu-id="71f4a-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="71f4a-194">對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</span><span class="sxs-lookup"><span data-stu-id="71f4a-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-196">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-196">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-197">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-198">呼叫者的 BSSID （如果使用無線）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="71f4a-199">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-201">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-202">來電者的連結。</span><span class="sxs-lookup"><span data-stu-id="71f4a-202">The caller's link.</span></span> <span data-ttu-id="71f4a-203">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="71f4a-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-205">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="71f4a-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-206">呼叫者終點的網路連結速度（以 bps 為來）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-208">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-208">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-209">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-210">呼叫接收器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-210">IP Address of the call receiver.</span></span> <span data-ttu-id="71f4a-211">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-213">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-214">呼叫接收器使用的埠。</span><span class="sxs-lookup"><span data-stu-id="71f4a-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-216">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-216">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-217">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-218">被呼叫者的子網。</span><span class="sxs-lookup"><span data-stu-id="71f4a-218">Subnet of callee.</span></span> <span data-ttu-id="71f4a-219">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-221">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-222">1代表呼叫接收器在商業網路內，0代表呼叫接收器在網路以外。</span><span class="sxs-lookup"><span data-stu-id="71f4a-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-224">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-224">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-225">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-226">被呼叫者的 Mac 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-226">Callee Mac address.</span></span> <span data-ttu-id="71f4a-227">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="71f4a-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-229">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-229">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-230">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-231">呼叫接收器所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="71f4a-232">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="71f4a-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-234">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-235">由呼叫接收器在 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="71f4a-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-237">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-237">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-238">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-239">捕獲呼叫接收器使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="71f4a-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="71f4a-240">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-242">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-242">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-243">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-244">呼叫接收器所使用的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="71f4a-244">Render device used by the call receiver.</span></span> <span data-ttu-id="71f4a-245">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-247">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-247">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-248">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-249">呼叫接收器的擷取裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="71f4a-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="71f4a-250">從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-252">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="71f4a-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71f4a-253">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-254">呼叫接收器的轉譯裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="71f4a-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="71f4a-255">從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-257">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="71f4a-258">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-259">表示被呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="71f4a-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="71f4a-260">值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。</span><span class="sxs-lookup"><span data-stu-id="71f4a-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="71f4a-261">對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</span><span class="sxs-lookup"><span data-stu-id="71f4a-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-263">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-263">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-264">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-265">被呼叫者的 BSSID （如果使用無線）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="71f4a-266">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="71f4a-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-268">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-269">呼叫接收器的連結;1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="71f4a-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-271">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="71f4a-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-272">呼叫接收器終點的網路連結速度，以 bps 為限。</span><span class="sxs-lookup"><span data-stu-id="71f4a-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-274">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="71f4a-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-275">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-277">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-278">這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="71f4a-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="71f4a-279">這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="71f4a-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="71f4a-280">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="71f4a-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-282">Smallint</span><span class="sxs-lookup"><span data-stu-id="71f4a-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-283">這是強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="71f4a-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="71f4a-284">它描述頻寬限制的來源： [原則伺服器]、[轉換伺服器]、[模態] 等等。</span><span class="sxs-lookup"><span data-stu-id="71f4a-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="71f4a-285">從<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="71f4a-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-286"><strong>呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-287">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-288">指出來自來電者的統計資料是否已收到;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="71f4a-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-289"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-290">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="71f4a-291">指出是否已收到來自呼叫接收器的指標;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="71f4a-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-293">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-294">指出報告是針對會話的一部分或完整的會話。</span><span class="sxs-lookup"><span data-stu-id="71f4a-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="71f4a-295">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-297">稍微</span><span class="sxs-lookup"><span data-stu-id="71f4a-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-298">指出通話是分類為不佳通話（值為1）或良好通話（0）。</span><span class="sxs-lookup"><span data-stu-id="71f4a-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="71f4a-299">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="71f4a-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-302">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="71f4a-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="71f4a-303">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-305">Tinyint</span><span class="sxs-lookup"><span data-stu-id="71f4a-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="71f4a-306">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="71f4a-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="71f4a-307">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-309">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-309">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-310">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-311">撥打電話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="71f4a-312">在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="71f4a-313">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-315">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-315">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-316">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-317">撥打電話之使用者所採用的 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="71f4a-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="71f4a-318">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-320">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-320">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-321">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-322">撥打電話之使用者所採用的 WiFi 驅動程式版本號碼。</span><span class="sxs-lookup"><span data-stu-id="71f4a-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="71f4a-323">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-325">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-325">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-326">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-327">接收通話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="71f4a-328">在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="71f4a-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="71f4a-329">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71f4a-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-331">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-331">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-332">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-333">接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="71f4a-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="71f4a-334">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71f4a-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="71f4a-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="71f4a-336">int</span><span class="sxs-lookup"><span data-stu-id="71f4a-336">int</span></span></p></td>
<td><p><span data-ttu-id="71f4a-337">外</span><span class="sxs-lookup"><span data-stu-id="71f4a-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="71f4a-338">接收通話之使用者所使用的 WiFi 驅動程式版本號碼。</span><span class="sxs-lookup"><span data-stu-id="71f4a-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="71f4a-339">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="71f4a-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

