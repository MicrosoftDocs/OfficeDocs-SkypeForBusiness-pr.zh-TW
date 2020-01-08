---
title: Lync Server 2013：位置基礎路由的部署程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e4d64-102">Lync Server 2013 中的位置基礎路由的部署程序</span><span class="sxs-lookup"><span data-stu-id="e4d64-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d64-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e4d64-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e4d64-104">本主題提供設定以位置為基礎的路由所涉及之程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="e4d64-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="e4d64-105">您必須先使用企業語音部署 Lync Server Enterprise Edition 或標準版，才能設定以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="e4d64-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="e4d64-106">部署企業語音時，已安裝並啟用位置路由所需的元件。</span><span class="sxs-lookup"><span data-stu-id="e4d64-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="e4d64-107">以位置為基礎的路由部署程式</span><span class="sxs-lookup"><span data-stu-id="e4d64-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4d64-108">分</span><span class="sxs-lookup"><span data-stu-id="e4d64-108">Phase</span></span></th>
<th><span data-ttu-id="e4d64-109">步驟</span><span class="sxs-lookup"><span data-stu-id="e4d64-109">Steps</span></span></th>
<th><span data-ttu-id="e4d64-110">必要的群組和角色</span><span class="sxs-lookup"><span data-stu-id="e4d64-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="e4d64-111">部署檔</span><span class="sxs-lookup"><span data-stu-id="e4d64-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-112">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="e4d64-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4d64-113">設定 Trunks</span><span class="sxs-lookup"><span data-stu-id="e4d64-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="e4d64-114">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="e4d64-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="e4d64-115">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4d64-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="e4d64-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="e4d64-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-117">CsAdministrator</span></span><br />
<span data-ttu-id="e4d64-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e4d64-119">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="e4d64-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4d64-120">驗證您的企業語音部署</span><span class="sxs-lookup"><span data-stu-id="e4d64-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e4d64-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="e4d64-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="e4d64-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-122">CsAdministrator</span></span><br />
<span data-ttu-id="e4d64-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-124">設定網路區域、網站和子網</span><span class="sxs-lookup"><span data-stu-id="e4d64-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4d64-125">建立網路區域</span><span class="sxs-lookup"><span data-stu-id="e4d64-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="e4d64-126">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="e4d64-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="e4d64-127">將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="e4d64-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4d64-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="e4d64-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="e4d64-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-129">CsAdministrator</span></span><br />
<span data-ttu-id="e4d64-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e4d64-131">關於網路區域、網站和子網</span><span class="sxs-lookup"><span data-stu-id="e4d64-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="e4d64-132">建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="e4d64-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="e4d64-133">建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="e4d64-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="e4d64-134">將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="e4d64-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4d64-135">設定以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e4d64-136">建立語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e4d64-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="e4d64-137">針對每個幹線定義不同的幹線設定</span><span class="sxs-lookup"><span data-stu-id="e4d64-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="e4d64-138">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="e4d64-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="e4d64-139">啟用以位置為基礎的路由設定</span><span class="sxs-lookup"><span data-stu-id="e4d64-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e4d64-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="e4d64-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="e4d64-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-141">CsAdministrator</span></span><br />
<span data-ttu-id="e4d64-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e4d64-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="e4d64-143">範例部署</span><span class="sxs-lookup"><span data-stu-id="e4d64-143">Sample Deployment</span></span>

<span data-ttu-id="e4d64-144">下列部署是用來進一步說明根據位置式路由啟用的機制。</span><span class="sxs-lookup"><span data-stu-id="e4d64-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="e4d64-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="e4d64-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="e4d64-146">打入的 PSTN 電話</span><span class="sxs-lookup"><span data-stu-id="e4d64-146">Incoming PSTN calls</span></span>

<span data-ttu-id="e4d64-147">系統管理員可以讓已定義的幹線將呼叫路由至「Site 1 閘道」以進行位置路由，並將「網站1閘道」與網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e4d64-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="e4d64-148">一旦啟用，透過 "Site 1 閘道" 路由的通話將只會路由至位於網站1的使用者。</span><span class="sxs-lookup"><span data-stu-id="e4d64-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="e4d64-149">透過「網站1閘道」幹線傳送給不同網站中的使用者的所有通話，例如 Site 2 將遭到封鎖，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="e4d64-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="e4d64-150">透過「網站1閘道」進行的所有撥出 PSTN 呼叫只允許路由至位於網站1中的端點。</span><span class="sxs-lookup"><span data-stu-id="e4d64-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="e4d64-151">例如，當「Lync 使用者1」移至 site 2 時，所有透過「Site 1 閘道」傳入的 PSTN 呼叫，都不會路由至位於網站2中的 [Lync 使用者 1] 端點。</span><span class="sxs-lookup"><span data-stu-id="e4d64-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="e4d64-152">如果「Lync 使用者1」移至無法判斷使用者位置的未知網路網站，就會套用相同的傳送規則。</span><span class="sxs-lookup"><span data-stu-id="e4d64-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="e4d64-153">下表概述了在這個內容中，「Lync 使用者1」的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="e4d64-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="e4d64-154">Lync 使用者1位於網路 site 1 的端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="e4d64-155">Lync 使用者1位於網路 site 2 中的端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="e4d64-156">Lync user 1 端點位於未知網路網站</span><span class="sxs-lookup"><span data-stu-id="e4d64-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-157">Lync 使用者1的入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="e4d64-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="e4d64-158">通話路由到此位置的端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="e4d64-159">通話未路由到此位置中的端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="e4d64-160">通話未路由到此位置中的端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="e4d64-161">出局 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e4d64-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="e4d64-162">在直接指派給使用者的語音原則中，以及指派給網路網站的語音路由策略，都會參照語音路由。</span><span class="sxs-lookup"><span data-stu-id="e4d64-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="e4d64-163">這兩個原則都包含對路由的參照，可以用來以不同方式路由通話。</span><span class="sxs-lookup"><span data-stu-id="e4d64-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="e4d64-164">例如，管理員可以為位於 network site 1 中的所有使用者定義語音路由策略，以便透過「Site 1 閘道」路由所有出站通話，而部分使用者的語音原則則是透過「Site 2 閘道」定義所有出站通話的路線。</span><span class="sxs-lookup"><span data-stu-id="e4d64-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="e4d64-165">當這些使用者位於網路網站1時，其輸出呼叫將會透過「網站1閘道」路由。</span><span class="sxs-lookup"><span data-stu-id="e4d64-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="e4d64-166">當使用者位於設定為位置路由的網路網站時，網路網站的語音路由策略路由會覆寫使用者的語音原則路由。</span><span class="sxs-lookup"><span data-stu-id="e4d64-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="e4d64-167">此規則對於暫時移至不同網站的使用者特別有用。</span><span class="sxs-lookup"><span data-stu-id="e4d64-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="e4d64-168">在這個特定情況下，使用者將永遠使用本機的閘道來進行位置。如果 "Lync 使用者 3" 位於「Site 2」，則所有的撥出通話都將透過「Site 2 閘道」路由，但如果他移至 site 1，則會透過「Site 1 閘道」路由傳送給網站1的所有撥出通話。</span><span class="sxs-lookup"><span data-stu-id="e4d64-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="e4d64-169">下表說明 Lync 使用者1從下列網路網站撥出電話的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="e4d64-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="e4d64-170">網路網站1</span><span class="sxs-lookup"><span data-stu-id="e4d64-170">Network site 1</span></span></th>
<th><span data-ttu-id="e4d64-171">網路網站2</span><span class="sxs-lookup"><span data-stu-id="e4d64-171">Network site 2</span></span></th>
<th><span data-ttu-id="e4d64-172">未知的網路網站，或未啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-173">撥出通話的授權</span><span class="sxs-lookup"><span data-stu-id="e4d64-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="e4d64-174">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="e4d64-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="e4d64-175">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="e4d64-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="e4d64-176">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="e4d64-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4d64-177">傳送撥出通話</span><span class="sxs-lookup"><span data-stu-id="e4d64-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="e4d64-178">網站1語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e4d64-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e4d64-179">Site 2 語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e4d64-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e4d64-180">使用者的語音原則，且僅適用于不支援位置路由的系統</span><span class="sxs-lookup"><span data-stu-id="e4d64-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="e4d64-181">來電轉接與轉寄</span><span class="sxs-lookup"><span data-stu-id="e4d64-181">Call transfers and forwards</span></span>

<span data-ttu-id="e4d64-182">轉接或轉接來電時，通話的路由會受到以位置為基礎的路由影響。</span><span class="sxs-lookup"><span data-stu-id="e4d64-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="e4d64-183">下表說明 Lync 使用者1將 PSTN 來電轉接或轉寄給另一個 Lync 使用者的情況。</span><span class="sxs-lookup"><span data-stu-id="e4d64-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4d64-184">使用者啟動來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="e4d64-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e4d64-185">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="e4d64-185">Lync user 2</span></span></th>
<th><span data-ttu-id="e4d64-186">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="e4d64-186">Lync user 4</span></span></th>
<th><span data-ttu-id="e4d64-187">網路網站中的 Lync 使用者未啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-188">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="e4d64-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="e4d64-189">允許呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="e4d64-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="e4d64-190">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="e4d64-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="e4d64-191">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="e4d64-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e4d64-192">下表說明如何根據傳送給 PSTN 端點的 Lync 使用者的位置（Lync 使用者2、Lync 使用者4等），來視位置路由影響呼叫路由的方式。</span><span class="sxs-lookup"><span data-stu-id="e4d64-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4d64-193">轉接至或轉寄通話的終點</span><span class="sxs-lookup"><span data-stu-id="e4d64-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="e4d64-194">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="e4d64-194">Lync user 2</span></span></th>
<th><span data-ttu-id="e4d64-195">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="e4d64-195">Lync user 4</span></span></th>
<th><span data-ttu-id="e4d64-196">網路網站中的 Lync 使用者未啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-197">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="e4d64-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="e4d64-198">呼叫轉寄或轉接透過 site 1 語音路由原則與外出，透過 Site 1 閘道進行路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="e4d64-199">呼叫轉寄或轉移是透過 site 2 語音路由原則與外出，透過 Site 2 閘道進行路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="e4d64-200">呼叫轉寄或轉接是透過 Lync 使用者語音原則傳送，而外出則是透過未啟用位置路由的閘道（如果有的話）來傳送。</span><span class="sxs-lookup"><span data-stu-id="e4d64-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="e4d64-201">同時響鈴</span><span class="sxs-lookup"><span data-stu-id="e4d64-201">Simultaneous ringing</span></span>

<span data-ttu-id="e4d64-202">在範例拓撲中設定位置式路由之後，就會強制執行下列互動。</span><span class="sxs-lookup"><span data-stu-id="e4d64-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="e4d64-203">下表說明根據位置路由是否允許不同的 Lync 使用者同時撥打（亦即 Lync 使用者2、Lync 使用者4等）。</span><span class="sxs-lookup"><span data-stu-id="e4d64-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4d64-204">打入的 PSTN 通話目標</span><span class="sxs-lookup"><span data-stu-id="e4d64-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="e4d64-205">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="e4d64-205">Lync user 2</span></span></th>
<th><span data-ttu-id="e4d64-206">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="e4d64-206">Lync user 4</span></span></th>
<th><span data-ttu-id="e4d64-207">網路網站中的 Lync 使用者未啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-208">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="e4d64-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="e4d64-209">允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="e4d64-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="e4d64-210">不允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="e4d64-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="e4d64-211">不允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="e4d64-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e4d64-212">下表說明根據位置路由是否允許從不同的 Lync 使用者同時撥打 PSTN 端點（亦即 Lync 使用者2、Lync 使用者4等）。</span><span class="sxs-lookup"><span data-stu-id="e4d64-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4d64-213">同時撥打目標</span><span class="sxs-lookup"><span data-stu-id="e4d64-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="e4d64-214">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="e4d64-214">Lync user 2</span></span></th>
<th><span data-ttu-id="e4d64-215">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="e4d64-215">Lync user 4</span></span></th>
<th><span data-ttu-id="e4d64-216">網路網站中的 Lync 使用者未啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4d64-217">Lync 使用者1行動電話（PSTN 端點）</span><span class="sxs-lookup"><span data-stu-id="e4d64-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="e4d64-218">呼叫是透過網路 site 1 的語音路由原則與外出，透過 site 1 閘道傳送</span><span class="sxs-lookup"><span data-stu-id="e4d64-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="e4d64-219">呼叫是透過網路網站2的語音路由原則與外出，透過 site 2 閘道傳送</span><span class="sxs-lookup"><span data-stu-id="e4d64-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="e4d64-220">通話是透過呼叫者語音原則路由的，而且會透過不支援位置路由的 PSTN 閘道進行出口</span><span class="sxs-lookup"><span data-stu-id="e4d64-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4d64-221">請參閱</span><span class="sxs-lookup"><span data-stu-id="e4d64-221">See Also</span></span>


[<span data-ttu-id="e4d64-222">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="e4d64-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

