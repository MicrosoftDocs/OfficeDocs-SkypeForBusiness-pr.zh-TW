---
title: Lync Server 2013：使用 ELIN 閘道路由傳送 E9-1-1 通話
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
ms.openlocfilehash: 7382411774fb9fcb51bf7ade7d64795781c0ebb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="810da-102">在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 通話</span><span class="sxs-lookup"><span data-stu-id="810da-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="810da-103">_**主題上次修改日期：** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="810da-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="810da-104">Unified Communications Open Interoperability Program 中的部分合作夥伴會提供具合格緊急位置識別碼 (ELIN) 功能的閘道，對合格的 E9-1-1 服務提供者而言，這些閘道可用來作為 SIP 主幹連線的替代方式。</span><span class="sxs-lookup"><span data-stu-id="810da-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="810da-105">ELIN 閘道支援 ISDN 或集中式自動訊息記帳 (CAMA) 連線到公用交換電話網路 (PSTN) E9-1-1 服務的功能。</span><span class="sxs-lookup"><span data-stu-id="810da-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="810da-106">如需提供 ELIN 閘道和其檔連結的合作夥伴詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) 。</span><span class="sxs-lookup"><span data-stu-id="810da-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="810da-107">與 E9-1-1 服務提供者的 SIP 主幹連線，ELIN 閘道也會提供方法，將緊急通話路由傳送至來電者最適當的公用安全回應點 (PSAP) ，但這些閘道使用 ELIN 做為位置識別碼。</span><span class="sxs-lookup"><span data-stu-id="810da-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="810da-108">您為組織中的每個緊急回應位置 (ERL) 定義 Elin (如需詳細資訊，請參閱[在 Lync Server 2013) 中管理 ELIN 閘道的位置](lync-server-2013-managing-locations-for-elin-gateways.md)。</span><span class="sxs-lookup"><span data-stu-id="810da-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="810da-109">當您使用 ELIN 閘道進行緊急通話時，請使用相同的 Lync Server E9-1-1 基礎結構，以便用於 SIP 主幹連線。</span><span class="sxs-lookup"><span data-stu-id="810da-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="810da-110">也就是說，位置資訊服務資料庫會提供 Lync Server 用戶端的位置，而位置原則會啟用該功能及定義路由。</span><span class="sxs-lookup"><span data-stu-id="810da-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="810da-111">不過，使用 ELIN 閘道時，您必須將 Elin 新增至位置資訊服務資料庫，並讓 PSTN 電信公司將其上傳至自動位置識別 (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="810da-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="810da-112">當 Lync 用戶端從 Location 資訊服務取得位置時，該位置會包含 ELIN。</span><span class="sxs-lookup"><span data-stu-id="810da-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="810da-113">在緊急通話期間，ELIN 會包含在傳送至 ELIN 閘道的位置中。</span><span class="sxs-lookup"><span data-stu-id="810da-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="810da-114">ELIN 閘道會將通話識別為緊急通話，並將來電者的號碼更換為 ELIN。</span><span class="sxs-lookup"><span data-stu-id="810da-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="810da-115">然後 ELIN 閘道會使用 ELIN 作為來電號碼將通話路由傳送至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="810da-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="810da-116">PSTN E9-1-1 提供者會在 ALI 資料庫中查詢 ELIN，該資料庫是主要街道地址指南 (MSAG) 資料庫的隨附資料庫。</span><span class="sxs-lookup"><span data-stu-id="810da-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="810da-117">然後 PSTN 會依據 ALI 查詢結果將通話傳送至最合適的 PSAP，PSAP 首先會依據 ALI 查詢結果將回應者傳送至發話方的位置。</span><span class="sxs-lookup"><span data-stu-id="810da-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="810da-118">在針對回撥預先定義的時間長度內，來電號碼會快取於 ELIN 閘道上。</span><span class="sxs-lookup"><span data-stu-id="810da-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="810da-119">回撥期間，PSAP 會到達 ELIN 閘道，閘道會將 ELIN 更換為發話方的直接向內撥號 (DID) 號碼。</span><span class="sxs-lookup"><span data-stu-id="810da-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="810da-120">ELIN 閘道僅支援從您組織的網路內部撥打的緊急通話。</span><span class="sxs-lookup"><span data-stu-id="810da-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="810da-121">這些閘道不支援從您網路外部撥打的緊急通話。</span><span class="sxs-lookup"><span data-stu-id="810da-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="810da-122">如需對緊急通話使用 SIP 主幹連線的詳細資訊，請參閱<A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">在 Lync Server 2013 中使用 sip 主幹路由 E9-1-1 呼叫</A>。</span><span class="sxs-lookup"><span data-stu-id="810da-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="810da-123">下圖顯示當您使用 ELIN 閘道時，緊急通話如何從 Lync Server 路由傳送至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="810da-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="810da-124">**使用 ELIN 閘道路由傳送 E9-1-1 通話**</span><span class="sxs-lookup"><span data-stu-id="810da-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="810da-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="810da-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="810da-126">包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="810da-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="810da-127">Lync Server 會比對緊急號碼，然後根據適用位置原則中所定義的**PSTN 使用**值，將 (通話路由傳送) 至轉送伺服器，以及從那裡 ELIN 閘道。</span><span class="sxs-lookup"><span data-stu-id="810da-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="810da-128">ELIN 閘道會透過 ISDN 或 CAMA 主幹，將通話路由傳送至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="810da-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="810da-p106">PSTN 會將該通話識別為緊急通話，並將它路由傳送至網路中 E9-1-1 選擇的路由器。E9-1-1 選擇的路由器會在 ALI 資料庫中查閱來電者的號碼，以取得地理位置。E9-1-1 選擇的路由器會根據從 ALI 資料庫擷取的位置資訊，將通話路由傳送至最適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="810da-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="810da-132">如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的 Lync 緊急通知立即訊息。</span><span class="sxs-lookup"><span data-stu-id="810da-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="810da-133">此訊息一律會快顯於安全人員的螢幕上，其中包含來電者的名稱、電話號碼、時間及位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="810da-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="810da-p108">如果通話提前中斷，PSAP 會使用 ELIN 直接連絡來電者。ELIN 閘道會將 ELIN 更換為來電者的 DID。</span><span class="sxs-lookup"><span data-stu-id="810da-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

