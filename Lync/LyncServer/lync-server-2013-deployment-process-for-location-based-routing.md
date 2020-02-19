---
title: Lync Server 2013： 部署程序的位置型的路由
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
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="29f38-102">Lync Server 2013 中的位置型路由的部署程序</span><span class="sxs-lookup"><span data-stu-id="29f38-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29f38-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="29f38-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="29f38-104">本主題提供參與設定位置型的路由程序的概觀。</span><span class="sxs-lookup"><span data-stu-id="29f38-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="29f38-105">設定位置型路由之前，您必須部署 Lync Server Enterprise Edition 或 Standard Edition 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="29f38-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="29f38-106">已安裝並當您部署企業語音時，啟用位置型路由所需的元件。</span><span class="sxs-lookup"><span data-stu-id="29f38-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="29f38-107">位置型路由的部署程序</span><span class="sxs-lookup"><span data-stu-id="29f38-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f38-108">階段</span><span class="sxs-lookup"><span data-stu-id="29f38-108">Phase</span></span></th>
<th><span data-ttu-id="29f38-109">步驟</span><span class="sxs-lookup"><span data-stu-id="29f38-109">Steps</span></span></th>
<th><span data-ttu-id="29f38-110">所需群組和角色</span><span class="sxs-lookup"><span data-stu-id="29f38-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="29f38-111">部署文件</span><span class="sxs-lookup"><span data-stu-id="29f38-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-112">部署企業語音</span><span class="sxs-lookup"><span data-stu-id="29f38-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="29f38-113">設定主幹</span><span class="sxs-lookup"><span data-stu-id="29f38-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="29f38-114">建立語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="29f38-115">定義語音路由</span><span class="sxs-lookup"><span data-stu-id="29f38-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="29f38-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="29f38-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="29f38-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-117">CsAdministrator</span></span><br />
<span data-ttu-id="29f38-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="29f38-119">部署 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="29f38-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f38-120">確認 Enterprise Voice 部署</span><span class="sxs-lookup"><span data-stu-id="29f38-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29f38-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="29f38-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="29f38-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-122">CsAdministrator</span></span><br />
<span data-ttu-id="29f38-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29f38-124">設定網路地區、 網站及子網路</span><span class="sxs-lookup"><span data-stu-id="29f38-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="29f38-125">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="29f38-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="29f38-126">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="29f38-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="29f38-127">夥伴子網路與網路網站</span><span class="sxs-lookup"><span data-stu-id="29f38-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="29f38-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="29f38-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="29f38-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-129">CsAdministrator</span></span><br />
<span data-ttu-id="29f38-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="29f38-131">關於網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="29f38-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="29f38-132">建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="29f38-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="29f38-133">建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="29f38-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="29f38-134">將子網路與網站產生關聯</span><span class="sxs-lookup"><span data-stu-id="29f38-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f38-135">設定位置型的路由</span><span class="sxs-lookup"><span data-stu-id="29f38-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="29f38-136">建立語音路由原則</span><span class="sxs-lookup"><span data-stu-id="29f38-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="29f38-137">定義每個主幹的個別的主幹組態</span><span class="sxs-lookup"><span data-stu-id="29f38-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="29f38-138">修改語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="29f38-139">啟用位置型路由設定</span><span class="sxs-lookup"><span data-stu-id="29f38-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="29f38-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="29f38-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="29f38-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-141">CsAdministrator</span></span><br />
<span data-ttu-id="29f38-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="29f38-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="29f38-143">範例部署</span><span class="sxs-lookup"><span data-stu-id="29f38-143">Sample Deployment</span></span>

<span data-ttu-id="29f38-144">下列部署用來進一步說明啟用位置型路由的機制。</span><span class="sxs-lookup"><span data-stu-id="29f38-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="29f38-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="29f38-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="29f38-146">傳入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="29f38-146">Incoming PSTN calls</span></span>

<span data-ttu-id="29f38-147">系統管理員可以啟用定義將通話路由傳送至 「 網站 1 閘道 」 以位置為主的路由主幹和閘道建立關聯 」 網站 1 」 的網站 1。</span><span class="sxs-lookup"><span data-stu-id="29f38-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="29f38-148">啟用之後，會透過 「 網站 1 閘道 」 路由傳送的呼叫會只是路由傳送至位於網站 1 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="29f38-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="29f38-149">例如，將可防止 PSTN 通話費封鎖站台 2 透過目的地中不同的站台，使用者的 「 網站 1 閘道 」 主幹路由傳送的所有呼叫略都過。</span><span class="sxs-lookup"><span data-stu-id="29f38-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="29f38-150">只允許透過 「 網站 1 閘道 」 的所有內送 PSTN 通話路由傳送到位於網站 1 的端點。</span><span class="sxs-lookup"><span data-stu-id="29f38-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="29f38-151">例如，當 「 Lync 使用者 1 」 移動至站台 2，透過 「 網站 1 閘道 」 的所有內送 PSTN 通話將不會路由至 「 Lync 使用者 1 」 端點位於站台 2。</span><span class="sxs-lookup"><span data-stu-id="29f38-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="29f38-152">如果 「 Lync 使用者 1 」 移動至其中無法判斷使用者的位置未知的網路網站，則會套用相同的路由規則。</span><span class="sxs-lookup"><span data-stu-id="29f38-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="29f38-153">下表概述 「 Lync 使用者 1 」 在此內容中的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="29f38-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="29f38-154">Lync 使用者 1 端點位於網路網站 1</span><span class="sxs-lookup"><span data-stu-id="29f38-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="29f38-155">Lync 使用者 1 端點位於網路網站 2</span><span class="sxs-lookup"><span data-stu-id="29f38-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="29f38-156">Lync 使用者 1 端點位於不明的網路網站</span><span class="sxs-lookup"><span data-stu-id="29f38-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-157">Lync 使用者 1 的內送的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="29f38-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="29f38-158">來電會路由傳送至在此位置的端點</span><span class="sxs-lookup"><span data-stu-id="29f38-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="29f38-159">在此位置的端點無法路由傳送通話</span><span class="sxs-lookup"><span data-stu-id="29f38-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="29f38-160">在此位置的端點無法路由傳送通話</span><span class="sxs-lookup"><span data-stu-id="29f38-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="29f38-161">撥出 PSTN 電話</span><span class="sxs-lookup"><span data-stu-id="29f38-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="29f38-162">語音路由會直接指派給使用者的語音原則和指派給網路網站的語音路由原則內的參照。</span><span class="sxs-lookup"><span data-stu-id="29f38-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="29f38-163">這兩個原則包含可用來以不同方式路由傳送來電的路由的參照。</span><span class="sxs-lookup"><span data-stu-id="29f38-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="29f38-164">例如，系統管理員可以定義語音路由原則的所有使用者位於網路網站 1 來路由傳送透過 「 網站 1 閘道 」 的所有撥出通話，雖然某些使用者的語音原則定義透過 「 網站 2 閘道 」 的所有撥出電話路由。</span><span class="sxs-lookup"><span data-stu-id="29f38-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="29f38-165">雖然這些使用者位於網路網站 1，其輸出通話都會透過 「 網站 1 閘道 」 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="29f38-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="29f38-166">當使用者位於設定位置型路由的網路網站時，網站的語音路由原則路由會覆寫使用者的語音原則路由。</span><span class="sxs-lookup"><span data-stu-id="29f38-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="29f38-167">此規則會特別有用的暫時將移至不同的站台的使用者。</span><span class="sxs-lookup"><span data-stu-id="29f38-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="29f38-168">在本例中特定使用者將一律使用是在本機至其位置; 閘道如果 「 Lync 使用者 3 」 是位在 「 網站 2 」，將透過 「 網站 2 閘道 」，路由傳送所有他撥出電話但如果他旅行網站 1，將會放置而他是在網站 1 他撥出電話路由透過 「 網站 1 閘道 」。</span><span class="sxs-lookup"><span data-stu-id="29f38-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="29f38-169">下表說明 Lync 使用者 1 將撥出電話設定為從下列網站的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="29f38-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="29f38-170">網路網站 1</span><span class="sxs-lookup"><span data-stu-id="29f38-170">Network site 1</span></span></th>
<th><span data-ttu-id="29f38-171">網路網站 2</span><span class="sxs-lookup"><span data-stu-id="29f38-171">Network site 2</span></span></th>
<th><span data-ttu-id="29f38-172">不明的網路站台或未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="29f38-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-173">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="29f38-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="29f38-174">Lync 使用者 1 的語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="29f38-175">Lync 使用者 1 的語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="29f38-176">Lync 使用者 1 的語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29f38-177">撥出電話路由</span><span class="sxs-lookup"><span data-stu-id="29f38-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="29f38-178">網站 1 語音路由原則</span><span class="sxs-lookup"><span data-stu-id="29f38-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="29f38-179">站台 2 語音路由原則</span><span class="sxs-lookup"><span data-stu-id="29f38-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="29f38-180">使用者的語音原則和僅提供給未啟用位置型路由的系統</span><span class="sxs-lookup"><span data-stu-id="29f38-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="29f38-181">來電轉接和轉寄郵件</span><span class="sxs-lookup"><span data-stu-id="29f38-181">Call transfers and forwards</span></span>

<span data-ttu-id="29f38-182">當呼叫會轉接或轉寄時，路由傳送來電會受到位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="29f38-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="29f38-183">下表說明 Lync 使用者 1 傳送或轉寄至另一位 Lync 使用者 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="29f38-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f38-184">使用者初始化來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="29f38-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="29f38-185">Lync 使用者 2</span><span class="sxs-lookup"><span data-stu-id="29f38-185">Lync user 2</span></span></th>
<th><span data-ttu-id="29f38-186">Lync 使用者 4</span><span class="sxs-lookup"><span data-stu-id="29f38-186">Lync user 4</span></span></th>
<th><span data-ttu-id="29f38-187">未啟用位置型路由的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="29f38-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-188">Lync 使用者 1</span><span class="sxs-lookup"><span data-stu-id="29f38-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="29f38-189">轉接通話] 或 [允許傳輸</span><span class="sxs-lookup"><span data-stu-id="29f38-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="29f38-190">轉接通話] 或 [不允許轉接</span><span class="sxs-lookup"><span data-stu-id="29f38-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="29f38-191">轉接通話] 或 [不允許轉接</span><span class="sxs-lookup"><span data-stu-id="29f38-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="29f38-192">下表說明如何位置型路由會影響通話路由傳送的方式取決於所傳送之 Lync 使用者的位置 （Lync 使用者 2、 Lync 使用者 4 等等） 至 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="29f38-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f38-193">呼叫是轉接或轉接至其中的端點</span><span class="sxs-lookup"><span data-stu-id="29f38-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="29f38-194">Lync 使用者 2</span><span class="sxs-lookup"><span data-stu-id="29f38-194">Lync user 2</span></span></th>
<th><span data-ttu-id="29f38-195">Lync 使用者 4</span><span class="sxs-lookup"><span data-stu-id="29f38-195">Lync user 4</span></span></th>
<th><span data-ttu-id="29f38-196">未啟用位置型路由的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="29f38-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-197">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="29f38-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="29f38-198">轉接通話] 或 [傳輸路由傳送到網站 1 語音路由原則及輸出透過網站 1 閘道</span><span class="sxs-lookup"><span data-stu-id="29f38-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="29f38-199">轉接通話] 或 [傳輸路由透過站台 2 語音路由原則和透過網站 2 閘道的輸出</span><span class="sxs-lookup"><span data-stu-id="29f38-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="29f38-200">轉接通話] 或 [傳輸路由傳送到輸出透過未啟用位置型路由 （如果有的話） 閘道與 Lync 使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="29f38-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="29f38-201">同時響鈴</span><span class="sxs-lookup"><span data-stu-id="29f38-201">Simultaneous ringing</span></span>

<span data-ttu-id="29f38-202">一旦位置型路由設定中的範例拓撲，則會強制執行下列互動。</span><span class="sxs-lookup"><span data-stu-id="29f38-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="29f38-203">下表說明是否依位置路由允許同時響鈴的不同 Lync 使用者 （亦即 Lync 使用者 2、 Lync 使用者 4 等）。</span><span class="sxs-lookup"><span data-stu-id="29f38-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f38-204">內送 PSTN 通話目標</span><span class="sxs-lookup"><span data-stu-id="29f38-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="29f38-205">Lync 使用者 2</span><span class="sxs-lookup"><span data-stu-id="29f38-205">Lync user 2</span></span></th>
<th><span data-ttu-id="29f38-206">Lync 使用者 4</span><span class="sxs-lookup"><span data-stu-id="29f38-206">Lync user 4</span></span></th>
<th><span data-ttu-id="29f38-207">未啟用位置型路由的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="29f38-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-208">Lync 使用者 1</span><span class="sxs-lookup"><span data-stu-id="29f38-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="29f38-209">允許同時響鈴</span><span class="sxs-lookup"><span data-stu-id="29f38-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="29f38-210">不允許同時響鈴</span><span class="sxs-lookup"><span data-stu-id="29f38-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="29f38-211">不允許同時響鈴</span><span class="sxs-lookup"><span data-stu-id="29f38-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="29f38-212">下表說明是否依位置路由允許同時響鈴的 PSTN 端點來自不同 Lync 使用者 （亦即 Lync 使用者 2、 Lync 使用者 4 等）。</span><span class="sxs-lookup"><span data-stu-id="29f38-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29f38-213">同時響鈴目標</span><span class="sxs-lookup"><span data-stu-id="29f38-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="29f38-214">Lync 使用者 2</span><span class="sxs-lookup"><span data-stu-id="29f38-214">Lync user 2</span></span></th>
<th><span data-ttu-id="29f38-215">Lync 使用者 4</span><span class="sxs-lookup"><span data-stu-id="29f38-215">Lync user 4</span></span></th>
<th><span data-ttu-id="29f38-216">未啟用位置型路由的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="29f38-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29f38-217">Lync 使用者 1 行動電話 （PSTN 端點）</span><span class="sxs-lookup"><span data-stu-id="29f38-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="29f38-218">透過網路網站 1 的語音路由原則和透過網站 1 閘道的輸出路由傳送來電</span><span class="sxs-lookup"><span data-stu-id="29f38-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="29f38-219">透過網路網站 2 的語音路由原則及輸出透過站台 2 閘道路由傳送來電</span><span class="sxs-lookup"><span data-stu-id="29f38-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="29f38-220">電話路由傳送到來電者的語音原則，並將 egress 透過 PSTN 閘道未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="29f38-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29f38-221">另請參閱</span><span class="sxs-lookup"><span data-stu-id="29f38-221">See Also</span></span>


[<span data-ttu-id="29f38-222">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="29f38-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

