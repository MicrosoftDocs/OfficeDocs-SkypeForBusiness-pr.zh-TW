---
title: Lync Server 2013：設定企業語音
description: Lync Server 2013：設定 Enterprise Voice。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548429"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="eece8-103">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="eece8-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eece8-104">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="eece8-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="eece8-105">若要部署 Enterprise Voice，您必須設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="eece8-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="eece8-106">建立主幹</span><span class="sxs-lookup"><span data-stu-id="eece8-106">Create a Trunk</span></span>

  - <span data-ttu-id="eece8-107">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="eece8-108">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="eece8-108">Define a Voice Route</span></span>

  - <span data-ttu-id="eece8-109">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="eece8-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="eece8-110">建立主幹</span><span class="sxs-lookup"><span data-stu-id="eece8-110">Create a Trunk</span></span>

<span data-ttu-id="eece8-111">您必須在您的企業語音部署中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="eece8-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="eece8-112">針對 Location-Based 路由，您必須為每個主幹建立主幹設定。</span><span class="sxs-lookup"><span data-stu-id="eece8-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="eece8-113">使用 Lync Server 拓撲產生器來定義主幹，並使用 Lync Server Windows PowerShell 命令、Get-cstrunkconfiguration 或 Lync Server 控制台定義對應的主幹設定。</span><span class="sxs-lookup"><span data-stu-id="eece8-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="eece8-114">有關如何啟用主幹設定 Location-Based 路由的詳細資訊，請參閱本節中的 [啟用 Location-Based 路由傳送至主幹] 主題中 [啟用 Lync Server 2013 中的 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="eece8-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="eece8-115">在此範例中，下表說明此案例中使用的主幹。</span><span class="sxs-lookup"><span data-stu-id="eece8-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="eece8-116">如需詳細資訊，請參閱 [在 Lync Server 2013 中的拓撲產生器中定義其他主幹](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="eece8-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eece8-117">主幹名稱</span><span class="sxs-lookup"><span data-stu-id="eece8-117">Trunk name</span></span></th>
<th><span data-ttu-id="eece8-118">系統類型</span><span class="sxs-lookup"><span data-stu-id="eece8-118">System type</span></span></th>
<th><span data-ttu-id="eece8-119">姓名</span><span class="sxs-lookup"><span data-stu-id="eece8-119">Name</span></span></th>
<th><span data-ttu-id="eece8-120">位置</span><span class="sxs-lookup"><span data-stu-id="eece8-120">Location</span></span></th>
<th><span data-ttu-id="eece8-121">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="eece8-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eece8-122">主幹 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-123">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="eece8-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="eece8-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-125">德里</span><span class="sxs-lookup"><span data-stu-id="eece8-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="eece8-126">MS1</span><span class="sxs-lookup"><span data-stu-id="eece8-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eece8-127">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-128">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="eece8-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="eece8-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-130">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="eece8-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="eece8-131">MS1</span><span class="sxs-lookup"><span data-stu-id="eece8-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eece8-132">主幹 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-133">Pbx</span><span class="sxs-lookup"><span data-stu-id="eece8-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-135">德里</span><span class="sxs-lookup"><span data-stu-id="eece8-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="eece8-136">MS1</span><span class="sxs-lookup"><span data-stu-id="eece8-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eece8-137">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-138">Pbx</span><span class="sxs-lookup"><span data-stu-id="eece8-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-140">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="eece8-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="eece8-141">MS1</span><span class="sxs-lookup"><span data-stu-id="eece8-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="eece8-142">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-142">Defines Voice Policies</span></span>

<span data-ttu-id="eece8-143">您必須定義 Enterprise Voice 部署的語音原則。</span><span class="sxs-lookup"><span data-stu-id="eece8-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="eece8-144">若要使用 Location-Based 路由，請定義語音原則，以強制執行 Location-Based 路由限制至使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="eece8-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="eece8-145">在此範例中，下表說明此案例中使用的語音原則。</span><span class="sxs-lookup"><span data-stu-id="eece8-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="eece8-146">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="eece8-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="eece8-147">如需詳細資訊，請參閱設定 [語音原則和 PSTN 使用方式記錄，以在 Lync Server 2013 中授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="eece8-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="eece8-148">語音原則1</span><span class="sxs-lookup"><span data-stu-id="eece8-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="eece8-149">語音原則2</span><span class="sxs-lookup"><span data-stu-id="eece8-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eece8-150">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="eece8-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="eece8-151">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="eece8-152">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eece8-153">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="eece8-154">新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="eece8-155">Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eece8-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="eece8-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="eece8-157">False</span><span class="sxs-lookup"><span data-stu-id="eece8-157">False</span></span></p></td>
<td><p><span data-ttu-id="eece8-158">False</span><span class="sxs-lookup"><span data-stu-id="eece8-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="eece8-159">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="eece8-159">Define Voice Routes</span></span>

<span data-ttu-id="eece8-160">您必須定義 Enterprise Voice 部署的語音路由。</span><span class="sxs-lookup"><span data-stu-id="eece8-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="eece8-161">在此範例中，下表說明此案例中使用的語音路由。</span><span class="sxs-lookup"><span data-stu-id="eece8-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="eece8-162">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="eece8-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="eece8-163">如需詳細資訊，請參閱 [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="eece8-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="eece8-164">語音路由1</span><span class="sxs-lookup"><span data-stu-id="eece8-164">Voice route 1</span></span></th>
<th><span data-ttu-id="eece8-165">語音路由2</span><span class="sxs-lookup"><span data-stu-id="eece8-165">Voice route 2</span></span></th>
<th><span data-ttu-id="eece8-166">語音路由3</span><span class="sxs-lookup"><span data-stu-id="eece8-166">Voice route 3</span></span></th>
<th><span data-ttu-id="eece8-167">語音路由4</span><span class="sxs-lookup"><span data-stu-id="eece8-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eece8-168">姓名</span><span class="sxs-lookup"><span data-stu-id="eece8-168">Name</span></span></p></td>
<td><p><span data-ttu-id="eece8-169">新德里路由</span><span class="sxs-lookup"><span data-stu-id="eece8-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="eece8-170">Hyderabad 路由</span><span class="sxs-lookup"><span data-stu-id="eece8-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="eece8-171">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="eece8-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="eece8-172">PBX Hyd route</span><span class="sxs-lookup"><span data-stu-id="eece8-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eece8-173">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="eece8-174">新德里使用</span><span class="sxs-lookup"><span data-stu-id="eece8-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="eece8-175">Hyderabad 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="eece8-176">PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="eece8-177">PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="eece8-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eece8-178">樹幹</span><span class="sxs-lookup"><span data-stu-id="eece8-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="eece8-179">主幹 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-180">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="eece8-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="eece8-181">主幹 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="eece8-182">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="eece8-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="eece8-183">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="eece8-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="eece8-184">為使用者啟用企業語音，並將您先前定義的語音原則指派給他們。</span><span class="sxs-lookup"><span data-stu-id="eece8-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="eece8-185">在此範例中，下表說明此案例中使用的工作分派。</span><span class="sxs-lookup"><span data-stu-id="eece8-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="eece8-186">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="eece8-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="eece8-187">如需詳細資訊，請參閱 [Enable users For Enterprise Voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="eece8-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="eece8-188">位於新德里的使用者</span><span class="sxs-lookup"><span data-stu-id="eece8-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="eece8-189">位於 Hyderabad 的使用者</span><span class="sxs-lookup"><span data-stu-id="eece8-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eece8-190">關聯的語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="eece8-191">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="eece8-192">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="eece8-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eece8-193">範例使用者</span><span class="sxs-lookup"><span data-stu-id="eece8-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="eece8-194">DEL-LYNC-1、DEL-LYNC-2、DEL-3</span><span class="sxs-lookup"><span data-stu-id="eece8-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="eece8-195">HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="eece8-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eece8-196">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eece8-196">See Also</span></span>


[<span data-ttu-id="eece8-197">在 Lync Server 2013 中設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="eece8-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

