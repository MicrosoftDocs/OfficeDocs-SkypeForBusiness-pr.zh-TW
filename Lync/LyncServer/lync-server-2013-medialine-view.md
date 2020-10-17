---
title: Lync Server 2013： MediaLine view
description: Lync Server 2013： MediaLine view。
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568679"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="a530d-103">Lync Server 2013 中的 MediaLine 視圖</span><span class="sxs-lookup"><span data-stu-id="a530d-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a530d-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a530d-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a530d-105">媒體行檢視會儲存資料庫中每一媒體行的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a530d-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="a530d-106">一個音訊工作階段通常會包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="a530d-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="a530d-107">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="a530d-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="a530d-108">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a530d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a530d-109">欄</span><span class="sxs-lookup"><span data-stu-id="a530d-109">Column</span></span></th>
<th><span data-ttu-id="a530d-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="a530d-110">Data Type</span></span></th>
<th><span data-ttu-id="a530d-111">細節</span><span class="sxs-lookup"><span data-stu-id="a530d-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a530d-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="a530d-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="a530d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="a530d-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="a530d-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a530d-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="a530d-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="a530d-116">int</span><span class="sxs-lookup"><span data-stu-id="a530d-116">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-117">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a530d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="a530d-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="a530d-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a530d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a530d-120">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="a530d-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a530d-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a530d-122">int</span><span class="sxs-lookup"><span data-stu-id="a530d-122">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-p102">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="a530d-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a530d-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a530d-126">int</span><span class="sxs-lookup"><span data-stu-id="a530d-126">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-p103">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="a530d-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-129">安全性</span><span class="sxs-lookup"><span data-stu-id="a530d-129">Security</span></span></p></td>
<td><p><span data-ttu-id="a530d-130">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a530d-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a530d-p104">使用中的安全性設定檔。0 是無 (NONE)，1 是 SRTP，2 是 V1。</span><span class="sxs-lookup"><span data-stu-id="a530d-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-133">傳輸</span><span class="sxs-lookup"><span data-stu-id="a530d-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="a530d-134">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a530d-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a530d-p105">傳輸類型。0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="a530d-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-138">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-p106">發話者的 IP 位址，可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="a530d-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="a530d-142">int</span><span class="sxs-lookup"><span data-stu-id="a530d-142">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-143">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a530d-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="a530d-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="a530d-145">位</span><span class="sxs-lookup"><span data-stu-id="a530d-145">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-p107">指出發話者是否在組織網路內。1 代表發話者在企業網路內。0 代表發話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="a530d-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="a530d-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="a530d-150">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-151">發話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-153">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-154">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="a530d-155">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a530d-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="a530d-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a530d-157">int</span><span class="sxs-lookup"><span data-stu-id="a530d-157">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-158">發話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a530d-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-160">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-161">發話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="a530d-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="a530d-162">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CallerIPAddr。</span><span class="sxs-lookup"><span data-stu-id="a530d-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a530d-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a530d-164">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-165">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="a530d-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a530d-167">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-168">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a530d-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a530d-170">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-171">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="a530d-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a530d-173">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-174">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="a530d-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="a530d-176">Varchar (256</span><span class="sxs-lookup"><span data-stu-id="a530d-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="a530d-177">發話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="a530d-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="a530d-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="a530d-179">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-180">發話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="a530d-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="a530d-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="a530d-182">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-183">發話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a530d-183">Details of caller’s network connection.</span></span> <span data-ttu-id="a530d-184">如需詳細資訊，請參閱 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a530d-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="a530d-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="a530d-186">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-187">發話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="a530d-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="a530d-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="a530d-189">位</span><span class="sxs-lookup"><span data-stu-id="a530d-189">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-p111">指出發話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a530d-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-193">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-194">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-194">IP address of the callee.</span></span> <span data-ttu-id="a530d-195">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="a530d-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="a530d-197">int</span><span class="sxs-lookup"><span data-stu-id="a530d-197">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-198">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a530d-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="a530d-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="a530d-200">位</span><span class="sxs-lookup"><span data-stu-id="a530d-200">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-p113">指出受話者是否在企業網路內。1 代表受話者在企業網路內，0 代表受話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="a530d-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="a530d-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="a530d-204">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-205">受話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-207">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-208">受話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a530d-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="a530d-209">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a530d-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="a530d-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a530d-211">int</span><span class="sxs-lookup"><span data-stu-id="a530d-211">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-212">受話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a530d-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="a530d-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a530d-214">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-215">受話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="a530d-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="a530d-216">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CalleeIPAddr。</span><span class="sxs-lookup"><span data-stu-id="a530d-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a530d-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a530d-218">var (50) </span><span class="sxs-lookup"><span data-stu-id="a530d-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a530d-219">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="a530d-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a530d-221">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-222">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a530d-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a530d-224">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-225">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="a530d-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a530d-227">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-228">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a530d-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="a530d-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="a530d-230">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-231">受話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="a530d-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="a530d-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="a530d-233">Varchar (256</span><span class="sxs-lookup"><span data-stu-id="a530d-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="a530d-234">受話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="a530d-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="a530d-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="a530d-236">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-237">受話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a530d-237">Details of callee’s network connection.</span></span> <span data-ttu-id="a530d-238">如需詳細資訊，請參閱 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="a530d-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="a530d-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="a530d-240">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-241">受話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="a530d-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="a530d-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="a530d-243">位</span><span class="sxs-lookup"><span data-stu-id="a530d-243">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-p117">指出受話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a530d-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="a530d-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="a530d-247">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="a530d-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a530d-248">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="a530d-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="a530d-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="a530d-250">int</span><span class="sxs-lookup"><span data-stu-id="a530d-250">int</span></span></p></td>
<td><p><span data-ttu-id="a530d-p118">這是在指定各種原則設定 (TURN、API、SDP、Policy Server 等等) 的情況下，套用至指定傳送端資料流的實際頻寬。不要將這個與有效頻寬混淆，因為根據頻寬預估值，會有較低的有效頻寬。基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="a530d-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="a530d-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="a530d-255">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="a530d-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a530d-p119">所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="a530d-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-258">Caller</span><span class="sxs-lookup"><span data-stu-id="a530d-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="a530d-259">位</span><span class="sxs-lookup"><span data-stu-id="a530d-259">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-260">指出是否收到發話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="a530d-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-261">方</span><span class="sxs-lookup"><span data-stu-id="a530d-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="a530d-262">位</span><span class="sxs-lookup"><span data-stu-id="a530d-262">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-263">指出是否收到受話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="a530d-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="a530d-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="a530d-265">位</span><span class="sxs-lookup"><span data-stu-id="a530d-265">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-266">指出此報告適用於部分通話或完整通話。</span><span class="sxs-lookup"><span data-stu-id="a530d-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="a530d-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="a530d-268">位</span><span class="sxs-lookup"><span data-stu-id="a530d-268">bit</span></span></p></td>
<td><p><span data-ttu-id="a530d-269">指出通話分類為通話不良 (1) 或通話良好 (0)。</span><span class="sxs-lookup"><span data-stu-id="a530d-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a530d-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="a530d-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="a530d-271">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a530d-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a530d-272">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="a530d-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a530d-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="a530d-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="a530d-274">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a530d-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a530d-275">指出受話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="a530d-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

