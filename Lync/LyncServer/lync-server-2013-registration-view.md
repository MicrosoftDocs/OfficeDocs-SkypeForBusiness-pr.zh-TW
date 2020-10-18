---
title: Lync Server 2013：註冊視圖
description: Lync Server 2013：註冊視圖。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578522"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="ee5ac-103">Lync Server 2013 中的註冊視圖</span><span class="sxs-lookup"><span data-stu-id="ee5ac-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5ac-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ee5ac-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ee5ac-105">[註冊] 視圖會儲存使用者註冊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="ee5ac-106">此視圖已引進 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee5ac-107">欄</span><span class="sxs-lookup"><span data-stu-id="ee5ac-107">Column</span></span></th>
<th><span data-ttu-id="ee5ac-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="ee5ac-108">Data Type</span></span></th>
<th><span data-ttu-id="ee5ac-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ee5ac-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ee5ac-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-112">Time of session request.</span></span> <span data-ttu-id="ee5ac-113">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ee5ac-114">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-116">int</span><span class="sxs-lookup"><span data-stu-id="ee5ac-116">int</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-117">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-117">ID number to identify the session.</span></span> <span data-ttu-id="ee5ac-118">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ee5ac-119">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ee5ac-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-122">發生註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-124">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-125">註冊之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-127">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-128">註冊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="ee5ac-129">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-132">註冊的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-132">Tenant of the user who registered.</span></span> <span data-ttu-id="ee5ac-133">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-135">唯一</span><span class="sxs-lookup"><span data-stu-id="ee5ac-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-136">使用者已註冊之端點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-138">唯一</span><span class="sxs-lookup"><span data-stu-id="ee5ac-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-139">唯一識別碼，用來區分包含相同使用者和相同端點的註冊。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-141">datetime</span><span class="sxs-lookup"><span data-stu-id="ee5ac-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-142">發生取消註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-144">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-145">取消註冊的原因。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-146"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.rule</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-147">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-148">註冊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-150">int</span><span class="sxs-lookup"><span data-stu-id="ee5ac-150">int</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-151">註冊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-151">Client used by the user who registered.</span></span> <span data-ttu-id="ee5ac-152">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-154">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-155">註冊的使用者所使用的用戶端類別。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-156"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-157">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-158">使用者註冊的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-158">IP Address the user registered with.</span></span> <span data-ttu-id="ee5ac-159">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-161">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-162">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-162">SIP dialog ID.</span></span> <span data-ttu-id="ee5ac-163">格式為：</span><span class="sxs-lookup"><span data-stu-id="ee5ac-163">The format of the is:</span></span></p>
<p><span data-ttu-id="ee5ac-164">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="ee5ac-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-166">int</span><span class="sxs-lookup"><span data-stu-id="ee5ac-166">int</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-p109">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-171">int</span><span class="sxs-lookup"><span data-stu-id="ee5ac-171">int</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-172">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-173"><strong>處長</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-174">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-175">註冊機的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-176"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-177">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-178">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-179"><strong>Edgeserver atl-edge</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-180">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-181">註冊之使用者所使用的 Edge Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-183">位</span><span class="sxs-lookup"><span data-stu-id="ee5ac-183">bit</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-184">指出使用者是否會從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-186">位</span><span class="sxs-lookup"><span data-stu-id="ee5ac-186">bit</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-187">會指出註冊時是否可使用 UserService。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-189">位</span><span class="sxs-lookup"><span data-stu-id="ee5ac-189">bit</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-190">會指出註冊是否與主要註冊機。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-192">Bigint</span><span class="sxs-lookup"><span data-stu-id="ee5ac-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-193">已登錄裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee5ac-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-195">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-196">已登錄裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="ee5ac-197">如需詳細資訊，請參閱 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee5ac-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ee5ac-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ee5ac-199">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ee5ac-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee5ac-200">已登錄裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-200">Hardware version of the device registered.</span></span> <span data-ttu-id="ee5ac-201">如需詳細資訊，請參閱 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="ee5ac-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

