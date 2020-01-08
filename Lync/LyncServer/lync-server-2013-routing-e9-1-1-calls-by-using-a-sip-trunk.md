---
title: Lync Server 2013：使用 SIP 主幹路由 E9-1-1 來電
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="44dc4-102">在 Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 來電</span><span class="sxs-lookup"><span data-stu-id="44dc4-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44dc4-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="44dc4-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="44dc4-104">使用 SIP 主幹來連線至合格的 E9-1-1 服務提供者，是一種部署 E9-1-1 的方式。</span><span class="sxs-lookup"><span data-stu-id="44dc4-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="44dc4-105">如需使用 ELIN 閘道連線至公用交換電話網絡（PSTN） E9-1-1 服務提供者的詳細資料，請參閱[在 Lync Server 2013 中使用 ELIN 閘道進行路由 E9-1 通話](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="44dc4-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="44dc4-106">下圖顯示當您使用 SIP 幹線與合格的 E9-1 服務提供者時，緊急通話如何從 Lync Server 路由到公用安全應答點（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="44dc4-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="44dc4-107">**透過 SIP 主幹路由 E9-1-1 通話**</span><span class="sxs-lookup"><span data-stu-id="44dc4-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="44dc4-108">![從 Lync server 進行緊急呼叫路由，以 PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "從 lync Server 傳送緊急呼叫路由至 PSAP")</span><span class="sxs-lookup"><span data-stu-id="44dc4-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="44dc4-109">從相容的 Lync Server 用戶端發出緊急通話時：</span><span class="sxs-lookup"><span data-stu-id="44dc4-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="44dc4-110">包含位置的 SIP 邀請、來電者的回呼號碼，以及（選擇性）通知 URL 和會議回呼號碼都會路由至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="44dc4-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="44dc4-111">Lync Server 符合緊急號碼，並將呼叫路由（根據適用位置原則中定義的**PSTN 使用量**值）到中繼伺服器，然後從 SIP 主幹轉移至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="44dc4-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="44dc4-112">E9-1-1 服務提供者會根據通話隨附的位置，將緊急通話路由到正確的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="44dc4-112">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call.</span></span> <span data-ttu-id="44dc4-113">當用戶端包含具有緊急呼叫的驗證緊急回應位置（ERL）時，提供者會自動將呼叫路由至適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="44dc4-113">When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP.</span></span> <span data-ttu-id="44dc4-114">如果該位置是由使用者手動輸入，則緊急呼叫回應中心（ECRC）會先 verbally 驗證與來電者之間的位置準確性，然後才會將緊急呼叫傳送至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="44dc4-114">If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="44dc4-115">如果您已設定通知的位置原則，您組織的一個或多個安全主管會傳送特殊的 Lync 緊急通知立即訊息。</span><span class="sxs-lookup"><span data-stu-id="44dc4-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="44dc4-116">此訊息永遠會出現在安全性監察官的畫面上，並包含來電者的名稱、電話號碼、時間和位置，讓安全人員能使用立即訊息或語音來快速回應緊急來電者。</span><span class="sxs-lookup"><span data-stu-id="44dc4-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="44dc4-117">如果您已設定會議的位置原則，且 E9-1-1 服務提供者支援它，就會使用一種單向音訊或雙向音訊，在通話中 conferenced 內部安全服務台。</span><span class="sxs-lookup"><span data-stu-id="44dc4-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="44dc4-118">如果通話過早中斷，PSAP 會使用回呼號碼直接聯絡來電者。</span><span class="sxs-lookup"><span data-stu-id="44dc4-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

