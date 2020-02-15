---
title: Lync Server 2013： 語音路由
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
ms.openlocfilehash: 350b64c15b0819813b8287bb9b40272845f3a285
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="6397d-102">Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="6397d-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6397d-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="6397d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6397d-104">電話路由指定 Lync Server 處理由 Enterprise Voice 使用者的撥出電話的方式。</span><span class="sxs-lookup"><span data-stu-id="6397d-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="6397d-105">當使用者撥號碼時，前端伺服器撥號對應表將字串標準化為 E.164 格式，如有必要，並嘗試將使其符合 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="6397d-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="6397d-106">如果伺服器無法進行比對，它會套用撥出電話路由邏輯數為基礎。</span><span class="sxs-lookup"><span data-stu-id="6397d-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="6397d-107">定義該邏輯的最後一個步驟是建立個別的具名的呼叫路由目的地電話號碼中每個撥號對應表所列的每一組。</span><span class="sxs-lookup"><span data-stu-id="6397d-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="6397d-108">您定義撥出電話路由之前，您應該完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6397d-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="6397d-109">部署一或多個主幹。</span><span class="sxs-lookup"><span data-stu-id="6397d-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="6397d-110">視需要針對網站、 個人和連絡人物件，請建立撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="6397d-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="6397d-111">建立公用交換的電話網路 (PSTN) 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="6397d-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="6397d-112">此外，若要啟用撥出電話路由，您必須建立並指派一或多個語音原則。</span><span class="sxs-lookup"><span data-stu-id="6397d-112">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="6397d-113">之前或之後您定義撥出電話路由，您可以這麼做。</span><span class="sxs-lookup"><span data-stu-id="6397d-113">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="6397d-114">針對每個路徑，您必須指定：</span><span class="sxs-lookup"><span data-stu-id="6397d-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="6397d-115">依據路由可以輕易識別名稱。</span><span class="sxs-lookup"><span data-stu-id="6397d-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="6397d-116">在其中用名稱表達可能不足以描述該路由的情況下選用描述。</span><span class="sxs-lookup"><span data-stu-id="6397d-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="6397d-117">規則運算式比對模式，以識別要路由套用，以及要比對的模式為不套用的例外狀況的目標電話號碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="6397d-118">您想要指派至路由的一或多個主幹。</span><span class="sxs-lookup"><span data-stu-id="6397d-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="6397d-119">使用者必須要有為了撥打符合目標電話號碼 PSTN 使用方式記錄號碼規則運算式。</span><span class="sxs-lookup"><span data-stu-id="6397d-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="6397d-120">您可以在 Lync Server Control Panel 指定電話路由。</span><span class="sxs-lookup"><span data-stu-id="6397d-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="6397d-121">這些路由填入伺服器路由表，Lync Server 用以將通話路由傳送目的地為 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="6397d-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="6397d-122">M:N 主幹支援</span><span class="sxs-lookup"><span data-stu-id="6397d-122">M:N Trunk Support</span></span>

<span data-ttu-id="6397d-123">Lync Server 提供彈性方式來電會路由傳送至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="6397d-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="6397d-124">語音路由會指定一組可用於特定的語音通話 pstn 主幹。</span><span class="sxs-lookup"><span data-stu-id="6397d-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="6397d-125">主幹關聯至中繼伺服器及連接埠號碼的 PSTN 閘道及接聽連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="6397d-126">此邏輯關聯可讓多個閘道器相關聯並擁有多個連線到相同的閘道中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="6397d-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="6397d-127">定義通話路由傳送，當您指定該路由，相關聯的主幹，但未指定的中繼伺服器與路由相關聯的。</span><span class="sxs-lookup"><span data-stu-id="6397d-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="6397d-128">若要建立主幹藉由定義中繼伺服器和 PSTN 閘道、 IP Pbx 和工作階段邊界控制器 (Sbc) 之間的關係使用拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="6397d-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="6397d-129">成本最低的路由</span><span class="sxs-lookup"><span data-stu-id="6397d-129">Least-Cost Routing</span></span>

<span data-ttu-id="6397d-130">若要指定不同的數字會路由傳送主幹功能可讓您判斷哪些路由的最低成本可能會形成和據以實作它們。</span><span class="sxs-lookup"><span data-stu-id="6397d-130">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="6397d-131">中選取主幹的一般規則是為了減少長途電話選擇位置的目的號碼最接近的閘道主幹。</span><span class="sxs-lookup"><span data-stu-id="6397d-131">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="6397d-132">例如，如果您是在紐約並呼叫羅馬中的數字，您會延續通話的閘道主幹 IP 網路羅馬 office，因而產生僅適用於本機通話的費用。</span><span class="sxs-lookup"><span data-stu-id="6397d-132">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="6397d-133">如可能使用方式的最低成本路由的範例，請考慮下列： Fabrikam 決定，來啟用德文使用美國主幹撥打美國號碼給使用者。</span><span class="sxs-lookup"><span data-stu-id="6397d-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="6397d-134">Fabrikam 也想要設定系統，以便從美國 Lync Server 使用者對德國和相鄰的國家/地區的所有呼叫都終止上主幹，且在德國的閘道。</span><span class="sxs-lookup"><span data-stu-id="6397d-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="6397d-135">此路由會節省金錢，，因為奧地利，從 Germany 呼叫，例如美國奧地利呼叫成本低於。</span><span class="sxs-lookup"><span data-stu-id="6397d-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="6397d-136">轉譯撥出撥號字串</span><span class="sxs-lookup"><span data-stu-id="6397d-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="6397d-137">Lync Server 2013 中，其立即的前置任務，像需要所有撥號對應表被正規化為 E.164 格式目的執行反向號碼查閱 (RNL) 的字串。</span><span class="sxs-lookup"><span data-stu-id="6397d-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="6397d-138">主幹與閘道或專用交換機 (Pbx) 需要本機撥號格式轉譯的數字，Lync Server 2013 可讓您建立一或多個規則，協助操作尚未所撥的號碼 (亦即要求 URI) 路由傳送至主幹。</span><span class="sxs-lookup"><span data-stu-id="6397d-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="6397d-139">例如，您可以撰寫 + 44 移除標頭的撥號對應表的字串，並取代為 0144年的規則。</span><span class="sxs-lookup"><span data-stu-id="6397d-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="6397d-140">搭配 Lync Server 2013，就可以建立一或多個規則，協助操作尚未路由傳送至主幹的來電號碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="6397d-141">在規劃可與中繼伺服器： 連接埠 」 配對建立關聯閘道： 連接埠 」 配對，可能會很有用群組主幹類似區域撥號要求，從而減少必需的轉譯規則和撰寫它們所花費的時間的數目。</span><span class="sxs-lookup"><span data-stu-id="6397d-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="6397d-142">設定來電者識別碼</span><span class="sxs-lookup"><span data-stu-id="6397d-142">Configuring Caller ID</span></span>

<span data-ttu-id="6397d-143">Lync Server 提供方法來處理撥出電話的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="6397d-144">例如，如果組織想要遮罩員工直接撥分機，並取代一般公司或部門的數字，系統管理員可以這麼做來隱藏來電者識別碼，並取代以使用 Lync Server Control Panel指定替代來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="6397d-145">在規劃您的路由邏輯，請考慮哪些個人、 群組、 您會想為此選項的網站，甚至，是為所有員工。</span><span class="sxs-lookup"><span data-stu-id="6397d-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6397d-146">透過 PSTN 重新路由傳送的通話，一般的來電者識別碼將會出現而不是原始的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6397d-146">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="6397d-147">這可能會導致呼叫略過 [請勿打擾或隱私權受話者可能已經設定的設定。</span><span class="sxs-lookup"><span data-stu-id="6397d-147">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="6397d-148">其他路由邏輯</span><span class="sxs-lookup"><span data-stu-id="6397d-148">Additional Routing Logic</span></span>

<span data-ttu-id="6397d-149">在建立撥出電話路由時，您應該注意下列可能影響路由邏輯的因素：</span><span class="sxs-lookup"><span data-stu-id="6397d-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="6397d-150">透過同盟界限建立通話後 URI 的網域部分用來透過將電話路由傳送到負責套用輸出路由邏輯的企業。</span><span class="sxs-lookup"><span data-stu-id="6397d-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="6397d-151">如果要求 URI 的網域部分不包含企業支援的網域，在伺服器上的輸出路由元件不會處理通話。</span><span class="sxs-lookup"><span data-stu-id="6397d-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="6397d-152">如果使用者未啟用 Enterprise voice，伺服器就會套用其他路由邏輯，視。</span><span class="sxs-lookup"><span data-stu-id="6397d-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="6397d-153">如果來電會路由傳送至完全佔據閘道 （所有長途電話線都是忙碌中），閘道拒絕來電，並輸出路由邏輯會重新導向至下一步] 最低成本路由通話。</span><span class="sxs-lookup"><span data-stu-id="6397d-153">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="6397d-154">授與此仔細考量，因為調整大小的小型辦公室載運到海外 (例如，Zurich) 的閘道可能實際執行大量的錢瑞士國際呼叫流量。</span><span class="sxs-lookup"><span data-stu-id="6397d-154">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="6397d-155">如果閘道會不正確的此額外的流量調整大小，可能會被路由傳送呼叫瑞士透過閘道在德國，導致較大的費用。</span><span class="sxs-lookup"><span data-stu-id="6397d-155">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

