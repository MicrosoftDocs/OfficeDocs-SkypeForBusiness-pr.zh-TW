---
title: Lync Server 2013： Location-Based 路由的部署程式
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
ms.openlocfilehash: f9d2dfa15dce07fa66678932d8d765ec7308ba75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526920"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="74544-102">Lync Server 2013 中 Location-Based 路由的部署程式</span><span class="sxs-lookup"><span data-stu-id="74544-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74544-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="74544-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="74544-104">本主題提供設定 Location-Based 路由的處理常式的概述。</span><span class="sxs-lookup"><span data-stu-id="74544-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="74544-105">您必須先部署 Lync Server Enterprise Edition 或 Standard Edition with Enterprise Voice，才能設定 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="74544-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="74544-106">當您部署企業語音時，已安裝並啟用 Location-Based 路由所需的元件。</span><span class="sxs-lookup"><span data-stu-id="74544-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="74544-107">Location-Based 路由部署程式</span><span class="sxs-lookup"><span data-stu-id="74544-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74544-108">階段</span><span class="sxs-lookup"><span data-stu-id="74544-108">Phase</span></span></th>
<th><span data-ttu-id="74544-109">步驟</span><span class="sxs-lookup"><span data-stu-id="74544-109">Steps</span></span></th>
<th><span data-ttu-id="74544-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="74544-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="74544-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="74544-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-112">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="74544-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74544-113">設定主幹</span><span class="sxs-lookup"><span data-stu-id="74544-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="74544-114">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="74544-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="74544-115">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="74544-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="74544-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="74544-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="74544-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-117">CsAdministrator</span></span><br />
<span data-ttu-id="74544-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74544-119">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="74544-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74544-120">驗證您的企業語音部署</span><span class="sxs-lookup"><span data-stu-id="74544-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74544-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="74544-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="74544-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-122">CsAdministrator</span></span><br />
<span data-ttu-id="74544-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74544-124">設定網路地區、網站及子網</span><span class="sxs-lookup"><span data-stu-id="74544-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74544-125">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="74544-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="74544-126">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="74544-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="74544-127">將子網與網路網站產生關聯</span><span class="sxs-lookup"><span data-stu-id="74544-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="74544-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="74544-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="74544-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-129">CsAdministrator</span></span><br />
<span data-ttu-id="74544-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="74544-131">關於網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="74544-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="74544-132">建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="74544-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="74544-133">建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="74544-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="74544-134">建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="74544-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74544-135">設定 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74544-136">建立語音路由原則</span><span class="sxs-lookup"><span data-stu-id="74544-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="74544-137">針對每個主幹定義個別主幹設定</span><span class="sxs-lookup"><span data-stu-id="74544-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="74544-138">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="74544-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="74544-139">啟用 Location-Based 路由設定</span><span class="sxs-lookup"><span data-stu-id="74544-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="74544-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="74544-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="74544-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-141">CsAdministrator</span></span><br />
<span data-ttu-id="74544-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74544-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="74544-143">部署範例</span><span class="sxs-lookup"><span data-stu-id="74544-143">Sample Deployment</span></span>

<span data-ttu-id="74544-144">下列部署是用來進一步說明 Location-Based 路由所啟用的機制。</span><span class="sxs-lookup"><span data-stu-id="74544-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="74544-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="74544-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="74544-146">傳入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="74544-146">Incoming PSTN calls</span></span>

<span data-ttu-id="74544-147">系統管理員可以讓已定義的主幹將通話路由傳送至「Site 1 Gateway」，以進行 Location-Based 路由傳送，並使 "Site 1 Gateway" 與 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="74544-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="74544-148">啟用後，透過 "Site 1 Gateway" 路由傳送的通話只會路由傳送至位於網站1的使用者。</span><span class="sxs-lookup"><span data-stu-id="74544-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="74544-149">透過「Site 1 Gateway」主幹路由傳送至不同網站中使用者的所有通話（例如 Site 2）都會遭到封鎖，以避免 PSTN 通話旁路。</span><span class="sxs-lookup"><span data-stu-id="74544-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="74544-150">透過 "Site 1 Gateway" 進行的所有傳入 PSTN 通話，只允許路由傳送至位於網站1的端點。</span><span class="sxs-lookup"><span data-stu-id="74544-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="74544-151">例如，當 "Lync user 1" 前往 site 2 時，所有經由 "Site 1 Gateway" 的內送 PSTN 通話，將不會路由至位於 site 2 中的「Lync user 1」端點。</span><span class="sxs-lookup"><span data-stu-id="74544-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="74544-152">如果 "Lync user 1" 前往無法判斷使用者位置的未知網路網站，則會套用相同的路由規則。</span><span class="sxs-lookup"><span data-stu-id="74544-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="74544-153">下表概述此內容中的「Lync user 1」的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="74544-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="74544-154">Lync 使用者1位於網路 site 1 的端點</span><span class="sxs-lookup"><span data-stu-id="74544-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="74544-155">位於網路 site 2 的 Lync 使用者1端點</span><span class="sxs-lookup"><span data-stu-id="74544-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="74544-156">位於未知網路網站的 Lync 使用者1端點</span><span class="sxs-lookup"><span data-stu-id="74544-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-157">Lync 使用者1的撥入 PSTN 來電</span><span class="sxs-lookup"><span data-stu-id="74544-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="74544-158">呼叫會路由傳送至此位置的端點</span><span class="sxs-lookup"><span data-stu-id="74544-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="74544-159">通話不會路由到此位置的端點</span><span class="sxs-lookup"><span data-stu-id="74544-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="74544-160">通話不會路由到此位置的端點</span><span class="sxs-lookup"><span data-stu-id="74544-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="74544-161">呼出 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="74544-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="74544-162">語音路由是以直接指派給使用者的語音原則，以及指派給網路網站的語音路由原則所參考。</span><span class="sxs-lookup"><span data-stu-id="74544-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="74544-163">這兩個原則都包含路由參考，可用來將通話路由傳送成不同的方式。</span><span class="sxs-lookup"><span data-stu-id="74544-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="74544-164">例如，管理員可以為位於網路 site 1 中的所有使用者定義一個語音路由原則，以便透過「Site 1 Gateway」路由傳送所有撥出電話，而部分使用者的語音原則則透過「Site 2 閘道」定義所有撥出電話的路由。</span><span class="sxs-lookup"><span data-stu-id="74544-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="74544-165">當這些使用者位於網路網站1時，其輸出通話將透過「網站1閘道」路由傳送。</span><span class="sxs-lookup"><span data-stu-id="74544-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="74544-166">當使用者位於為 Location-Based 路由設定之網路網站時，網路網站的語音路由原則路由會覆寫使用者的語音原則路由。</span><span class="sxs-lookup"><span data-stu-id="74544-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="74544-167">此規則對於暫時移至不同網站的使用者尤其有用。</span><span class="sxs-lookup"><span data-stu-id="74544-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="74544-168">在此特定案例中，使用者將永遠使用本機到其位置的閘道;如果 "Lync user 3" 位於 "Site 2"，他的所有撥出電話都會透過「Site 2 閘道」路由傳送，但如果是前往 site 1，他在 site 1 進行的所有撥出呼叫都會透過 "Site 1 Gateway" 進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="74544-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="74544-169">下表說明 Lync 使用者1的使用者經驗，可從下列網路網站撥出電話。</span><span class="sxs-lookup"><span data-stu-id="74544-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="74544-170">網路網站1</span><span class="sxs-lookup"><span data-stu-id="74544-170">Network site 1</span></span></th>
<th><span data-ttu-id="74544-171">網路網站2</span><span class="sxs-lookup"><span data-stu-id="74544-171">Network site 2</span></span></th>
<th><span data-ttu-id="74544-172">未啟用 Location-Based 路由的未知網路網站</span><span class="sxs-lookup"><span data-stu-id="74544-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-173">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="74544-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="74544-174">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="74544-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="74544-175">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="74544-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="74544-176">Lync 使用者1語音原則</span><span class="sxs-lookup"><span data-stu-id="74544-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74544-177">路由撥出通話</span><span class="sxs-lookup"><span data-stu-id="74544-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="74544-178">網站1語音路由原則</span><span class="sxs-lookup"><span data-stu-id="74544-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="74544-179">網站2語音路由原則</span><span class="sxs-lookup"><span data-stu-id="74544-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="74544-180">使用者的語音原則，且僅限未啟用 Location-Based 路由的系統</span><span class="sxs-lookup"><span data-stu-id="74544-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="74544-181">通話轉接及轉寄</span><span class="sxs-lookup"><span data-stu-id="74544-181">Call transfers and forwards</span></span>

<span data-ttu-id="74544-182">當轉接來電或轉寄來電時，通話的路由會受到 Location-Based 路由的影響。</span><span class="sxs-lookup"><span data-stu-id="74544-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="74544-183">下表描述 Lync 使用者1將 PSTN 通話轉接或轉寄給另一個 Lync 使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="74544-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74544-184">使用者起始來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="74544-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="74544-185">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="74544-185">Lync user 2</span></span></th>
<th><span data-ttu-id="74544-186">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="74544-186">Lync user 4</span></span></th>
<th><span data-ttu-id="74544-187">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-188">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="74544-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="74544-189">允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="74544-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="74544-190">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="74544-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="74544-191">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="74544-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="74544-192">下表說明 Location-Based 路由會如何根據正在轉接的 Lync 使用者位置（ (Lync 使用者2、Lync 使用者4等) 至 PSTN 端點），如何影響通話的路由</span><span class="sxs-lookup"><span data-stu-id="74544-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74544-193">轉接或轉寄通話的終點</span><span class="sxs-lookup"><span data-stu-id="74544-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="74544-194">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="74544-194">Lync user 2</span></span></th>
<th><span data-ttu-id="74544-195">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="74544-195">Lync user 4</span></span></th>
<th><span data-ttu-id="74544-196">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-197">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="74544-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="74544-198">呼叫轉寄或轉接透過 site 1 語音路由原則及透過 Site 1 閘道的方式路由傳送</span><span class="sxs-lookup"><span data-stu-id="74544-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="74544-199">呼叫轉寄或轉接透過 site 2 語音路由原則，以及透過 Site 2 閘道的出局進行路由</span><span class="sxs-lookup"><span data-stu-id="74544-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="74544-200">呼叫轉寄或轉接透過 Lync 使用者語音原則傳送，並透過未啟用位置基礎路由 (的閘道來傳送（如果有的話）) </span><span class="sxs-lookup"><span data-stu-id="74544-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="74544-201">同時震鈴</span><span class="sxs-lookup"><span data-stu-id="74544-201">Simultaneous ringing</span></span>

<span data-ttu-id="74544-202">在範例拓撲中設定位置基礎路由之後，會強制執行下列互動。</span><span class="sxs-lookup"><span data-stu-id="74544-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="74544-203">下表說明 Location-Based 路由是否允許不同的 Lync 使用者同時震鈴 (（例如，Lync 使用者2、Lync 使用者4等) ）。</span><span class="sxs-lookup"><span data-stu-id="74544-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74544-204">傳入 PSTN 通話目標</span><span class="sxs-lookup"><span data-stu-id="74544-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="74544-205">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="74544-205">Lync user 2</span></span></th>
<th><span data-ttu-id="74544-206">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="74544-206">Lync user 4</span></span></th>
<th><span data-ttu-id="74544-207">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-208">Lync 使用者1</span><span class="sxs-lookup"><span data-stu-id="74544-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="74544-209">允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="74544-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="74544-210">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="74544-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="74544-211">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="74544-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="74544-212">下表說明 Location-Based 路由是否允許從不同的 Lync 使用者同時撥打 PSTN 端點 (例如，Lync 使用者2、Lync 使用者4等) 。</span><span class="sxs-lookup"><span data-stu-id="74544-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74544-213">同時環目標</span><span class="sxs-lookup"><span data-stu-id="74544-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="74544-214">Lync 使用者2</span><span class="sxs-lookup"><span data-stu-id="74544-214">Lync user 2</span></span></th>
<th><span data-ttu-id="74544-215">Lync 使用者4</span><span class="sxs-lookup"><span data-stu-id="74544-215">Lync user 4</span></span></th>
<th><span data-ttu-id="74544-216">網站中的 Lync 使用者未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74544-217">Lync user 1 行動電話 (PSTN 端點) </span><span class="sxs-lookup"><span data-stu-id="74544-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="74544-218">透過網路 site 1 的語音路由原則及透過 site 1 閘道的出局進行路由傳送的通話</span><span class="sxs-lookup"><span data-stu-id="74544-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="74544-219">透過網路 site 2 的語音路由原則及透過 site 2 閘道的傳出的通話</span><span class="sxs-lookup"><span data-stu-id="74544-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="74544-220">透過來電者語音原則路由傳送，並透過未啟用 Location-Based 路由的 PSTN 閘道進行出局</span><span class="sxs-lookup"><span data-stu-id="74544-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74544-221">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74544-221">See Also</span></span>


[<span data-ttu-id="74544-222">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="74544-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

