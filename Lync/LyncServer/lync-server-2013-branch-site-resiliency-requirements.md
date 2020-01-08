---
title: Lync Server 2013：分支網站復原需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="0189b-102">Lync Server 2013 的分支網站復原需求</span><span class="sxs-lookup"><span data-stu-id="0189b-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0189b-103">_**主題上次修改日期：** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="0189b-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="0189b-104">本主題將協助您準備使用者以進行分支網站復原及語音信箱留存，同時也會指定相關的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="0189b-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="0189b-105">準備分支使用者以進行分支網站復原</span><span class="sxs-lookup"><span data-stu-id="0189b-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="0189b-106">將自己的註冊機構池設定為 Survivable 分支機搆（SBA）或 Survivable 分支伺服器，以準備使用者以進行分支網站復原。</span><span class="sxs-lookup"><span data-stu-id="0189b-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="0189b-107">分支使用者的註冊機構指派</span><span class="sxs-lookup"><span data-stu-id="0189b-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="0189b-108">不論您選擇哪一個分支網站復原解決方案，您都必須將主要註冊機構指派給每個使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="0189b-109">分支網站使用者無論是在 Survivable 分支裝置、Survivable 分支伺服器或獨立的 Lync Server 2013 標準版或 Enterprise Edition 伺服器中，都必須在分支網站上註冊註冊機構。</span><span class="sxs-lookup"><span data-stu-id="0189b-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="0189b-110">必須具備網域名稱系統（DNS）服務（SRV）資源記錄，才能讓用戶端探索其註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="0189b-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="0189b-111">如果 Survivable 分支裝置無法使用，這就是分支網站用戶端將如何自動探索備份註冊機構。</span><span class="sxs-lookup"><span data-stu-id="0189b-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="0189b-112">如果分支網站沒有 DNS 伺服器，有兩種方法可讓您設定發現 Survivable 分支裝置或 Survivable 分支伺服器的兩種方式：</span><span class="sxs-lookup"><span data-stu-id="0189b-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="0189b-113">在分支網站的動態主機設定通訊協定（DHCP）伺服器上，設定 DHCP 選項120，以指向 Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="0189b-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0189b-114">將 Survivable 分支裝置或 Survivable 分支伺服器設定為回應 DHCP 120 查詢。</span><span class="sxs-lookup"><span data-stu-id="0189b-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="0189b-115">分支使用者的語音路由</span><span class="sxs-lookup"><span data-stu-id="0189b-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="0189b-116">我們建議您針對分支網站中的使用者，建立個別的使用者層級語音透過網際網路通訊協定（VoIP）原則。</span><span class="sxs-lookup"><span data-stu-id="0189b-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="0189b-117">此原則應該包含使用 Survivable 分支裝置或分支伺服器閘道的主要路由，以及使用主幹與中央網站上的公用交換電話網絡（PSTN）閘道的一或多個備份路由。</span><span class="sxs-lookup"><span data-stu-id="0189b-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="0189b-118">如果主要路線無法使用，則會改用使用一或多個中央網站閘道的備份路由。</span><span class="sxs-lookup"><span data-stu-id="0189b-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="0189b-119">如此一來，不論使用者的登錄位置為何（在分支網站註冊機構或中央網站的 [備份註冊機構] 池中），使用者的 VoIP 原則都將會生效。</span><span class="sxs-lookup"><span data-stu-id="0189b-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="0189b-120">在容錯移轉案例中，這是一個重要的考慮。</span><span class="sxs-lookup"><span data-stu-id="0189b-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="0189b-121">例如，如果您需要重新命名 Survivable 分支裝置，或重新設定 Survivable 分支裝置以連線到中央網站上的備份註冊機構池，則您必須將分支網站使用者移至中心網站中的持續時間。</span><span class="sxs-lookup"><span data-stu-id="0189b-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="0189b-122">（如需重新命名或重新配置 Survivable 分支裝置的詳細資料，請參閱附錄 B：在部署檔中的[Lync Server 2013 中管理 Survivable 分支裝置](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)。）如果這些使用者沒有使用者層級 VoIP 原則或使用者層級的撥號方案，當使用者移至另一個網站時，中心網站的網站層級 VoIP 原則和網站層級撥號方案預設會套用至使用者，而不是分支網站網站層級 VoIP 原則和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0189b-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="0189b-123">在這種情況下，除非 [備份註冊器] 池所使用的網站層級 VoIP 原則和網站層級撥號方案也會套用至分支網站使用者，否則他們的呼叫將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0189b-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="0189b-124">例如，如果將位於日本的分支網站的使用者移至雷蒙德中的中央網站，則會將適用于所有7位數通話的正常化規則（含1425此標準），不可能針對這些使用者適當地翻譯通話。</span><span class="sxs-lookup"><span data-stu-id="0189b-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0189b-125">當您建立分支辦公室備份路線時，建議您將兩個 PSTN 手機使用量記錄新增至分支機搆使用者原則，並將不同的路由指派給每一個。</span><span class="sxs-lookup"><span data-stu-id="0189b-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="0189b-126">第一個或 [主要] 路由會直接呼叫與 Survivable 分支裝置（SBA）或分支伺服器關聯的閘道;第二個或 [備份] 路由會直接呼叫中央網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="0189b-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="0189b-127">在定向呼叫中，SBA 或分支伺服器會在嘗試第二筆使用記錄之前，先嘗試指派給第一個 PSTN 使用狀況記錄的所有路由。</span><span class="sxs-lookup"><span data-stu-id="0189b-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="0189b-128">若要確保當分支機搆或 Survivable 分支裝置網站的 Windows 元件無法使用（例如，如果 Survivable 分支裝置或分支）時，對分支網站使用者的撥入呼叫將會達到這些使用者的要求（例如，可能會發生這種情況）。閘道已關閉維護），請在閘道建立容錯移轉路由（或使用您的直接向內撥號（已執行）提供者），將來電重新導向到中央網站上的備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="0189b-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="0189b-129">從這裡開始，通話會透過 WAN 連結路由至分支使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="0189b-130">請確定路由會將數位轉換成符合 PSTN 閘道或其他中繼對等的已接受電話號碼格式。</span><span class="sxs-lookup"><span data-stu-id="0189b-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="0189b-131">如需建立容錯移轉路由的詳細資料，請參閱[在 Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)。</span><span class="sxs-lookup"><span data-stu-id="0189b-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="0189b-132">同時為與分支網站上的閘道相關聯的主幹建立服務層級撥號方案，以正常化來電。</span><span class="sxs-lookup"><span data-stu-id="0189b-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="0189b-133">如果您在分支網站上有兩個 Survivable 分支裝置，您可以為這兩者建立一個網站層級撥號方案，除非有任何需要的不同服務層級方案。</span><span class="sxs-lookup"><span data-stu-id="0189b-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0189b-134">若要考慮由任何分支網站使用者使用中心網站資源來進行目前狀態、會議或容錯移轉，我們建議您考慮每個分支網站使用者，就像該使用者已在中央網站註冊一樣。</span><span class="sxs-lookup"><span data-stu-id="0189b-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="0189b-135">分支網站使用者的數目目前沒有限制，包括向 Survivable 分支裝置註冊的使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="0189b-136">我們也建議您建立使用者層級撥號方案和語音原則，然後將它指派給分支網站使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="0189b-137">如需詳細資訊，請參閱[在 Lync server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)，並在部署檔中[為 Lync server 2013 中的分支使用者建立 VoIP 路由策略](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)。</span><span class="sxs-lookup"><span data-stu-id="0189b-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="0189b-138">路由分機號碼</span><span class="sxs-lookup"><span data-stu-id="0189b-138">Routing Extension Numbers</span></span>

<span data-ttu-id="0189b-139">當您為分支網站使用者準備撥號方案和語音原則時，請務必包含符合在 msRTCSIP 行（或 Line URI）屬性中使用之字串和數位格式的正常化規則和翻譯規則，以便在分支之間啟用 Lync 2013 通話網站使用者和中央網站使用者將會正確路由，特別是在由於 WAN 連結無法使用時，必須將呼叫重新路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="0189b-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="0189b-140">此外，撥打號碼時也有特殊考慮，包括分機號碼，而不只是電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="0189b-141">正常化規則與包含副檔名的行 Uri 相符，不論是獨佔或除了完整的 E. 164 電話號碼，還有其他需求。</span><span class="sxs-lookup"><span data-stu-id="0189b-141">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements.</span></span> <span data-ttu-id="0189b-142">本節將說明幾個範例案例，以使用分機號碼來路由行 Uri 通話。</span><span class="sxs-lookup"><span data-stu-id="0189b-142">This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="0189b-143">如果您的組織沒有為個別使用者設定直接撥出電話號碼，且每個使用者的 Line URI 都*只*使用分機號碼進行設定，則內部使用者可以撥打電話給對方，只撥打分機號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-143">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number.</span></span> <span data-ttu-id="0189b-144">不過，您必須設定正常化規則，才能套用到分支網站使用者的呼叫與分機號碼相符的中心網站使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-144">However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="0189b-145">在分支網站與中央網站之間提供 WAN 連結的情況下，分支網站使用者對中央網站使用者的呼叫不需要搭配的正常化規則來轉譯數位，因為通話不是透過 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="0189b-145">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN.</span></span> <span data-ttu-id="0189b-146">例如：</span><span class="sxs-lookup"><span data-stu-id="0189b-146">For example:</span></span>


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
<th><span data-ttu-id="0189b-147">規則名稱</span><span class="sxs-lookup"><span data-stu-id="0189b-147">Rule name</span></span></th>
<th><span data-ttu-id="0189b-148">描述</span><span class="sxs-lookup"><span data-stu-id="0189b-148">Description</span></span></th>
<th><span data-ttu-id="0189b-149">數位模式</span><span class="sxs-lookup"><span data-stu-id="0189b-149">Number pattern</span></span></th>
<th><span data-ttu-id="0189b-150">翻譯</span><span class="sxs-lookup"><span data-stu-id="0189b-150">Translation</span></span></th>
<th><span data-ttu-id="0189b-151">範例</span><span class="sxs-lookup"><span data-stu-id="0189b-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0189b-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="0189b-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="0189b-153">不會轉譯5位數的數位</span><span class="sxs-lookup"><span data-stu-id="0189b-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="0189b-154">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="0189b-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0189b-155">$1</span><span class="sxs-lookup"><span data-stu-id="0189b-155">$1</span></span></p></td>
<td><p><span data-ttu-id="0189b-156">未翻譯10001</span><span class="sxs-lookup"><span data-stu-id="0189b-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0189b-157">您也必須針對特定案例（例如當分支網站與中央網站之間的 WAN 連結無法使用，且必須透過 PSTN 路由來自分支網站的呼叫），才能容納延伸號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-157">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN.</span></span> <span data-ttu-id="0189b-158">在 WAN 中斷期間，如果分支網站使用者只是透過撥入中央網站使用者的副檔名話務中心網站使用者，您必須有一個加入中心網站使用者的完整電話號碼的輸出轉換規則。</span><span class="sxs-lookup"><span data-stu-id="0189b-158">During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number.</span></span> <span data-ttu-id="0189b-159">如果使用者的行 URI 包含貴組織的完整電話號碼和使用者的唯一分機號碼，而不是使用者唯一的電話號碼，則您必須有一個輸出翻譯規則，以將貴組織的完整電話號碼改為.</span><span class="sxs-lookup"><span data-stu-id="0189b-159">If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead.</span></span> <span data-ttu-id="0189b-160">例如：</span><span class="sxs-lookup"><span data-stu-id="0189b-160">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0189b-161">描述</span><span class="sxs-lookup"><span data-stu-id="0189b-161">Description</span></span></th>
<th><span data-ttu-id="0189b-162">相符的模式</span><span class="sxs-lookup"><span data-stu-id="0189b-162">Matching pattern</span></span></th>
<th><span data-ttu-id="0189b-163">翻譯</span><span class="sxs-lookup"><span data-stu-id="0189b-163">Translation</span></span></th>
<th><span data-ttu-id="0189b-164">範例</span><span class="sxs-lookup"><span data-stu-id="0189b-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0189b-165">將5位數的數位轉換為使用者的電話號碼和分機</span><span class="sxs-lookup"><span data-stu-id="0189b-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="0189b-166">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="0189b-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0189b-167">+ 14255550123; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="0189b-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="0189b-168">10001已轉譯為 + 14255550123; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="0189b-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0189b-169">將5位數的數位轉換為貴組織的電話號碼和使用者的分機</span><span class="sxs-lookup"><span data-stu-id="0189b-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="0189b-170">^ （\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="0189b-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="0189b-171">+ 14255550100; ext = $ 1</span><span class="sxs-lookup"><span data-stu-id="0189b-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="0189b-172">10001已轉譯為 + 14255550100; ext = 10001</span><span class="sxs-lookup"><span data-stu-id="0189b-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0189b-173">在這種情況下，如果處理對 PSTN 重新路由的幹線對等，不支援分機號碼，則輸出轉換規則也必須移除延伸號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-173">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number.</span></span> <span data-ttu-id="0189b-174">例如：</span><span class="sxs-lookup"><span data-stu-id="0189b-174">For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0189b-175">描述</span><span class="sxs-lookup"><span data-stu-id="0189b-175">Description</span></span></th>
<th><span data-ttu-id="0189b-176">相符的模式</span><span class="sxs-lookup"><span data-stu-id="0189b-176">Matching pattern</span></span></th>
<th><span data-ttu-id="0189b-177">翻譯</span><span class="sxs-lookup"><span data-stu-id="0189b-177">Translation</span></span></th>
<th><span data-ttu-id="0189b-178">範例</span><span class="sxs-lookup"><span data-stu-id="0189b-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0189b-179">從電話號碼中移除副檔名</span><span class="sxs-lookup"><span data-stu-id="0189b-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="0189b-180">^\+（\d *）; ext = （\d*） $</span><span class="sxs-lookup"><span data-stu-id="0189b-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="0189b-181">+ $1</span><span class="sxs-lookup"><span data-stu-id="0189b-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="0189b-182">+ 14255550123; ext = 10001 已轉譯為 + 14255550123</span><span class="sxs-lookup"><span data-stu-id="0189b-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0189b-183">無論是否有提供 WAN 連結，如果您的組織沒有為個別使用者設定號碼，且使用者的行 URI 包含貴組織的電話號碼和使用者的唯一分機號碼，則您必須設定組織的電話號碼行 URI，且分支網站上的幹線對等或 PSTN 閘道可達到該號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-183">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site.</span></span> <span data-ttu-id="0189b-184">您也必須設定貴組織的電話號碼行 URI，以包含自己的唯一分機，讓呼叫路由到該號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-184">You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="0189b-185">如需網站之間的 WAN 連結無法使用，請參閱本主題稍後的「準備語音信箱的準備工作] 使用者。</span><span class="sxs-lookup"><span data-stu-id="0189b-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="0189b-186">如需撥號方案和正常化規則的詳細資料（包括其他範例規則），請參閱在 lync server 2013 中的[撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)，並在 [部署] 檔中的 [ [lync server 2013](lync-server-2013-configuring-dial-plans.md) ] 中設定撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0189b-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="0189b-187">如需輸出轉換規則的詳細資料，請參閱在 lync server 2013 中的 [[翻譯] 規則](lync-server-2013-translation-rules.md)，並在 [部署] 檔中的 [ [lync server 2013] 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="0189b-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="0189b-188">準備語音信箱的留存能力</span><span class="sxs-lookup"><span data-stu-id="0189b-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="0189b-189">Exchange 整合通訊（UM）通常只會安裝在中央網站，而不是分支網站上。</span><span class="sxs-lookup"><span data-stu-id="0189b-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="0189b-190">即使分支網站與中央網站之間的 WAN 連結無法使用，來電者仍能留下語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="0189b-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="0189b-191">因此，針對為分支網站使用者提供語音信箱的 Exchange UM 自動語音應答電話號碼設定行 URI，除了語音原則、撥號方案，以及適用于該語音信箱的正常化規則以外，還需要考慮的事項。電話.</span><span class="sxs-lookup"><span data-stu-id="0189b-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="0189b-192">Survivable 分支裝置（SBAs）和 Survivable 分支伺服器會在 WAN 停機期間為分支使用者提供語音信箱留存。</span><span class="sxs-lookup"><span data-stu-id="0189b-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="0189b-193">特別是，如果您使用的是 Survivable 分支裝置或 Survivable 分支伺服器，且 WAN 無法使用，則 SBA 或 Survivable 分支伺服器會在中央網站將未接聽的電話重新連接到 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="0189b-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="0189b-194">在 SBA 或 Survivable 分支伺服器中，使用者也可以在 WAN 中斷期間透過 PSTN 檢索語音信箱訊息。</span><span class="sxs-lookup"><span data-stu-id="0189b-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="0189b-195">最後，在 WAN 中斷期間，Survivable 分支裝置或 Survivable 分支伺服器會列隊未接來電通知，然後在 WAN 還原時，將其上傳到 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0189b-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="0189b-196">若要確保語音信箱重新路由有復原能力，請務必將中央網站池的 FQDN 和 Edge 伺服器 FQDN 的專案新增至 Survivable 分支伺服器上的 hosts 檔案。</span><span class="sxs-lookup"><span data-stu-id="0189b-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="0189b-197">否則，如果您在分支網站上沒有 DNS 伺服器，則 DNS 解析可能會超時。</span><span class="sxs-lookup"><span data-stu-id="0189b-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="0189b-198">我們建議針對分支網站使用者的語音信箱留存功能進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="0189b-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="0189b-199">Microsoft Exchange 管理員應該將 Exchange UM 自動語音應答（AA）設定為僅接受郵件。</span><span class="sxs-lookup"><span data-stu-id="0189b-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="0189b-200">這個設定會停用所有其他的一般功能，例如轉接給使用者或傳送到操作員，並限制 AA 只接受訊息。</span><span class="sxs-lookup"><span data-stu-id="0189b-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="0189b-201">或者，Exchange 管理員可以使用一般 AA 或自訂的 AA，將呼叫路由至接線員。</span><span class="sxs-lookup"><span data-stu-id="0189b-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="0189b-202">Lync Server 管理員應採用 AA 電話號碼，並使用該電話號碼作為 Survivable 分支裝置或分支伺服器的語音信箱重新路由設定中的**exchange um 自動**語音應答號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="0189b-203">Lync Server 管理員應該取得 Exchange UM 訂閱者存取電話號碼，並在 Survivable 分支裝置或 Survivable 分支伺服器的語音信箱重新路由設定中，使用該號碼作為**訂閱者存取**號碼。</span><span class="sxs-lookup"><span data-stu-id="0189b-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0189b-204">Lync Server 管理員應該設定 Exchange UM，以便在 WAN 停機期間，只有一個撥號方案會與需要存取語音信箱的所有分支使用者產生關聯。</span><span class="sxs-lookup"><span data-stu-id="0189b-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="0189b-205">當 WAN 連結無法使用時，分支網站使用者的呼叫可以傳送到使用者的 Exchange 整合通訊（UM）語音信箱，但只有當套用到通話的語音原則指定了唯一且不含延伸的語音信箱電話號碼時電話.</span><span class="sxs-lookup"><span data-stu-id="0189b-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="0189b-206">分支網站復原的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="0189b-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="0189b-207">硬體和軟體需求會根據您的復原方案而有所不同。</span><span class="sxs-lookup"><span data-stu-id="0189b-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="0189b-208">Survivable 分支裝置的需求</span><span class="sxs-lookup"><span data-stu-id="0189b-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="0189b-209">Survivable 分支裝置內建了必要的硬體和軟體。</span><span class="sxs-lookup"><span data-stu-id="0189b-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="0189b-210">不過，我們也建議每個分支網站都要部署 DHCP 伺服器來取得用戶端 IP 位址;否則，當 DHCP 租約到期時，用戶端將沒有 IP 連線能力。</span><span class="sxs-lookup"><span data-stu-id="0189b-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="0189b-211">如果企業 DNS 伺服器只位於中央網站，分支網站使用者將無法在 WAN 中斷期間連線至這些使用者，因此使用 DNS SRV （服務（SRV）資源記錄）的 Lync Server 探索將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0189b-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="0189b-212">為了確保 WAN 停機期間的提示重新路由，DNS 記錄必須在分支網站上緩存。</span><span class="sxs-lookup"><span data-stu-id="0189b-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="0189b-213">如果分支路由器支援它，請開啟 DNS 快取。</span><span class="sxs-lookup"><span data-stu-id="0189b-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="0189b-214">或者，您可以在分支部署 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0189b-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="0189b-215">這可以是獨立伺服器或支援 DNS 功能的 Survivable 分支裝置版本。</span><span class="sxs-lookup"><span data-stu-id="0189b-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="0189b-216">如需詳細資訊，請與您的 Survivable 分支裝置提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="0189b-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0189b-217">在分支網站上不需要有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="0189b-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="0189b-218">Survivable 分支裝置會使用特殊憑證來驗證用戶端，讓用戶端在登入時回應用戶端的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="0189b-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="0189b-219">Lync 用戶端可以使用 DHCP 選項120（SIP 註冊器選項）來探索 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0189b-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="0189b-220">這可以使用下列兩種方法的其中一種來設定：</span><span class="sxs-lookup"><span data-stu-id="0189b-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="0189b-221">在分支網站設定 DHCP 伺服器，以回復 DHCP 120 查詢，這會傳回 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0189b-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="0189b-222">開啟 Lync Server DHCP。</span><span class="sxs-lookup"><span data-stu-id="0189b-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="0189b-223">開啟此功能時，Lync Server 註冊機構會回應 DHCP 選項120查詢。</span><span class="sxs-lookup"><span data-stu-id="0189b-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="0189b-224">請注意，註冊機構不會回應 DHCP 選項120以外的任何 DHCP 查詢。</span><span class="sxs-lookup"><span data-stu-id="0189b-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="0189b-225">此外，對於有多個子網的大型分支網站，必須啟用 DHCP 中繼代理程式，才能將 DHCP 選項120查詢轉寄至 DHCP 伺服器（設定1）或註冊機（配置2）。</span><span class="sxs-lookup"><span data-stu-id="0189b-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="0189b-226">最後，分支網站使用者必須針對企業語音進行設定，並使用適當的整合通訊端點進行設定。</span><span class="sxs-lookup"><span data-stu-id="0189b-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="0189b-227">Survivable 分支伺服器的需求</span><span class="sxs-lookup"><span data-stu-id="0189b-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="0189b-228">Survivable 分支伺服器的需求與前端伺服器的需求相同。</span><span class="sxs-lookup"><span data-stu-id="0189b-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="0189b-229">如需詳細資訊，請參閱規劃檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="0189b-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="0189b-230">全式 Lync Server 分支網站部署的需求</span><span class="sxs-lookup"><span data-stu-id="0189b-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="0189b-231">如需詳細資訊，請參閱在規劃檔中[判斷 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0189b-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

