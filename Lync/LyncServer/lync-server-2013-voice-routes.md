---
title: Lync Server 2013：語音路由
description: Lync Server 2013：語音路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f3c548890c6d2a8c16808eebd9dd50e3ed2715
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554049"
---
# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="8abd7-103">Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="8abd7-103">Voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8abd7-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8abd7-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8abd7-105">通話路由會指定 Lync Server 如何處理 Enterprise Voice 使用者撥出的電話。</span><span class="sxs-lookup"><span data-stu-id="8abd7-105">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="8abd7-106">當使用者撥打號碼時，前端伺服器會將撥號字串正常化為 e.164 格式（如有必要），並嘗試將它與 SIP URI 進行比對。</span><span class="sxs-lookup"><span data-stu-id="8abd7-106">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="8abd7-107">如果伺服器無法進行相符，它會根據數目來套用傳出的呼叫路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="8abd7-107">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="8abd7-108">定義該邏輯的最後一個步驟，就是針對每一組每個撥號對應表中所列的目的地電話號碼建立個別命名的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="8abd7-108">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="8abd7-109">在您定義撥出電話路由之前，您應該完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8abd7-109">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="8abd7-110">部署一或多個主幹。</span><span class="sxs-lookup"><span data-stu-id="8abd7-110">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="8abd7-111">視需要建立網站、個人和連絡人物件的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="8abd7-111">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="8abd7-112">建立公用交換電話網路 (PSTN) 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="8abd7-112">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="8abd7-113">此外，若要啟用撥出電話路由，您必須建立並指派一或多個語音原則。</span><span class="sxs-lookup"><span data-stu-id="8abd7-113">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="8abd7-114">您可以在定義撥出電話路由之前或之後執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8abd7-114">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="8abd7-115">您必須為每個路由指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="8abd7-115">For each route, you must specify:</span></span>

  - <span data-ttu-id="8abd7-116">可輕鬆識別路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="8abd7-116">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="8abd7-117">選用的描述，在僅限名稱可能不足以描述路由的情況。</span><span class="sxs-lookup"><span data-stu-id="8abd7-117">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="8abd7-118">正則運算式比對模式，用來識別路由所套用的目的地電話號碼，以及不會套用對應模式的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="8abd7-118">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="8abd7-119">您想要指派給路由的一或多個主幹。</span><span class="sxs-lookup"><span data-stu-id="8abd7-119">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="8abd7-120">使用者必須具備的 PSTN 使用方式記錄，才能呼叫符合目的地電話號碼正則運算式的號碼。</span><span class="sxs-lookup"><span data-stu-id="8abd7-120">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="8abd7-121">您可以在 Lync Server 控制台中指定通話路由。</span><span class="sxs-lookup"><span data-stu-id="8abd7-121">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="8abd7-122">這些呼叫路由會填入伺服器路由表，Lync Server 會使用該表格路由傳送目的地為 PSTN 的電話。</span><span class="sxs-lookup"><span data-stu-id="8abd7-122">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="8abd7-123">M:N 主幹支援</span><span class="sxs-lookup"><span data-stu-id="8abd7-123">M:N Trunk Support</span></span>

<span data-ttu-id="8abd7-124">Lync Server 提供如何將通話路由傳送至 PSTN 的彈性。</span><span class="sxs-lookup"><span data-stu-id="8abd7-124">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="8abd7-125">語音路由會為 PSTN 指定一組主幹，以供特定語音通話使用。</span><span class="sxs-lookup"><span data-stu-id="8abd7-125">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="8abd7-126">主幹會將轉送伺服器與埠號碼與 PSTN 閘道和聆聽埠號碼產生關聯。</span><span class="sxs-lookup"><span data-stu-id="8abd7-126">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="8abd7-127">這個邏輯關聯可讓轉送伺服器與多個閘道產生關聯，並有多個連線到同一個閘道。</span><span class="sxs-lookup"><span data-stu-id="8abd7-127">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="8abd7-128">在定義呼叫路由時，您會指定與該路由相關聯的主幹，但不會指定哪些轉送伺服器與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="8abd7-128">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="8abd7-129">若要透過定義轉送伺服器和 PSTN 閘道、IP PBXs 及會話邊界控制器之間的關係來建立主幹 (SBCs) ，請使用拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="8abd7-129">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="8abd7-130">Least-Cost 路由</span><span class="sxs-lookup"><span data-stu-id="8abd7-130">Least-Cost Routing</span></span>

<span data-ttu-id="8abd7-131">指定傳送不同數位之主幹的功能，可讓您判斷哪個路由會產生最低的成本，並據此加以實施。</span><span class="sxs-lookup"><span data-stu-id="8abd7-131">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="8abd7-132">選取主幹的一般規則是選擇與目的地編號最接近之閘道的主幹，以最小化長途話費。</span><span class="sxs-lookup"><span data-stu-id="8abd7-132">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="8abd7-133">例如，如果您在紐約撥打的電話號碼，您可以使用羅馬 office 中的閘道來傳送 IP 網路的電話，因此只會對本機通話收取費用。</span><span class="sxs-lookup"><span data-stu-id="8abd7-133">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="8abd7-134">如需如何使用最低成本路由的範例，請考慮下列各項： Fabrikam 決定讓德文使用者使用 U.S. 主幹來撥打 U.S. 號碼。</span><span class="sxs-lookup"><span data-stu-id="8abd7-134">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="8abd7-135">Fabrikam 也會想要設定系統，使來自美國 Lync Server 使用者的所有呼叫都使用德國的閘道，以德國的主幹和連續的國家/地區終止。</span><span class="sxs-lookup"><span data-stu-id="8abd7-135">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="8abd7-136">這種路由會省錢，因為從德國到奧地利的呼叫的費用低於從美國到奧地利的呼叫成本。</span><span class="sxs-lookup"><span data-stu-id="8abd7-136">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="8abd7-137">轉換輸出撥號字串</span><span class="sxs-lookup"><span data-stu-id="8abd7-137">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="8abd7-138">Lync Server 2013 （如它的直屬前置任務）需要將所有撥號字串正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="8abd7-138">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="8abd7-139">針對使用閘道或私人分支交換的主幹 (PBXs) 需要以本機撥號格式轉譯的數位，Lync Server 2013 可讓您建立一或多個規則，協助操縱所撥打的號碼 (例如，在將它路由傳送至主幹之前要求 URI) 。</span><span class="sxs-lookup"><span data-stu-id="8abd7-139">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="8abd7-140">例如，您可以撰寫規則，以從撥號字串的 head 移除 + 44，並以0144取代。</span><span class="sxs-lookup"><span data-stu-id="8abd7-140">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="8abd7-141">使用 Lync Server 2013，可以建立一或多個規則，協助您在將通話號碼路由傳送至主幹之前操縱通話號碼。</span><span class="sxs-lookup"><span data-stu-id="8abd7-141">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="8abd7-142">在規劃主幹以關聯閘道：埠組與轉送伺服器：埠組，使用類似的本機撥號需求群組主幹可能會非常實用，因此可減少所需的轉譯規則數量，以及寫入其所需的時間。</span><span class="sxs-lookup"><span data-stu-id="8abd7-142">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="8abd7-143">設定來電者識別碼</span><span class="sxs-lookup"><span data-stu-id="8abd7-143">Configuring Caller ID</span></span>

<span data-ttu-id="8abd7-144">Lync Server 提供一種方法，用來操縱撥出電話的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="8abd7-144">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="8abd7-145">例如，如果組織想要掩蓋員工的直接撥號分機，並以一般公司或部門號碼取代它們，系統管理員可以使用 Lync Server 控制台來抑制來電者識別碼，並以指定的替代來電者識別碼取代它。</span><span class="sxs-lookup"><span data-stu-id="8abd7-145">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="8abd7-146">在規劃您的路由規則時，請考慮您要為其選擇此選項的個人、群組、網站（甚至是針對所有員工）。</span><span class="sxs-lookup"><span data-stu-id="8abd7-146">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8abd7-147">如果是透過 PSTN 重新路由傳送的通話，將會呈現一般來電者識別碼，而不是原始的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="8abd7-147">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="8abd7-148">這可能會導致來電繞過來電者可能已設定的 [打擾] 或 [隱私權] 設定。</span><span class="sxs-lookup"><span data-stu-id="8abd7-148">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="8abd7-149">其他路由邏輯</span><span class="sxs-lookup"><span data-stu-id="8abd7-149">Additional Routing Logic</span></span>

<span data-ttu-id="8abd7-150">在建立撥出電話路由時，您應該注意下列可能會影響路由邏輯的因素：</span><span class="sxs-lookup"><span data-stu-id="8abd7-150">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="8abd7-151">在透過同盟界限建立通話的情況下，URI 的網域部分是用來將通話路由傳送到負責應用輸出路由邏輯的企業。</span><span class="sxs-lookup"><span data-stu-id="8abd7-151">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="8abd7-152">如果要求 URI 的網域部分不包含企業所支援的網域，則伺服器上的輸出路由元件不會處理通話。</span><span class="sxs-lookup"><span data-stu-id="8abd7-152">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="8abd7-153">如果使用者未啟用 Enterprise Voice，則伺服器會依照適當方式套用其他路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="8abd7-153">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="8abd7-154">如果呼叫路由傳送至已完全佔用的閘道 (所有的骨幹路都會忙碌) 中，閘道會拒絕通話，而輸出路由邏輯會將呼叫重新導向至下一個最低成本的路由。</span><span class="sxs-lookup"><span data-stu-id="8abd7-154">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="8abd7-155">請特別注意，由於小型辦公室海外的閘道大小 (例如，蘇黎世) 實際上可能會攜帶大量非使用中的流量，以供瑞士撥打國際電話。</span><span class="sxs-lookup"><span data-stu-id="8abd7-155">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="8abd7-156">如果此額外流量的閘道大小不正確，則通話的電話會透過德國的閘道來路由傳送，進而產生較大的計費。</span><span class="sxs-lookup"><span data-stu-id="8abd7-156">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

