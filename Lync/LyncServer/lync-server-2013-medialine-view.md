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
ms.openlocfilehash: f1b8cac172b4973f86916269585d2d9b02cdc728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505730"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="89d4f-102">Lync Server 2013 中的 MediaLine 視圖</span><span class="sxs-lookup"><span data-stu-id="89d4f-102">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89d4f-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="89d4f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="89d4f-104">媒體行檢視會儲存資料庫中每一媒體行的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89d4f-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="89d4f-105">一個音訊工作階段通常會包含一個音訊媒體行。</span><span class="sxs-lookup"><span data-stu-id="89d4f-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="89d4f-106">一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。</span><span class="sxs-lookup"><span data-stu-id="89d4f-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="89d4f-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="89d4f-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d4f-108">欄</span><span class="sxs-lookup"><span data-stu-id="89d4f-108">Column</span></span></th>
<th><span data-ttu-id="89d4f-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="89d4f-109">Data Type</span></span></th>
<th><span data-ttu-id="89d4f-110">細節</span><span class="sxs-lookup"><span data-stu-id="89d4f-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="89d4f-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="89d4f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="89d4f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="89d4f-113">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="89d4f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="89d4f-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="89d4f-115">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-115">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-116">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="89d4f-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="89d4f-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="89d4f-118">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89d4f-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d4f-119">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="89d4f-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="89d4f-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="89d4f-121">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-121">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p102">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="89d4f-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="89d4f-125">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-125">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p103">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-128">安全性</span><span class="sxs-lookup"><span data-stu-id="89d4f-128">Security</span></span></p></td>
<td><p><span data-ttu-id="89d4f-129">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89d4f-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p104">使用中的安全性設定檔。0 是無 (NONE)，1 是 SRTP，2 是 V1。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-132">傳輸</span><span class="sxs-lookup"><span data-stu-id="89d4f-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="89d4f-133">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89d4f-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p105">傳輸類型。0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-137">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p106">發話者的 IP 位址，可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="89d4f-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="89d4f-141">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-141">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-142">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="89d4f-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="89d4f-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="89d4f-144">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-144">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p107">指出發話者是否在組織網路內。1 代表發話者在企業網路內。0 代表發話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="89d4f-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="89d4f-149">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-150">發話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-152">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-153">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="89d4f-154">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="89d4f-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="89d4f-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="89d4f-156">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-156">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-157">發話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="89d4f-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-159">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-160">發話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="89d4f-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="89d4f-161">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CallerIPAddr。</span><span class="sxs-lookup"><span data-stu-id="89d4f-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="89d4f-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="89d4f-163">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-164">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="89d4f-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="89d4f-166">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-167">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="89d4f-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="89d4f-169">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-170">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="89d4f-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="89d4f-172">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-173">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="89d4f-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="89d4f-175">Varchar (256</span><span class="sxs-lookup"><span data-stu-id="89d4f-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="89d4f-176">發話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="89d4f-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="89d4f-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="89d4f-178">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-179">發話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="89d4f-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="89d4f-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="89d4f-181">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-182">發話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89d4f-182">Details of caller’s network connection.</span></span> <span data-ttu-id="89d4f-183">如需詳細資訊，請參閱 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="89d4f-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="89d4f-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="89d4f-185">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-186">發話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="89d4f-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="89d4f-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="89d4f-188">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-188">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p111">指出發話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-192">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-193">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-193">IP address of the callee.</span></span> <span data-ttu-id="89d4f-194">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="89d4f-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="89d4f-196">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-196">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-197">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="89d4f-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="89d4f-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="89d4f-199">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-199">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p113">指出受話者是否在企業網路內。1 代表受話者在企業網路內，0 代表受話者在網路外。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="89d4f-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="89d4f-203">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-204">受話者使用之網路介面的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-206">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-207">受話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="89d4f-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="89d4f-208">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="89d4f-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="89d4f-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="89d4f-210">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-210">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-211">受話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="89d4f-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="89d4f-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="89d4f-213">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-214">受話者的 IP 位址，如 A/V Edge Service 所報告。</span><span class="sxs-lookup"><span data-stu-id="89d4f-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="89d4f-215">例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CalleeIPAddr。</span><span class="sxs-lookup"><span data-stu-id="89d4f-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="89d4f-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="89d4f-217">var (50) </span><span class="sxs-lookup"><span data-stu-id="89d4f-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-218">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="89d4f-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="89d4f-220">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-221">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="89d4f-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="89d4f-223">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-224">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="89d4f-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="89d4f-226">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-227">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="89d4f-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="89d4f-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="89d4f-229">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-230">受話者的 Wifi 驅動程式說明。</span><span class="sxs-lookup"><span data-stu-id="89d4f-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="89d4f-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="89d4f-232">Varchar (256</span><span class="sxs-lookup"><span data-stu-id="89d4f-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="89d4f-233">受話者的 Wifi 驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="89d4f-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="89d4f-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="89d4f-235">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-236">受話者網路連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="89d4f-236">Details of callee’s network connection.</span></span> <span data-ttu-id="89d4f-237">如需詳細資訊，請參閱 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="89d4f-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="89d4f-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="89d4f-239">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-240">受話者 WiFi 連線所使用的基本服務組識別碼。</span><span class="sxs-lookup"><span data-stu-id="89d4f-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="89d4f-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="89d4f-242">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-242">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p117">指出受話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="89d4f-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="89d4f-246">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="89d4f-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-247">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="89d4f-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="89d4f-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-249">int</span><span class="sxs-lookup"><span data-stu-id="89d4f-249">int</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p118">這是在指定各種原則設定 (TURN、API、SDP、Policy Server 等等) 的情況下，套用至指定傳送端資料流的實際頻寬。不要將這個與有效頻寬混淆，因為根據頻寬預估值，會有較低的有效頻寬。基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="89d4f-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="89d4f-254">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="89d4f-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="89d4f-p119">所採用的頻寬容量來源。其會說明頻寬限制的來源 (例如，「原則伺服器」、「TURN 伺服器」或「形式」)。</span><span class="sxs-lookup"><span data-stu-id="89d4f-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-257">Caller</span><span class="sxs-lookup"><span data-stu-id="89d4f-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="89d4f-258">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-258">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-259">指出是否收到發話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="89d4f-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-260">方</span><span class="sxs-lookup"><span data-stu-id="89d4f-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="89d4f-261">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-261">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-262">指出是否收到受話者的計量；1 為是，0 為否。</span><span class="sxs-lookup"><span data-stu-id="89d4f-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="89d4f-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="89d4f-264">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-264">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-265">指出此報告適用於部分通話或完整通話。</span><span class="sxs-lookup"><span data-stu-id="89d4f-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="89d4f-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="89d4f-267">位</span><span class="sxs-lookup"><span data-stu-id="89d4f-267">bit</span></span></p></td>
<td><p><span data-ttu-id="89d4f-268">指出通話分類為通話不良 (1) 或通話良好 (0)。</span><span class="sxs-lookup"><span data-stu-id="89d4f-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d4f-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="89d4f-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="89d4f-270">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89d4f-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d4f-271">指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="89d4f-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d4f-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="89d4f-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="89d4f-273">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89d4f-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d4f-274">指出受話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</span><span class="sxs-lookup"><span data-stu-id="89d4f-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

