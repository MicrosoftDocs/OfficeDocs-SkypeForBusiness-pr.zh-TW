---
title: Lync Server 2013：註冊視圖
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
ms.openlocfilehash: cdf0e0edd69685af866905fea08144de327c446c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536580"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="b084b-102">Lync Server 2013 中的註冊視圖</span><span class="sxs-lookup"><span data-stu-id="b084b-102">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b084b-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b084b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b084b-104">[註冊] 視圖會儲存使用者註冊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b084b-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="b084b-105">此視圖已引進 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b084b-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b084b-106">欄</span><span class="sxs-lookup"><span data-stu-id="b084b-106">Column</span></span></th>
<th><span data-ttu-id="b084b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="b084b-107">Data Type</span></span></th>
<th><span data-ttu-id="b084b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b084b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b084b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b084b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b084b-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="b084b-111">Time of session request.</span></span> <span data-ttu-id="b084b-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b084b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b084b-113">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-115">int</span><span class="sxs-lookup"><span data-stu-id="b084b-115">int</span></span></p></td>
<td><p><span data-ttu-id="b084b-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="b084b-116">ID number to identify the session.</span></span> <span data-ttu-id="b084b-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="b084b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b084b-118">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="b084b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="b084b-121">發生註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="b084b-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-123">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b084b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b084b-124">註冊之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b084b-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-126">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-127">註冊之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="b084b-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="b084b-128">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-130">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-131">註冊的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="b084b-131">Tenant of the user who registered.</span></span> <span data-ttu-id="b084b-132">如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-134">唯一</span><span class="sxs-lookup"><span data-stu-id="b084b-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b084b-135">使用者已註冊之端點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b084b-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-137">唯一</span><span class="sxs-lookup"><span data-stu-id="b084b-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b084b-138">唯一識別碼，用來區分包含相同使用者和相同端點的註冊。</span><span class="sxs-lookup"><span data-stu-id="b084b-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-140">datetime</span><span class="sxs-lookup"><span data-stu-id="b084b-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="b084b-141">發生取消註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="b084b-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-143">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-144">取消註冊的原因。</span><span class="sxs-lookup"><span data-stu-id="b084b-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-145"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.rule</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-146">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-147">註冊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="b084b-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-149">int</span><span class="sxs-lookup"><span data-stu-id="b084b-149">int</span></span></p></td>
<td><p><span data-ttu-id="b084b-150">註冊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b084b-150">Client used by the user who registered.</span></span> <span data-ttu-id="b084b-151">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-153">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="b084b-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b084b-154">註冊的使用者所使用的用戶端類別。</span><span class="sxs-lookup"><span data-stu-id="b084b-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-155"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-156">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-157">使用者註冊的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="b084b-157">IP Address the user registered with.</span></span> <span data-ttu-id="b084b-158">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b084b-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-160">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="b084b-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="b084b-161">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="b084b-161">SIP dialog ID.</span></span> <span data-ttu-id="b084b-162">格式為：</span><span class="sxs-lookup"><span data-stu-id="b084b-162">The format of the is:</span></span></p>
<p><span data-ttu-id="b084b-163">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="b084b-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-165">int</span><span class="sxs-lookup"><span data-stu-id="b084b-165">int</span></span></p></td>
<td><p><span data-ttu-id="b084b-p109">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="b084b-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-170">int</span><span class="sxs-lookup"><span data-stu-id="b084b-170">int</span></span></p></td>
<td><p><span data-ttu-id="b084b-171">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="b084b-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-172"><strong>處長</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-173">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-174">註冊機的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b084b-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-175"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-176">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-177">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b084b-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-178"><strong>Edgeserver atl-edge</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-179">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-180">註冊之使用者所使用的 Edge Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="b084b-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-182">位</span><span class="sxs-lookup"><span data-stu-id="b084b-182">bit</span></span></p></td>
<td><p><span data-ttu-id="b084b-183">指出使用者是否會從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="b084b-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-185">位</span><span class="sxs-lookup"><span data-stu-id="b084b-185">bit</span></span></p></td>
<td><p><span data-ttu-id="b084b-186">會指出註冊時是否可使用 UserService。</span><span class="sxs-lookup"><span data-stu-id="b084b-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-188">位</span><span class="sxs-lookup"><span data-stu-id="b084b-188">bit</span></span></p></td>
<td><p><span data-ttu-id="b084b-189">會指出註冊是否與主要註冊機。</span><span class="sxs-lookup"><span data-stu-id="b084b-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-191">Bigint</span><span class="sxs-lookup"><span data-stu-id="b084b-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="b084b-192">已登錄裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="b084b-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b084b-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-194">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-195">已登錄裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="b084b-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="b084b-196">如需詳細資訊，請參閱 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b084b-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b084b-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b084b-198">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b084b-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b084b-199">已登錄裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="b084b-199">Hardware version of the device registered.</span></span> <span data-ttu-id="b084b-200">如需詳細資訊，請參閱 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b084b-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

