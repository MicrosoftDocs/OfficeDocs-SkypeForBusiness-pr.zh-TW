---
title: Lync Server 2013：配置企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="7c1bb-102">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="7c1bb-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c1bb-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="7c1bb-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="7c1bb-104">若要部署企業語音，您需要設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="7c1bb-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="7c1bb-105">建立主幹</span><span class="sxs-lookup"><span data-stu-id="7c1bb-105">Create a Trunk</span></span>

  - <span data-ttu-id="7c1bb-106">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="7c1bb-107">定義語音路線</span><span class="sxs-lookup"><span data-stu-id="7c1bb-107">Define a Voice Route</span></span>

  - <span data-ttu-id="7c1bb-108">允許使用者使用企業語音</span><span class="sxs-lookup"><span data-stu-id="7c1bb-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="7c1bb-109">建立主幹</span><span class="sxs-lookup"><span data-stu-id="7c1bb-109">Create a Trunk</span></span>

<span data-ttu-id="7c1bb-110">您必須在企業語音部署中定義 trunks。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="7c1bb-111">對於以位置為基礎的路由，您必須針對每個幹線建立幹線設定。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="7c1bb-112">使用 Lync Server 拓撲建立器來定義您的 trunks，並使用 Lync Server Windows PowerShell 命令、新的 New-cstrunkconfiguration，或 Lync Server 控制台來定義相對應的幹線設定。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="7c1bb-113">在[Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)中啟用位置路由的詳細資訊，請參閱在 Lync 設定上啟用位置路由的方式（在 Trunks 中啟用位置路由）一節。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="7c1bb-114">在這個範例中，下表說明這個案例中使用的 trunks。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="7c1bb-115">如需詳細資訊，請參閱[在 Lync Server 2013 的拓撲建立器中定義其他 trunks](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="7c1bb-116">主幹名稱</span><span class="sxs-lookup"><span data-stu-id="7c1bb-116">Trunk name</span></span></th>
<th><span data-ttu-id="7c1bb-117">系統類型</span><span class="sxs-lookup"><span data-stu-id="7c1bb-117">System type</span></span></th>
<th><span data-ttu-id="7c1bb-118">名稱</span><span class="sxs-lookup"><span data-stu-id="7c1bb-118">Name</span></span></th>
<th><span data-ttu-id="7c1bb-119">位置</span><span class="sxs-lookup"><span data-stu-id="7c1bb-119">Location</span></span></th>
<th><span data-ttu-id="7c1bb-120">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="7c1bb-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-121">幹線 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-122">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="7c1bb-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-124">新德里</span><span class="sxs-lookup"><span data-stu-id="7c1bb-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-125">MS1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bb-126">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-127">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="7c1bb-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7c1bb-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-130">MS1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-131">幹線 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-132">PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-134">新德里</span><span class="sxs-lookup"><span data-stu-id="7c1bb-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-135">MS1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bb-136">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-137">PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="7c1bb-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-140">MS1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="7c1bb-141">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-141">Defines Voice Policies</span></span>

<span data-ttu-id="7c1bb-142">您必須為企業語音部署定義語音原則。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="7c1bb-143">如果您只需要使用位置的路由，請定義語音原則，以將位置基礎路由限制強制到使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="7c1bb-144">在這個範例中，下表說明此案例中使用的語音原則。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="7c1bb-145">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="7c1bb-146">如需詳細資訊，請參閱設定[語音原則和 PSTN 使用記錄，以在 Lync Server 2013 中授權呼叫功能與許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="7c1bb-147">語音原則1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="7c1bb-148">語音原則2</span><span class="sxs-lookup"><span data-stu-id="7c1bb-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-149">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="7c1bb-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-150">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-151">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bb-152">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="7c1bb-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-153">新德里使用量、PBX Del 用法、PBX Hyd 使用量</span><span class="sxs-lookup"><span data-stu-id="7c1bb-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-154">Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="7c1bb-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="7c1bb-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-156">虛假</span><span class="sxs-lookup"><span data-stu-id="7c1bb-156">False</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-157">虛假</span><span class="sxs-lookup"><span data-stu-id="7c1bb-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="7c1bb-158">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="7c1bb-158">Define Voice Routes</span></span>

<span data-ttu-id="7c1bb-159">您必須為企業語音部署定義語音路由。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="7c1bb-160">在這個範例中，下表說明此案例中使用的語音路線。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="7c1bb-161">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="7c1bb-162">如需詳細資訊，請參閱[在 Lync Server 2013 中設定出站通話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="7c1bb-163">語音路由1</span><span class="sxs-lookup"><span data-stu-id="7c1bb-163">Voice route 1</span></span></th>
<th><span data-ttu-id="7c1bb-164">語音路由2</span><span class="sxs-lookup"><span data-stu-id="7c1bb-164">Voice route 2</span></span></th>
<th><span data-ttu-id="7c1bb-165">語音路由3</span><span class="sxs-lookup"><span data-stu-id="7c1bb-165">Voice route 3</span></span></th>
<th><span data-ttu-id="7c1bb-166">語音路由4</span><span class="sxs-lookup"><span data-stu-id="7c1bb-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-167">名稱</span><span class="sxs-lookup"><span data-stu-id="7c1bb-167">Name</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-168">新德里路線</span><span class="sxs-lookup"><span data-stu-id="7c1bb-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-169">Hyderabad 路線</span><span class="sxs-lookup"><span data-stu-id="7c1bb-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-170">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="7c1bb-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-171">PBX Hyd 路由</span><span class="sxs-lookup"><span data-stu-id="7c1bb-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bb-172">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="7c1bb-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-173">新德里使用量</span><span class="sxs-lookup"><span data-stu-id="7c1bb-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-174">Hyderabad 使用量</span><span class="sxs-lookup"><span data-stu-id="7c1bb-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-175">PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="7c1bb-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-176">PBX Hyd 使用量</span><span class="sxs-lookup"><span data-stu-id="7c1bb-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-177">去</span><span class="sxs-lookup"><span data-stu-id="7c1bb-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-178">幹線 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-179">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="7c1bb-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-180">幹線 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-181">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="7c1bb-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="7c1bb-182">允許使用者使用企業語音</span><span class="sxs-lookup"><span data-stu-id="7c1bb-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="7c1bb-183">允許使用者使用企業語音，並將您先前定義的語音原則指派給他們。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="7c1bb-184">在這個範例中，下表說明這個案例中所使用的作業。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="7c1bb-185">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="7c1bb-186">如需詳細資訊，請參閱[在 Lync Server 2013 中啟用企業語音的使用者](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1bb-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="7c1bb-187">位於新德里的使用者</span><span class="sxs-lookup"><span data-stu-id="7c1bb-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="7c1bb-188">位於 Hyderabad 的使用者</span><span class="sxs-lookup"><span data-stu-id="7c1bb-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c1bb-189">相關的語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-190">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-191">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="7c1bb-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c1bb-192">範例使用者</span><span class="sxs-lookup"><span data-stu-id="7c1bb-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-193">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="7c1bb-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="7c1bb-194">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="7c1bb-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c1bb-195">請參閱</span><span class="sxs-lookup"><span data-stu-id="7c1bb-195">See Also</span></span>


[<span data-ttu-id="7c1bb-196">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="7c1bb-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

