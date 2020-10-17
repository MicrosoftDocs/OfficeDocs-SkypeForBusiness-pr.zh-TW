---
title: Lync Server 2013： Location-Based 路由的部署程式
description: Lync Server 2013： Location-Based 路由的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551059"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8e4f5-103">Lync Server 2013 中 Location-Based 路由的部署程式</span><span class="sxs-lookup"><span data-stu-id="8e4f5-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e4f5-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8e4f5-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8e4f5-105">本主題提供設定 Location-Based 路由的處理常式的概述。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="8e4f5-106">您必須先部署 Lync Server Enterprise Edition 或 Standard Edition with Enterprise Voice，才能設定 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="8e4f5-107">當您部署企業語音時，已安裝並啟用 Location-Based 路由所需的元件。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="8e4f5-108">Location-Based 路由部署程式</span><span class="sxs-lookup"><span data-stu-id="8e4f5-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e4f5-109">階段</span><span class="sxs-lookup"><span data-stu-id="8e4f5-109">Phase</span></span></th>
<th><span data-ttu-id="8e4f5-110">步驟</span><span class="sxs-lookup"><span data-stu-id="8e4f5-110">Steps</span></span></th>
<th><span data-ttu-id="8e4f5-111">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="8e4f5-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="8e4f5-112">部署文件</span><span class="sxs-lookup"><span data-stu-id="8e4f5-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-113">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="8e4f5-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8e4f5-114">設定主幹</span><span class="sxs-lookup"><span data-stu-id="8e4f5-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-115">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-116">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e4f5-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="8e4f5-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="8e4f5-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-118">CsAdministrator</span></span><br />
<span data-ttu-id="8e4f5-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-120">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="8e4f5-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4f5-121">驗證您的企業語音部署</span><span class="sxs-lookup"><span data-stu-id="8e4f5-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e4f5-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="8e4f5-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="8e4f5-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-123">CsAdministrator</span></span><br />
<span data-ttu-id="8e4f5-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-125">設定網路地區、網站及子網</span><span class="sxs-lookup"><span data-stu-id="8e4f5-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8e4f5-126">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="8e4f5-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-127">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="8e4f5-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-128">將子網與網路網站產生關聯</span><span class="sxs-lookup"><span data-stu-id="8e4f5-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e4f5-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="8e4f5-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="8e4f5-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-130">CsAdministrator</span></span><br />
<span data-ttu-id="8e4f5-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-132">關於網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="8e4f5-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="8e4f5-133">建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="8e4f5-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="8e4f5-134">建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="8e4f5-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="8e4f5-135">建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="8e4f5-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4f5-136">設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8e4f5-137">建立語音路由原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-138">針對每個主幹定義個別主幹設定</span><span class="sxs-lookup"><span data-stu-id="8e4f5-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-139">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="8e4f5-140">啟用 Location-Based 路由設定</span><span class="sxs-lookup"><span data-stu-id="8e4f5-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e4f5-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="8e4f5-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="8e4f5-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-142">CsAdministrator</span></span><br />
<span data-ttu-id="8e4f5-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8e4f5-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="8e4f5-144">部署範例</span><span class="sxs-lookup"><span data-stu-id="8e4f5-144">Sample Deployment</span></span>

<span data-ttu-id="8e4f5-145">下列部署是用來進一步說明 Location-Based 路由所啟用的機制。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="8e4f5-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="8e4f5-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="8e4f5-147">傳入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="8e4f5-147">Incoming PSTN calls</span></span>

<span data-ttu-id="8e4f5-148">系統管理員可以讓已定義的主幹將通話路由傳送至「Site 1 Gateway」，以進行 Location-Based 路由傳送，並使 "Site 1 Gateway" 與 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="8e4f5-149">啟用後，透過 "Site 1 Gateway" 路由傳送的通話只會路由傳送至位於網站1的使用者。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="8e4f5-150">透過「Site 1 Gateway」主幹路由傳送至不同網站中使用者的所有通話（例如 Site 2）都會遭到封鎖，以避免 PSTN 通話旁路。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="8e4f5-151">透過 "Site 1 Gateway" 進行的所有傳入 PSTN 通話，只允許路由傳送至位於網站1的端點。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="8e4f5-152">例如，當 "Lync user 1" 前往 site 2 時，所有經由 "Site 1 Gateway" 的內送 PSTN 通話，將不會路由至位於 site 2 中的「Lync user 1」端點。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="8e4f5-153">如果 "Lync user 1" 前往無法判斷使用者位置的未知網路網站，則會套用相同的路由規則。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="8e4f5-154">下表概述此內容中的「Lync user 1」的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8e4f5-155">Lync 使用者1位於網路 site 1 的端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="8e4f5-156">位於網路 site 2 的 Lync 使用者1端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="8e4f5-157">位於未知網路網站的 Lync 使用者1端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-158">Lync 使用者1的撥入 PSTN 來電</span><span class="sxs-lookup"><span data-stu-id="8e4f5-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-159">呼叫會路由傳送至此位置的端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-160">通話不會路由到此位置的端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-161">通話不會路由到此位置的端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="8e4f5-162">呼出 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="8e4f5-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="8e4f5-163">語音路由是以直接指派給使用者的語音原則，以及指派給網路網站的語音路由原則所參考。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="8e4f5-164">這兩個原則都包含路由參考，可用來將通話路由傳送成不同的方式。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="8e4f5-165">例如，管理員可以為位於網路 site 1 中的所有使用者定義一個語音路由原則，以便透過「Site 1 Gateway」路由傳送所有撥出電話，而部分使用者的語音原則則透過「Site 2 閘道」定義所有撥出電話的路由。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="8e4f5-166">當這些使用者位於網路網站1時，其輸出通話將透過「網站1閘道」路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="8e4f5-167">當使用者位於為 Location-Based 路由設定之網路網站時，網路網站的語音路由原則路由會覆寫使用者的語音原則路由。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="8e4f5-168">此規則對於暫時移至不同網站的使用者尤其有用。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="8e4f5-169">在此特定案例中，使用者將永遠使用本機到其位置的閘道;如果 "Lync user 3" 位於 "Site 2"，他的所有撥出電話都會透過「Site 2 閘道」路由傳送，但如果是前往 site 1，他在 site 1 進行的所有撥出呼叫都會透過 "Site 1 Gateway" 進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="8e4f5-170">下表說明 Lync 使用者1的使用者經驗，可從下列網路網站撥出電話。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8e4f5-171">網路網站1</span><span class="sxs-lookup"><span data-stu-id="8e4f5-171">Network site 1</span></span></th>
<th><span data-ttu-id="8e4f5-172">網路網站2</span><span class="sxs-lookup"><span data-stu-id="8e4f5-172">Network site 2</span></span></th>
<th><span data-ttu-id="8e4f5-173">未啟用 Location-Based 路由的未知網路網站</span><span class="sxs-lookup"><span data-stu-id="8e4f5-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-174">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="8e4f5-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-175">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-176">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-177">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e4f5-178">路由撥出通話</span><span class="sxs-lookup"><span data-stu-id="8e4f5-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-179">網站1語音路由原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-180">網站2語音路由原則</span><span class="sxs-lookup"><span data-stu-id="8e4f5-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-181">使用者的語音原則，且僅限未啟用 Location-Based 路由的系統</span><span class="sxs-lookup"><span data-stu-id="8e4f5-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="8e4f5-182">通話轉接及轉寄</span><span class="sxs-lookup"><span data-stu-id="8e4f5-182">Call transfers and forwards</span></span>

<span data-ttu-id="8e4f5-183">當轉接來電或轉寄來電時，通話的路由會受到 Location-Based 路由的影響。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="8e4f5-184">下表描述 Lync 使用者1將 PSTN 通話轉接或轉寄給另一個 Lync 使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e4f5-185">使用者起始來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="8e4f5-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="8e4f5-186">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="8e4f5-186">Lync user 2</span></span></th>
<th><span data-ttu-id="8e4f5-187">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="8e4f5-187">Lync user 4</span></span></th>
<th><span data-ttu-id="8e4f5-188">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-189">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="8e4f5-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-190">允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="8e4f5-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-191">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="8e4f5-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-192">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="8e4f5-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="8e4f5-193">下表說明 Location-Based 路由會如何根據正在轉接的 Lync 使用者位置（ (Lync 使用者2、Lync 使用者4等) 至 PSTN 端點），如何影響通話的路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e4f5-194">轉接或轉寄通話的終點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="8e4f5-195">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="8e4f5-195">Lync user 2</span></span></th>
<th><span data-ttu-id="8e4f5-196">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="8e4f5-196">Lync user 4</span></span></th>
<th><span data-ttu-id="8e4f5-197">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-198">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="8e4f5-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-199">呼叫轉寄或轉接透過 site 1 語音路由原則及透過 Site 1 閘道的方式路由傳送</span><span class="sxs-lookup"><span data-stu-id="8e4f5-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-200">呼叫轉寄或轉接透過 site 2 語音路由原則，以及透過 Site 2 閘道的出局進行路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-201">呼叫轉寄或轉接透過 Lync 使用者語音原則傳送，並透過未啟用位置基礎路由 (的閘道來傳送（如果有的話）) </span><span class="sxs-lookup"><span data-stu-id="8e4f5-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="8e4f5-202">同時震鈴</span><span class="sxs-lookup"><span data-stu-id="8e4f5-202">Simultaneous ringing</span></span>

<span data-ttu-id="8e4f5-203">在範例拓撲中設定位置基礎路由之後，會強制執行下列互動。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="8e4f5-204">下表說明 Location-Based 路由是否允許不同的 Lync 使用者同時震鈴 (（例如，Lync 使用者2、Lync 使用者4等) ）。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e4f5-205">傳入 PSTN 通話目標</span><span class="sxs-lookup"><span data-stu-id="8e4f5-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="8e4f5-206">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="8e4f5-206">Lync user 2</span></span></th>
<th><span data-ttu-id="8e4f5-207">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="8e4f5-207">Lync user 4</span></span></th>
<th><span data-ttu-id="8e4f5-208">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-209">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="8e4f5-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-210">允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="8e4f5-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-211">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="8e4f5-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-212">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="8e4f5-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="8e4f5-213">下表說明 Location-Based 路由是否允許從不同的 Lync 使用者同時撥打 PSTN 端點 (例如，Lync 使用者2、Lync 使用者4等) 。</span><span class="sxs-lookup"><span data-stu-id="8e4f5-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e4f5-214">同時環目標</span><span class="sxs-lookup"><span data-stu-id="8e4f5-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="8e4f5-215">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="8e4f5-215">Lync user 2</span></span></th>
<th><span data-ttu-id="8e4f5-216">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="8e4f5-216">Lync user 4</span></span></th>
<th><span data-ttu-id="8e4f5-217">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e4f5-218">Lync user 1 行動電話 (PSTN 端點) </span><span class="sxs-lookup"><span data-stu-id="8e4f5-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-219">透過網路 site 1 的語音路由原則及透過 site 1 閘道的出局進行路由傳送的通話</span><span class="sxs-lookup"><span data-stu-id="8e4f5-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-220">透過網路 site 2 的語音路由原則及透過 site 2 閘道的傳出的通話</span><span class="sxs-lookup"><span data-stu-id="8e4f5-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="8e4f5-221">透過來電者語音原則路由傳送，並透過未啟用 Location-Based 路由的 PSTN 閘道進行出局</span><span class="sxs-lookup"><span data-stu-id="8e4f5-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e4f5-222">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8e4f5-222">See Also</span></span>


[<span data-ttu-id="8e4f5-223">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="8e4f5-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

