---
title: " (規劃工具的功能綜述) "
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: 商務用 Skype Server 2015 規劃工具
ms.openlocfilehash: 7f408de792672445c727b107a7e4050ef1502259
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800283"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="115fa-103"> (規劃工具的功能綜述) </span><span class="sxs-lookup"><span data-stu-id="115fa-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="115fa-104">商務用 Skype Server 2015 規劃工具</span><span class="sxs-lookup"><span data-stu-id="115fa-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="115fa-105">您可以使用規劃工具的 [ **中央網站** ] 頁面，設計商務用 Skype Server 部署。</span><span class="sxs-lookup"><span data-stu-id="115fa-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="115fa-106">您可以建立兩種集中式或分散式部署。</span><span class="sxs-lookup"><span data-stu-id="115fa-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="115fa-107">集中式部署只有一個中央網站，它會為組織中的所有商務用 Skype 使用者提供總部。</span><span class="sxs-lookup"><span data-stu-id="115fa-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="115fa-108">分散式部署有一個以上的中央網站。</span><span class="sxs-lookup"><span data-stu-id="115fa-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="115fa-109">如果您在多個中央網站上部署商務用 Skype Server，您會在規劃工具中的每個中央網站上輸入使用者數目。</span><span class="sxs-lookup"><span data-stu-id="115fa-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="115fa-110">若要完成中央網站的定義，您必須先提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="115fa-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="115fa-111">**網站名稱** 輸入中央網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="115fa-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="115fa-112">**使用者數目** 輸入使用者數目（包括位於中央網站的分支網站使用者）。</span><span class="sxs-lookup"><span data-stu-id="115fa-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="115fa-113">**雲端穴使用者** 輸入從商務用 Skype Online 進入中央網站的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="115fa-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="115fa-114">UI 元素</span><span class="sxs-lookup"><span data-stu-id="115fa-114">UI Elements</span></span>

<span data-ttu-id="115fa-115">其餘的元素已填入您提供給「 **入門** 」嚮導中所述問題的答案，或者，如果您已略過該嚮導，會由規劃工具自動填入。</span><span class="sxs-lookup"><span data-stu-id="115fa-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="115fa-116">線上合作</span><span class="sxs-lookup"><span data-stu-id="115fa-116">Online Collaboration</span></span>

 <span data-ttu-id="115fa-117">**線上合作** 包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="115fa-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="115fa-118">**IM 和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="115fa-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="115fa-119">立即訊息 (IM) 可讓使用者在其電腦上使用文字型郵件進行即時通訊。</span><span class="sxs-lookup"><span data-stu-id="115fa-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="115fa-120">同時支援雙方或多方 IM 工作階段。</span><span class="sxs-lookup"><span data-stu-id="115fa-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="115fa-121">目前狀態為使用者提供有關網路上其他人狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="115fa-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="115fa-122">使用者的目前狀態會提供資訊，以協助其他人決定使用者是否線上，以及如何最好地聯繫使用者。</span><span class="sxs-lookup"><span data-stu-id="115fa-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="115fa-123">例如，在會議中的使用者最好是透過電子郵件聯繫。</span><span class="sxs-lookup"><span data-stu-id="115fa-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="115fa-124">**音訊與視訊會議**</span><span class="sxs-lookup"><span data-stu-id="115fa-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="115fa-125">Audio/Video (A/V) 會議可啟用即時音訊和視訊會議。</span><span class="sxs-lookup"><span data-stu-id="115fa-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="115fa-126">**電話撥入式會議**</span><span class="sxs-lookup"><span data-stu-id="115fa-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="115fa-127">電話撥入式會議可讓使用者從 PSTN 上的電話加入 A/V。</span><span class="sxs-lookup"><span data-stu-id="115fa-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="115fa-128">電話撥入式會議需要您部署會議助理和會議宣告服務應用程式。</span><span class="sxs-lookup"><span data-stu-id="115fa-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="115fa-129">**Web 會議**</span><span class="sxs-lookup"><span data-stu-id="115fa-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="115fa-130">Web 會議可讓防火牆內外的企業使用者建立及加入內部伺服器所主控的即時會議。</span><span class="sxs-lookup"><span data-stu-id="115fa-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="115fa-131">**常設聊天室**</span><span class="sxs-lookup"><span data-stu-id="115fa-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="115fa-132">Persistent Chat 可讓多位使用者參與交談，以在其中張貼和存取特定主題的內容，包括文字、連結及檔案。</span><span class="sxs-lookup"><span data-stu-id="115fa-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="115fa-133">雖然使用者可以在會話中即時進行通訊，但每個會話的內容都是持續性的，這表示當會話結束後，它仍可繼續使用。</span><span class="sxs-lookup"><span data-stu-id="115fa-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="115fa-134">使用者</span><span class="sxs-lookup"><span data-stu-id="115fa-134">Users</span></span>

 <span data-ttu-id="115fa-135">**使用者** 包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="115fa-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="115fa-136">**內部組織**</span><span class="sxs-lookup"><span data-stu-id="115fa-136">**Internal organization**</span></span>
    
- <span data-ttu-id="115fa-137">**與其他組織同盟**</span><span class="sxs-lookup"><span data-stu-id="115fa-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="115fa-138">**與舊版本的同盟**</span><span class="sxs-lookup"><span data-stu-id="115fa-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="115fa-139">**與公用 IM 服務提供者的同盟** 可讓您組織中的使用者與公用立即訊息服務提供者（例如 MSN、Yahoo！和 AOL）建立通訊。</span><span class="sxs-lookup"><span data-stu-id="115fa-139">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="115fa-140">需要有個別的授權，才能建立與公用立即訊息網路的同盟。</span><span class="sxs-lookup"><span data-stu-id="115fa-140">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="115fa-141">**與 XMPP 基礎服務提供者的同盟**</span><span class="sxs-lookup"><span data-stu-id="115fa-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="115fa-142">商務用 Skype Server 2015 引進在 Edge server 上部署的完整整合式 XMPP proxy () 以及在前端伺服器上部署的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="115fa-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="115fa-143">您可以部署新增及設定 XMPP proxy 和 XMPP 閘道，以允許商務用 Skype Server 2015 使用者從 XMPP 的協力廠商夥伴新增連絡人，以進行立即訊息 (IM) 及顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="115fa-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="115fa-144">**行動性**</span><span class="sxs-lookup"><span data-stu-id="115fa-144">**Mobility**</span></span>
    
    <span data-ttu-id="115fa-145">當您部署商務用 Skype Server 2015 行動性服務時，使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行這類活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="115fa-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="115fa-146">**Exchange 信箱 W15**</span><span class="sxs-lookup"><span data-stu-id="115fa-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="115fa-147">商務用 Skype Server 2015 可讓您將語音信箱訊息儲存在 Exchange 整合通訊 (UM) 中;這些語音信箱訊息會以電子郵件訊息的方式顯示在使用者的收件匣中。</span><span class="sxs-lookup"><span data-stu-id="115fa-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="115fa-148">語音</span><span class="sxs-lookup"><span data-stu-id="115fa-148">Voice</span></span>

 <span data-ttu-id="115fa-149">**Voice** 包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="115fa-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="115fa-150">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="115fa-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="115fa-151">Enterprise voice 是 Microsft 軟體供電的 VoIP 解決方案。</span><span class="sxs-lookup"><span data-stu-id="115fa-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="115fa-152">Enterprise voice 可讓使用者使用商務用 Skype 撥打來自其電腦的電話。</span><span class="sxs-lookup"><span data-stu-id="115fa-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="115fa-153">**Exchange 整合通訊**</span><span class="sxs-lookup"><span data-stu-id="115fa-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="115fa-154">Exchange 整合通訊 (UM) 會將語音信箱和電子郵件合併成單一郵件基礎結構。</span><span class="sxs-lookup"><span data-stu-id="115fa-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="115fa-155">商務用 Skype Server 2015 使用 Exchange UM 提供呼叫回應、使用者存取、來電通知和自動語音應答服務。</span><span class="sxs-lookup"><span data-stu-id="115fa-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="115fa-156">如果您使用這些服務，將需要在共用 Active Directory 拓撲中整合 Exchange UM 和商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="115fa-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="115fa-157">其他部署選項</span><span class="sxs-lookup"><span data-stu-id="115fa-157">Additional Deployment Options</span></span>

 <span data-ttu-id="115fa-158">**其他部署選項** 包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="115fa-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="115fa-159">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="115fa-159">**High Availability**</span></span>
    
    <span data-ttu-id="115fa-160">高可用性啟用容錯移轉支援的待機伺服器。</span><span class="sxs-lookup"><span data-stu-id="115fa-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="115fa-161">**嚴重損壞修復**</span><span class="sxs-lookup"><span data-stu-id="115fa-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="115fa-162">嚴重損壞修復措施可讓您將位於兩部資料中心的前端集區配對。</span><span class="sxs-lookup"><span data-stu-id="115fa-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="115fa-163">**監視**</span><span class="sxs-lookup"><span data-stu-id="115fa-163">**Monitoring**</span></span>
    
    <span data-ttu-id="115fa-164">監控會捕獲與通訊會話相關的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="115fa-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="115fa-165">此外，它也會從出席者端點的音訊和影片收集計量。</span><span class="sxs-lookup"><span data-stu-id="115fa-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="115fa-166">監控伺服器提供使用統計資料、趨勢及媒體質量統計資料。</span><span class="sxs-lookup"><span data-stu-id="115fa-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="115fa-167">**封存**</span><span class="sxs-lookup"><span data-stu-id="115fa-167">**Archiving**</span></span>
    
    <span data-ttu-id="115fa-168">封存會儲存立即訊息交談和會議。</span><span class="sxs-lookup"><span data-stu-id="115fa-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="115fa-169">**Exchange 封存整合**</span><span class="sxs-lookup"><span data-stu-id="115fa-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="115fa-170">如果您有位於 Exchange 2013 的使用者，且其信箱已放在 In-Place 保留狀態，您可以選擇將商務用 Skype Server 2015 儲存裝置與 Exchange storage 整合的選項。</span><span class="sxs-lookup"><span data-stu-id="115fa-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="115fa-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="115fa-171">**IPv4**</span></span>
    
    <span data-ttu-id="115fa-172">IPv4 位址是 32 位元位址，可讓電腦透過網際網路進行通訊。</span><span class="sxs-lookup"><span data-stu-id="115fa-172">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="115fa-173">由於世界各地的裝置數目不斷增加，所以可用的 IPv4 位址已用盡。因此，許多新裝置會移至使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="115fa-173">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="115fa-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="115fa-174">**IPv6**</span></span>
    
    <span data-ttu-id="115fa-175">IPv6 位址執行與 IPv4 位址相同的功能 (並增加一些功能)，但是 IPv6 位址使用 128 位元，而不是只使用 32 位元。</span><span class="sxs-lookup"><span data-stu-id="115fa-175">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="115fa-176">這不僅提供全新的一組位址，也提供更多的位址數目。</span><span class="sxs-lookup"><span data-stu-id="115fa-176">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="115fa-177">**裝置更新 Web 服務**</span><span class="sxs-lookup"><span data-stu-id="115fa-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="115fa-178">裝置更新 Web 服務提供一種自動化的方式，來更新組織外部署的所有裝置，例如商務用 Skype for Windows Phone。</span><span class="sxs-lookup"><span data-stu-id="115fa-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="115fa-179">伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="115fa-179">Server Applications</span></span>

 <span data-ttu-id="115fa-180">**伺服器應用程式** 包含下列選項：</span><span class="sxs-lookup"><span data-stu-id="115fa-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="115fa-181">**回應群組**</span><span class="sxs-lookup"><span data-stu-id="115fa-181">**Response Group**</span></span>
    
    <span data-ttu-id="115fa-182">回應群組應用程式會自動接聽並將通話分配給可用的服務台代理商。</span><span class="sxs-lookup"><span data-stu-id="115fa-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="115fa-183">**公告**</span><span class="sxs-lookup"><span data-stu-id="115fa-183">**Announcement**</span></span>
    
    <span data-ttu-id="115fa-184">如果您想要部署 Enterprise Voice，您可能想要在撥打的號碼有效但未指派給使用者共同區域時，設定如何處理電話通話的方式。</span><span class="sxs-lookup"><span data-stu-id="115fa-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="115fa-185">管理員可以設定宣告服務，讓這些來電轉接至預先決定的目的地 (電話號碼或 SIP URI) 或播放音訊宣告或兩者。</span><span class="sxs-lookup"><span data-stu-id="115fa-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="115fa-186">使用宣告服務可避免來電者 misdials 及聽到忙碌色調或 SIP 用戶端收到錯誤訊息的情況。</span><span class="sxs-lookup"><span data-stu-id="115fa-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="115fa-187">宣告服務功能是一般的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="115fa-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="115fa-188">**通話駐留**</span><span class="sxs-lookup"><span data-stu-id="115fa-188">**Call Park**</span></span>
    
    <span data-ttu-id="115fa-189">通話駐留應用程式可讓企業語音使用者從一部電話接聽來電，然後從另一部電話接聽來電，而不會在接收通話的電話上撥打資源。</span><span class="sxs-lookup"><span data-stu-id="115fa-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="115fa-190">當使用者需要轉接通話，但特定收件者未知時，通話駐留應用程式十分有用。</span><span class="sxs-lookup"><span data-stu-id="115fa-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="115fa-191">**會議助理**</span><span class="sxs-lookup"><span data-stu-id="115fa-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="115fa-192">會議應答應用程式會在沒有協力廠商音訊會議提供者服務的情況下，向電話使用者提供音訊會議功能。</span><span class="sxs-lookup"><span data-stu-id="115fa-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="115fa-193">**會議宣告**</span><span class="sxs-lookup"><span data-stu-id="115fa-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="115fa-194">會議宣告應用程式會產生色調，當使用者進入或離開會議時，以及當電話使用者已靜音或 unmuted 時發出通知。</span><span class="sxs-lookup"><span data-stu-id="115fa-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="115fa-195">**通話許可控制**</span><span class="sxs-lookup"><span data-stu-id="115fa-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="115fa-196">通話許可控制 (CAC) （也稱為 WAN 頻寬管理）可協助您根據可用的頻寬，判斷是否允許及建立新的即時通訊會話，以防止使用者在擁擠的網路上的經驗品質不良。</span><span class="sxs-lookup"><span data-stu-id="115fa-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="115fa-197">CAC 只會控制即時流量，而且不會影響資料流量。</span><span class="sxs-lookup"><span data-stu-id="115fa-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="115fa-198">如果新的語音或影片會話超過您在 WAN 上所指派的頻寬限制，則會話會封鎖或 (僅限通話) 重新路由至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="115fa-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

