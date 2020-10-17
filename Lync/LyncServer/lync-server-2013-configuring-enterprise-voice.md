---
title: Lync Server 2013：設定企業語音
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
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532550"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d716f-102">在 Lync Server 2013 中設定企業語音</span><span class="sxs-lookup"><span data-stu-id="d716f-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d716f-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d716f-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d716f-104">若要部署 Enterprise Voice，您必須設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="d716f-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="d716f-105">建立主幹</span><span class="sxs-lookup"><span data-stu-id="d716f-105">Create a Trunk</span></span>

  - <span data-ttu-id="d716f-106">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="d716f-107">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="d716f-107">Define a Voice Route</span></span>

  - <span data-ttu-id="d716f-108">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="d716f-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="d716f-109">建立主幹</span><span class="sxs-lookup"><span data-stu-id="d716f-109">Create a Trunk</span></span>

<span data-ttu-id="d716f-110">您必須在您的企業語音部署中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="d716f-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="d716f-111">針對 Location-Based 路由，您必須為每個主幹建立主幹設定。</span><span class="sxs-lookup"><span data-stu-id="d716f-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="d716f-112">使用 Lync Server 拓撲產生器來定義主幹，並使用 Lync Server Windows PowerShell 命令、Get-cstrunkconfiguration 或 Lync Server 控制台定義對應的主幹設定。</span><span class="sxs-lookup"><span data-stu-id="d716f-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="d716f-113">有關如何啟用主幹設定 Location-Based 路由的詳細資訊，請參閱本節中的 [啟用 Location-Based 路由傳送至主幹] 主題中 [啟用 Lync Server 2013 中的 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="d716f-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="d716f-114">在此範例中，下表說明此案例中使用的主幹。</span><span class="sxs-lookup"><span data-stu-id="d716f-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="d716f-115">如需詳細資訊，請參閱 [在 Lync Server 2013 中的拓撲產生器中定義其他主幹](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="d716f-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="d716f-116">主幹名稱</span><span class="sxs-lookup"><span data-stu-id="d716f-116">Trunk name</span></span></th>
<th><span data-ttu-id="d716f-117">系統類型</span><span class="sxs-lookup"><span data-stu-id="d716f-117">System type</span></span></th>
<th><span data-ttu-id="d716f-118">姓名</span><span class="sxs-lookup"><span data-stu-id="d716f-118">Name</span></span></th>
<th><span data-ttu-id="d716f-119">位置</span><span class="sxs-lookup"><span data-stu-id="d716f-119">Location</span></span></th>
<th><span data-ttu-id="d716f-120">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d716f-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d716f-121">主幹 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-122">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="d716f-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="d716f-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-124">德里</span><span class="sxs-lookup"><span data-stu-id="d716f-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d716f-125">MS1</span><span class="sxs-lookup"><span data-stu-id="d716f-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d716f-126">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-127">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="d716f-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="d716f-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-129">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="d716f-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d716f-130">MS1</span><span class="sxs-lookup"><span data-stu-id="d716f-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d716f-131">主幹 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-132">Pbx</span><span class="sxs-lookup"><span data-stu-id="d716f-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-134">德里</span><span class="sxs-lookup"><span data-stu-id="d716f-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d716f-135">MS1</span><span class="sxs-lookup"><span data-stu-id="d716f-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d716f-136">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-137">Pbx</span><span class="sxs-lookup"><span data-stu-id="d716f-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-139">海德拉巴</span><span class="sxs-lookup"><span data-stu-id="d716f-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d716f-140">MS1</span><span class="sxs-lookup"><span data-stu-id="d716f-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="d716f-141">定義語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-141">Defines Voice Policies</span></span>

<span data-ttu-id="d716f-142">您必須定義 Enterprise Voice 部署的語音原則。</span><span class="sxs-lookup"><span data-stu-id="d716f-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="d716f-143">若要使用 Location-Based 路由，請定義語音原則，以強制執行 Location-Based 路由限制至使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="d716f-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="d716f-144">在此範例中，下表說明此案例中使用的語音原則。</span><span class="sxs-lookup"><span data-stu-id="d716f-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="d716f-145">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="d716f-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d716f-146">如需詳細資訊，請參閱設定 [語音原則和 PSTN 使用方式記錄，以在 Lync Server 2013 中授權呼叫功能和許可權](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="d716f-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d716f-147">語音原則1</span><span class="sxs-lookup"><span data-stu-id="d716f-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="d716f-148">語音原則2</span><span class="sxs-lookup"><span data-stu-id="d716f-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d716f-149">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="d716f-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="d716f-150">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="d716f-151">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d716f-152">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="d716f-153">新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="d716f-154">Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d716f-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="d716f-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="d716f-156">False</span><span class="sxs-lookup"><span data-stu-id="d716f-156">False</span></span></p></td>
<td><p><span data-ttu-id="d716f-157">False</span><span class="sxs-lookup"><span data-stu-id="d716f-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="d716f-158">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="d716f-158">Define Voice Routes</span></span>

<span data-ttu-id="d716f-159">您必須定義 Enterprise Voice 部署的語音路由。</span><span class="sxs-lookup"><span data-stu-id="d716f-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="d716f-160">在此範例中，下表說明此案例中使用的語音路由。</span><span class="sxs-lookup"><span data-stu-id="d716f-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="d716f-161">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="d716f-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d716f-162">如需詳細資訊，請參閱 [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="d716f-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="d716f-163">語音路由1</span><span class="sxs-lookup"><span data-stu-id="d716f-163">Voice route 1</span></span></th>
<th><span data-ttu-id="d716f-164">語音路由2</span><span class="sxs-lookup"><span data-stu-id="d716f-164">Voice route 2</span></span></th>
<th><span data-ttu-id="d716f-165">語音路由3</span><span class="sxs-lookup"><span data-stu-id="d716f-165">Voice route 3</span></span></th>
<th><span data-ttu-id="d716f-166">語音路由4</span><span class="sxs-lookup"><span data-stu-id="d716f-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d716f-167">姓名</span><span class="sxs-lookup"><span data-stu-id="d716f-167">Name</span></span></p></td>
<td><p><span data-ttu-id="d716f-168">新德里路由</span><span class="sxs-lookup"><span data-stu-id="d716f-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="d716f-169">Hyderabad 路由</span><span class="sxs-lookup"><span data-stu-id="d716f-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="d716f-170">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="d716f-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="d716f-171">PBX Hyd route</span><span class="sxs-lookup"><span data-stu-id="d716f-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d716f-172">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="d716f-173">新德里使用</span><span class="sxs-lookup"><span data-stu-id="d716f-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="d716f-174">Hyderabad 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="d716f-175">PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="d716f-176">PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="d716f-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d716f-177">樹幹</span><span class="sxs-lookup"><span data-stu-id="d716f-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="d716f-178">主幹 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-179">主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d716f-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d716f-180">主幹 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d716f-181">主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d716f-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="d716f-182">為使用者啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="d716f-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="d716f-183">為使用者啟用企業語音，並將您先前定義的語音原則指派給他們。</span><span class="sxs-lookup"><span data-stu-id="d716f-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="d716f-184">在此範例中，下表說明此案例中使用的工作分派。</span><span class="sxs-lookup"><span data-stu-id="d716f-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="d716f-185">只有 Location-Based 路由特有的設定才會包含在表格中，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="d716f-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d716f-186">如需詳細資訊，請參閱 [Enable users For Enterprise Voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="d716f-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d716f-187">位於新德里的使用者</span><span class="sxs-lookup"><span data-stu-id="d716f-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="d716f-188">位於 Hyderabad 的使用者</span><span class="sxs-lookup"><span data-stu-id="d716f-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d716f-189">關聯的語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="d716f-190">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="d716f-191">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="d716f-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d716f-192">範例使用者</span><span class="sxs-lookup"><span data-stu-id="d716f-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="d716f-193">DEL-LYNC-1、DEL-LYNC-2、DEL-3</span><span class="sxs-lookup"><span data-stu-id="d716f-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="d716f-194">HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d716f-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d716f-195">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d716f-195">See Also</span></span>


[<span data-ttu-id="d716f-196">在 Lync Server 2013 中設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="d716f-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

