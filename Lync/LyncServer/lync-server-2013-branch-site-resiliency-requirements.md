---
title: Lync Server 2013：分支網站恢復需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76107fc419891561b8c98cf0989bbb0cbddbee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504840"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="8b54a-102">Lync Server 2013 的分支網站恢復需求</span><span class="sxs-lookup"><span data-stu-id="8b54a-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b54a-103">_**主題上次修改日期：** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="8b54a-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="8b54a-104">本主題將協助您為使用者準備分支網站恢復功能及語音信箱留存性，也會指定相關的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="8b54a-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="8b54a-105">準備分支使用者 Branch-Site 恢復功能</span><span class="sxs-lookup"><span data-stu-id="8b54a-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="8b54a-106">將其註冊機構集區設為 Survivable Branch 裝置 (SBA) 或 Survivable Branch Server），為使用者準備分支網站恢復功能。</span><span class="sxs-lookup"><span data-stu-id="8b54a-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="8b54a-107">分支使用者的註冊機構指派</span><span class="sxs-lookup"><span data-stu-id="8b54a-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="8b54a-108">不論您選擇哪一個分支網站恢復解決方案，您都必須將主要註冊器指派給每個使用者。</span><span class="sxs-lookup"><span data-stu-id="8b54a-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="8b54a-109">分支網站使用者應始終向分支網站上的註冊機構註冊，不論該報名者是位於 Survivable Branch 裝置、Survivable Branch Server，還是獨立的 Lync Server 2013 Standard 或 Enterprise Edition server。</span><span class="sxs-lookup"><span data-stu-id="8b54a-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="8b54a-110">網域名稱系統 (DNS) 服務 (SRV) 資源記錄是必要的，讓用戶端能夠探索其註冊區集區。</span><span class="sxs-lookup"><span data-stu-id="8b54a-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="8b54a-111">如果 Survivable 分支裝置無法使用，這就是分支網站用戶端將如何自動探索備份註冊機。</span><span class="sxs-lookup"><span data-stu-id="8b54a-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="8b54a-112">如果分支網站沒有 DNS 伺服器，有兩種方法可用於設定 Survivable 分支裝置或 Survivable Branch 伺服器的探索：</span><span class="sxs-lookup"><span data-stu-id="8b54a-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="8b54a-113">在分支網站的動態主機設定通訊協定上，設定 DHCP 選項120。 (DHCP) 伺服器指向 Survivable Branch 裝置或 Survivable Branch 伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="8b54a-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="8b54a-114">設定 Survivable 分支裝置或 Survivable 分支伺服器以回應 DHCP 120 查詢。</span><span class="sxs-lookup"><span data-stu-id="8b54a-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="8b54a-115">分支使用者的語音路由</span><span class="sxs-lookup"><span data-stu-id="8b54a-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="8b54a-116">建議您建立個別的使用者層級語音 over 網際網路通訊協定 (VoIP 分支網站中使用者的) 原則。</span><span class="sxs-lookup"><span data-stu-id="8b54a-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="8b54a-117">這個原則應包含使用 Survivable Branch 裝置或 Branch server 閘道的主要路由，以及一個或多個在中央網站上使用具有公用電話 (交換網之公用電話) 閘道的主幹的備份路由。</span><span class="sxs-lookup"><span data-stu-id="8b54a-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="8b54a-118">如果主要路由無法使用，則改為使用使用一或多部中央網站閘道的備份路由。</span><span class="sxs-lookup"><span data-stu-id="8b54a-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="8b54a-119">這種方式不論登錄使用者的位置為何（位於中央網站的分支網站註冊機構或備份註冊機構集區），使用者的 VoIP 原則都是有效的。</span><span class="sxs-lookup"><span data-stu-id="8b54a-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="8b54a-120">這是容錯移轉案例的重要考慮。</span><span class="sxs-lookup"><span data-stu-id="8b54a-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="8b54a-121">例如，如果您需要重新命名 Survivable 分支裝置，或重新設定 Survivable Branch 裝置以連線至中央網站的備份註冊機構集區，則必須將分支網站使用者移至中央網站的持續時間。</span><span class="sxs-lookup"><span data-stu-id="8b54a-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="8b54a-122"> (如需重新命名或重新配置 Survivable 分支裝置的詳細資訊，請參閱部署檔中的 [附錄 B：管理 Lync Server 2013 中的 Survivable Branch 裝置](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) 。 ) 如果這些使用者沒有使用者層級 VoIP 原則或使用者層級撥號對應表，當使用者移至另一個網站時，中心網站的網站層級 VoIP 原則和網站層級撥號對應表預設會套用至使用者，而不是分支網站網站層級 VoIP 原則及撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8b54a-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="8b54a-123">在此情況下，除非備份註冊機構集區所使用的網站層級 VoIP 原則和網站層級撥號對應表也可以套用至分支網站使用者，否則他們的呼叫將會失敗。</span><span class="sxs-lookup"><span data-stu-id="8b54a-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="8b54a-124">例如，如果位於日本的分支網站中的使用者已移至 Redmond 中的中央網站，則在其上預置 + 1425 至所有7位數通話的正規化規則的撥號對應表，將不會適當地為這些使用者轉譯來電。</span><span class="sxs-lookup"><span data-stu-id="8b54a-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b54a-125">當您建立分支辦公室備份路由時，建議您將兩個 PSTN 電話使用方式記錄新增至分支 office 使用者原則，並將個別的路由指派給每個。</span><span class="sxs-lookup"><span data-stu-id="8b54a-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="8b54a-126">第一個或 [主要] 路由會直接呼叫與 Survivable Branch 裝置相關聯的閘道 (SBA) 或分支伺服器;第二個或 [備份] 路由會將呼叫直接呼叫至中央網站的閘道。</span><span class="sxs-lookup"><span data-stu-id="8b54a-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="8b54a-127">在接聽來電中，SBA 或 branch 伺服器會先嘗試所有指派給第一個 PSTN 使用方式記錄的路由，再嘗試第二個使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="8b54a-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="8b54a-128">若要協助確定分支網站使用者的來電網關或 Survivable 分支裝置網站的 Windows 元件無法使用時，是否會到達這些使用者， (會發生此情況。例如，如果 Survivable 分支裝置或分支閘道停機以進行維護) ，請在閘道上建立容錯移轉路由 (或使用直接向內撥號 (已) 提供者) 將來電重新導向至中央網站的備份註冊機構集區。</span><span class="sxs-lookup"><span data-stu-id="8b54a-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="8b54a-129">在此，來電會透過 WAN 連結路由傳送至分支使用者。</span><span class="sxs-lookup"><span data-stu-id="8b54a-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="8b54a-130">請確定路由會轉譯數位，使其符合 PSTN 閘道或其他主幹對等公認的電話號碼格式。</span><span class="sxs-lookup"><span data-stu-id="8b54a-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="8b54a-131">如需建立容錯移轉路由的詳細資訊，請參閱 [在 Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)。</span><span class="sxs-lookup"><span data-stu-id="8b54a-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="8b54a-132">另外，也為分支網站上與閘道相關聯的主幹建立服務層級撥號對應表，以正常化來電。</span><span class="sxs-lookup"><span data-stu-id="8b54a-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="8b54a-133">如果您有兩個 Survivable 分支裝置在分支網站上，您可以為這兩種方案建立一個網站層級撥號對應表，除非每個必要都要有個別的服務層級計畫。</span><span class="sxs-lookup"><span data-stu-id="8b54a-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b54a-134">若要使用依賴中央網站以進行顯示狀態、會議或容錯移轉的任何分支網站使用者，針對中央網站資源的消費，建議您考慮每個分支網站使用者，就像使用者已向中央網站註冊。</span><span class="sxs-lookup"><span data-stu-id="8b54a-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="8b54a-135">分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。</span><span class="sxs-lookup"><span data-stu-id="8b54a-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="8b54a-136">此外，我們也建議您建立使用者層級撥號對應表和語音原則，然後將其指派給分支網站使用者。</span><span class="sxs-lookup"><span data-stu-id="8b54a-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="8b54a-137">如需詳細資訊，請參閱部署檔中的在 lync server [2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表，並在 [lync Server 2013 中建立分支使用者的 VoIP 路由原則](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b54a-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="8b54a-138">路由分機號碼</span><span class="sxs-lookup"><span data-stu-id="8b54a-138">Routing Extension Numbers</span></span>

<span data-ttu-id="8b54a-139">為分支網站使用者準備撥號對應表和語音原則時，請務必包含符合 msRTCSIP-line (或 Line URI) 屬性中所用之字串及數位格式的正規化規則和轉譯規則，如此一來，在分支網站使用者與中央網站使用者之間啟用的 Lync 2013 通話才能正確路由傳送，尤其是當由於 WAN 連結無法使用時，必須以 PSTN 重新路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8b54a-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="8b54a-140">此外，撥打號碼的特殊考慮（包括分機號碼），而不只是電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="8b54a-141">包含分機號碼之行 URIs 的正規化規則和轉譯規則，不論是獨佔還是除了完整的 e.164 電話號碼，都有額外的需求。</span><span class="sxs-lookup"><span data-stu-id="8b54a-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="8b54a-142">本節說明使用分機號碼來路由傳送電話 URIs 的幾個範例案例。</span><span class="sxs-lookup"><span data-stu-id="8b54a-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="8b54a-143">如果您的組織沒有直接向內撥號 () 為個別使用者設定的電話號碼，且每位使用者的線路 URI *只* 會以分機號碼來設定，則內部使用者可以只撥打分機號碼撥打一個分機號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="8b54a-144">不過，您必須設定標準化規則，以套用至分支網站使用者的呼叫與分機號碼相符的中央網站使用者。</span><span class="sxs-lookup"><span data-stu-id="8b54a-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="8b54a-145">在分支網站與中央網站之間的 WAN 連結可供使用的情況下，分支網站使用者對中央網站使用者的呼叫不需要符合的正規化規則來轉譯號碼，因為通話不會透過 PSTN 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8b54a-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="8b54a-146">例如：</span><span class="sxs-lookup"><span data-stu-id="8b54a-146">For example:</span></span>


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
<th><span data-ttu-id="8b54a-147">規則名稱</span><span class="sxs-lookup"><span data-stu-id="8b54a-147">Rule name</span></span></th>
<th><span data-ttu-id="8b54a-148">描述</span><span class="sxs-lookup"><span data-stu-id="8b54a-148">Description</span></span></th>
<th><span data-ttu-id="8b54a-149">號碼模式</span><span class="sxs-lookup"><span data-stu-id="8b54a-149">Number pattern</span></span></th>
<th><span data-ttu-id="8b54a-150">Translation</span><span class="sxs-lookup"><span data-stu-id="8b54a-150">Translation</span></span></th>
<th><span data-ttu-id="8b54a-151">範例</span><span class="sxs-lookup"><span data-stu-id="8b54a-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b54a-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="8b54a-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="8b54a-153">不轉譯5位數的數位</span><span class="sxs-lookup"><span data-stu-id="8b54a-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="8b54a-154">^ ( \d {5}) $</span><span class="sxs-lookup"><span data-stu-id="8b54a-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="8b54a-155">$1</span><span class="sxs-lookup"><span data-stu-id="8b54a-155">$1</span></span></p></td>
<td><p><span data-ttu-id="8b54a-156">未轉譯10001</span><span class="sxs-lookup"><span data-stu-id="8b54a-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b54a-157">您也必須在特定案例中容納分機號碼，例如在分支網站與中央網站之間的 WAN 連結無法使用，以及必須透過 PSTN 路由傳送分支網站的電話時。</span><span class="sxs-lookup"><span data-stu-id="8b54a-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="8b54a-158">在 WAN 中斷期間，如果分支網站使用者只會撥打中央網站使用者的分機呼叫中央網站使用者，您必須有一個輸出轉譯規則，以加入中央網站使用者的完整電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="8b54a-159">如果使用者的列 URI 包含您組織的完整電話號碼和使用者的唯一分機號碼，而不是使用者特有的完整電話號碼，則您必須有一個輸出轉譯規則，可改為新增組織的完整電話號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="8b54a-160">例如：</span><span class="sxs-lookup"><span data-stu-id="8b54a-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b54a-161">描述</span><span class="sxs-lookup"><span data-stu-id="8b54a-161">Description</span></span></th>
<th><span data-ttu-id="8b54a-162">符合模式</span><span class="sxs-lookup"><span data-stu-id="8b54a-162">Matching pattern</span></span></th>
<th><span data-ttu-id="8b54a-163">Translation</span><span class="sxs-lookup"><span data-stu-id="8b54a-163">Translation</span></span></th>
<th><span data-ttu-id="8b54a-164">範例</span><span class="sxs-lookup"><span data-stu-id="8b54a-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b54a-165">將5位數號碼轉譯為使用者的電話號碼和分機號碼</span><span class="sxs-lookup"><span data-stu-id="8b54a-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="8b54a-166">^ ( \d {5}) $</span><span class="sxs-lookup"><span data-stu-id="8b54a-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="8b54a-167">+ 14255550123; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="8b54a-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="8b54a-168">10001會轉譯為 + 14255550123; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="8b54a-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b54a-169">將5位數號碼轉譯為您組織的電話號碼和使用者的分機號碼</span><span class="sxs-lookup"><span data-stu-id="8b54a-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="8b54a-170">^ ( \d {5}) $</span><span class="sxs-lookup"><span data-stu-id="8b54a-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="8b54a-171">+ 14255550100; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="8b54a-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="8b54a-172">10001會轉譯為 + 14255550100; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="8b54a-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b54a-173">在此案例中，如果處理與 PSTN 間重新路由的主幹對等動作不支援分機號碼，則輸出轉譯規則也必須移除分機號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="8b54a-174">例如：</span><span class="sxs-lookup"><span data-stu-id="8b54a-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b54a-175">描述</span><span class="sxs-lookup"><span data-stu-id="8b54a-175">Description</span></span></th>
<th><span data-ttu-id="8b54a-176">符合模式</span><span class="sxs-lookup"><span data-stu-id="8b54a-176">Matching pattern</span></span></th>
<th><span data-ttu-id="8b54a-177">Translation</span><span class="sxs-lookup"><span data-stu-id="8b54a-177">Translation</span></span></th>
<th><span data-ttu-id="8b54a-178">範例</span><span class="sxs-lookup"><span data-stu-id="8b54a-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b54a-179">從具有分機號碼的電話號碼中移除分機號碼</span><span class="sxs-lookup"><span data-stu-id="8b54a-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="8b54a-180">^\+ ( \d *) ; ext = ( \d*) $</span><span class="sxs-lookup"><span data-stu-id="8b54a-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="8b54a-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="8b54a-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="8b54a-182">+ 14255550123; ext = 10001 會轉譯成 + 14255550123</span><span class="sxs-lookup"><span data-stu-id="8b54a-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b54a-183">WAN 連結是否可供使用時，如果您的組織未針對個別使用者設定號碼，且使用者的線路 URI 中包含組織的電話號碼和使用者的唯一分機號碼，則您必須使用分支網站上的主幹對等或 PSTN 閘道可存取的號碼，設定組織的電話號碼行 URI。</span><span class="sxs-lookup"><span data-stu-id="8b54a-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="8b54a-184">您也必須設定組織的電話號碼行 URI，以包含其專屬的唯一分機，以路由傳送至該號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="8b54a-185">如需網站間的 WAN 連結無法使用時，從中央網站使用者呼叫至分支網站使用者的詳細資訊，請參閱本主題稍後的「準備語音信箱留存功能」。</span><span class="sxs-lookup"><span data-stu-id="8b54a-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="8b54a-186">如需撥號對應表及正規化規則（包括其他範例規則）的詳細資訊，請參閱部署檔中的規劃檔及設定[Lync server 2013](lync-server-2013-configuring-dial-plans.md)中的撥號對應表中的撥號對應表[和正常化2013規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="8b54a-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="8b54a-187">如需輸出轉譯規則的詳細資訊，請參閱部署檔中的規劃檔及[定義轉譯2013規則](lync-server-2013-defining-translation-rules.md)中的 lync server 2013 中的[轉譯規則](lync-server-2013-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="8b54a-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="8b54a-188">準備語音信箱留存能力</span><span class="sxs-lookup"><span data-stu-id="8b54a-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="8b54a-189">Exchange 整合通訊 (UM) 通常只安裝在中央網站，而非位於分支網站。</span><span class="sxs-lookup"><span data-stu-id="8b54a-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="8b54a-190">即使分支網站與中央網站之間的 WAN 連結無法使用，來電者還是可以留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="8b54a-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="8b54a-191">因此，設定 Exchange UM 自動語音應答電話號碼（為分支網站使用者提供語音信箱）的行 URI 時，除了語音原則、撥號對應表，以及適用于該語音信箱號碼的正規化規則之外，還需要特別考慮。</span><span class="sxs-lookup"><span data-stu-id="8b54a-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="8b54a-192">Survivable 分支裝置 (Sba) 和 Survivable 分支伺服器在 WAN 中斷期間為分支使用者提供語音信箱留存能力。</span><span class="sxs-lookup"><span data-stu-id="8b54a-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="8b54a-193">具體說來，如果您是使用 Survivable 分支裝置或 Survivable 分支伺服器，而 WAN 變成無法使用，則 SBA 或 Survivable Branch 伺服器會透過 PSTN 將未接聽的電話重新連接到中央網站的 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="8b54a-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="8b54a-194">透過 SBA 或 Survivable Branch 伺服器，使用者也可以透過 PSTN 在 WAN 中斷期間取回語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="8b54a-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="8b54a-195">最後，在 WAN 中斷期間，Survivable Branch 裝置或 Survivable Branch 伺服器會將未接來電通知排入佇列，然後在 WAN 還原時，將其上傳至 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8b54a-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="8b54a-196">若要協助確保語音信箱重新路由可復原，請確定您已將中央網站集區的 FQDN 和 Edge Server FQDN 專案的專案新增至 Survivable 分支伺服器上的主機檔案。</span><span class="sxs-lookup"><span data-stu-id="8b54a-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="8b54a-197">否則，如果您在分支網站上沒有 DNS 伺服器，則 DNS 解析可能會超時。</span><span class="sxs-lookup"><span data-stu-id="8b54a-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="8b54a-198">我們建議分支網站使用者的語音信箱留存能力的下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b54a-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="8b54a-199">Microsoft Exchange 管理員應該設定 Exchange UM 自動語音應答 (AA) 只接受郵件。</span><span class="sxs-lookup"><span data-stu-id="8b54a-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="8b54a-200">此設定會停用所有其他一般功能，例如轉接至使用者或轉接至操作員，並且限制 AA 只接受郵件。</span><span class="sxs-lookup"><span data-stu-id="8b54a-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="8b54a-201">此外，Exchange 系統管理員可以使用一般 AA 或自訂的 AA，將通話路由傳送至操作員。</span><span class="sxs-lookup"><span data-stu-id="8b54a-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="8b54a-202">Lync Server 管理員應該取得 AA 電話號碼，並使用該電話號碼做為 Survivable 分支裝置或分支伺服器之語音信箱重新路由設定中的 **exchange um 自動** 語音應答編號。</span><span class="sxs-lookup"><span data-stu-id="8b54a-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="8b54a-203">Lync Server 系統管理員應取得 Exchange UM 訂戶存取電話號碼，並使用該號碼做為 Survivable Branch 裝置或 Survivable Branch 伺服器之語音信箱重新路由設定中的 **訂戶訪問** 號碼。</span><span class="sxs-lookup"><span data-stu-id="8b54a-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="8b54a-204">Lync Server 管理員應該設定 Exchange UM，以便在 WAN 中斷期間，只有一個撥號對應表與需要存取語音信箱的所有分支使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="8b54a-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="8b54a-205">當 WAN 連結無法使用時，可將分支網站使用者的通話路由傳送至使用者的 Exchange 整合通訊 (UM) 語音信箱，但只有在套用至通話的語音原則指定了唯一且不含分機號碼的語音信箱電話號碼時。</span><span class="sxs-lookup"><span data-stu-id="8b54a-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="8b54a-206">Branch-Site 恢復功能的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="8b54a-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="8b54a-207">硬體和軟體需求會根據您的恢復解決方案而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8b54a-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="8b54a-208">Survivable 分支裝置的需求</span><span class="sxs-lookup"><span data-stu-id="8b54a-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="8b54a-209">必要的硬體和軟體已內置於 Survivable 分支裝置中。</span><span class="sxs-lookup"><span data-stu-id="8b54a-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="8b54a-210">不過，我們也建議每個分支網站部署 DHCP 伺服器以取得用戶端 IP 位址;否則，當 DHCP 租用到期時，用戶端將不會有 IP 連線能力。</span><span class="sxs-lookup"><span data-stu-id="8b54a-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="8b54a-211">如果企業 DNS 伺服器僅位於中央網站，分支網站使用者將無法在 WAN 中斷期間與其連線，因此使用 DNS SRV (服務 (SRV) 資源記錄) 的 Lync Server 探索會失敗。</span><span class="sxs-lookup"><span data-stu-id="8b54a-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="8b54a-212">為了確保 WAN 中斷期間的提示重新路由，必須在分支網站上快取 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="8b54a-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="8b54a-213">如果分支路由器支援，請開啟 DNS 快取。</span><span class="sxs-lookup"><span data-stu-id="8b54a-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="8b54a-214">或者，您可以在分支部署 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8b54a-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="8b54a-215">這可以是獨立的伺服器，也可以是支援 DNS 功能的 Survivable 分支裝置版本。</span><span class="sxs-lookup"><span data-stu-id="8b54a-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="8b54a-216">如需詳細資訊，請與您的 Survivable 分支裝置提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="8b54a-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b54a-217">不需要有分支網站的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="8b54a-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="8b54a-218">Survivable 分支裝置會使用特殊的憑證來驗證用戶端，以回應用戶端的憑證要求登入。</span><span class="sxs-lookup"><span data-stu-id="8b54a-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="8b54a-219">Lync 用戶端可以使用 DHCP 選項 120 (SIP 註冊器選項) 探索 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="8b54a-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="8b54a-220">這可以採用下列其中一種方式進行設定：</span><span class="sxs-lookup"><span data-stu-id="8b54a-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="8b54a-221">在分支網站上設定 DHCP 伺服器以回復 DHCP 120 查詢，傳回 Survivable Branch 裝置或 Survivable Branch Server 上之註冊機的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8b54a-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="8b54a-222">開啟 Lync Server DHCP。</span><span class="sxs-lookup"><span data-stu-id="8b54a-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="8b54a-223">當此功能開啟時，Lync Server 註冊機構會回應 DHCP 選項120查詢。</span><span class="sxs-lookup"><span data-stu-id="8b54a-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="8b54a-224">請注意，註冊機構不會回應 DHCP 選項120以外的任何 DHCP 查詢。</span><span class="sxs-lookup"><span data-stu-id="8b54a-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="8b54a-225">此外，針對具有多個子網的大型分支網站，應啟用 DHCP 轉送代理程式，以將 DHCP 選項120查詢轉寄至 DHCP 伺服器 (設定 1) 或註冊機 (設定 2) 。</span><span class="sxs-lookup"><span data-stu-id="8b54a-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="8b54a-226">最後，分支網站使用者必須針對 Enterprise Voice 進行設定，並使用適當的整合通訊端點進行布建。</span><span class="sxs-lookup"><span data-stu-id="8b54a-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="8b54a-227">Survivable 分支伺服器的需求</span><span class="sxs-lookup"><span data-stu-id="8b54a-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="8b54a-228">Survivable 分支伺服器的需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="8b54a-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="8b54a-229">如需詳細資訊，請參閱規劃檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b54a-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="8b54a-230">Full-Scale Lync Server Branch-Site 部署的需求</span><span class="sxs-lookup"><span data-stu-id="8b54a-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="8b54a-231">如需詳細資訊，請參閱規劃檔中的 [判斷您的 Lync Server 2013 基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b54a-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

