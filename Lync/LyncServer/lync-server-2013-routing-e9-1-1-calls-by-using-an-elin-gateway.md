---
title: Lync Server 2013：使用 ELIN 閘道路由 E9-1-1 來電
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="7a70b-102">在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 來電</span><span class="sxs-lookup"><span data-stu-id="7a70b-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a70b-103">_**主題上次修改日期：** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="7a70b-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="7a70b-104">整合通訊開啟互通性計畫中的部分合作夥伴會提供合格的緊急位置識別號碼（ELIN）支援的閘道，這可以作為認證的 E9-1-1 服務提供者的 SIP 中繼連線。</span><span class="sxs-lookup"><span data-stu-id="7a70b-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="7a70b-105">ELIN 閘道支援 ISDN 或集中式自動訊息會計（CAMA）連線至公用交換式電話網絡（PSTN）的 E9-1-1 服務。</span><span class="sxs-lookup"><span data-stu-id="7a70b-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="7a70b-106">如需提供 ELIN 閘道及其檔連結的合作夥伴的詳細資訊[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="7a70b-106">For details about partners who provide ELIN gateways and links to their documentation, see [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="7a70b-107">就像 SIP 幹線連線至 E9-1 服務提供者，ELIN 閘道也提供將緊急呼叫路由至呼叫者最適當的公用安全應答點（PSAP）的方式，但這些閘道會使用 ELIN 做為位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="7a70b-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="7a70b-108">您可以針對組織中的每個緊急回應位置（ERL）定義 ELINs （如需詳細資訊，請參閱[在 Lync Server 2013 中管理 ELIN 閘道的位置](lync-server-2013-managing-locations-for-elin-gateways.md)）。</span><span class="sxs-lookup"><span data-stu-id="7a70b-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="7a70b-109">當您使用 ELIN 閘道進行緊急通話時，您會使用與用於 SIP 中繼連線的同一個 Lync Server E9-1 個基礎結構。</span><span class="sxs-lookup"><span data-stu-id="7a70b-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="7a70b-110">也就是說，位置資訊服務資料庫會將位置提供給 Lync Server 用戶端，而位置原則則可啟用該功能並定義路由。</span><span class="sxs-lookup"><span data-stu-id="7a70b-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="7a70b-111">不過，有了 ELIN 閘道，您需要將 ELINs 新增到位置資訊服務資料庫，然後將 PSTN 載波上傳到自動位置識別（阿裡）資料庫。</span><span class="sxs-lookup"><span data-stu-id="7a70b-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="7a70b-112">當 Lync 用戶端從位置資訊服務獲得其位置時，位置會包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="7a70b-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="7a70b-113">在緊急通話期間，ELIN 會隨附于傳送至 ELIN 閘道的位置。</span><span class="sxs-lookup"><span data-stu-id="7a70b-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="7a70b-114">ELIN 閘道會將呼叫識別為緊急通話，並將通話方的號碼與 ELIN 交換。</span><span class="sxs-lookup"><span data-stu-id="7a70b-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="7a70b-115">ELIN 閘道然後將呼叫路由到 PSTN，並將 ELIN 做為通話號碼。</span><span class="sxs-lookup"><span data-stu-id="7a70b-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="7a70b-116">PSTN E9-1-1 提供者會在阿裡 database 中尋找 ELIN，這是主要街道位址指南（MSAG）資料庫的隨附資料庫。</span><span class="sxs-lookup"><span data-stu-id="7a70b-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="7a70b-117">PSTN 接著根據阿裡 lookup 將呼叫傳送到最合適的 PSAP，而 PSAP 會根據阿裡 lookup 將第一個回應程式傳送給來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="7a70b-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="7a70b-118">呼叫號碼會在 ELIN 閘道上緩存，以預先定義的回呼時間長度。</span><span class="sxs-lookup"><span data-stu-id="7a70b-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="7a70b-119">在回撥期間，PSAP 會達到 ELIN 閘道，交換呼叫者的直接撥入撥號（已有）號碼的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="7a70b-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="7a70b-120">ELIN 閘道只支援從貴組織的網路內部進行緊急通話。</span><span class="sxs-lookup"><span data-stu-id="7a70b-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="7a70b-121">它們不支援從您的網路外部發出的緊急通話。</span><span class="sxs-lookup"><span data-stu-id="7a70b-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a70b-122">如需有關使用 SIP 中繼連線進行緊急通話的詳細資料，請參閱<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">在 Lync Server 2013 中使用 sip 幹線進行路由 E9-1 通話</A>。</span><span class="sxs-lookup"><span data-stu-id="7a70b-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7a70b-123">下圖顯示當您使用 ELIN 閘道時，緊急呼叫如何從 Lync Server 路由至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="7a70b-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="7a70b-124">**使用 ELIN 閘道進行路由 E9-1 通話**</span><span class="sxs-lookup"><span data-stu-id="7a70b-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="7a70b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="7a70b-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="7a70b-126">包含位置的 SIP 邀請、來電者的回呼號碼，以及（選擇性）通知 URL 和會議回呼號碼都會路由至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="7a70b-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="7a70b-127">Lync Server 會與緊急號碼相符，然後將呼叫路由（根據適當位置原則中定義的**PSTN 使用量**值），並傳送到 ELIN 閘道。</span><span class="sxs-lookup"><span data-stu-id="7a70b-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="7a70b-128">ELIN 閘道會透過 ISDN 或 CAMA 幹線將呼叫路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="7a70b-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="7a70b-129">PSTN 會將通話識別為緊急通話，並將其路由至網路中的 E9 選擇性路由器。</span><span class="sxs-lookup"><span data-stu-id="7a70b-129">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network.</span></span> <span data-ttu-id="7a70b-130">E9-1-1 選擇性路由器會在阿裡 database 中尋找來電者的號碼，以取得地理位置。</span><span class="sxs-lookup"><span data-stu-id="7a70b-130">The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location.</span></span> <span data-ttu-id="7a70b-131">E9-1-1 選擇性路由器會根據從阿裡 database 檢索到的位置資訊，將呼叫傳送至最適合的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="7a70b-131">The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="7a70b-132">如果您已設定通知的位置原則，您組織的一個或多個安全主管會傳送特殊的 Lync 緊急通知立即訊息。</span><span class="sxs-lookup"><span data-stu-id="7a70b-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="7a70b-133">此訊息永遠會出現在安全性監察官的畫面上，並包含來電者的名稱、電話號碼、時間和位置，讓安全人員能使用立即訊息或語音來快速回應緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="7a70b-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="7a70b-134">如果通話過早中斷，PSAP 會使用 ELIN 直接聯絡來電者。</span><span class="sxs-lookup"><span data-stu-id="7a70b-134">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly.</span></span> <span data-ttu-id="7a70b-135">ELIN 閘道會調換呼叫者所做的 ELIN。</span><span class="sxs-lookup"><span data-stu-id="7a70b-135">The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

