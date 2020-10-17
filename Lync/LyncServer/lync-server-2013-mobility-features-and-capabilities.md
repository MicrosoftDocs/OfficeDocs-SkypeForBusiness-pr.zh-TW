---
title: Lync Server 2013：行動性功能及功能
description: Lync Server 2013：行動性功能和功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20713145c18260f22d9635c34af291e9a7c5ea9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550579"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="96a87-103">Lync Server 2013 中的行動功能與功能</span><span class="sxs-lookup"><span data-stu-id="96a87-103">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96a87-104">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="96a87-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="96a87-105">Lync Server 2013 的累計更新所引進的行動功能：2月2013支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="96a87-105">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="96a87-106">當您部署 Lync Server 2013 行動性服務時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 行動裝置執行諸如傳送和接收立即訊息、查看連絡人及查看顯示狀態等活動。</span><span class="sxs-lookup"><span data-stu-id="96a87-106">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="96a87-107">此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="96a87-107">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="96a87-108">Lync Server 2013 的累計更新所引進的新功能：二月份2013包括「語音 over IP」 (VoIP) 功能和影片 (對會議出席者的 H-p) 。</span><span class="sxs-lookup"><span data-stu-id="96a87-108">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="96a87-109">Lync Server 2013 的累計更新引進的行動功能：2月2013支援 Lync 2013 行動用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="96a87-109">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="96a87-110">Lync Server 2013 的累計更新：2月2013安裝統一通訊網頁 API 或 UCWA。</span><span class="sxs-lookup"><span data-stu-id="96a87-110">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="96a87-111">UCWA 是 Lync 2013 行動用戶端所使用的元件。</span><span class="sxs-lookup"><span data-stu-id="96a87-111">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="96a87-112">在 Lync Server 2013 中，Mcx 是用於 Lync 2010 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="96a87-112">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="96a87-113">Lync Server 2013 的累計更新：二月份2013引進 UCWA 做為行動服務的新進入點。</span><span class="sxs-lookup"><span data-stu-id="96a87-113">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="96a87-114">Lync Server 2013 同時在 Lync Server 2011 2010 的累積更新中引入行動服務 (Mcx) ，並提供對 Lync 2010 Mobile 的支援。</span><span class="sxs-lookup"><span data-stu-id="96a87-114">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="96a87-115">當您部署 Lync Server 2013 的累計更新時：2月2013，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone mobile 裝置執行這類活動，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96a87-115">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96a87-116">Lync Server 2010 的累計更新支援的行動服務功能：11月 2011 (Mcx) 中注明。</span><span class="sxs-lookup"><span data-stu-id="96a87-116">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="96a87-117">所有列出的功能都是由 UCWA 所支援，在 Lync Server 2013 的累計更新中引進：2月2013。</span><span class="sxs-lookup"><span data-stu-id="96a87-117">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="96a87-118"> (Mcx) 傳送和接收立即訊息</span><span class="sxs-lookup"><span data-stu-id="96a87-118">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="96a87-119"> (Mcx) 中查看顯示狀態</span><span class="sxs-lookup"><span data-stu-id="96a87-119">View presence (Mcx)</span></span>

  - <span data-ttu-id="96a87-120"> (Mcx) 中查看連絡人</span><span class="sxs-lookup"><span data-stu-id="96a87-120">View contacts (Mcx)</span></span>

  - <span data-ttu-id="96a87-121">按一下以加入會議 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="96a87-121">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="96a87-122">透過作品撥打 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="96a87-122">Call via work (Mcx)</span></span>

  - <span data-ttu-id="96a87-123">單一號碼 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="96a87-123">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="96a87-124">語音信箱 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="96a87-124">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="96a87-125">未接來電通知 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="96a87-125">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="96a87-126">Voice over IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="96a87-126">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="96a87-127">出席者影片 (H-p) </span><span class="sxs-lookup"><span data-stu-id="96a87-127">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96a87-128">Lync 2010 Mobile 提供 Nokia Symbian 裝置的用戶端。</span><span class="sxs-lookup"><span data-stu-id="96a87-128">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="96a87-129">Lync 2013 Mobile 將不會有用戶端用於 Nokia Symbian 型裝置。</span><span class="sxs-lookup"><span data-stu-id="96a87-129">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="96a87-130">Apple iPad 使用者將可存取增強型功能。</span><span class="sxs-lookup"><span data-stu-id="96a87-130">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="96a87-131">使用音訊來電加入會議之後，iPad 使用者就能夠在會議中查看上傳的 Microsoft PowerPoint 簡報、共用應用程式與桌面、查看會議參與者清單，以及接收其他在會議中共用的內容類型通知。</span><span class="sxs-lookup"><span data-stu-id="96a87-131">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="96a87-132">使用單一號碼搜尋時，使用者可以用行動電話接收撥打至公司號碼的電話。</span><span class="sxs-lookup"><span data-stu-id="96a87-132">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="96a87-133">透過公司的來電，使用者可以使用公司電話號碼，而不是行動電話號碼，從 Lync Mobile 用戶端撥出電話。</span><span class="sxs-lookup"><span data-stu-id="96a87-133">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="96a87-134">透過撥出，用戶端會根據 Lync Mobile 版本) ，將要求傳送至 Mcx 或 UCWA (，以進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="96a87-134">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="96a87-135">此伺服器會起始通話，然後回撥給使用者的行動電話。</span><span class="sxs-lookup"><span data-stu-id="96a87-135">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="96a87-136">當使用者應答時，伺服器就會撥打給另一方，以完成通話。</span><span class="sxs-lookup"><span data-stu-id="96a87-136">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="96a87-137">藉由使用「從公司撥號」，使用者可以在通話期間維持其公司身分識別，這表示受話者不會看到來電者的行動電話號碼，而且來電者可避免產生撥出電話的費用。</span><span class="sxs-lookup"><span data-stu-id="96a87-137">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="96a87-138">並非所有功能都會在所有行動裝置上以完全相同的方式運作。</span><span class="sxs-lookup"><span data-stu-id="96a87-138">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="96a87-139">如需行動裝置上支援之功能的詳細資訊，請參閱 at Mobile Client Comparison Tables <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> 。</span><span class="sxs-lookup"><span data-stu-id="96a87-139">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="96a87-140">如需支援的裝置和作業系統的詳細資訊，請參閱 <A href="lync-server-2013-planning-for-mobile-clients.md">規劃 Lync Server 2013 中行動用戶端</A>的需求主題。</span><span class="sxs-lookup"><span data-stu-id="96a87-140">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="96a87-141">當您使用 Lync Server 2013 自動探索功能時，行動應用程式可以自動找出 Lync Server 2013 Web 服務，而不需要使用者在其裝置設定中手動輸入 URLs。</span><span class="sxs-lookup"><span data-stu-id="96a87-141">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="96a87-142">但是也支援在行動裝置設定中手動輸入 URL，主要是用於疑難排解。</span><span class="sxs-lookup"><span data-stu-id="96a87-142">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96a87-143">Mcx 和 UCWA 都是免費服務，且都是部署來支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="96a87-143">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="96a87-144">Lync 2013 Mobile 將無法登入 Lync Server 2010 部署。</span><span class="sxs-lookup"><span data-stu-id="96a87-144">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="96a87-145">Lync 2010 行動裝置和 Lync 2013 行動裝置將能夠使用 Lync Server 2013 部署，其累計更新為 Lync Server 2013：已套用二月份2013。</span><span class="sxs-lookup"><span data-stu-id="96a87-145">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="96a87-146">行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」\*\*。</span><span class="sxs-lookup"><span data-stu-id="96a87-146">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="96a87-147">推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。</span><span class="sxs-lookup"><span data-stu-id="96a87-147">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="96a87-148">例如，未接立即訊息 (IM) 邀請可能會產生推播通知。</span><span class="sxs-lookup"><span data-stu-id="96a87-148">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="96a87-149">Lync Server 2013 提供 Mcx、UCWA、自動探索服務及支援推播通知。</span><span class="sxs-lookup"><span data-stu-id="96a87-149">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="96a87-150">更新用戶端功能，並將 UCWA 當作行動性進入點，會在 Lync Server 2013 的累計更新中引進：2月2013。</span><span class="sxs-lookup"><span data-stu-id="96a87-150">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

