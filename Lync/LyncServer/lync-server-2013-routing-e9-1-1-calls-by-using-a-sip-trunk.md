---
title: Lync Server 2013：使用 SIP 主幹路由傳送 E9-1-1 通話
description: Lync Server 2013：使用 SIP 主幹路由傳送 E9-1-1 通話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571819"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="dda76-103">在 Lync Server 2013 中使用 SIP 主幹路由傳送 E9-1-1 通話</span><span class="sxs-lookup"><span data-stu-id="dda76-103">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda76-104">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="dda76-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="dda76-105">使用 SIP 主幹來連線到合格的 E9-1-1 服務提供者，是部署 E9-1-1 的方式之一。</span><span class="sxs-lookup"><span data-stu-id="dda76-105">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="dda76-106">如需使用 ELIN 閘道來連線至公用交換電話網路 (PSTN) 型 E9-1-1 服務提供者的詳細資訊，請參閱 [在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="dda76-106">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="dda76-107">下圖顯示當您使用 SIP 主幹和合格的 E9-1-1 服務提供者時，如何將緊急通話從 Lync Server 路由傳送至公用安全回復點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="dda76-107">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="dda76-108">**透過 SIP 主幹路由傳送 E9-1-1 通話**</span><span class="sxs-lookup"><span data-stu-id="dda76-108">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="dda76-109">![從 Lync Server 到 PSAP 的緊急通話路由](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "從 Lync Server 到 PSAP 的緊急通話路由")</span><span class="sxs-lookup"><span data-stu-id="dda76-109">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="dda76-110">當緊急通話來自相容的 Lync Server 用戶端時：</span><span class="sxs-lookup"><span data-stu-id="dda76-110">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="dda76-111">包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="dda76-111">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="dda76-112">Lync Server 會根據 E9-1-1 服務提供者的適用位置) 原則中所定義的 **PSTN 使用** 值，以符合緊急號碼，並將 (通話路由傳送至-1-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="dda76-112">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="dda76-p102">E9-1-1 服務提供者會依據隨附於通話的位置，將緊急通話路由傳送至正確的 PSAP。當用戶端將驗證過的緊急回應位置 (ERL) 隨附於緊急通話，提供者會自動將通話路由傳送至適當的 PSAP。如果位置是由使用者手動輸入，緊急通話回應中心 (ECRC) 會先向發話者口頭確認位置的精確度，才將緊急通話路由傳送至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="dda76-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="dda76-116">如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的 Lync 緊急通知立即訊息。</span><span class="sxs-lookup"><span data-stu-id="dda76-116">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="dda76-117">此訊息一律會快顯在安全人員的螢幕上，並包含發話者的名稱、電話號碼、時間和位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急發話者。</span><span class="sxs-lookup"><span data-stu-id="dda76-117">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="dda76-118">如果您設定了會議的位置原則，且其受到 E9-1-1 服務提供者支援，則內部安全性桌面會以單向音訊或雙向音訊加入電話會議。</span><span class="sxs-lookup"><span data-stu-id="dda76-118">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="dda76-119">如果通話突然中斷，PSAP 會直接使用回撥號碼來連絡發話者。</span><span class="sxs-lookup"><span data-stu-id="dda76-119">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

