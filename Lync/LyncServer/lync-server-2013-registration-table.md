---
title: Lync Server 2013：註冊表
description: Lync Server 2013：註冊表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578521"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="37ba3-103">Lync Server 2013 中的註冊表</span><span class="sxs-lookup"><span data-stu-id="37ba3-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ba3-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="37ba3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="37ba3-105">每筆記錄都代表一個使用者註冊事件。</span><span class="sxs-lookup"><span data-stu-id="37ba3-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37ba3-106">欄</span><span class="sxs-lookup"><span data-stu-id="37ba3-106">Column</span></span></th>
<th><span data-ttu-id="37ba3-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="37ba3-107">Data Type</span></span></th>
<th><span data-ttu-id="37ba3-108">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="37ba3-108">Key/Index</span></span></th>
<th><span data-ttu-id="37ba3-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="37ba3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="37ba3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="37ba3-112">主要，外部</span><span class="sxs-lookup"><span data-stu-id="37ba3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-113">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="37ba3-113">Time of session request.</span></span> <span data-ttu-id="37ba3-114">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="37ba3-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="37ba3-115">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-117">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-117">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-118">主要，外部</span><span class="sxs-lookup"><span data-stu-id="37ba3-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-119">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-119">ID number to identify the session.</span></span> <span data-ttu-id="37ba3-120">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="37ba3-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="37ba3-121">如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-123">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-123">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-124">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-125">使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-125">The user ID.</span></span> <span data-ttu-id="37ba3-126">如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-128">唯一</span><span class="sxs-lookup"><span data-stu-id="37ba3-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-p104">識別註冊端點的 GUID。通常，來自相同使用者電腦的註冊事件會具備相同的端點識別碼，不同的機器則會有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-133">唯一</span><span class="sxs-lookup"><span data-stu-id="37ba3-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-134">用於區分相同使用者和相同端點相關之登錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="37ba3-135">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="37ba3-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-137">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-137">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-138">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-139">目前使用者的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="37ba3-139">Client version of current user.</span></span> <span data-ttu-id="37ba3-140">如需詳細資訊，請參閱 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-142">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-142">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-143">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-144">登錄伺服器用於登錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="37ba3-145">如需詳細資訊，請參閱 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 資料表</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-147">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-147">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-148">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-149">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="37ba3-150">如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-152">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-152">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-153">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-154">登錄通過的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="37ba3-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="37ba3-155">如需詳細資訊，請參閱 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-157">位</span><span class="sxs-lookup"><span data-stu-id="37ba3-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-158">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="37ba3-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-160">位</span><span class="sxs-lookup"><span data-stu-id="37ba3-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-161">UserService 是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="37ba3-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-163">位</span><span class="sxs-lookup"><span data-stu-id="37ba3-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-164">是否登錄至主要登錄器。</span><span class="sxs-lookup"><span data-stu-id="37ba3-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-166">位</span><span class="sxs-lookup"><span data-stu-id="37ba3-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-167">表示是否使用 Survivable Branch Appliance 登錄使用者。</span><span class="sxs-lookup"><span data-stu-id="37ba3-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="37ba3-168">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="37ba3-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-170">datetime</span><span class="sxs-lookup"><span data-stu-id="37ba3-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-171">登錄時間。</span><span class="sxs-lookup"><span data-stu-id="37ba3-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-173">datetime</span><span class="sxs-lookup"><span data-stu-id="37ba3-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-174">解除登錄時間。</span><span class="sxs-lookup"><span data-stu-id="37ba3-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-176">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-177">登錄要求的回應碼。</span><span class="sxs-lookup"><span data-stu-id="37ba3-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-179">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-p109">登錄要求的診斷識別碼。這會指出診斷資訊類型。</span><span class="sxs-lookup"><span data-stu-id="37ba3-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-183">int</span><span class="sxs-lookup"><span data-stu-id="37ba3-183">int</span></span></p></td>
<td><p><span data-ttu-id="37ba3-184">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-185">登錄要求的來源裝置。</span><span class="sxs-lookup"><span data-stu-id="37ba3-185">The device that the register request is coming from.</span></span> <span data-ttu-id="37ba3-186">如需詳細資訊，請參閱 <a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a> 的 [裝置] 表格。</span><span class="sxs-lookup"><span data-stu-id="37ba3-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37ba3-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-188">Tinyint</span><span class="sxs-lookup"><span data-stu-id="37ba3-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="37ba3-189">Foreign</span><span class="sxs-lookup"><span data-stu-id="37ba3-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="37ba3-190">解除登錄的原因，例如「由用戶端起始」、「註冊到期」或「用戶端失敗」等。</span><span class="sxs-lookup"><span data-stu-id="37ba3-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="37ba3-191">如需詳細資訊，請參閱 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="37ba3-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37ba3-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="37ba3-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="37ba3-193">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="37ba3-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37ba3-194">使用者登錄所使用的端點 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="37ba3-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="37ba3-195">可以是 IPv4 位址或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="37ba3-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="37ba3-196">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="37ba3-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

