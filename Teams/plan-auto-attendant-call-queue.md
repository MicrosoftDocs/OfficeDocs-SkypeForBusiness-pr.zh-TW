---
title: 規劃小組自動語音應答及呼叫佇列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解自動語音應答和通話佇列，以及如何使用它們，協助呼叫者在功能表系統中移動，以吸引您組織中的人員或部門。
ms.openlocfilehash: 3e1a7fe6b5f059236e0fafd64dbf87b7cebbeecf
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48209978"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a><span data-ttu-id="25515-103">規劃小組自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="25515-103">Plan for Teams auto attendants and call queues</span></span>

<span data-ttu-id="25515-104">自動語音應答可讓您根據本機號碼來設定功能表選項，以路由通話。</span><span class="sxs-lookup"><span data-stu-id="25515-104">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="25515-105">功能表選項 ( [銷售額]，請按1。</span><span class="sxs-lookup"><span data-stu-id="25515-105">Menu options ("For Sales, press 1.</span></span>  <span data-ttu-id="25515-106">針對服務，請按下 [自動語音] 的 [) ]，組織就能提供一系列的選項，讓呼叫者快速引導來電者，而不需依靠人工接線員來處理來電。</span><span class="sxs-lookup"><span data-stu-id="25515-106">For Services press 2") for an auto attendant let an organization provide a series of choices that guide callers to their destination quickly, without relying on a human operator to handle incoming calls.</span></span>


<span data-ttu-id="25515-107">通話佇列是呼叫者的等待區域。</span><span class="sxs-lookup"><span data-stu-id="25515-107">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="25515-108">針對來電者需要接觸特定專業的人員（例如銷售或服務），而不是特定人員，您可以使用呼叫佇列將呼叫者連線至可協助他們的工程師群組。</span><span class="sxs-lookup"><span data-stu-id="25515-108">For situations where callers need to reach someone with a particular specialty - such as sales or service - rather than a specific person, you can use call queues to connect callers to the group of agents who can assist them.</span></span> <span data-ttu-id="25515-109">呼叫者將保留，直到指派給佇列的代理程式可供您接聽通話。</span><span class="sxs-lookup"><span data-stu-id="25515-109">Callers are put on hold until an agent assigned to the queue is available to take their call.</span></span>

<span data-ttu-id="25515-110">[自動語音應答] 和 [呼叫佇列] 可搭配使用，輕鬆地將呼叫者路由至組織中的適當人員或部門。</span><span class="sxs-lookup"><span data-stu-id="25515-110">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

## <a name="auto-attendants"></a><span data-ttu-id="25515-111">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="25515-111">Auto attendants</span></span>

<span data-ttu-id="25515-112">自動語音應答的主要用途是根據來電者輸入，將呼叫者引導至所提供的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="25515-112">The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options.</span></span> <span data-ttu-id="25515-113">來電者可以導向貴組織內的特定人員，打電話給對方等候與下一個可用的 agent 或語音信箱交談的佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-113">Callers can be directed to specific people within your organization, to call queues where they wait to talk to the next available agent, or to voicemail.</span></span> <span data-ttu-id="25515-114">您可以針對 [上班時間]、[下班時間] 和 [假日] 指定不同的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="25515-114">Different call routing options can be specified for business hours, off hours, and holidays.</span></span>

<span data-ttu-id="25515-115">您可以使用文字轉換語音 (系統產生的提示) 或上傳錄製的音訊檔案，來建立功能表提示。</span><span class="sxs-lookup"><span data-stu-id="25515-115">Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file.</span></span> <span data-ttu-id="25515-116">語音辨識接受語音命令以進行無人流覽，但通話中的人員也可以使用電話鍵流覽功能表。</span><span class="sxs-lookup"><span data-stu-id="25515-116">Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>

<span data-ttu-id="25515-117">每個自動助理都有特定的語言和時區。</span><span class="sxs-lookup"><span data-stu-id="25515-117">Each auto attendant has a specific language and time zone.</span></span> <span data-ttu-id="25515-118">如果您有多個語言或世界各地的業務，您可以根據需要建立許多不同的自動語音應答，以適應您的來電者。</span><span class="sxs-lookup"><span data-stu-id="25515-118">If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.</span></span>

<span data-ttu-id="25515-119">針對每個自動語音應答，您可以設定操作員。</span><span class="sxs-lookup"><span data-stu-id="25515-119">For each auto attendant, you can configure an operator.</span></span> <span data-ttu-id="25515-120">雖然您可以設定操作員通話來移至各種不同的目的地，但操作員的功能是設計來讓呼叫者與組織中的特定人員交談，以協助他們。</span><span class="sxs-lookup"><span data-stu-id="25515-120">While you can configure operator calls to go to a variety of destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.</span></span>

<span data-ttu-id="25515-121">自動語音應答可以設定為允許呼叫者搜尋貴組織的目錄（依名稱或分機號碼）。</span><span class="sxs-lookup"><span data-stu-id="25515-121">Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number.</span></span> <span data-ttu-id="25515-122">在自動語音應答中，您可以選擇要加入或排除的使用者群組，以指定可供目錄搜尋使用的人員。</span><span class="sxs-lookup"><span data-stu-id="25515-122">Within an auto attendant, you can specify who is available for the directory search by choosing groups of users to include or exclude.</span></span> <span data-ttu-id="25515-123"> (這稱為 *撥號作用*中。 ) </span><span class="sxs-lookup"><span data-stu-id="25515-123">(This is known as *dial scope*.)</span></span>

<span data-ttu-id="25515-124">來電者可以透過直接電話號碼（如果有設定的話）或從另一個自動語音應答或呼叫佇列重新導向來取得自動助理。</span><span class="sxs-lookup"><span data-stu-id="25515-124">Callers can reach an auto attendant either by direct phone number, if configured, or by being redirected from another auto attendant or a call queue.</span></span>

## <a name="call-queues"></a><span data-ttu-id="25515-125">通話佇列</span><span class="sxs-lookup"><span data-stu-id="25515-125">Call queues</span></span>

<span data-ttu-id="25515-126">通話佇列類似于實際建築物中的等待會議室。</span><span class="sxs-lookup"><span data-stu-id="25515-126">A call queue is analogous to a waiting room in a physical building.</span></span> <span data-ttu-id="25515-127">來電者會在通話時等待，並將呼叫路由到佇列中的代理程式，因為它們變為可用。</span><span class="sxs-lookup"><span data-stu-id="25515-127">Callers wait on hold while calls are routed to the agents in the queue as they become available.</span></span> <span data-ttu-id="25515-128">通話佇列通常是用來進行銷售與服務的功能，但在通話數量超過您的內部容量（例如，繁忙設施中的接待員）的情況下，都可以使用。</span><span class="sxs-lookup"><span data-stu-id="25515-128">Call queues are commonly used for sales and service functions, but can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.</span></span>

<span data-ttu-id="25515-129">在佇列中的呼叫者總數或等待時間超過您指定的限制情況下，通話佇列允許特定的通話路由。</span><span class="sxs-lookup"><span data-stu-id="25515-129">Call queues allow for specific routing of calls in cases where the total number of callers in the queue or the wait time exceeds the limits that you specify.</span></span> <span data-ttu-id="25515-130">通話可以路由至特定人員、語音信箱、其他通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="25515-130">Calls can be routed to specific people, voicemail, other call queues, or auto attendants.</span></span>

<span data-ttu-id="25515-131">就像自動語音應答一樣，通話佇列中的每一個都有語言設定。</span><span class="sxs-lookup"><span data-stu-id="25515-131">Like auto attendants, call queues each have a language setting.</span></span> <span data-ttu-id="25515-132">如果您有多個語言的商務，您可以使用不同的通話佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-132">You can use different call queues if you do business in multiple languages.</span></span> <span data-ttu-id="25515-133">如果代理人是多語言，則可以是多個佇列的成員。</span><span class="sxs-lookup"><span data-stu-id="25515-133">Agents can be members of more than one queue if they're multi-lingual.</span></span>

<span data-ttu-id="25515-134">針對每個通話佇列，您可以指定佇列中的代理程式是否可以選擇不接聽通話，以及是否應該根據其在團隊中的目前狀態指示來傳送呼叫給對方。</span><span class="sxs-lookup"><span data-stu-id="25515-134">For each call queue, you can specify if agents in the queue can opt out of taking calls and if calls should be routed to them based on their presence indication in Teams.</span></span>

<span data-ttu-id="25515-135">您可以將電話號碼指派給通話佇列，不過通話佇列不會提供獨立的呼叫路由來提供下班時間和假日。</span><span class="sxs-lookup"><span data-stu-id="25515-135">You can assign a phone number to a call queue, however call queues do not provide separate call routing for off hours and holidays.</span></span> <span data-ttu-id="25515-136">除非您的通話佇列是配備24/7 的人員，否則建議您將電話號碼指派給在營業期間重新導向呼叫佇列的自動回應。</span><span class="sxs-lookup"><span data-stu-id="25515-136">Unless your call queue is staffed 24/7, we recommend assigning the phone number to an auto attendant that redirects to the call queue during business hours.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25515-137">必要條件</span><span class="sxs-lookup"><span data-stu-id="25515-137">Prerequisites</span></span>

<span data-ttu-id="25515-138">若要設定自動語音應答及呼叫佇列，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="25515-138">To configure auto attendants and call queues, you need the following:</span></span>

- <span data-ttu-id="25515-139">每個自動語音應答及每個通話佇列的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="25515-139">A resource account for each auto attendant and each call queue</span></span>
- <span data-ttu-id="25515-140">每個資源帳戶的免費電話系統-虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="25515-140">A free Phone System - Virtual User license for each resource account</span></span>
- <span data-ttu-id="25515-141">您想要直接撥打之每個自動語音應答或通話佇列的服務號碼</span><span class="sxs-lookup"><span data-stu-id="25515-141">A service number for each auto attendant or call queue that you want to be directly dialable</span></span>
- <span data-ttu-id="25515-142">每個要接收通話佇列通話的人員的通話方案</span><span class="sxs-lookup"><span data-stu-id="25515-142">A calling plan for each person who will be receiving call queue calls</span></span>

> [!NOTE]
> <span data-ttu-id="25515-143">僅限 Microsoft 團隊使用者和呼叫代理程式支援自動語音應答和通話佇列的直接路由服務號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-143">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and call agents only.</span></span>

## <a name="business-decisions"></a><span data-ttu-id="25515-144">商務決策</span><span class="sxs-lookup"><span data-stu-id="25515-144">Business decisions</span></span>

<span data-ttu-id="25515-145">在您設定自動語音應答及呼叫佇列之前，請先決定如何在您的企業中使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="25515-145">Before you set up your auto attendants and call queues, there are some decisions that you should make about how to use these features in your business.</span></span> <span data-ttu-id="25515-146">當您設定自動語音應答及呼叫佇列時，這些決定將決定您選擇的設定。</span><span class="sxs-lookup"><span data-stu-id="25515-146">These decisions will determine the settings that you choose when you configure your auto attendants and call queues.</span></span>

<span data-ttu-id="25515-147">記錄這些問題的答案，並提供管理員進行設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="25515-147">Document your answers to these questions and provide the information the the administrator doing the configuration.</span></span>

- <span data-ttu-id="25515-148">您需要哪些語言？</span><span class="sxs-lookup"><span data-stu-id="25515-148">What languages do you need?</span></span> <span data-ttu-id="25515-149">需要這些語言的位置-哪個部門或群組？</span><span class="sxs-lookup"><span data-stu-id="25515-149">Where are these languages needed - which department or group?</span></span>
- <span data-ttu-id="25515-150">您想要允許來自呼叫者的語音輸入或只允許撥號輸入嗎？</span><span class="sxs-lookup"><span data-stu-id="25515-150">Do you want to allow voice inputs from callers or only dialing inputs?</span></span>
- <span data-ttu-id="25515-151">您是否需要個別的呼叫路由來關閉時間或假期？</span><span class="sxs-lookup"><span data-stu-id="25515-151">Do you need separate call routing for off hours or holidays?</span></span> <span data-ttu-id="25515-152">有哪些時間和假日？</span><span class="sxs-lookup"><span data-stu-id="25515-152">What are the hours and holidays?</span></span>
- <span data-ttu-id="25515-153">您想要允許通話佇列中的代理程式選擇不接聽通話嗎？</span><span class="sxs-lookup"><span data-stu-id="25515-153">Do you want to allow agents in a call queue to opt out of taking calls?</span></span>
- <span data-ttu-id="25515-154">您想讓通話佇列中的代理程式，或您的操作員在撥出時有特定的本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="25515-154">Do you want agents in your call queues or your operator to have a specific caller ID if they dial out?</span></span> 
- <span data-ttu-id="25515-155">您想要在組織中啟用 [呼叫停用和檢索](call-park-and-retrieve.md) ，協助在人員或部門間呼叫提交嗎？</span><span class="sxs-lookup"><span data-stu-id="25515-155">Do you want to enable [call parking and retrieval](call-park-and-retrieve.md) in your organization to assist in call handoffs between people or departments?</span></span>
- <span data-ttu-id="25515-156">針對語音提示，您想要自行錄製或使用系統產生的語音嗎？</span><span class="sxs-lookup"><span data-stu-id="25515-156">For the voice prompts, do you want to record your own or use the system-generated voice?</span></span> <span data-ttu-id="25515-157"> (系統產生的語音很容易更新。 ) </span><span class="sxs-lookup"><span data-stu-id="25515-157">(The system-generated voice is very easy to update.)</span></span>

## <a name="technical-decisions"></a><span data-ttu-id="25515-158">技術決策</span><span class="sxs-lookup"><span data-stu-id="25515-158">Technical decisions</span></span>

<span data-ttu-id="25515-159">使用 [自動語音應答] 和 [呼叫佇列] 將呼叫者連線至組織中的人員時，您必須先進行一些技術決策，才能開始進行設定。</span><span class="sxs-lookup"><span data-stu-id="25515-159">When using auto attendants and call queues to connect callers to people in your organization, there are some technical decisions to make before you start the configuration.</span></span>

<span data-ttu-id="25515-160">您可以透過下列方式將代理新增至通話佇列：</span><span class="sxs-lookup"><span data-stu-id="25515-160">Agents can be added to call queues in the following ways:</span></span>

- <span data-ttu-id="25515-161">個別使用者</span><span class="sxs-lookup"><span data-stu-id="25515-161">Individual users</span></span>
- <span data-ttu-id="25515-162">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="25515-162">Distribution lists</span></span>
- <span data-ttu-id="25515-163">安全性群組，包括已啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="25515-163">Security groups, including mail-enabled security groups</span></span>
- <span data-ttu-id="25515-164">Microsoft 365 群組或團隊</span><span class="sxs-lookup"><span data-stu-id="25515-164">Microsoft 365 Groups or Teams</span></span>

<span data-ttu-id="25515-165">如有需要，您可以針對每個佇列使用這些選項的組合。</span><span class="sxs-lookup"><span data-stu-id="25515-165">You can use a combination of these options for each queue if needed.</span></span> <span data-ttu-id="25515-166">具有電子郵件地址的群組可用於語音信箱。</span><span class="sxs-lookup"><span data-stu-id="25515-166">Groups that have an email address can be used for voicemail.</span></span> <span data-ttu-id="25515-167">使用團隊提供許多優點，包括共用檔案儲存和在代理程式之間聊天、可接收語音訊息的常見信箱，以及可納入與您的商務用 office 應用程式或 Power App 整合的可擴展平臺。</span><span class="sxs-lookup"><span data-stu-id="25515-167">Using Teams offers a number of advantages, including shared file storage and chat between agents, a common mailbox where voicemails can be received, and an extensible platform that can include integration with your line of business applications or Power Apps.</span></span>

<span data-ttu-id="25515-168">我們建議您選擇一個策略，在開始進行設定之前，將呼叫代理程式新增到佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-168">We recommend choosing a strategy for adding call agents to queues before you start your configuration.</span></span>

<span data-ttu-id="25515-169">如果您有現有的自動語音應答及呼叫佇列基礎結構，且您要遷移至小組，您需要將現有的電話號碼轉移到新的自動語音應答及呼叫佇列的方案。</span><span class="sxs-lookup"><span data-stu-id="25515-169">If you have an existing auto attendant and call queue infrastructure and you're migrating to Teams, you'll need a plan to transfer your existing phone numbers to the new auto attendants and call queues.</span></span> <span data-ttu-id="25515-170">您可能需要建立 [埠順序](phone-number-calling-plans/port-order-overview.md) ，才能從其他提供者移動您的號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-170">You may need to create a [port order](phone-number-calling-plans/port-order-overview.md) to move your numbers from another providers.</span></span> <span data-ttu-id="25515-171">我們建議您暫時取得一或多個新的電話號碼，並測試您的自動語音應答及呼叫佇列流程，然後再切換到您目前已提供服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-171">We recommend that you temporarily acquire one or more new phone numbers and test your auto attendant and call queue flows before switching them over the numbers you currently have in service.</span></span>

<span data-ttu-id="25515-172">[*會議模式*] 是通話佇列中的一個選項，可大幅減少將小組 VOIP 通話和 PSTN 呼叫連線至代理程式所需的時間量。</span><span class="sxs-lookup"><span data-stu-id="25515-172">*Conference mode* is an option in call queues that significantly reduces the amount of time it takes to connect Teams VOIP calls and PSTN calls to an agent.</span></span> <span data-ttu-id="25515-173">若要使用會議模式，通話佇列中的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="25515-173">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="25515-174">最新版本的 Microsoft 團隊桌面用戶端、Android 應用程式或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="25515-174">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="25515-175">Microsoft 團隊手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="25515-175">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="25515-176">必須將代理的小群組帳戶設定為 [僅限團隊模式]。</span><span class="sxs-lookup"><span data-stu-id="25515-176">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="25515-177">不符合需求的工程師不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="25515-177">Agents who don't meet the requirements aren't included in the call routing list.</span></span>

<span data-ttu-id="25515-178">如果您的代理全部使用相容的用戶端，我們建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="25515-178">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="25515-179">[會議模式] 不支援 [忙碌] 功能。</span><span class="sxs-lookup"><span data-stu-id="25515-179">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="25515-180">如果未啟用目前狀態路由，非呼叫佇列呼叫上的代理程式可能仍會顯示呼叫佇列呼叫。</span><span class="sxs-lookup"><span data-stu-id="25515-180">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

## <a name="plan-your-call-routing-flow"></a><span data-ttu-id="25515-181">規劃通話路由流程</span><span class="sxs-lookup"><span data-stu-id="25515-181">Plan your call routing flow</span></span>

<span data-ttu-id="25515-182">在規劃程式中，我們建議您在圖表中處理貴組織的通話路由。</span><span class="sxs-lookup"><span data-stu-id="25515-182">As part of the planning process, we recommend that you work out the call routing for your organization in a diagram.</span></span> <span data-ttu-id="25515-183">這可協助您判斷在您的組織中呼叫人員的最有效路由。</span><span class="sxs-lookup"><span data-stu-id="25515-183">This will help determine the most efficient routing for people calling in to your organization.</span></span> <span data-ttu-id="25515-184">您也可以使用圖表來判斷您需要建立的自動語音應答及呼叫佇列，以及服務號碼、授權及資源帳戶等相關需求。</span><span class="sxs-lookup"><span data-stu-id="25515-184">You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.</span></span>

<span data-ttu-id="25515-185">讓我們來看看自動語音應答及呼叫佇列路由通話的方式。</span><span class="sxs-lookup"><span data-stu-id="25515-185">Let's look at how auto attendants and call queues route calls.</span></span>

<span data-ttu-id="25515-186">自動回應會以下列其中一種方式路由所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="25515-186">Auto attendants route all calls in one of the following ways:</span></span>

- <span data-ttu-id="25515-187">[**立即重新導向**]-通話可能會被重新導向至下列其中一個呼叫路由目標 () 在您接聽或初始問候語後立即顯示。</span><span class="sxs-lookup"><span data-stu-id="25515-187">**Redirect immediately** - calls can be redirected to one of the call routing destinations (listed below) immediately upon answering or after an initial greeting.</span></span>
- <span data-ttu-id="25515-188">**根據撥號選項重新導向** -來電者可在指派給電話鍵台（0-9）號碼的選項之間進行選擇。</span><span class="sxs-lookup"><span data-stu-id="25515-188">**Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad, 0-9.</span></span> <span data-ttu-id="25515-189">您可以為每個撥號鍵指派呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="25515-189">Each dial key can be assigned a call routing destinations.</span></span>
- <span data-ttu-id="25515-190">透過**名稱或分機號碼撥打人員**：您可以將來電者的分機號碼撥打給您組織的目錄，或使用拼寫給人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="25515-190">**Dial people by name or extension** - callers can be directed to dial the extension number of the person they are trying to reach in your organization's directory, or by spelling the person's name.</span></span>
- <span data-ttu-id="25515-191">**中斷** 連線-自動語音應答可能會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="25515-191">**Disconnect** - an auto attendant can hang up the call.</span></span>

> [!NOTE]
> <span data-ttu-id="25515-192">單一自動語音應答只支援單一 "撥號方式" 方法。</span><span class="sxs-lookup"><span data-stu-id="25515-192">A single Auto attendant can only support a single "dial by" method.</span></span>  <span data-ttu-id="25515-193">若要允許呼叫者以名稱和依號碼撥號，您必須建立一個自動語音應答，讓它有撥打電話給撥號選項，另一種是透過分機撥打電話。</span><span class="sxs-lookup"><span data-stu-id="25515-193">To allow callers to dial by name and by number, you will need to create an auto attendant that has an option for dial by name and the another for dial by extension.</span></span>  <span data-ttu-id="25515-194">每個選項都會路由到針對這些「撥號者」案例設定的個別自動 attenants。</span><span class="sxs-lookup"><span data-stu-id="25515-194">Each of these options will route to separate auto attenants configured for these "dial by" scenarios.</span></span> 

<span data-ttu-id="25515-195">當來電是由自動語音應答重新導向時，您可以從下列通話路由目的地選擇：</span><span class="sxs-lookup"><span data-stu-id="25515-195">When calls are redirected by an auto attendant, you can choose from the following call routing destinations:</span></span>

- <span data-ttu-id="25515-196">**組織中的人員** -您組織中能夠接聽語音通話的人員。</span><span class="sxs-lookup"><span data-stu-id="25515-196">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="25515-197">這可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="25515-197">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="25515-198">**語音 app** -另一個自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-198">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="25515-199">選擇與目的地相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="25515-199">Choose the resource account associated with the destination.</span></span>
- <span data-ttu-id="25515-200">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-200">**External phone number** - any phone number.</span></span> <span data-ttu-id="25515-201"> (查看 [外部轉接技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。</span><span class="sxs-lookup"><span data-stu-id="25515-201">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="25515-202">**語音信箱** -與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="25515-202">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="25515-203">**Operator** -為自動語音應答定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="25515-203">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="25515-204">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="25515-204">Defining an operator is optional.</span></span> <span data-ttu-id="25515-205">運算子可以是此清單中的任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="25515-205">An operator can be any of the other destinations in this list.</span></span>

<span data-ttu-id="25515-206">自動語音應答會提供單獨的呼叫路由選項，用於在上班時間以外的電話和假日上接收的通話。</span><span class="sxs-lookup"><span data-stu-id="25515-206">Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.</span></span> <span data-ttu-id="25515-207">[下班後] 呼叫路由可允許上述所有選項，而 [假日通話路由] 只允許重新導向通話或中斷通話，但沒有撥號鍵選項。</span><span class="sxs-lookup"><span data-stu-id="25515-207">After-hours call routing allows all the options listed above, while holiday call routing allows only redirecting or disconnecting a call, but no dial key options.</span></span>

<span data-ttu-id="25515-208">[通話佇列] 會將呼叫者放在 [保留]，直到指派給該佇列的代理程式可用於接聽電話。</span><span class="sxs-lookup"><span data-stu-id="25515-208">Call queues place the caller on hold until an agent assigned to the queue is available to take their call.</span></span> <span data-ttu-id="25515-209">在兩種情況下，可能會將來電者導向到佇列：</span><span class="sxs-lookup"><span data-stu-id="25515-209">There are two situations where a caller might be directed out of the queue:</span></span>

- <span data-ttu-id="25515-210">**呼叫溢出** -如果佇列中的呼叫數量超過您設定的限制，新的呼叫者就會從佇列中重新導向。</span><span class="sxs-lookup"><span data-stu-id="25515-210">**Call overflow** - if the number of calls in the queue exceeds the limit that you set, then new callers are redirected out of the queue.</span></span>
- <span data-ttu-id="25515-211">**通話超時** -如果來電者在佇列中的時間超過設定的超時設定，就會從佇列中重新導向。</span><span class="sxs-lookup"><span data-stu-id="25515-211">**Call timeout** - if a caller has been in the queue longer than the configured timeout setting, they are redirected out of the queue.</span></span>

<span data-ttu-id="25515-212">除了操作員之外，您可以將呼叫已重新導向的通話傳送至上述任何呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="25515-212">Calls redirected out of a queue can be sent to any of the call routing destinations listed above except for an operator.</span></span> <span data-ttu-id="25515-213"> (通話佇列沒有操作員，但您可以將呼叫者重新導向至與您已為自動語音應答設定的操作員相同的目的地。 ) </span><span class="sxs-lookup"><span data-stu-id="25515-213">(Call queues don't have operators, but you can redirect callers to the same destination as an operator that you've configured for an auto attendant.)</span></span>

<span data-ttu-id="25515-214">下列範例顯示使用 [自動語音應答] 和 [通話佇列] 呼叫路由的範例。</span><span class="sxs-lookup"><span data-stu-id="25515-214">The example below shows an example of call routing using auto attendants and call queues.</span></span>

![](media/attendant-and-queue-call-routing.png)

<span data-ttu-id="25515-215">在上述範例中：</span><span class="sxs-lookup"><span data-stu-id="25515-215">In the example above:</span></span>
- <span data-ttu-id="25515-216">零 (0) 金鑰會將呼叫者重新導向到操作員。</span><span class="sxs-lookup"><span data-stu-id="25515-216">The zero (0) key redirects callers to an operator.</span></span> <span data-ttu-id="25515-217">該自動語音應答的操作員已設定為 **組織中的人員**。</span><span class="sxs-lookup"><span data-stu-id="25515-217">The operator for that auto attendant has been configured as a **Person in the organization**.</span></span>
- <span data-ttu-id="25515-218">一個 (1) 金鑰會將來電者重新導向到銷售通話佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-218">The one (1) key redirects callers the the sales call queue.</span></span> <span data-ttu-id="25515-219">此通話佇列已連接至包含指派給該佇列之銷售小組的小組。</span><span class="sxs-lookup"><span data-stu-id="25515-219">This call queue is connected to a team which contains the sales team assigned to the queue.</span></span>
- <span data-ttu-id="25515-220">兩個 (2) 金鑰會將呼叫者重新導向至支援電話列隊。</span><span class="sxs-lookup"><span data-stu-id="25515-220">The two (2) key redirects callers to the support call queue.</span></span> <span data-ttu-id="25515-221">此通話佇列已連接至包含指派給該小組之支援小組的小組。</span><span class="sxs-lookup"><span data-stu-id="25515-221">This call queue is connected to a team which contains the support team assigned to the team.</span></span>
- <span data-ttu-id="25515-222">支援通話佇列有一個透過中間自動語音應答的直接電話號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-222">The support call queue has a direct phone number via an intervening auto attendant.</span></span> <span data-ttu-id="25515-223">讓自動語音應答能接聽支援行，就能分隔下班時間與假期通話路線。</span><span class="sxs-lookup"><span data-stu-id="25515-223">Having an auto attendant answer the support line allows for separate off hours and holiday call routing.</span></span>
- <span data-ttu-id="25515-224">這三個 (3) 金鑰會將使用者重新導向至公司目錄的另一個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="25515-224">The three (3) key redirects users to another auto attendant for the company directory.</span></span> <span data-ttu-id="25515-225">公司目錄自動語音應答可讓呼叫者撥打電話給組織中的人員，方法是撥打他們的名稱或分機號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-225">The company directory auto attendant allows callers to call individuals in the organization by dialing their name or extension.</span></span>

<span data-ttu-id="25515-226">我們建議您建立一個或多個類似上方的圖表，以對應您的通話路線。</span><span class="sxs-lookup"><span data-stu-id="25515-226">We recommend that you create one or more diagrams similar to the one above to map out your call routing.</span></span> <span data-ttu-id="25515-227">請務必在您的圖表或隨附的檔中包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="25515-227">Be sure to include the following in your diagram or accompanying documentation:</span></span>

- <span data-ttu-id="25515-228">哪一個自動語音應答將透過電話號碼直接存取</span><span class="sxs-lookup"><span data-stu-id="25515-228">Which auto attendants will have direct access via phone numbers</span></span>
- <span data-ttu-id="25515-229">每個自動語音應答的時間和假日路由需求為何？</span><span class="sxs-lookup"><span data-stu-id="25515-229">What are the off-hours and holiday routing requirements for each auto attendants?</span></span>
- <span data-ttu-id="25515-230">每個通話佇列的成員資格。</span><span class="sxs-lookup"><span data-stu-id="25515-230">The membership for each call queue.</span></span> <span data-ttu-id="25515-231"> (您可以個別新增使用者，或將佇列對應到不同類型的群組。</span><span class="sxs-lookup"><span data-stu-id="25515-231">(You can add users individually or map the queue to different kinds of groups.</span></span> <span data-ttu-id="25515-232">將佇列對應至團隊可提供最廣泛的使用體驗。 ) </span><span class="sxs-lookup"><span data-stu-id="25515-232">Mapping a queue to a team provides the most versatile experience.)</span></span>

<span data-ttu-id="25515-233">以下是一些呼叫路由最佳做法：</span><span class="sxs-lookup"><span data-stu-id="25515-233">Here are some call routing best practices:</span></span>

- <span data-ttu-id="25515-234">查看您現有的電話系統，並分析來電的類型和頻率。</span><span class="sxs-lookup"><span data-stu-id="25515-234">Look at your existing calling system and analyze the types and frequency of incoming calls.</span></span> <span data-ttu-id="25515-235">使用此資訊來協助通知您的自動語音應答及呼叫佇列結構。</span><span class="sxs-lookup"><span data-stu-id="25515-235">Use this information to help inform your auto attendant and call queue structure.</span></span>
- <span data-ttu-id="25515-236">將最常見的選項放在功能表中，盡可能快速地路由通話。</span><span class="sxs-lookup"><span data-stu-id="25515-236">Put the most common options earliest in the menu to route calls as quickly as possible.</span></span>
- <span data-ttu-id="25515-237">除非有可用的佇列24/7，否則請避免直接將服務號碼連線至呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-237">Avoid connecting service numbers directly to call queues unless the queues are available 24/7.</span></span> <span data-ttu-id="25515-238">[通話佇列] 不允許針對非工作日或假日進行個別的呼叫處理。</span><span class="sxs-lookup"><span data-stu-id="25515-238">Call queues do not allow for separate call handling for off hours or holidays.</span></span> <span data-ttu-id="25515-239">如果您想要使用直接號碼的佇列，請將該號碼指派給自動語音應答，該自動語音應答會在營業期間自動重新導向至該佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-239">If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.</span></span>
- <span data-ttu-id="25515-240">如果您收到許多要求您的公司有基本資訊（例如，商務時數、位置或網站位址）的通話，請考慮建立自動語音應答，以針對錄製的訊息回答這些問題。</span><span class="sxs-lookup"><span data-stu-id="25515-240">If you receive a lot of calls requesting basic information about your company, such as business hours, location, or web site address, consider creating an auto attendant to answer these questions with recorded messages.</span></span>
- <span data-ttu-id="25515-241">讓功能表項目目清單保持在5個或更少。</span><span class="sxs-lookup"><span data-stu-id="25515-241">Keep the list of menu items to five or fewer.</span></span> <span data-ttu-id="25515-242">呼叫者可能無法記住五個以上的選項。</span><span class="sxs-lookup"><span data-stu-id="25515-242">Callers can have trouble remembering more than five options.</span></span> <span data-ttu-id="25515-243">如果需要更多選項才能正確路由通話，請使用嵌套的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="25515-243">Use nested auto attendants if more options are needed to properly route a call.</span></span>
- <span data-ttu-id="25515-244">首先描述服務，然後再按下 (的選項：針對 Sales 按 1) ，而不是 (例如的其他方式。</span><span class="sxs-lookup"><span data-stu-id="25515-244">Describe the service first, followed by the option to press (eg: For Sales press 1) rather than the other way around (eg.</span></span> <span data-ttu-id="25515-245">按1以取得銷售) 。</span><span class="sxs-lookup"><span data-stu-id="25515-245">Press 1 for Sales).</span></span> 
- <span data-ttu-id="25515-246">您的呼叫者將瞭解的使用者術語，而不是您在內部使用的專案。</span><span class="sxs-lookup"><span data-stu-id="25515-246">User terminology your callers will understand rather than what you may use internally.</span></span>
- <span data-ttu-id="25515-247">避免經常更新通話路由。</span><span class="sxs-lookup"><span data-stu-id="25515-247">Avoid frequent updates to call routing.</span></span> <span data-ttu-id="25515-248">如果您在將來變更自動語音應答的功能表選項，請在前30天撥打電話給語音提示。</span><span class="sxs-lookup"><span data-stu-id="25515-248">If you change your menu options for an auto attendant in the future, call that out in the voice prompts for the first 30 days.</span></span>

## <a name="resource-accounts-and-phone-numbers"></a><span data-ttu-id="25515-249">資源帳戶和電話號碼</span><span class="sxs-lookup"><span data-stu-id="25515-249">Resource accounts and phone numbers</span></span>

<span data-ttu-id="25515-250">團隊會使用 *[資源帳戶](manage-resource-accounts.md)* 來連接自動語音應答及呼叫佇列，並視需要將電話號碼指派給他們。</span><span class="sxs-lookup"><span data-stu-id="25515-250">Teams uses *[resource accounts](manage-resource-accounts.md)* to connect auto attendants and call queues to each other and to assign them phone numbers if desired.</span></span>

- <span data-ttu-id="25515-251">每個通話佇列和自動語音應答都需要至少一個資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="25515-251">Each call queue and auto attendant requires at least one resource account.</span></span>
- <span data-ttu-id="25515-252">每個資源帳戶都需要一個免費的電話系統-虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="25515-252">Each resource account requires a free Phone System - Virtual User license.</span></span>
- <span data-ttu-id="25515-253">您可以選擇性地將資源帳戶指派給一或多個服務號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-253">A resource account can optionally be assigned one or more service numbers.</span></span> <span data-ttu-id="25515-254"> (這是將電話號碼指派給自動語音應答及呼叫佇列的方式。 ) </span><span class="sxs-lookup"><span data-stu-id="25515-254">(This is how phone numbers get assigned to auto attendants and call queues.)</span></span>

<span data-ttu-id="25515-255">您可以將 [Microsoft 服務號碼](getting-service-phone-numbers.md)、直接銀行代號或混合式數位指派給資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="25515-255">You can assign a [Microsoft service number](getting-service-phone-numbers.md), a direct routing number, or a hybrid number to a resource account.</span></span>

<span data-ttu-id="25515-256">您可以使用付費或免付費服務號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-256">You can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="25515-257">您無法使用自動語音應答或通話佇列的使用者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="25515-257">You cannot use user phone numbers for auto attendants or call queues.</span></span>

## <a name="getting-started"></a><span data-ttu-id="25515-258">快速入門</span><span class="sxs-lookup"><span data-stu-id="25515-258">Getting started</span></span>

<span data-ttu-id="25515-259">完成本文中的規劃工作後，請遵循下列步驟來取得自動語音應答及通話佇列設定：</span><span class="sxs-lookup"><span data-stu-id="25515-259">Once you have completed the planning tasks in this article, follow these steps to get your auto attendants and call queues set up:</span></span>

1. <span data-ttu-id="25515-260">取得您想要的自動語音應答及呼叫佇列所需的服務號碼，以便透過直接撥號從貴組織以外的電話進行存取。</span><span class="sxs-lookup"><span data-stu-id="25515-260">Get the service numbers that you need for the auto attendants and call queues that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="25515-261">這可能包括 [從另一個提供者轉移號碼](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [要求新的服務號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="25515-261">This might include [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](getting-service-phone-numbers.md).</span></span>

2. <span data-ttu-id="25515-262">取得您打算建立的每個資源帳戶的 [電話系統-虛擬使用者授權](teams-add-on-licensing/virtual-user.md) 。</span><span class="sxs-lookup"><span data-stu-id="25515-262">Get a [Phone System - Virtual User license](teams-add-on-licensing/virtual-user.md) for each resource account that you plan to create.</span></span> <span data-ttu-id="25515-263">這些授權是免費的，因此我們建議您先取得幾個額外的案例，以備日後決定變更您的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="25515-263">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.</span></span>

3. <span data-ttu-id="25515-264">針對您要建立的每個自動語音應答和通話佇列[建立資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="25515-264">[Create a resource account](manage-resource-accounts.md) for each auto attendant and call queue that you want to create.</span></span> <span data-ttu-id="25515-265">將每個帳戶指派給電話系統-虛擬使用者授權，並選擇服務號碼（選擇性）。</span><span class="sxs-lookup"><span data-stu-id="25515-265">Assign each account a Phone System - Virtual User license and, optionally, a service number.</span></span>

4. <span data-ttu-id="25515-266">在自動語音應答中，建立您想要單獨撥打通話路線的[假日](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="25515-266">[Create the holidays](set-up-holidays-in-teams.md) for which you want to have separate call routing in your auto attendants.</span></span>

5. <span data-ttu-id="25515-267">或者，如果您想要使用此功能協助來電轉接 [，請設定 [通話停](call-park-and-retrieve.md) 用] 和 [檢索]。</span><span class="sxs-lookup"><span data-stu-id="25515-267">Optionally, [set up call parking and retrieval](call-park-and-retrieve.md) if you want to use this feature to help with call transfers.</span></span>

6. <span data-ttu-id="25515-268">建立您想要用來包含通話佇列之通話代理程式的群組。</span><span class="sxs-lookup"><span data-stu-id="25515-268">Create the groups that you want to use to contain the call agents for the call queues.</span></span>

7. <span data-ttu-id="25515-269">如果您打算允許透過分機撥打，請確定您已將使用者的分機號碼新增至其 Azure Active Directory 設定檔。</span><span class="sxs-lookup"><span data-stu-id="25515-269">If you plan to allow dial by extension, ensure that you've added your users' extension number to their Azure Active Directory profile.</span></span>

<span data-ttu-id="25515-270">完成上述步驟之後，您就可以開始建立自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-270">Once you've completed the steps above, you're ready to create your auto attendants and call queues.</span></span> <span data-ttu-id="25515-271">因為自動語音應答及呼叫佇列可以重新導向來電，所以請參閱您建立的工作流程圖表，以判斷應該首先建立哪個自動語音應答或呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="25515-271">Because auto attendants and call queues can redirect calls to each other, refer to the workflow diagram that you created to determine which auto attendant or call queue should be created first.</span></span> <span data-ttu-id="25515-272">在上圖中的範例中，您會在建立 Contoso 主自動語音應答前，建立 [銷售及支援電話] 佇列，因為主要自動語音應答必須將呼叫者指引至銷售和支援電話列隊。</span><span class="sxs-lookup"><span data-stu-id="25515-272">In the example in the diagram above, you would create the sales and support call queues before you create the Contoso main auto attendant because the main auto attendant needs to direct callers to the sales and support call queues.</span></span>

<span data-ttu-id="25515-273">如需如何建立自動語音應答及呼叫佇列的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="25515-273">See the following articles for information on how to create auto attendants and call queues:</span></span>

- [<span data-ttu-id="25515-274">設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="25515-274">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="25515-275">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="25515-275">Create a call queue</span></span>](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a><span data-ttu-id="25515-276">相關主題</span><span class="sxs-lookup"><span data-stu-id="25515-276">Related topics</span></span>

[<span data-ttu-id="25515-277">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="25515-277">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="25515-278">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="25515-278">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="25515-279">小型企業範例 - 設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="25515-279">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)
