---
title: Lync Server 2013： [註冊] 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="463f7-102">Lync Server 2013 中的 [註冊] 視圖</span><span class="sxs-lookup"><span data-stu-id="463f7-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="463f7-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="463f7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="463f7-104">[註冊] 視圖儲存使用者註冊的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="463f7-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="463f7-105">此視圖是在 Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="463f7-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="463f7-106">左欄</span><span class="sxs-lookup"><span data-stu-id="463f7-106">Column</span></span></th>
<th><span data-ttu-id="463f7-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="463f7-107">Data Type</span></span></th>
<th><span data-ttu-id="463f7-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="463f7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="463f7-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="463f7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="463f7-111">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="463f7-111">Time of session request.</span></span> <span data-ttu-id="463f7-112">與 SessionIdSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="463f7-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="463f7-113">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-115">int</span><span class="sxs-lookup"><span data-stu-id="463f7-115">int</span></span></p></td>
<td><p><span data-ttu-id="463f7-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="463f7-116">ID number to identify the session.</span></span> <span data-ttu-id="463f7-117">與 SessionIdTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="463f7-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="463f7-118">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-120">datetime</span><span class="sxs-lookup"><span data-stu-id="463f7-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="463f7-121">發生註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="463f7-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-123">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="463f7-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="463f7-124">已登錄之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="463f7-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-126">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-127">已登錄之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="463f7-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="463f7-128">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-130">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-131">已註冊的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="463f7-131">Tenant of the user who registered.</span></span> <span data-ttu-id="463f7-132">如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="463f7-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="463f7-135">已登錄之使用者之端點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="463f7-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="463f7-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="463f7-138">唯一識別碼，用於區分涉及相同使用者和同一個端點的登記。</span><span class="sxs-lookup"><span data-stu-id="463f7-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-140">datetime</span><span class="sxs-lookup"><span data-stu-id="463f7-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="463f7-141">發生取消註冊的時間。</span><span class="sxs-lookup"><span data-stu-id="463f7-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-143">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-144">取消註冊的原因。</span><span class="sxs-lookup"><span data-stu-id="463f7-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-146">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-147">註冊的使用者所使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="463f7-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-149">int</span><span class="sxs-lookup"><span data-stu-id="463f7-149">int</span></span></p></td>
<td><p><span data-ttu-id="463f7-150">已註冊的使用者所使用的用戶端。</span><span class="sxs-lookup"><span data-stu-id="463f7-150">Client used by the user who registered.</span></span> <span data-ttu-id="463f7-151">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-153">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="463f7-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="463f7-154">已註冊的使用者所使用的用戶端類別。</span><span class="sxs-lookup"><span data-stu-id="463f7-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-156">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-157">使用者註冊的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="463f7-157">IP Address the user registered with.</span></span> <span data-ttu-id="463f7-158">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="463f7-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-160">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="463f7-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="463f7-161">SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="463f7-161">SIP dialog ID.</span></span> <span data-ttu-id="463f7-162">的格式為：</span><span class="sxs-lookup"><span data-stu-id="463f7-162">The format of the is:</span></span></p>
<p><span data-ttu-id="463f7-163">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="463f7-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-165">int</span><span class="sxs-lookup"><span data-stu-id="463f7-165">int</span></span></p></td>
<td><p><span data-ttu-id="463f7-166">SIP 回應程式碼加入會話邀請。</span><span class="sxs-lookup"><span data-stu-id="463f7-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="463f7-167">這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。</span><span class="sxs-lookup"><span data-stu-id="463f7-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="463f7-168">如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</span><span class="sxs-lookup"><span data-stu-id="463f7-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-170">int</span><span class="sxs-lookup"><span data-stu-id="463f7-170">int</span></span></p></td>
<td><p><span data-ttu-id="463f7-171">從 SIP 標頭捕獲的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="463f7-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-172"><strong>註冊機構</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-173">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-174">註冊機構的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="463f7-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-175"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-176">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-177">捕獲會話資料之池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="463f7-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-179">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-180">已註冊的使用者所使用的邊緣伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="463f7-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-182">稍微</span><span class="sxs-lookup"><span data-stu-id="463f7-182">bit</span></span></p></td>
<td><p><span data-ttu-id="463f7-183">指示使用者是否從內部網路登入。</span><span class="sxs-lookup"><span data-stu-id="463f7-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-185">稍微</span><span class="sxs-lookup"><span data-stu-id="463f7-185">bit</span></span></p></td>
<td><p><span data-ttu-id="463f7-186">指示在註冊時間是否可以使用 UserService。</span><span class="sxs-lookup"><span data-stu-id="463f7-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-188">稍微</span><span class="sxs-lookup"><span data-stu-id="463f7-188">bit</span></span></p></td>
<td><p><span data-ttu-id="463f7-189">指出註冊是否與主要註冊機構一起使用。</span><span class="sxs-lookup"><span data-stu-id="463f7-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-191">Bigint</span><span class="sxs-lookup"><span data-stu-id="463f7-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="463f7-192">已註冊的裝置 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="463f7-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="463f7-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-194">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-195">已註冊裝置的製造商。</span><span class="sxs-lookup"><span data-stu-id="463f7-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="463f7-196">如需詳細資訊，請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中</a>的 [製造商] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="463f7-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="463f7-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="463f7-198">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="463f7-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="463f7-199">已註冊裝置的硬體版本。</span><span class="sxs-lookup"><span data-stu-id="463f7-199">Hardware version of the device registered.</span></span> <span data-ttu-id="463f7-200">如需詳細資訊，請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中</a>的 [HardwareVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="463f7-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

