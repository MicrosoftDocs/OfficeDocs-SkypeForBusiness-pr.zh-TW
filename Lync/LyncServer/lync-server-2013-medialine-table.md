---
title: Lync Server 2013： MediaLine 表格
description: Lync Server 2013： MediaLine 表格。
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572109"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="a004b-103">Lync Server 2013 中的 MediaLine 表格</span><span class="sxs-lookup"><span data-stu-id="a004b-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a004b-104">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="a004b-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="a004b-105">每筆記錄代表一個媒體行。</span><span class="sxs-lookup"><span data-stu-id="a004b-105">Each record represents one media line.</span></span> <span data-ttu-id="a004b-106"> (一個音訊會話通常會包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="a004b-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="a004b-107">一個音訊和影片 (A/V) 會話通常會包含一個音訊媒體線和一個影片媒體線，但如果使用會議裝置或使用畫廊 View，則會話可能會包含兩個影片媒體線。</span><span class="sxs-lookup"><span data-stu-id="a004b-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a004b-108"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a004b-109"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a004b-110"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a004b-111"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a004b-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a004b-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="a004b-114">主要</span><span class="sxs-lookup"><span data-stu-id="a004b-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="a004b-115">從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-117">int</span><span class="sxs-lookup"><span data-stu-id="a004b-117">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-118">主要</span><span class="sxs-lookup"><span data-stu-id="a004b-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="a004b-119">從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-121">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a004b-122">主要</span><span class="sxs-lookup"><span data-stu-id="a004b-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="a004b-123">0為主要音訊、1為主要影片，2是全景影片，3是應用程式/桌面共用。</span><span class="sxs-lookup"><span data-stu-id="a004b-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="a004b-124">此標籤在單一會話中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a004b-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-126">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-127">此欄存在，但未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a004b-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a004b-128">CallerConnectivityICE 和 CalleeConnectivityICE 欄中已捕獲用於媒體線之連線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a004b-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-130">int</span><span class="sxs-lookup"><span data-stu-id="a004b-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-131">有關互動式連線建立 (冰) 程式的資訊，請參閱 bits 旗中所述的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a004b-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="a004b-132">如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</span><span class="sxs-lookup"><span data-stu-id="a004b-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-134">int</span><span class="sxs-lookup"><span data-stu-id="a004b-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-135">與 CallerIceWarningFlags 相同，但在被呼叫者的一端。</span><span class="sxs-lookup"><span data-stu-id="a004b-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="a004b-136">如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</span><span class="sxs-lookup"><span data-stu-id="a004b-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-137"><strong>安全性</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-138">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-139">使用中的安全性設定檔。</span><span class="sxs-lookup"><span data-stu-id="a004b-139">The security profile in use.</span></span> <span data-ttu-id="a004b-140">0 是無 (NONE)，1 是 SRTP，2 是 V1。</span><span class="sxs-lookup"><span data-stu-id="a004b-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-141"><strong>傳輸</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-142">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-143">0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="a004b-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-145">int</span><span class="sxs-lookup"><span data-stu-id="a004b-145">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-146">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-147">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-147">IP Address of the caller.</span></span> <span data-ttu-id="a004b-148">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-150">int</span><span class="sxs-lookup"><span data-stu-id="a004b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-151">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a004b-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-153">int</span><span class="sxs-lookup"><span data-stu-id="a004b-153">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-154"> 外國</span><span class="sxs-lookup"><span data-stu-id="a004b-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-155">來電者的子網。</span><span class="sxs-lookup"><span data-stu-id="a004b-155">The subnet of the caller.</span></span> <span data-ttu-id="a004b-156">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-158">位</span><span class="sxs-lookup"><span data-stu-id="a004b-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-159">1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="a004b-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-161">int</span><span class="sxs-lookup"><span data-stu-id="a004b-161">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-162">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-163">來電者的 mac 位址（從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照）。</span><span class="sxs-lookup"><span data-stu-id="a004b-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-165">int</span><span class="sxs-lookup"><span data-stu-id="a004b-165">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-166">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-167">呼叫者使用之 Lync Server A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="a004b-168">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-170">int</span><span class="sxs-lookup"><span data-stu-id="a004b-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-171">呼叫者在 A/V Edge service 上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="a004b-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-173">int</span><span class="sxs-lookup"><span data-stu-id="a004b-173">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-174">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-175">呼叫者使用的捕獲裝置。</span><span class="sxs-lookup"><span data-stu-id="a004b-175">Capture device used by the caller.</span></span> <span data-ttu-id="a004b-176">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-178">int</span><span class="sxs-lookup"><span data-stu-id="a004b-178">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-179">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-180">由來電者使用的呈現裝置。</span><span class="sxs-lookup"><span data-stu-id="a004b-180">Render device used by caller.</span></span> <span data-ttu-id="a004b-181">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-183">int</span><span class="sxs-lookup"><span data-stu-id="a004b-183">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-184">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-185">呼叫者的捕獲裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-187">int</span><span class="sxs-lookup"><span data-stu-id="a004b-187">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-188">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-189">呼叫者的轉譯裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-191">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a004b-192">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-193">會指出來電者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="a004b-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="a004b-194"><a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。</span><span class="sxs-lookup"><span data-stu-id="a004b-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="a004b-195">一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</span><span class="sxs-lookup"><span data-stu-id="a004b-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-197">int</span><span class="sxs-lookup"><span data-stu-id="a004b-197">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-198">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-199">使用無線時的來電者 BSSID。</span><span class="sxs-lookup"><span data-stu-id="a004b-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="a004b-200"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-202">位</span><span class="sxs-lookup"><span data-stu-id="a004b-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-203">來電者的連結。</span><span class="sxs-lookup"><span data-stu-id="a004b-203">The caller's link.</span></span> <span data-ttu-id="a004b-204">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a004b-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-206">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="a004b-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-207">來電者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="a004b-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-209">int</span><span class="sxs-lookup"><span data-stu-id="a004b-209">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-210">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-211">通話接收器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-211">IP Address of the call receiver.</span></span> <span data-ttu-id="a004b-212">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-214">位</span><span class="sxs-lookup"><span data-stu-id="a004b-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-215">呼叫接收器使用的埠。</span><span class="sxs-lookup"><span data-stu-id="a004b-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-217">int</span><span class="sxs-lookup"><span data-stu-id="a004b-217">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-218">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-219">被呼叫者的子網。</span><span class="sxs-lookup"><span data-stu-id="a004b-219">Subnet of callee.</span></span> <span data-ttu-id="a004b-220">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-222">位</span><span class="sxs-lookup"><span data-stu-id="a004b-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-223">1表示呼叫接收器位於商業網路內，0表示通話接收器位於網路外。</span><span class="sxs-lookup"><span data-stu-id="a004b-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-225">int</span><span class="sxs-lookup"><span data-stu-id="a004b-225">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-226">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-227">被呼叫者的 Mac 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-227">Callee Mac address.</span></span> <span data-ttu-id="a004b-228">從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-230">int</span><span class="sxs-lookup"><span data-stu-id="a004b-230">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-231">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-232">呼叫接收器所使用之 A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="a004b-233">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a004b-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-235">int</span><span class="sxs-lookup"><span data-stu-id="a004b-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-236">呼叫接收器在 A/V Edge Service 上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="a004b-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-238">int</span><span class="sxs-lookup"><span data-stu-id="a004b-238">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-239">外國</span><span class="sxs-lookup"><span data-stu-id="a004b-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-240">用於呼叫接收器的捕獲裝置。</span><span class="sxs-lookup"><span data-stu-id="a004b-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="a004b-241">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-243">int</span><span class="sxs-lookup"><span data-stu-id="a004b-243">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-244">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-245">會呈現呼叫接收器所使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="a004b-245">Render device used by the call receiver.</span></span> <span data-ttu-id="a004b-246">從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-248">int</span><span class="sxs-lookup"><span data-stu-id="a004b-248">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-249">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-250">呼叫接收器的捕獲裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="a004b-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="a004b-251"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-253">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a004b-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a004b-254">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-255">呼叫接收器的呈現裝置的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="a004b-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="a004b-256"><a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-258">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a004b-259">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-260">會指出被呼叫者連線到網路的方式。</span><span class="sxs-lookup"><span data-stu-id="a004b-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="a004b-261"><a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。</span><span class="sxs-lookup"><span data-stu-id="a004b-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="a004b-262">一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</span><span class="sxs-lookup"><span data-stu-id="a004b-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-264">int</span><span class="sxs-lookup"><span data-stu-id="a004b-264">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-265">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-266">使用無線時，被呼叫者的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="a004b-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="a004b-267"><a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a004b-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-269">位</span><span class="sxs-lookup"><span data-stu-id="a004b-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-270">通話接收器的連結;1是虛擬私人網路 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a004b-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-272">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="a004b-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-273">通話接收器端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="a004b-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-275">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="a004b-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-276">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="a004b-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-278">int</span><span class="sxs-lookup"><span data-stu-id="a004b-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-279">這是套用至指定之傳送端資料流程的實際頻寬，指定各種原則設定 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="a004b-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="a004b-280">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="a004b-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="a004b-281">基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="a004b-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-283">Smallint</span><span class="sxs-lookup"><span data-stu-id="a004b-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-284">這是所採用的頻寬容量來源。</span><span class="sxs-lookup"><span data-stu-id="a004b-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="a004b-285">它說明頻寬限制來自 ( "Policy Server"、"輪流伺服器"、"模態" 等) 。</span><span class="sxs-lookup"><span data-stu-id="a004b-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="a004b-286">從 <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a004b-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-288">位</span><span class="sxs-lookup"><span data-stu-id="a004b-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-289">會指出是否已收到來自來電者的計量值;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="a004b-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-290"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-291">位</span><span class="sxs-lookup"><span data-stu-id="a004b-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a004b-292">會指出是否已收到來自呼叫接收器的計量值;1為 [是]，null 值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="a004b-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-294">位</span><span class="sxs-lookup"><span data-stu-id="a004b-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-295">會指出報表是針對會話的一部分，還是完整的會話。</span><span class="sxs-lookup"><span data-stu-id="a004b-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="a004b-296">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-298">位</span><span class="sxs-lookup"><span data-stu-id="a004b-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-299">會指出呼叫是否分類為 (1) 或良好通話 (0) 的通話是否不良。</span><span class="sxs-lookup"><span data-stu-id="a004b-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="a004b-300">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="a004b-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-303">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="a004b-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="a004b-304">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-306">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a004b-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a004b-307">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="a004b-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="a004b-308">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-310">int</span><span class="sxs-lookup"><span data-stu-id="a004b-310">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-311">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-312">撥打電話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="a004b-313">在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="a004b-314">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-316">int</span><span class="sxs-lookup"><span data-stu-id="a004b-316">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-317">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-318">撥打通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="a004b-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="a004b-319">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-321">int</span><span class="sxs-lookup"><span data-stu-id="a004b-321">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-322">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-323">撥打通話之使用者所使用 WiFi 驅動程式的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a004b-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="a004b-324">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-326">int</span><span class="sxs-lookup"><span data-stu-id="a004b-326">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-327">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-328">接收通話之使用者的反身 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="a004b-329">在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a004b-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="a004b-330">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a004b-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-332">int</span><span class="sxs-lookup"><span data-stu-id="a004b-332">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-333">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-334">接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</span><span class="sxs-lookup"><span data-stu-id="a004b-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="a004b-335">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a004b-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a004b-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a004b-337">int</span><span class="sxs-lookup"><span data-stu-id="a004b-337">int</span></span></p></td>
<td><p><span data-ttu-id="a004b-338">Foreign</span><span class="sxs-lookup"><span data-stu-id="a004b-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a004b-339">接收通話之使用者所使用 WiFi 驅動程式的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a004b-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="a004b-340">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="a004b-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

