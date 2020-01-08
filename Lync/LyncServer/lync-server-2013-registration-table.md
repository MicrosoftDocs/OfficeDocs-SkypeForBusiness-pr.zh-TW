---
title: Lync Server 2013：登錄表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="41715-102">Lync Server 2013 中的登錄表格</span><span class="sxs-lookup"><span data-stu-id="41715-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41715-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="41715-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="41715-104">每個記錄代表一個使用者註冊事件。</span><span class="sxs-lookup"><span data-stu-id="41715-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41715-105">左欄</span><span class="sxs-lookup"><span data-stu-id="41715-105">Column</span></span></th>
<th><span data-ttu-id="41715-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="41715-106">Data Type</span></span></th>
<th><span data-ttu-id="41715-107">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="41715-107">Key/Index</span></span></th>
<th><span data-ttu-id="41715-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="41715-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41715-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="41715-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-110">datetime</span><span class="sxs-lookup"><span data-stu-id="41715-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="41715-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="41715-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="41715-112">Time of session request.</span></span> <span data-ttu-id="41715-113">與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="41715-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41715-114">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41715-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-116">int</span><span class="sxs-lookup"><span data-stu-id="41715-116">int</span></span></p></td>
<td><p><span data-ttu-id="41715-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="41715-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="41715-118">ID number to identify the session.</span></span> <span data-ttu-id="41715-119">與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="41715-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41715-120">如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-122">int</span><span class="sxs-lookup"><span data-stu-id="41715-122">int</span></span></p></td>
<td><p><span data-ttu-id="41715-123">外</span><span class="sxs-lookup"><span data-stu-id="41715-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-124">使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="41715-124">The user ID.</span></span> <span data-ttu-id="41715-125">如需詳細資訊，請參閱<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 [使用者] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="41715-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-128">識別註冊端點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="41715-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="41715-129">通常，來自同一個使用者的同一部電腦的 register 事件將會有相同的端點 ID。</span><span class="sxs-lookup"><span data-stu-id="41715-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="41715-130">不同的電腦都有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="41715-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="41715-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="41715-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-133">用於區分涉及相同使用者和同一個端點的登記的識別碼。</span><span class="sxs-lookup"><span data-stu-id="41715-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="41715-134">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="41715-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-136">int</span><span class="sxs-lookup"><span data-stu-id="41715-136">int</span></span></p></td>
<td><p><span data-ttu-id="41715-137">外</span><span class="sxs-lookup"><span data-stu-id="41715-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-138">目前使用者的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="41715-138">Client version of current user.</span></span> <span data-ttu-id="41715-139">如需詳細資訊，請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中</a>的 [ClientVersions] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-141">int</span><span class="sxs-lookup"><span data-stu-id="41715-141">int</span></span></p></td>
<td><p><span data-ttu-id="41715-142">外</span><span class="sxs-lookup"><span data-stu-id="41715-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-143">註冊所用的註冊機構伺服器 ID。</span><span class="sxs-lookup"><span data-stu-id="41715-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="41715-144">如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-146">int</span><span class="sxs-lookup"><span data-stu-id="41715-146">int</span></span></p></td>
<td><p><span data-ttu-id="41715-147">外</span><span class="sxs-lookup"><span data-stu-id="41715-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-148">捕獲會話的池 ID。</span><span class="sxs-lookup"><span data-stu-id="41715-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="41715-149">如需詳細資訊，請參閱<a href="lync-server-2013-pools-table.md">Lync Server 2013 中</a>的 [pool] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-151">int</span><span class="sxs-lookup"><span data-stu-id="41715-151">int</span></span></p></td>
<td><p><span data-ttu-id="41715-152">外</span><span class="sxs-lookup"><span data-stu-id="41715-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-153">註冊即將進行的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="41715-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="41715-154">如需詳細資訊，請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中</a>的 [EdgeServers] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="41715-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-156">稍微</span><span class="sxs-lookup"><span data-stu-id="41715-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-157">使用者是否已從內部登入。</span><span class="sxs-lookup"><span data-stu-id="41715-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="41715-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-159">稍微</span><span class="sxs-lookup"><span data-stu-id="41715-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-160">UserService 是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="41715-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="41715-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-162">稍微</span><span class="sxs-lookup"><span data-stu-id="41715-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-163">是否註冊到主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="41715-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="41715-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-165">稍微</span><span class="sxs-lookup"><span data-stu-id="41715-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-166">指出使用者是否已向 survivable 分支裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="41715-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="41715-167">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="41715-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="41715-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-169">datetime</span><span class="sxs-lookup"><span data-stu-id="41715-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-170">註冊時間。</span><span class="sxs-lookup"><span data-stu-id="41715-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="41715-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-172">datetime</span><span class="sxs-lookup"><span data-stu-id="41715-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-173">取消註冊時間。</span><span class="sxs-lookup"><span data-stu-id="41715-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="41715-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-175">int</span><span class="sxs-lookup"><span data-stu-id="41715-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-176">寄存器要求的回應代碼。</span><span class="sxs-lookup"><span data-stu-id="41715-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-178">int</span><span class="sxs-lookup"><span data-stu-id="41715-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-179">寄存器要求的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="41715-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="41715-180">這表示診斷資訊類型。</span><span class="sxs-lookup"><span data-stu-id="41715-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-182">int</span><span class="sxs-lookup"><span data-stu-id="41715-182">int</span></span></p></td>
<td><p><span data-ttu-id="41715-183">外</span><span class="sxs-lookup"><span data-stu-id="41715-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-184">寄存器要求所來自的裝置。</span><span class="sxs-lookup"><span data-stu-id="41715-184">The device that the register request is coming from.</span></span> <span data-ttu-id="41715-185">如需詳細資訊，請參閱<a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a>的 [裝置] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41715-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="41715-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-187">Tinyint</span><span class="sxs-lookup"><span data-stu-id="41715-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="41715-188">外</span><span class="sxs-lookup"><span data-stu-id="41715-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="41715-189">取消註冊的原因，例如「使用者已啟動」、「註冊已過期」、「用戶端失敗」等等。</span><span class="sxs-lookup"><span data-stu-id="41715-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="41715-190">如需詳細資訊，請參閱<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中</a>的 [DeRegisterType] 資料表。</span><span class="sxs-lookup"><span data-stu-id="41715-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41715-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="41715-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="41715-192">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="41715-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41715-193">使用者註冊之端點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="41715-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="41715-194">這可以是 IPv4 位址或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="41715-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="41715-195">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="41715-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

