---
title: Lync Server 2013：MediaLine 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="d8544-102">Lync Server 2013 中的 MediaLine 表格</span><span class="sxs-lookup"><span data-stu-id="d8544-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8544-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="d8544-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="d8544-104">每個記錄代表一個媒體線。</span><span class="sxs-lookup"><span data-stu-id="d8544-104">Each record represents one media line.</span></span> <span data-ttu-id="d8544-105">（一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="d8544-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="d8544-106">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個視頻媒體線，但如果是使用會議裝置或使用了圖庫視圖，該會話可能包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="d8544-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8544-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d8544-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d8544-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d8544-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8544-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d8544-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8544-113">首選</span><span class="sxs-lookup"><span data-stu-id="d8544-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8544-114"><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="d8544-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-116">int</span><span class="sxs-lookup"><span data-stu-id="d8544-116">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-117">首選</span><span class="sxs-lookup"><span data-stu-id="d8544-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8544-118"><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="d8544-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8544-121">首選</span><span class="sxs-lookup"><span data-stu-id="d8544-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="d8544-122">0為主要音訊，1為主要影片，2為全景影片，3為應用程式/桌面共用。</span><span class="sxs-lookup"><span data-stu-id="d8544-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="d8544-123">這個標籤在單一會話中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d8544-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-125">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-126">此欄存在，但在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="d8544-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d8544-127">在 CallerConnectivityICE 和 CalleeConnectivityICE 欄中，會捕獲針對媒體線使用之連線性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d8544-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-129">int</span><span class="sxs-lookup"><span data-stu-id="d8544-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-130">有關在 bits 標誌中描述的互動式連接建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d8544-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="d8544-131">如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</span><span class="sxs-lookup"><span data-stu-id="d8544-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-133">int</span><span class="sxs-lookup"><span data-stu-id="d8544-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-134">與 CallerIceWarningFlags 相同，但在被呼叫方端的那一側。</span><span class="sxs-lookup"><span data-stu-id="d8544-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="d8544-135">如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</span><span class="sxs-lookup"><span data-stu-id="d8544-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-136"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-137">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-138">使用中的安全性設定檔。</span><span class="sxs-lookup"><span data-stu-id="d8544-138">The security profile in use.</span></span> <span data-ttu-id="d8544-139">0為 [無]，1為 SRTP，2為 V1。</span><span class="sxs-lookup"><span data-stu-id="d8544-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-140"><strong>傳輸</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-141">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-142">0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="d8544-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-144">int</span><span class="sxs-lookup"><span data-stu-id="d8544-144">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-145">外</span><span class="sxs-lookup"><span data-stu-id="d8544-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-146">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-146">IP Address of the caller.</span></span> <span data-ttu-id="d8544-147">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-149">int</span><span class="sxs-lookup"><span data-stu-id="d8544-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-150">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d8544-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-152">int</span><span class="sxs-lookup"><span data-stu-id="d8544-152">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-153"> 外</span><span class="sxs-lookup"><span data-stu-id="d8544-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-154">來電者的子網。</span><span class="sxs-lookup"><span data-stu-id="d8544-154">The subnet of the caller.</span></span> <span data-ttu-id="d8544-155">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-157">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-158">1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="d8544-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-160">int</span><span class="sxs-lookup"><span data-stu-id="d8544-160">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-161">外</span><span class="sxs-lookup"><span data-stu-id="d8544-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-162">來電者的 mac 位址，從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-164">int</span><span class="sxs-lookup"><span data-stu-id="d8544-164">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-165">外</span><span class="sxs-lookup"><span data-stu-id="d8544-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-166">呼叫者使用的 Lync Server A/V 邊緣服務 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="d8544-167">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-169">int</span><span class="sxs-lookup"><span data-stu-id="d8544-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-170">呼叫者在 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d8544-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-172">int</span><span class="sxs-lookup"><span data-stu-id="d8544-172">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-173">外</span><span class="sxs-lookup"><span data-stu-id="d8544-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-174">呼叫者使用的擷取裝置。</span><span class="sxs-lookup"><span data-stu-id="d8544-174">Capture device used by the caller.</span></span> <span data-ttu-id="d8544-175">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-177">int</span><span class="sxs-lookup"><span data-stu-id="d8544-177">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-178">外</span><span class="sxs-lookup"><span data-stu-id="d8544-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-179">由呼叫者使用的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="d8544-179">Render device used by caller.</span></span> <span data-ttu-id="d8544-180">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-182">int</span><span class="sxs-lookup"><span data-stu-id="d8544-182">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-183">外</span><span class="sxs-lookup"><span data-stu-id="d8544-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-184">呼叫者的捕獲裝置驅動程式（從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用）。</span><span class="sxs-lookup"><span data-stu-id="d8544-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-186">int</span><span class="sxs-lookup"><span data-stu-id="d8544-186">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-187">外</span><span class="sxs-lookup"><span data-stu-id="d8544-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-188">呼叫者轉譯裝置的驅動程式，從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-190">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8544-191">外</span><span class="sxs-lookup"><span data-stu-id="d8544-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-192">指出呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="d8544-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="d8544-193">值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。</span><span class="sxs-lookup"><span data-stu-id="d8544-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d8544-194">對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</span><span class="sxs-lookup"><span data-stu-id="d8544-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-196">int</span><span class="sxs-lookup"><span data-stu-id="d8544-196">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-197">外</span><span class="sxs-lookup"><span data-stu-id="d8544-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-198">呼叫者的 BSSID （如果使用無線）。</span><span class="sxs-lookup"><span data-stu-id="d8544-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="d8544-199">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-201">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-202">來電者的連結。</span><span class="sxs-lookup"><span data-stu-id="d8544-202">The caller's link.</span></span> <span data-ttu-id="d8544-203">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="d8544-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-205">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="d8544-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-206">呼叫者終點的網路連結速度（以 bps 為來）。</span><span class="sxs-lookup"><span data-stu-id="d8544-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-208">int</span><span class="sxs-lookup"><span data-stu-id="d8544-208">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-209">外</span><span class="sxs-lookup"><span data-stu-id="d8544-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-210">呼叫接收器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-210">IP Address of the call receiver.</span></span> <span data-ttu-id="d8544-211">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-213">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-214">呼叫接收器使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d8544-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-216">int</span><span class="sxs-lookup"><span data-stu-id="d8544-216">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-217">外</span><span class="sxs-lookup"><span data-stu-id="d8544-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-218">被呼叫者的子網。</span><span class="sxs-lookup"><span data-stu-id="d8544-218">Subnet of callee.</span></span> <span data-ttu-id="d8544-219">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-221">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-222">1代表呼叫接收器在商業網路內，0代表呼叫接收器在網路以外。</span><span class="sxs-lookup"><span data-stu-id="d8544-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-224">int</span><span class="sxs-lookup"><span data-stu-id="d8544-224">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-225">外</span><span class="sxs-lookup"><span data-stu-id="d8544-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-226">被呼叫者的 Mac 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-226">Callee Mac address.</span></span> <span data-ttu-id="d8544-227">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="d8544-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-229">int</span><span class="sxs-lookup"><span data-stu-id="d8544-229">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-230">外</span><span class="sxs-lookup"><span data-stu-id="d8544-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-231">呼叫接收器所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="d8544-232">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="d8544-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-234">int</span><span class="sxs-lookup"><span data-stu-id="d8544-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-235">由呼叫接收器在 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="d8544-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-237">int</span><span class="sxs-lookup"><span data-stu-id="d8544-237">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-238">外</span><span class="sxs-lookup"><span data-stu-id="d8544-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-239">捕獲呼叫接收器使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="d8544-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="d8544-240">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-242">int</span><span class="sxs-lookup"><span data-stu-id="d8544-242">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-243">外</span><span class="sxs-lookup"><span data-stu-id="d8544-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-244">呼叫接收器所使用的轉譯裝置。</span><span class="sxs-lookup"><span data-stu-id="d8544-244">Render device used by the call receiver.</span></span> <span data-ttu-id="d8544-245">從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-247">int</span><span class="sxs-lookup"><span data-stu-id="d8544-247">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-248">外</span><span class="sxs-lookup"><span data-stu-id="d8544-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-249">呼叫接收器的擷取裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d8544-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="d8544-250">從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-252">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="d8544-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8544-253">外</span><span class="sxs-lookup"><span data-stu-id="d8544-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-254">呼叫接收器的轉譯裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d8544-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="d8544-255">從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-257">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8544-258">外</span><span class="sxs-lookup"><span data-stu-id="d8544-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-259">表示被呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="d8544-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="d8544-260">值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。</span><span class="sxs-lookup"><span data-stu-id="d8544-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d8544-261">對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</span><span class="sxs-lookup"><span data-stu-id="d8544-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-263">int</span><span class="sxs-lookup"><span data-stu-id="d8544-263">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-264">外</span><span class="sxs-lookup"><span data-stu-id="d8544-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-265">被呼叫者的 BSSID （如果使用無線）。</span><span class="sxs-lookup"><span data-stu-id="d8544-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="d8544-266">從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="d8544-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-268">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-269">呼叫接收器的連結;1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="d8544-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-271">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="d8544-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-272">呼叫接收器終點的網路連結速度，以 bps 為限。</span><span class="sxs-lookup"><span data-stu-id="d8544-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-274">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="d8544-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-275">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="d8544-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-277">int</span><span class="sxs-lookup"><span data-stu-id="d8544-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-278">這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="d8544-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="d8544-279">這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="d8544-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="d8544-280">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="d8544-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-282">Smallint</span><span class="sxs-lookup"><span data-stu-id="d8544-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-283">這是強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="d8544-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="d8544-284">它描述頻寬限制的來源： [原則伺服器]、[轉換伺服器]、[模態] 等等。</span><span class="sxs-lookup"><span data-stu-id="d8544-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="d8544-285">從<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="d8544-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-286"><strong>呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-287">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-288">指出來自來電者的統計資料是否已收到;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="d8544-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-289"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-290">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d8544-291">指出是否已收到來自呼叫接收器的指標;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="d8544-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-293">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-294">指出報告是針對會話的一部分或完整的會話。</span><span class="sxs-lookup"><span data-stu-id="d8544-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="d8544-295">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-297">稍微</span><span class="sxs-lookup"><span data-stu-id="d8544-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-298">指出通話是分類為不佳通話（值為1）或良好通話（0）。</span><span class="sxs-lookup"><span data-stu-id="d8544-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="d8544-299">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="d8544-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-302">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="d8544-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="d8544-303">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-305">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d8544-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8544-306">指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</span><span class="sxs-lookup"><span data-stu-id="d8544-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="d8544-307">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-309">int</span><span class="sxs-lookup"><span data-stu-id="d8544-309">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-310">外</span><span class="sxs-lookup"><span data-stu-id="d8544-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-311">撥打電話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="d8544-312">在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="d8544-313">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-315">int</span><span class="sxs-lookup"><span data-stu-id="d8544-315">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-316">外</span><span class="sxs-lookup"><span data-stu-id="d8544-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-317">撥打電話之使用者所採用的 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="d8544-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="d8544-318">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-320">int</span><span class="sxs-lookup"><span data-stu-id="d8544-320">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-321">外</span><span class="sxs-lookup"><span data-stu-id="d8544-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-322">撥打電話之使用者所採用的 WiFi 驅動程式版本號碼。</span><span class="sxs-lookup"><span data-stu-id="d8544-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="d8544-323">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-325">int</span><span class="sxs-lookup"><span data-stu-id="d8544-325">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-326">外</span><span class="sxs-lookup"><span data-stu-id="d8544-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-327">接收通話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="d8544-328">在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d8544-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="d8544-329">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8544-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-331">int</span><span class="sxs-lookup"><span data-stu-id="d8544-331">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-332">外</span><span class="sxs-lookup"><span data-stu-id="d8544-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-333">接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="d8544-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="d8544-334">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8544-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d8544-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d8544-336">int</span><span class="sxs-lookup"><span data-stu-id="d8544-336">int</span></span></p></td>
<td><p><span data-ttu-id="d8544-337">外</span><span class="sxs-lookup"><span data-stu-id="d8544-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d8544-338">接收通話之使用者所使用的 WiFi 驅動程式版本號碼。</span><span class="sxs-lookup"><span data-stu-id="d8544-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="d8544-339">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d8544-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

