---
title: 'Lync Server 2013: Registration 檢視'
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
ms.openlocfilehash: d3683965562d01c5aff33000450182c83e4d4c7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="e925b-102">Lync Server 2013 中的 registration 檢視</span><span class="sxs-lookup"><span data-stu-id="e925b-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e925b-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="e925b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e925b-104">Registration 檢視儲存使用者註冊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="e925b-105">Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="e925b-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e925b-106">欄</span><span class="sxs-lookup"><span data-stu-id="e925b-106">Column</span></span></th>
<th><span data-ttu-id="e925b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="e925b-107">Data Type</span></span></th>
<th><span data-ttu-id="e925b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e925b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e925b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e925b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e925b-111">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="e925b-111">Time of session request.</span></span> <span data-ttu-id="e925b-112">與 SessionIdSeq 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e925b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e925b-113"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e925b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-115">int</span><span class="sxs-lookup"><span data-stu-id="e925b-115">int</span></span></p></td>
<td><p><span data-ttu-id="e925b-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="e925b-116">ID number to identify the session.</span></span> <span data-ttu-id="e925b-117">與 SessionIdTime 搭配使用，以唯一識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="e925b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e925b-118"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="e925b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="e925b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="e925b-121">註冊發生的時間。</span><span class="sxs-lookup"><span data-stu-id="e925b-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-123">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e925b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e925b-124">登錄之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e925b-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-127">註冊的使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="e925b-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="e925b-128">請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-131">租用戶的使用者註冊。</span><span class="sxs-lookup"><span data-stu-id="e925b-131">Tenant of the user who registered.</span></span> <span data-ttu-id="e925b-132">請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租用戶表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-134">唯一</span><span class="sxs-lookup"><span data-stu-id="e925b-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e925b-135">註冊的使用者的端點唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e925b-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-137">唯一</span><span class="sxs-lookup"><span data-stu-id="e925b-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e925b-138">用來區分涉及相同使用者及相同端點的註冊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e925b-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-140">datetime</span><span class="sxs-lookup"><span data-stu-id="e925b-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="e925b-141">時間進行取消註冊的。</span><span class="sxs-lookup"><span data-stu-id="e925b-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-144">取消註冊的原因。</span><span class="sxs-lookup"><span data-stu-id="e925b-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-147">註冊的用戶端之使用者所使用的版本。</span><span class="sxs-lookup"><span data-stu-id="e925b-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-149">int</span><span class="sxs-lookup"><span data-stu-id="e925b-149">int</span></span></p></td>
<td><p><span data-ttu-id="e925b-150">使用用戶端之使用者所註冊。</span><span class="sxs-lookup"><span data-stu-id="e925b-150">Client used by the user who registered.</span></span> <span data-ttu-id="e925b-151">請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-153">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="e925b-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e925b-154">註冊的用戶端之使用者所使用的類別。</span><span class="sxs-lookup"><span data-stu-id="e925b-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-157">使用者註冊的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e925b-157">IP Address the user registered with.</span></span> <span data-ttu-id="e925b-158">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="e925b-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-160">varstring(775)</span><span class="sxs-lookup"><span data-stu-id="e925b-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e925b-161">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="e925b-161">SIP dialog ID.</span></span> <span data-ttu-id="e925b-162">格式為：</span><span class="sxs-lookup"><span data-stu-id="e925b-162">The format of the is:</span></span></p>
<p><span data-ttu-id="e925b-163">對話方塊; 從標籤; 來標記</span><span class="sxs-lookup"><span data-stu-id="e925b-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-165">int</span><span class="sxs-lookup"><span data-stu-id="e925b-165">int</span></span></p></td>
<td><p><span data-ttu-id="e925b-p109">工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</span><span class="sxs-lookup"><span data-stu-id="e925b-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-170">int</span><span class="sxs-lookup"><span data-stu-id="e925b-170">int</span></span></p></td>
<td><p><span data-ttu-id="e925b-171">從 SIP 標頭擷取而來的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="e925b-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-172"><strong>註冊機構</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-174">登錄器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e925b-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-177">擷取工作階段適用之資料的集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e925b-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-180">註冊的使用者所使用的 Edge server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e925b-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-182">位元</span><span class="sxs-lookup"><span data-stu-id="e925b-182">bit</span></span></p></td>
<td><p><span data-ttu-id="e925b-183">指出使用者是否會從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="e925b-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-185">位元</span><span class="sxs-lookup"><span data-stu-id="e925b-185">bit</span></span></p></td>
<td><p><span data-ttu-id="e925b-186">會指出是否 userservice 註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="e925b-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-188">位元</span><span class="sxs-lookup"><span data-stu-id="e925b-188">bit</span></span></p></td>
<td><p><span data-ttu-id="e925b-189">指出是否向主要登錄器註冊。</span><span class="sxs-lookup"><span data-stu-id="e925b-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-191">bigint</span><span class="sxs-lookup"><span data-stu-id="e925b-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="e925b-192">註冊裝置的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="e925b-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e925b-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-195">註冊裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="e925b-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="e925b-196">請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e925b-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e925b-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e925b-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e925b-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e925b-199">硬體版本的裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="e925b-199">Hardware version of the device registered.</span></span> <span data-ttu-id="e925b-200">請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e925b-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

