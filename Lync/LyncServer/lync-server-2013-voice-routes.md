---
title: Lync Server 2013：語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="c0995-102">Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="c0995-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0995-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c0995-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c0995-104">[通話路線] 可指定 Lync Server 處理企業語音使用者所放的出站通話的方式。</span><span class="sxs-lookup"><span data-stu-id="c0995-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="c0995-105">當使用者撥打電話號碼時，前端伺服器會根據需要將撥號字串正常化為. 164 格式，並嘗試將它與 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="c0995-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="c0995-106">如果伺服器無法進行相符，就會根據數位來套用撥出電話路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="c0995-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="c0995-107">定義該邏輯的最後一個步驟，就是針對每一組在每個撥號方案中列出的目的地電話號碼，建立單獨的命名呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c0995-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="c0995-108">在您定義出站呼叫路由前，您應該完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c0995-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="c0995-109">部署一個或多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="c0995-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="c0995-110">視需要為網站、個人和連絡人物件建立撥號方案。</span><span class="sxs-lookup"><span data-stu-id="c0995-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="c0995-111">建立公用交換電話網絡（PSTN）使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="c0995-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="c0995-112">此外，若要啟用出站呼叫路由，您必須建立並指派一或多個語音原則。</span><span class="sxs-lookup"><span data-stu-id="c0995-112">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="c0995-113">您可以在定義出站通話路由之前或之後執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c0995-113">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="c0995-114">針對每個路線，您必須指定：</span><span class="sxs-lookup"><span data-stu-id="c0995-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="c0995-115">可輕鬆辨識路由的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0995-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="c0995-116">在名稱本身可能不足以描述路由的情況下，選用的描述。</span><span class="sxs-lookup"><span data-stu-id="c0995-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="c0995-117">標識要套用路線之目的地電話號碼的正則運算式相符模式，以及不要套用相符模式的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="c0995-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="c0995-118">您想要指派給路線的一個或多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="c0995-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="c0995-119">使用者必須擁有的 PSTN 使用記錄，才能撥打符合目的地電話號碼正則運算式的號碼。</span><span class="sxs-lookup"><span data-stu-id="c0995-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="c0995-120">您可以在 Lync Server [控制台] 中指定呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c0995-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="c0995-121">這些呼叫路由會填入伺服器路由表，讓 Lync Server 用來傳送發往 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c0995-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="c0995-122">M:N 幹線支援</span><span class="sxs-lookup"><span data-stu-id="c0995-122">M:N Trunk Support</span></span>

<span data-ttu-id="c0995-123">Lync Server 提供如何將呼叫路由至 PSTN 的靈活性。</span><span class="sxs-lookup"><span data-stu-id="c0995-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="c0995-124">語音路由指定 PSTN 的一組 trunks，可用於特定語音通話。</span><span class="sxs-lookup"><span data-stu-id="c0995-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="c0995-125">幹線會將中繼伺服器與埠號碼與 PSTN 閘道和偵聽埠號碼建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c0995-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="c0995-126">這個邏輯關聯可讓中繼伺服器與多個閘道建立關聯，且有多個連線至同一個閘道。</span><span class="sxs-lookup"><span data-stu-id="c0995-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="c0995-127">定義通話路線時，您可以指定與該路線相關聯的 trunks，但不會指定哪些中繼伺服器與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="c0995-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="c0995-128">若要透過定義中繼伺服器與 PSTN 閘道、IP Pbx 及會話邊界控制器（SBCs）之間的關聯來建立 trunks，請使用 [拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="c0995-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="c0995-129">最低成本的路由</span><span class="sxs-lookup"><span data-stu-id="c0995-129">Least-Cost Routing</span></span>

<span data-ttu-id="c0995-130">您可以指定要傳送不同數位的 trunks，讓您能夠判斷哪些路線會產生最低的成本並據此進行執行。</span><span class="sxs-lookup"><span data-stu-id="c0995-130">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="c0995-131">選取 [trunks] 中的一般規則是，選擇最接近目的地編號位置的主幹，以將長途費用降至最低。</span><span class="sxs-lookup"><span data-stu-id="c0995-131">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="c0995-132">例如，如果您使用的是位於紐約，且是以羅馬的方式撥打數位，您就會在您的羅馬 office 中，將電話撥入到與閘道的主幹，因此只會在當地電話中承擔費用。</span><span class="sxs-lookup"><span data-stu-id="c0995-132">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="c0995-133">如需如何使用最低成本路由的範例，請考慮下列事項： Fabrikam 決定讓德文使用者使用美國主幹來撥打美制電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c0995-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="c0995-134">Fabrikam 也想要設定系統，讓來自美國 Lync 伺服器使用者的所有呼叫在德國，以及在與在德國的閘道的主幹中連續的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="c0995-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="c0995-135">這份工藝路線將節省金錢，因為從德國到奧地利的呼叫會比從美國至奧地利通話的費用低。</span><span class="sxs-lookup"><span data-stu-id="c0995-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="c0995-136">翻譯出站撥號字串</span><span class="sxs-lookup"><span data-stu-id="c0995-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="c0995-137">Lync Server 2013 （例如其直屬前置任務）需要將所有撥號字串標準化為 E.i 格式，才能執行反向數位查閱（RNL）。</span><span class="sxs-lookup"><span data-stu-id="c0995-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c0995-138">針對需要以本機撥號格式翻譯數位的閘道或私人分支交換（Pbx），Lync Server 2013 可讓您建立一或多個規則，協助您在將呼叫的號碼傳送到去.</span><span class="sxs-lookup"><span data-stu-id="c0995-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="c0995-139">例如，您可以撰寫規則，以從撥號字串的開頭移除 + 44，然後將它取代為0144。</span><span class="sxs-lookup"><span data-stu-id="c0995-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="c0995-140">有了 Lync Server 2013，就可以建立一或多個規則，協助您在將通話號碼傳送到主幹之前操作。</span><span class="sxs-lookup"><span data-stu-id="c0995-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="c0995-141">在規劃您的 trunks 中，將閘道與中繼伺服器：埠配對進行關聯，將 trunks 設定為類似的本機撥號需求，然後減少所需翻譯規則的數目，以及撰寫它們所需的時間。</span><span class="sxs-lookup"><span data-stu-id="c0995-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="c0995-142">設定本機號碼</span><span class="sxs-lookup"><span data-stu-id="c0995-142">Configuring Caller ID</span></span>

<span data-ttu-id="c0995-143">Lync Server 提供一種操作本機號碼撥出電話的方式。</span><span class="sxs-lookup"><span data-stu-id="c0995-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="c0995-144">例如，如果組織想要遮罩員工的直接撥號延伸，並以一般的公司或部門編號加以取代，系統管理員可以使用 Lync Server [控制台] 來取消本機號碼，並將它取代為指定的替換呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="c0995-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="c0995-145">在規劃路由邏輯時，請考慮您想要此選項的人員、群組、網站（甚至對於所有員工而言，也是如此）。</span><span class="sxs-lookup"><span data-stu-id="c0995-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0995-146">對於在 PSTN 上重新路由的呼叫，將會出現一般本機號碼，而不是原始本機號碼。</span><span class="sxs-lookup"><span data-stu-id="c0995-146">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="c0995-147">這可能會導致呼叫避開受呼叫者所設定的 [請勿打擾] 或 [隱私權設定]。</span><span class="sxs-lookup"><span data-stu-id="c0995-147">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="c0995-148">其他路由邏輯</span><span class="sxs-lookup"><span data-stu-id="c0995-148">Additional Routing Logic</span></span>

<span data-ttu-id="c0995-149">在建立出站通話路線中，您應該注意到下列因素可能會影響路由邏輯：</span><span class="sxs-lookup"><span data-stu-id="c0995-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="c0995-150">在聯盟邊界建立通話的位置，URI 的網域部分是用來將呼叫路由到負責套用輸出路由邏輯的企業。</span><span class="sxs-lookup"><span data-stu-id="c0995-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="c0995-151">如果要求 URI 的網域部分不包含企業支援的網域，伺服器上的傳出路由元件不會處理通話。</span><span class="sxs-lookup"><span data-stu-id="c0995-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="c0995-152">如果使用者未啟用企業語音，伺服器會視需要套用其他路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="c0995-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="c0995-153">如果通話路由至完全佔用的閘道（所有幹線線路都繁忙），閘道就會拒絕通話，而輸出路由邏輯則會將呼叫重新導向到下一個最低成本的路線。</span><span class="sxs-lookup"><span data-stu-id="c0995-153">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="c0995-154">請謹慎考慮，因為小型辦公室海外（例如，蘇黎世）的閘道可能會實際攜帶大量非使用中的通訊，以進行國際通話。</span><span class="sxs-lookup"><span data-stu-id="c0995-154">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="c0995-155">如果沒有針對此額外的流量正確地調整閘道大小，就可以透過德國的閘道來傳送對瑞士的呼叫，從而產生較大的付費費用。</span><span class="sxs-lookup"><span data-stu-id="c0995-155">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

