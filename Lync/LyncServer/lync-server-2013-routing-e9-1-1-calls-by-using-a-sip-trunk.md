---
title: Lync Server 2013： 使用 SIP 主幹路由 E9-1-1 通話
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
ms.openlocfilehash: 035279fe9c87b7901092408941538871f1c663fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="2d8c6-102">Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="2d8c6-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d8c6-103">_**主題上次修改日期：** 2012年-09-29_</span><span class="sxs-lookup"><span data-stu-id="2d8c6-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="2d8c6-104">使用 SIP 主幹來連線到合格的 E9-1-1 服務提供者，是部署 E9-1-1 的方式之一。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="2d8c6-105">如需詳細資訊來連線至公用交換的電話網路 (PSTN) 使用 ELIN 閘道-型 E9-1-1 服務提供者，請參閱[使用 Lync Server 2013 中的 ELIN 閘道路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="2d8c6-106">下圖顯示如何將緊急通話路由傳送從 Lync Server 到公用安全回應點 (PSAP) 當您使用 SIP 主幹及合格的 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="2d8c6-107">**透過 SIP 主幹路由傳送 E9-1-1 通話**</span><span class="sxs-lookup"><span data-stu-id="2d8c6-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="2d8c6-108">![緊急電話從 Lync Server 路由傳送至 PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "緊急電話從 Lync Server 路由傳送至 PSAP")</span><span class="sxs-lookup"><span data-stu-id="2d8c6-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="2d8c6-109">當從相容的 Lync Server 用戶端撥打緊急電話：</span><span class="sxs-lookup"><span data-stu-id="2d8c6-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="2d8c6-110">Lync server 路由傳送的 SIP INVITE，包含位置、 發話者回撥號碼，以及 （選擇性） 通知 URL 和會議回撥號碼。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="2d8c6-111">Lync Server 比對緊急號碼，並將通話路由傳送 （依據適用位置原則中定義的**PSTN 使用方式**值） 到中繼伺服器，並且從那裡透過 SIP 主幹 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="2d8c6-p102">E9-1-1 服務提供者會依據隨附於通話的位置，將緊急通話路由傳送至正確的 PSAP。當用戶端將驗證過的緊急回應位置 (ERL) 隨附於緊急通話，提供者會自動將通話路由傳送至適當的 PSAP。如果位置是由使用者手動輸入，緊急通話回應中心 (ECRC) 會先向發話者口頭確認位置的精確度，才將緊急通話路由傳送至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="2d8c6-115">如果您設定的位置原則，通知，一或多個組織的安全性人員所傳送的特殊 Lync 緊急通知立即訊息。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="2d8c6-116">此訊息一律會快顯在安全人員的螢幕上，並包含發話者的名稱、電話號碼、時間和位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急發話者。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="2d8c6-117">如果您設定了會議的位置原則，且其受到 E9-1-1 服務提供者支援，則內部安全性桌面會以單向音訊或雙向音訊加入電話會議。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="2d8c6-118">如果通話突然中斷，PSAP 會直接使用回撥號碼來連絡發話者。</span><span class="sxs-lookup"><span data-stu-id="2d8c6-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

