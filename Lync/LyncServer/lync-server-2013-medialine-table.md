---
title: Lync Server 2013： MediaLine 表格
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
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516140"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="94402-102">Lync Server 2013 中的 MediaLine 表格</span><span class="sxs-lookup"><span data-stu-id="94402-102">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94402-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="94402-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="94402-104">每筆記錄代表一個媒體行。</span><span class="sxs-lookup"><span data-stu-id="94402-104">Each record represents one media line.</span></span> <span data-ttu-id="94402-105"> (一個音訊會話通常會包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="94402-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="94402-106">一個音訊和影片 (A/V) 會話通常會包含一個音訊媒體線和一個影片媒體線，但如果使用會議裝置或使用畫廊 View，則會話可能會包含兩個影片媒體線。</span><span class="sxs-lookup"><span data-stu-id="94402-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94402-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="94402-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="94402-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="94402-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="94402-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="94402-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="94402-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="94402-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94402-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="94402-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-112">datetime</span><span class="sxs-lookup"><span data-stu-id="94402-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="94402-113">主要</span><span class="sxs-lookup"><span data-stu-id="94402-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="94402-114">從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="94402-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-116">int</span><span class="sxs-lookup"><span data-stu-id="94402-116">int</span></span></p></td>
<td><p><span data-ttu-id="94402-117">主要</span><span class="sxs-lookup"><span data-stu-id="94402-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="94402-118">從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="94402-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="94402-121">主要</span><span class="sxs-lookup"><span data-stu-id="94402-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="94402-122">0為主要音訊、1為主要影片，2是全景影片，3是應用程式/桌面共用。</span><span class="sxs-lookup"><span data-stu-id="94402-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="94402-123">此標籤在單一會話中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="94402-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="94402-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-125">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-126">此欄存在，但未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="94402-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="94402-127">CallerConnectivityICE 和 CalleeConnectivityICE 欄中已捕獲用於媒體線之連線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="94402-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="94402-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-129">int</span><span class="sxs-lookup"><span data-stu-id="94402-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-130">有關互動式連線建立 (冰) 程式的資訊，請參閱 bits 旗中所述的處理常式。</span><span class="sxs-lookup"><span data-stu-id="94402-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="94402-131">如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</span><span class="sxs-lookup"><span data-stu-id="94402-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="94402-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-133">int</span><span class="sxs-lookup"><span data-stu-id="94402-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-134">與 CallerIceWarningFlags 相同，但在被呼叫者的一端。</span><span class="sxs-lookup"><span data-stu-id="94402-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="94402-135">如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</span><span class="sxs-lookup"><span data-stu-id="94402-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-136"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="94402-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-137">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-138">使用中的安全性設定檔。</span><span class="sxs-lookup"><span data-stu-id="94402-138">The security profile in use.</span></span> <span data-ttu-id="94402-139">0 是無 (NONE)，1 是 SRTP，2 是 V1。</span><span class="sxs-lookup"><span data-stu-id="94402-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-140"><strong>傳輸</strong></span><span class="sxs-lookup"><span data-stu-id="94402-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-141">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-142">0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="94402-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-144">int</span><span class="sxs-lookup"><span data-stu-id="94402-144">int</span></span></p></td>
<td><p><span data-ttu-id="94402-145">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-146">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-146">IP Address of the caller.</span></span> <span data-ttu-id="94402-147">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="94402-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-149">int</span><span class="sxs-lookup"><span data-stu-id="94402-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-150">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="94402-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="94402-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-152">int</span><span class="sxs-lookup"><span data-stu-id="94402-152">int</span></span></p></td>
<td><p><span data-ttu-id="94402-153"> 外國</span><span class="sxs-lookup"><span data-stu-id="94402-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-154">來電者的子網。</span><span class="sxs-lookup"><span data-stu-id="94402-154">The subnet of the caller.</span></span> <span data-ttu-id="94402-155">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="94402-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-157">位</span><span class="sxs-lookup"><span data-stu-id="94402-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-158">1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="94402-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="94402-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-160">int</span><span class="sxs-lookup"><span data-stu-id="94402-160">int</span></span></p></td>
<td><p><span data-ttu-id="94402-161">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-162">來電者的 mac 位址（從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照）。</span><span class="sxs-lookup"><span data-stu-id="94402-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-164">int</span><span class="sxs-lookup"><span data-stu-id="94402-164">int</span></span></p></td>
<td><p><span data-ttu-id="94402-165">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-166">呼叫者使用之 Lync Server A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="94402-167">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="94402-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-169">int</span><span class="sxs-lookup"><span data-stu-id="94402-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-170">呼叫者在 A/V Edge service 上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="94402-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="94402-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-172">int</span><span class="sxs-lookup"><span data-stu-id="94402-172">int</span></span></p></td>
<td><p><span data-ttu-id="94402-173">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-174">呼叫者使用的捕獲裝置。</span><span class="sxs-lookup"><span data-stu-id="94402-174">Capture device used by the caller.</span></span> <span data-ttu-id="94402-175">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="94402-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-177">int</span><span class="sxs-lookup"><span data-stu-id="94402-177">int</span></span></p></td>
<td><p><span data-ttu-id="94402-178">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-179">由來電者使用的呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="94402-179">Render device used by caller.</span></span> <span data-ttu-id="94402-180">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="94402-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-182">int</span><span class="sxs-lookup"><span data-stu-id="94402-182">int</span></span></p></td>
<td><p><span data-ttu-id="94402-183">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-184">呼叫者的捕獲裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="94402-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-186">int</span><span class="sxs-lookup"><span data-stu-id="94402-186">int</span></span></p></td>
<td><p><span data-ttu-id="94402-187">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-188">呼叫者的轉譯裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="94402-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-190">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="94402-191">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-192">會指出來電者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="94402-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="94402-193"><a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。</span><span class="sxs-lookup"><span data-stu-id="94402-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="94402-194">一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</span><span class="sxs-lookup"><span data-stu-id="94402-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="94402-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-196">int</span><span class="sxs-lookup"><span data-stu-id="94402-196">int</span></span></p></td>
<td><p><span data-ttu-id="94402-197">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-198">使用無線時的來電者 BSSID。</span><span class="sxs-lookup"><span data-stu-id="94402-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="94402-199"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="94402-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-201">位</span><span class="sxs-lookup"><span data-stu-id="94402-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-202">來電者的連結。</span><span class="sxs-lookup"><span data-stu-id="94402-202">The caller's link.</span></span> <span data-ttu-id="94402-203">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="94402-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="94402-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-205">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="94402-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-206">來電者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="94402-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-208">int</span><span class="sxs-lookup"><span data-stu-id="94402-208">int</span></span></p></td>
<td><p><span data-ttu-id="94402-209">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-210">通話接收器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-210">IP Address of the call receiver.</span></span> <span data-ttu-id="94402-211">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="94402-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-213">位</span><span class="sxs-lookup"><span data-stu-id="94402-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-214">呼叫接收器使用的埠。</span><span class="sxs-lookup"><span data-stu-id="94402-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="94402-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-216">int</span><span class="sxs-lookup"><span data-stu-id="94402-216">int</span></span></p></td>
<td><p><span data-ttu-id="94402-217">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-218">被呼叫者的子網。</span><span class="sxs-lookup"><span data-stu-id="94402-218">Subnet of callee.</span></span> <span data-ttu-id="94402-219">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="94402-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-221">位</span><span class="sxs-lookup"><span data-stu-id="94402-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-222">1表示呼叫接收器位於商業網路內，0表示通話接收器位於網路外。</span><span class="sxs-lookup"><span data-stu-id="94402-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="94402-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-224">int</span><span class="sxs-lookup"><span data-stu-id="94402-224">int</span></span></p></td>
<td><p><span data-ttu-id="94402-225">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-226">被呼叫者的 Mac 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-226">Callee Mac address.</span></span> <span data-ttu-id="94402-227">從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-229">int</span><span class="sxs-lookup"><span data-stu-id="94402-229">int</span></span></p></td>
<td><p><span data-ttu-id="94402-230">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-231">呼叫接收器所使用之 A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="94402-232">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="94402-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="94402-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-234">int</span><span class="sxs-lookup"><span data-stu-id="94402-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-235">呼叫接收器在 A/V Edge Service 上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="94402-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="94402-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-237">int</span><span class="sxs-lookup"><span data-stu-id="94402-237">int</span></span></p></td>
<td><p><span data-ttu-id="94402-238">外國</span><span class="sxs-lookup"><span data-stu-id="94402-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-239">用於呼叫接收器的捕獲裝置。</span><span class="sxs-lookup"><span data-stu-id="94402-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="94402-240">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="94402-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-242">int</span><span class="sxs-lookup"><span data-stu-id="94402-242">int</span></span></p></td>
<td><p><span data-ttu-id="94402-243">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-244">會呈現呼叫接收器所使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="94402-244">Render device used by the call receiver.</span></span> <span data-ttu-id="94402-245">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="94402-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-247">int</span><span class="sxs-lookup"><span data-stu-id="94402-247">int</span></span></p></td>
<td><p><span data-ttu-id="94402-248">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-249">呼叫接收器的捕獲裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="94402-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="94402-250"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="94402-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-252">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="94402-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="94402-253">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-254">呼叫接收器的呈現裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="94402-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="94402-255"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="94402-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-257">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="94402-258">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-259">會指出被呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="94402-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="94402-260"><a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。</span><span class="sxs-lookup"><span data-stu-id="94402-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="94402-261">一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</span><span class="sxs-lookup"><span data-stu-id="94402-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="94402-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-263">int</span><span class="sxs-lookup"><span data-stu-id="94402-263">int</span></span></p></td>
<td><p><span data-ttu-id="94402-264">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-265">使用無線時，被呼叫者的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="94402-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="94402-266"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="94402-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="94402-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-268">位</span><span class="sxs-lookup"><span data-stu-id="94402-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-269">通話接收器的連結;1是虛擬私人網路 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="94402-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="94402-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-271">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="94402-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-272">通話接收器端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="94402-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="94402-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-274">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="94402-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-275">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="94402-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="94402-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-277">int</span><span class="sxs-lookup"><span data-stu-id="94402-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-278">這是套用至指定之傳送端資料流程的實際頻寬，指定各種原則設定 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="94402-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="94402-279">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="94402-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="94402-280">基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="94402-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="94402-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-282">Smallint</span><span class="sxs-lookup"><span data-stu-id="94402-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-283">這是所採用的頻寬容量來源。</span><span class="sxs-lookup"><span data-stu-id="94402-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="94402-284">它說明頻寬限制來自 ( "Policy Server"、"輪流伺服器"、"模態" 等) 。</span><span class="sxs-lookup"><span data-stu-id="94402-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="94402-285">從 <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="94402-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="94402-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-287">位</span><span class="sxs-lookup"><span data-stu-id="94402-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-288">會指出是否已收到來自來電者的計量值;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="94402-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-289"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="94402-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-290">位</span><span class="sxs-lookup"><span data-stu-id="94402-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="94402-291">會指出是否已收到來自呼叫接收器的計量值;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="94402-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="94402-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-293">位</span><span class="sxs-lookup"><span data-stu-id="94402-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-294">會指出報表是針對會話的一部分，還是完整的會話。</span><span class="sxs-lookup"><span data-stu-id="94402-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="94402-295">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="94402-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-297">位</span><span class="sxs-lookup"><span data-stu-id="94402-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-298">會指出呼叫是否分類為 (1) 或良好通話 (0) 的通話是否不良。</span><span class="sxs-lookup"><span data-stu-id="94402-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="94402-299">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="94402-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="94402-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-302">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="94402-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="94402-303">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="94402-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-305">Tinyint</span><span class="sxs-lookup"><span data-stu-id="94402-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="94402-306">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="94402-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="94402-307">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-309">int</span><span class="sxs-lookup"><span data-stu-id="94402-309">int</span></span></p></td>
<td><p><span data-ttu-id="94402-310">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-311">撥打電話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="94402-312">在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="94402-313">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="94402-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-315">int</span><span class="sxs-lookup"><span data-stu-id="94402-315">int</span></span></p></td>
<td><p><span data-ttu-id="94402-316">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-317">撥打通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="94402-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="94402-318">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="94402-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-320">int</span><span class="sxs-lookup"><span data-stu-id="94402-320">int</span></span></p></td>
<td><p><span data-ttu-id="94402-321">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-322">撥打通話之使用者所使用 WiFi 驅動程式的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="94402-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="94402-323">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="94402-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-325">int</span><span class="sxs-lookup"><span data-stu-id="94402-325">int</span></span></p></td>
<td><p><span data-ttu-id="94402-326">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-327">接收通話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="94402-328">在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="94402-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="94402-329">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94402-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="94402-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-331">int</span><span class="sxs-lookup"><span data-stu-id="94402-331">int</span></span></p></td>
<td><p><span data-ttu-id="94402-332">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-333">接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="94402-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="94402-334">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94402-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="94402-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="94402-336">int</span><span class="sxs-lookup"><span data-stu-id="94402-336">int</span></span></p></td>
<td><p><span data-ttu-id="94402-337">Foreign</span><span class="sxs-lookup"><span data-stu-id="94402-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="94402-338">接收通話之使用者所使用 WiFi 驅動程式的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="94402-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="94402-339">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="94402-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

