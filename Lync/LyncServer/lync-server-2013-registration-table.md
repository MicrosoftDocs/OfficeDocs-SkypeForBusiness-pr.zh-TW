---
title: 'Lync Server 2013: Registration 表格'
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
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="2a495-102">Lync Server 2013 中的 registration 表格</span><span class="sxs-lookup"><span data-stu-id="2a495-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a495-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="2a495-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2a495-104">每筆記錄都代表一個使用者註冊事件。</span><span class="sxs-lookup"><span data-stu-id="2a495-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a495-105">欄</span><span class="sxs-lookup"><span data-stu-id="2a495-105">Column</span></span></th>
<th><span data-ttu-id="2a495-106">資料類型</span><span class="sxs-lookup"><span data-stu-id="2a495-106">Data Type</span></span></th>
<th><span data-ttu-id="2a495-107">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="2a495-107">Key/Index</span></span></th>
<th><span data-ttu-id="2a495-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2a495-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a495-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2a495-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2a495-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="2a495-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="2a495-112">Time of session request.</span></span> <span data-ttu-id="2a495-113">其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="2a495-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2a495-114"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="2a495-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-116">int</span><span class="sxs-lookup"><span data-stu-id="2a495-116">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="2a495-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-118">ID number to identify the session.</span></span> <span data-ttu-id="2a495-119">會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="2a495-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2a495-120"><a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="2a495-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-122">int</span><span class="sxs-lookup"><span data-stu-id="2a495-122">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-124">使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-124">The user ID.</span></span> <span data-ttu-id="2a495-125">請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="2a495-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-127">唯一</span><span class="sxs-lookup"><span data-stu-id="2a495-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-p104">識別註冊端點的 GUID。通常，來自相同使用者電腦的註冊事件會具備相同的端點識別碼，不同的機器則會有不同的端點識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-132">唯一</span><span class="sxs-lookup"><span data-stu-id="2a495-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-133">用於區分相同使用者和相同端點相關之登錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="2a495-134">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="2a495-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-136">int</span><span class="sxs-lookup"><span data-stu-id="2a495-136">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-137">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-138">目前使用者的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="2a495-138">Client version of current user.</span></span> <span data-ttu-id="2a495-139">請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a495-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-141">int</span><span class="sxs-lookup"><span data-stu-id="2a495-141">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-142">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-143">登錄伺服器用於登錄的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="2a495-144">請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a495-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-146">int</span><span class="sxs-lookup"><span data-stu-id="2a495-146">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-147">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-148">擷取工作階段所在集區的識別碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="2a495-149">請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="2a495-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-151">int</span><span class="sxs-lookup"><span data-stu-id="2a495-151">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-152">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-153">登錄通過的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="2a495-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="2a495-154">請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a495-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-156">位元</span><span class="sxs-lookup"><span data-stu-id="2a495-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-157">使用者是否從內部登入。</span><span class="sxs-lookup"><span data-stu-id="2a495-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-159">位元</span><span class="sxs-lookup"><span data-stu-id="2a495-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-160">UserService 是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="2a495-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-162">位元</span><span class="sxs-lookup"><span data-stu-id="2a495-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-163">是否登錄至主要登錄器。</span><span class="sxs-lookup"><span data-stu-id="2a495-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-165">位元</span><span class="sxs-lookup"><span data-stu-id="2a495-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-166">表示是否使用 Survivable Branch Appliance 登錄使用者。</span><span class="sxs-lookup"><span data-stu-id="2a495-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="2a495-167">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="2a495-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-169">datetime</span><span class="sxs-lookup"><span data-stu-id="2a495-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-170">登錄時間。</span><span class="sxs-lookup"><span data-stu-id="2a495-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-172">datetime</span><span class="sxs-lookup"><span data-stu-id="2a495-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-173">解除登錄時間。</span><span class="sxs-lookup"><span data-stu-id="2a495-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-175">int</span><span class="sxs-lookup"><span data-stu-id="2a495-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-176">登錄要求的回應碼。</span><span class="sxs-lookup"><span data-stu-id="2a495-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-178">int</span><span class="sxs-lookup"><span data-stu-id="2a495-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-p109">登錄要求的診斷識別碼。這會指出診斷資訊類型。</span><span class="sxs-lookup"><span data-stu-id="2a495-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-182">int</span><span class="sxs-lookup"><span data-stu-id="2a495-182">int</span></span></p></td>
<td><p><span data-ttu-id="2a495-183">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-184">登錄要求的來源裝置。</span><span class="sxs-lookup"><span data-stu-id="2a495-184">The device that the register request is coming from.</span></span> <span data-ttu-id="2a495-185">請參閱<a href="lync-server-2013-devices-table.md">Lync Server 2013 中的裝置表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a495-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a495-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="2a495-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2a495-188">Foreign</span><span class="sxs-lookup"><span data-stu-id="2a495-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a495-189">解除登錄的原因，例如「由用戶端起始」、「註冊到期」或「用戶端失敗」等。</span><span class="sxs-lookup"><span data-stu-id="2a495-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="2a495-190">請參閱<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2a495-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a495-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="2a495-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2a495-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a495-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a495-193">使用者登錄所使用的端點 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2a495-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="2a495-194">可以是 IPv4 位址或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="2a495-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="2a495-195">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="2a495-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

