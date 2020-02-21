---
title: 'Lync Server 2013: MediaLine 檢視'
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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="45ea7-102">Lync Server 2013 中的 MediaLine 檢視</span><span class="sxs-lookup"><span data-stu-id="45ea7-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ea7-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="45ea7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="45ea7-104">媒體行檢視會儲存資料庫中每一媒體行的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea7-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="45ea7-105">一個音訊工作階段通常會包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="45ea7-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="45ea7-106">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="45ea7-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="45ea7-107">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="45ea7-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45ea7-108">欄</span><span class="sxs-lookup"><span data-stu-id="45ea7-108">Column</span></span></th>
<th><span data-ttu-id="45ea7-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="45ea7-109">Data Type</span></span></th>
<th><span data-ttu-id="45ea7-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="45ea7-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="45ea7-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="45ea7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="45ea7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="45ea7-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="45ea7-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="45ea7-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="45ea7-115">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-115">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-116">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="45ea7-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="45ea7-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="45ea7-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="45ea7-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45ea7-119">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="45ea7-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="45ea7-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="45ea7-121">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-121">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p102">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="45ea7-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="45ea7-125">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-125">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p103">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-128">安全性</span><span class="sxs-lookup"><span data-stu-id="45ea7-128">Security</span></span></p></td>
<td><p><span data-ttu-id="45ea7-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="45ea7-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p104">使用中的安全性設定檔。0 是無 (NONE)，1 是 SRTP，2 是 V1。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-132">傳輸</span><span class="sxs-lookup"><span data-stu-id="45ea7-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="45ea7-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="45ea7-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p105">傳輸類型。0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-137">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p106">發話者的 IP 位址，可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="45ea7-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="45ea7-141">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-141">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-142">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="45ea7-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="45ea7-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="45ea7-144">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-144">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p107">指出發話者是否在組織網路內。1 代表發話者在企業網路內。0 代表發話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="45ea7-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="45ea7-149">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-150">發話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-152">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-153">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="45ea7-154">請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea7-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="45ea7-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="45ea7-156">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-156">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-157">發話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="45ea7-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-159">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-160">發話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="45ea7-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="45ea7-161">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CallerIPAddr。</span><span class="sxs-lookup"><span data-stu-id="45ea7-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="45ea7-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="45ea7-163">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-164">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="45ea7-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="45ea7-166">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-167">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="45ea7-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="45ea7-169">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-170">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="45ea7-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="45ea7-172">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-173">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="45ea7-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="45ea7-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="45ea7-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="45ea7-176">發話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="45ea7-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="45ea7-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="45ea7-178">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-179">發話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="45ea7-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="45ea7-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="45ea7-181">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-182">發話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="45ea7-182">Details of caller’s network connection.</span></span> <span data-ttu-id="45ea7-183">請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea7-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="45ea7-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="45ea7-185">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-186">發話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="45ea7-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="45ea7-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="45ea7-188">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-188">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p111">指出發話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-192">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-193">受話者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-193">IP address of the callee.</span></span> <span data-ttu-id="45ea7-194">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="45ea7-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="45ea7-196">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-196">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-197">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="45ea7-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="45ea7-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="45ea7-199">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-199">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p113">指出受話者是否在企業網路內。1 代表受話者在企業網路內，0 代表受話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="45ea7-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="45ea7-203">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-204">受話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-206">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-207">受話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="45ea7-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="45ea7-208">請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea7-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="45ea7-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="45ea7-210">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-210">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-211">受話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="45ea7-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="45ea7-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="45ea7-213">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-214">受話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="45ea7-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="45ea7-215">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CalleeIPAddr。</span><span class="sxs-lookup"><span data-stu-id="45ea7-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="45ea7-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="45ea7-217">var(50)</span><span class="sxs-lookup"><span data-stu-id="45ea7-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-218">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="45ea7-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="45ea7-220">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-221">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="45ea7-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="45ea7-223">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-224">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="45ea7-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="45ea7-226">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-227">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="45ea7-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="45ea7-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="45ea7-229">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-230">受話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="45ea7-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="45ea7-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="45ea7-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="45ea7-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="45ea7-233">受話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="45ea7-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="45ea7-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="45ea7-235">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-236">受話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="45ea7-236">Details of callee’s network connection.</span></span> <span data-ttu-id="45ea7-237">請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="45ea7-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="45ea7-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="45ea7-239">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-240">受話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="45ea7-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="45ea7-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="45ea7-242">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-242">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p117">指出受話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="45ea7-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="45ea7-246">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="45ea7-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-247">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="45ea7-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="45ea7-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-249">int</span><span class="sxs-lookup"><span data-stu-id="45ea7-249">int</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p118">這是在指定各種原則設定 (TURN、API、SDP、Policy Server 等等) 的情況下，套用至指定傳送端資料流的實際頻寬。不要將這個與有效頻寬混淆，因為根據頻寬預估值，會有較低的有效頻寬。基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="45ea7-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="45ea7-254">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="45ea7-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="45ea7-p119">所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="45ea7-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-257">Caller</span><span class="sxs-lookup"><span data-stu-id="45ea7-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="45ea7-258">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-258">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-259">指出是否收到發話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="45ea7-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-260">受話者</span><span class="sxs-lookup"><span data-stu-id="45ea7-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="45ea7-261">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-261">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-262">指出是否收到受話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="45ea7-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="45ea7-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="45ea7-264">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-264">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-265">指出此報告適用於部分通話或完整通話。</span><span class="sxs-lookup"><span data-stu-id="45ea7-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="45ea7-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="45ea7-267">位元</span><span class="sxs-lookup"><span data-stu-id="45ea7-267">bit</span></span></p></td>
<td><p><span data-ttu-id="45ea7-268">指出通話分類為通話不良 (1) 或通話良好 (0)。</span><span class="sxs-lookup"><span data-stu-id="45ea7-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45ea7-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="45ea7-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="45ea7-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="45ea7-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45ea7-271">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="45ea7-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45ea7-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="45ea7-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="45ea7-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="45ea7-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="45ea7-274">指出受話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="45ea7-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

