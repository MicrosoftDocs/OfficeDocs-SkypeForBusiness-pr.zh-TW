---
title: Lync Server 2013：行動功能與性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="0bb04-102">Lync Server 2013 中的行動功能與性能</span><span class="sxs-lookup"><span data-stu-id="0bb04-102">Mobility features and capabilities in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bb04-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="0bb04-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="0bb04-104">Lync Server 2013 的累積更新中引入的行動功能：2月2013支援 Lync 2010 行動裝置和 Lync 2013 行動用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="0bb04-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="0bb04-105">當您部署 Lync Server 2013 行動服務時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。</span><span class="sxs-lookup"><span data-stu-id="0bb04-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="0bb04-106">此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="0bb04-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="0bb04-107">Lync Server 2013 的累積更新中引入的新功能：2月2013包含適用于會議出席者的語音 IP （VoIP）功能和視頻（H-p）。</span><span class="sxs-lookup"><span data-stu-id="0bb04-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="0bb04-108">Lync Server 2013 的累積更新中引入的行動功能功能：2月2013支援 Lync 2013 行動用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="0bb04-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="0bb04-109">Lync Server 2013 的累計更新：2月2013安裝統一通訊網頁 API 或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="0bb04-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="0bb04-110">UCWA 是 Lync 2013 行動用戶端所用的元件。</span><span class="sxs-lookup"><span data-stu-id="0bb04-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="0bb04-111">在 Lync Server 2013 中，Mcx 是用於 Lync 2010 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="0bb04-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="0bb04-112">Lync Server 2013 的累積更新：2月2013將 UCWA 做為行動服務的新進入點。</span><span class="sxs-lookup"><span data-stu-id="0bb04-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="0bb04-113">Lync Server 2013 同時實現行動服務（Mcx），這是在 Lync Server 2010 的累積更新中引入的（即年11月2011，並提供 Lync 2010 行動裝置支援。</span><span class="sxs-lookup"><span data-stu-id="0bb04-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="0bb04-114">當您部署 Lync Server 2013 2013 的累加更新時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 行動裝置來執行下列活動：</span><span class="sxs-lookup"><span data-stu-id="0bb04-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bb04-115">行動服務支援的功能來自 Lync Server 2010 的累積更新：2011年11月，請注意（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="0bb04-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="0bb04-116">在 Lync Server 2013 的累積更新中引入的所有列出功能都受 UCWA：2013年2月。</span><span class="sxs-lookup"><span data-stu-id="0bb04-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="0bb04-117">傳送和接收立即訊息（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="0bb04-118">[查看目前狀態] （Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="0bb04-119">[查看連絡人] （Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="0bb04-120">按一下以加入會議（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="0bb04-121">透過公司通話（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="0bb04-122">單一數位延伸（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="0bb04-123">語音信箱（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="0bb04-124">未接來電通知（Mcx）</span><span class="sxs-lookup"><span data-stu-id="0bb04-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="0bb04-125">[語音 over IP （VoIP）]</span><span class="sxs-lookup"><span data-stu-id="0bb04-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="0bb04-126">出席者影片（H-p）</span><span class="sxs-lookup"><span data-stu-id="0bb04-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0bb04-127">Lync 2010 Mobile 提供 Nokia Symbian 裝置的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0bb04-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="0bb04-128">Lync 2013 Mobile 將沒有適用于 Nokia Symbian 裝置的用戶端。</span><span class="sxs-lookup"><span data-stu-id="0bb04-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="0bb04-129">Apple iPad 使用者將能夠存取增強功能。</span><span class="sxs-lookup"><span data-stu-id="0bb04-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="0bb04-130">使用音訊來電加入會議之後，iPad 使用者就能在會議中查看上傳的 Microsoft PowerPoint 簡報、共用應用程式和桌上型電腦、查看會議參與者清單，以及接收其他內容類型的通知在會議中共用的專案。</span><span class="sxs-lookup"><span data-stu-id="0bb04-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0bb04-131">在有一個數位的情況下，使用者會在已撥打至公司電話的行動電話上接聽通話。</span><span class="sxs-lookup"><span data-stu-id="0bb04-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="0bb04-132">透過 [通話]，使用者可以使用公司電話號碼（而不是行動電話號碼），從 Lync 行動用戶端撥出出站通話。</span><span class="sxs-lookup"><span data-stu-id="0bb04-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="0bb04-133">在撥出時，用戶端會傳送要求給 Mcx 或 UCWA （根據 Lync 行動裝置版本）來撥打電話給他們。</span><span class="sxs-lookup"><span data-stu-id="0bb04-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="0bb04-134">伺服器會啟動通話，然後將使用者傳回行動電話。</span><span class="sxs-lookup"><span data-stu-id="0bb04-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="0bb04-135">當使用者應答時，伺服器會撥打電話給其他方來完成通話。</span><span class="sxs-lookup"><span data-stu-id="0bb04-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="0bb04-136">透過 [透過公司通話]，使用者可以在通話期間維持自己的工作身分識別，這表示通話收件者不會看到來電者的行動電話號碼，且來電者不會產生撥出電話費。</span><span class="sxs-lookup"><span data-stu-id="0bb04-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0bb04-137">並非所有的功能在所有行動裝置上都能完全相同。</span><span class="sxs-lookup"><span data-stu-id="0bb04-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="0bb04-138">如需行動裝置上支援之功能的詳細資訊，請參閱中的<A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>行動用戶端比較表。</span><span class="sxs-lookup"><span data-stu-id="0bb04-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="0bb04-139">如需支援的裝置和作業系統的詳細資料，請參閱<A href="lync-server-2013-planning-for-mobile-clients.md">規劃 Lync Server 2013 中行動用戶端</A>的需求主題。</span><span class="sxs-lookup"><span data-stu-id="0bb04-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="0bb04-140">當您使用 Lync Server 2013 自動探索功能時，行動應用程式可以自動找出 Lync Server 2013 Web 服務，而不需要使用者在其裝置設定中手動輸入 Url。</span><span class="sxs-lookup"><span data-stu-id="0bb04-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="0bb04-141">在行動裝置設定中，也支援手動輸入 Url，主要是為了進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="0bb04-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0bb04-142">Mcx 和 UCWA 都是免費服務，而且都是為了支援 Lync 2010 行動裝置和 Lync 2013 行動用戶端而部署。</span><span class="sxs-lookup"><span data-stu-id="0bb04-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="0bb04-143">Lync 2013 Mobile 將無法登入 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="0bb04-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="0bb04-144">Lync 2010 行動裝置和 Lync 2013 行動裝置將能夠使用 Lync server 2013 部署與 Lync Server 2013 的累積更新：已套用二月2013。</span><span class="sxs-lookup"><span data-stu-id="0bb04-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="0bb04-145">行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的*推播通知*。</span><span class="sxs-lookup"><span data-stu-id="0bb04-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="0bb04-146">推播通知是傳送給行動裝置的通知，在行動應用程式處於非使用中時，發生該事件。</span><span class="sxs-lookup"><span data-stu-id="0bb04-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="0bb04-147">例如，未接的立即訊息（IM）邀請可能會產生推播通知。</span><span class="sxs-lookup"><span data-stu-id="0bb04-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="0bb04-148">Mcx、UCWA、自動探索服務以及 Lync Server 2013 中提供推播通知支援。</span><span class="sxs-lookup"><span data-stu-id="0bb04-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="0bb04-149">更新之用戶端功能、功能，以及使用 UCWA 做為行動進入點，會在 Lync Server 2013 的累積更新中引入：2013年2月。</span><span class="sxs-lookup"><span data-stu-id="0bb04-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

