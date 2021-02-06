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
- m365initiative-voice
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
ms.openlocfilehash: 65dac48267379d17b76443e42eb70e2e866f6e8f
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125665"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a><span data-ttu-id="36826-103">規劃小組自動語音應答及呼叫佇列</span><span class="sxs-lookup"><span data-stu-id="36826-103">Plan for Teams auto attendants and call queues</span></span>

<span data-ttu-id="36826-104">自動語音應答可讓您根據本機號碼來設定功能表選項，以路由通話。</span><span class="sxs-lookup"><span data-stu-id="36826-104">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="36826-105">功能表選項，例如 [銷售]，請按1。</span><span class="sxs-lookup"><span data-stu-id="36826-105">Menu options, such as "For Sales, press 1.</span></span>  <span data-ttu-id="36826-106">針對服務按下 [2]，對於自動語音應答，組織會提供一系列選項，讓呼叫者快速引導來電者，而不需要依靠人工接線員來處理來電。</span><span class="sxs-lookup"><span data-stu-id="36826-106">For Services press 2", for an auto attendant let an organization provide a series of choices that guide callers to their destination quickly, without relying on a human operator to handle incoming calls.</span></span>

<span data-ttu-id="36826-107">通話佇列是呼叫者的等待區域。</span><span class="sxs-lookup"><span data-stu-id="36826-107">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="36826-108">針對來電者需要接觸特定專業的人員（例如銷售或服務），而不是特定人員，您可以使用呼叫佇列將呼叫者連線至可協助他們的工程師群組。</span><span class="sxs-lookup"><span data-stu-id="36826-108">For situations where callers need to reach someone with a particular specialty - such as sales or service - rather than a specific person, you can use call queues to connect callers to the group of agents who can assist them.</span></span> <span data-ttu-id="36826-109">呼叫者將保留，直到指派給佇列的代理程式可供您接聽通話。</span><span class="sxs-lookup"><span data-stu-id="36826-109">Callers are put on hold until an agent assigned to the queue is available to take their call.</span></span>

<span data-ttu-id="36826-110">[自動語音應答] 和 [呼叫佇列] 可搭配使用，輕鬆地將呼叫者路由至組織中的適當人員或部門。</span><span class="sxs-lookup"><span data-stu-id="36826-110">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

## <a name="auto-attendants"></a><span data-ttu-id="36826-111">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="36826-111">Auto attendants</span></span>

<span data-ttu-id="36826-112">自動語音應答的主要用途是根據來電者輸入，將呼叫者引導至所提供的功能表選項。</span><span class="sxs-lookup"><span data-stu-id="36826-112">The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options.</span></span> <span data-ttu-id="36826-113">來電者可以導向貴組織內的特定人員，打電話給對方等候與下一個可用的 agent 或語音信箱交談的佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-113">Callers can be directed to specific people within your organization, to call queues where they wait to talk to the next available agent, or to voicemail.</span></span> <span data-ttu-id="36826-114">您可以針對 [上班時間]、[下班時間] 和 [假日] 指定不同的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="36826-114">Different call routing options can be specified for business hours, off hours, and holidays.</span></span>

<span data-ttu-id="36826-115">您可以使用文字轉換語音 (系統產生的提示) 或上傳錄製的音訊檔案，來建立功能表提示。</span><span class="sxs-lookup"><span data-stu-id="36826-115">Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file.</span></span> <span data-ttu-id="36826-116">語音辨識接受語音命令以進行無人流覽，但通話中的人員也可以使用電話鍵流覽功能表。</span><span class="sxs-lookup"><span data-stu-id="36826-116">Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>

<span data-ttu-id="36826-117">每個自動助理都有特定的語言和時區。</span><span class="sxs-lookup"><span data-stu-id="36826-117">Each auto attendant has a specific language and time zone.</span></span> <span data-ttu-id="36826-118">如果您有多個語言或世界各地的業務，您可以根據需要建立許多不同的自動語音應答，以適應您的來電者。</span><span class="sxs-lookup"><span data-stu-id="36826-118">If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.</span></span>

<span data-ttu-id="36826-119">針對每個自動語音應答，您可以設定操作員。</span><span class="sxs-lookup"><span data-stu-id="36826-119">For each auto attendant, you can configure an operator.</span></span> <span data-ttu-id="36826-120">雖然您可以設定操作員通話來移至各種不同的目的地，但操作員的功能是設計來讓呼叫者與組織中的特定人員交談，以協助他們。</span><span class="sxs-lookup"><span data-stu-id="36826-120">While you can configure operator calls to go to a variety of destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.</span></span>

<span data-ttu-id="36826-121">自動語音應答可以設定為允許呼叫者搜尋貴組織的目錄（依名稱或分機號碼）。</span><span class="sxs-lookup"><span data-stu-id="36826-121">Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number.</span></span> <span data-ttu-id="36826-122">在自動語音應答中，您可以選擇要加入或排除的使用者群組，以指定可供目錄搜尋使用的人員。</span><span class="sxs-lookup"><span data-stu-id="36826-122">Within an auto attendant, you can specify who is available for the directory search by choosing groups of users to include or exclude.</span></span> <span data-ttu-id="36826-123"> (這稱為 *撥號作用* 中。 ) </span><span class="sxs-lookup"><span data-stu-id="36826-123">(This is known as *dial scope*.)</span></span>

<span data-ttu-id="36826-124">來電者可以透過直接電話號碼（如果有設定的話）或從另一個自動語音應答或呼叫佇列重新導向來取得自動助理。</span><span class="sxs-lookup"><span data-stu-id="36826-124">Callers can reach an auto attendant either by direct phone number, if configured, or by being redirected from another auto attendant or a call queue.</span></span>

## <a name="call-queues"></a><span data-ttu-id="36826-125">通話佇列</span><span class="sxs-lookup"><span data-stu-id="36826-125">Call queues</span></span>

<span data-ttu-id="36826-126">通話佇列類似于實際建築物中的等待會議室。</span><span class="sxs-lookup"><span data-stu-id="36826-126">A call queue is analogous to a waiting room in a physical building.</span></span> <span data-ttu-id="36826-127">來電者會在通話路由到佇列中的代理程式時等待通話。</span><span class="sxs-lookup"><span data-stu-id="36826-127">Callers wait on hold while calls are routed to the agents in the queue.</span></span> <span data-ttu-id="36826-128">通話佇列通常用於銷售與服務功能。</span><span class="sxs-lookup"><span data-stu-id="36826-128">Call queues are commonly used for sales and service functions.</span></span> <span data-ttu-id="36826-129">不過，通話佇列可用於任何呼叫次數超過您的內部容量（例如，繁忙設施中的接待員）的情況。</span><span class="sxs-lookup"><span data-stu-id="36826-129">However, call queues can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.</span></span>

<span data-ttu-id="36826-130">在佇列中的呼叫者總數或等待時間超過您指定的限制情況下，通話佇列允許特定的通話路由。</span><span class="sxs-lookup"><span data-stu-id="36826-130">Call queues allow for specific routing of calls in cases where the total number of callers in the queue or the wait time exceeds the limits that you specify.</span></span> <span data-ttu-id="36826-131">通話可以路由至特定人員、語音信箱、其他通話佇列或自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="36826-131">Calls can be routed to specific people, voicemail, other call queues, or auto attendants.</span></span>

<span data-ttu-id="36826-132">就像自動語音應答一樣，通話佇列中的每一個都有語言設定。</span><span class="sxs-lookup"><span data-stu-id="36826-132">Like auto attendants, call queues each have a language setting.</span></span> <span data-ttu-id="36826-133">如果您有多個語言的商務，您可以使用不同的通話佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-133">You can use different call queues if you do business in multiple languages.</span></span> <span data-ttu-id="36826-134">如果代理人是多語言，則可以是多個佇列的成員。</span><span class="sxs-lookup"><span data-stu-id="36826-134">Agents can be members of more than one queue if they're multi-lingual.</span></span>

<span data-ttu-id="36826-135">針對每個通話佇列，您可以指定佇列中的代理程式是否可以選擇不接聽通話，以及是否應該根據其在團隊中的目前狀態指示來傳送呼叫給對方。</span><span class="sxs-lookup"><span data-stu-id="36826-135">For each call queue, you can specify if agents in the queue can opt out of taking calls and if calls should be routed to them based on their presence indication in Teams.</span></span>

<span data-ttu-id="36826-136">您可以將電話號碼指派給通話佇列，不過通話佇列不會提供獨立的呼叫路由來提供下班時間和假日。</span><span class="sxs-lookup"><span data-stu-id="36826-136">You can assign a phone number to a call queue, however call queues do not provide separate call routing for off hours and holidays.</span></span> <span data-ttu-id="36826-137">除非您的通話佇列是配備24/7 的人員，否則建議您將電話號碼指派給在營業期間重新導向呼叫佇列的自動回應。</span><span class="sxs-lookup"><span data-stu-id="36826-137">Unless your call queue is staffed 24/7, we recommend assigning the phone number to an auto attendant that redirects to the call queue during business hours.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36826-138">必要條件</span><span class="sxs-lookup"><span data-stu-id="36826-138">Prerequisites</span></span>

<span data-ttu-id="36826-139">若要設定自動語音應答及呼叫佇列，您必須具備下列資源：</span><span class="sxs-lookup"><span data-stu-id="36826-139">To configure auto attendants and call queues, you need the following resources:</span></span>

- <span data-ttu-id="36826-140">每個自動語音應答及每個通話佇列的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="36826-140">A resource account for each auto attendant and each call queue</span></span>
- <span data-ttu-id="36826-141">每個資源帳戶的免費電話系統-虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="36826-141">A free Phone System - Virtual User license for each resource account</span></span>
- <span data-ttu-id="36826-142">至少有一個 [Microsoft 服務號碼](getting-service-phone-numbers.md)、直接銀行代號，或您要直接撥入之每個資源帳戶的混合式編號</span><span class="sxs-lookup"><span data-stu-id="36826-142">At least one [Microsoft service number](getting-service-phone-numbers.md), direct routing number, or a hybrid number for each resource account that you want to be directly dialable</span></span>
 - <span data-ttu-id="36826-143">服務號碼可能是付費或免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="36826-143">The service number may be a toll or toll-free number</span></span>

<span data-ttu-id="36826-144">從通話佇列接收通話的代理程式必須是線上啟用企業語音或內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="36826-144">Agents who receive calls from the call queues must be Enterprise Voice enabled online or on-premise users.</span></span> <span data-ttu-id="36826-145">此外，如果通話佇列使用的是直接銀行代號，則需要會議或轉接通話的工程師也需要：</span><span class="sxs-lookup"><span data-stu-id="36826-145">In addition, if the call queues are using Direct Routing numbers, agents who need to conference or transfer calls also require:</span></span>

- <span data-ttu-id="36826-146">呼叫佇列使用傳輸模式時指派的線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="36826-146">An online voice routing policy assigned if the call queue uses transfer mode</span></span>
- <span data-ttu-id="36826-147">通話佇列使用會議模式時指派的音訊會議授權或線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="36826-147">An Audio Conferencing license or online voice routing policy assigned if the call queue uses conference mode</span></span>

<span data-ttu-id="36826-148">如果您的代理正在使用 Microsoft 團隊 app 進行通話佇列通話，則必須在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="36826-148">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="36826-149">當您將來電轉接至外部電話號碼時，執行傳送 (的資源帳戶（也就是與自動語音應答或通話佇列相關聯的資源帳戶）) 必須有電話號碼和 Microsoft 365 電話系統虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="36826-149">When transferring calls to an external phone number, the resource account performing the transfer (that is, the one associated with the auto attendant or call queue) must have a phone number and a Microsoft 365 Phone System Virtual User license.</span></span> <span data-ttu-id="36826-150">此外</span><span class="sxs-lookup"><span data-stu-id="36826-150">Additionally:</span></span>

- <span data-ttu-id="36826-151">針對含有通話方案編號的資源帳戶，請指派 [通話方案](calling-plans-for-office-365.md) 授權。</span><span class="sxs-lookup"><span data-stu-id="36826-151">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="36826-152">針對有直接傳送號碼的資源帳戶，請指派 [線上語音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="36826-152">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36826-153">僅限 Microsoft 團隊使用者和呼叫代理程式支援自動語音應答和通話佇列的直接路由服務號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-153">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and call agents only.</span></span><br>
> <span data-ttu-id="36826-154">不支援通話方案 trunks 和直接路由 trunks 之間的轉移。</span><span class="sxs-lookup"><span data-stu-id="36826-154">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

## <a name="business-decisions"></a><span data-ttu-id="36826-155">商務決策</span><span class="sxs-lookup"><span data-stu-id="36826-155">Business decisions</span></span>

<span data-ttu-id="36826-156">在您設定自動語音應答及呼叫佇列之前，請先決定如何在您的企業中使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="36826-156">Before you set up your auto attendants and call queues, there are some decisions that you should make about how to use these features in your business.</span></span> <span data-ttu-id="36826-157">當您設定自動語音應答及呼叫佇列時，這些決定將決定您選擇的設定。</span><span class="sxs-lookup"><span data-stu-id="36826-157">These decisions will determine the settings that you choose when you configure your auto attendants and call queues.</span></span>

<span data-ttu-id="36826-158">記錄這些問題的答案，並將資訊提供給管理員進行設定。</span><span class="sxs-lookup"><span data-stu-id="36826-158">Document your answers to these questions and provide the information to the administrator doing the configuration.</span></span>

- <span data-ttu-id="36826-159">您需要哪些語言？</span><span class="sxs-lookup"><span data-stu-id="36826-159">What languages do you need?</span></span> <span data-ttu-id="36826-160">需要這些語言的位置-哪個部門或群組？</span><span class="sxs-lookup"><span data-stu-id="36826-160">Where are these languages needed - which department or group?</span></span>
- <span data-ttu-id="36826-161">您想要允許來自呼叫者的語音輸入或只允許撥號輸入嗎？</span><span class="sxs-lookup"><span data-stu-id="36826-161">Do you want to allow voice inputs from callers or only dialing inputs?</span></span>
- <span data-ttu-id="36826-162">您是否需要個別的呼叫路由來關閉時間或假期？</span><span class="sxs-lookup"><span data-stu-id="36826-162">Do you need separate call routing for off hours or holidays?</span></span> <span data-ttu-id="36826-163">有哪些時間和假日？</span><span class="sxs-lookup"><span data-stu-id="36826-163">What are the hours and holidays?</span></span>
- <span data-ttu-id="36826-164">您想要允許通話佇列中的代理程式選擇不接聽通話嗎？</span><span class="sxs-lookup"><span data-stu-id="36826-164">Do you want to allow agents in a call queue to opt out of taking calls?</span></span>
- <span data-ttu-id="36826-165">您想讓通話佇列中的代理程式，或您的操作員在撥出時有特定的本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="36826-165">Do you want agents in your call queues or your operator to have a specific caller ID if they dial out?</span></span>
- <span data-ttu-id="36826-166">您想要在組織中啟用 [呼叫停用和檢索](call-park-and-retrieve.md) ，協助在人員或部門間呼叫提交嗎？</span><span class="sxs-lookup"><span data-stu-id="36826-166">Do you want to enable [call parking and retrieval](call-park-and-retrieve.md) in your organization to assist in call handoffs between people or departments?</span></span>
- <span data-ttu-id="36826-167">針對語音提示，您想要自行錄製或使用系統產生的語音嗎？</span><span class="sxs-lookup"><span data-stu-id="36826-167">For the voice prompts, do you want to record your own or use the system-generated voice?</span></span> <span data-ttu-id="36826-168"> (系統產生的語音很容易更新。 ) </span><span class="sxs-lookup"><span data-stu-id="36826-168">(The system-generated voice is easy to update.)</span></span>

## <a name="technical-decisions"></a><span data-ttu-id="36826-169">技術決策</span><span class="sxs-lookup"><span data-stu-id="36826-169">Technical decisions</span></span>

<span data-ttu-id="36826-170">使用 [自動語音應答] 和 [呼叫佇列] 將呼叫者連線至組織中的人員時，您必須先進行一些技術決策，才能開始進行設定。</span><span class="sxs-lookup"><span data-stu-id="36826-170">When using auto attendants and call queues to connect callers to people in your organization, there are some technical decisions to make before you start the configuration.</span></span>

<span data-ttu-id="36826-171">您可以透過下列方式將代理新增至通話佇列：</span><span class="sxs-lookup"><span data-stu-id="36826-171">Agents can be added to call queues in the following ways:</span></span>

- <span data-ttu-id="36826-172">個別使用者</span><span class="sxs-lookup"><span data-stu-id="36826-172">Individual users</span></span>
- <span data-ttu-id="36826-173">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="36826-173">Distribution lists</span></span>
- <span data-ttu-id="36826-174">安全性群組，包括已啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="36826-174">Security groups, including mail-enabled security groups</span></span>
- <span data-ttu-id="36826-175">Microsoft 365 群組或團隊</span><span class="sxs-lookup"><span data-stu-id="36826-175">Microsoft 365 Groups or Teams</span></span>

<span data-ttu-id="36826-176">如有需要，您可以針對每個佇列使用這些選項的組合。</span><span class="sxs-lookup"><span data-stu-id="36826-176">You can use a combination of these options for each queue if needed.</span></span> <span data-ttu-id="36826-177">具有電子郵件地址的群組可用於語音信箱。</span><span class="sxs-lookup"><span data-stu-id="36826-177">Groups that have an email address can be used for voicemail.</span></span> <span data-ttu-id="36826-178">使用團隊提供許多優點，包括共用檔案儲存和在代理程式之間聊天、可接收語音訊息的常見信箱，以及可納入與您的商務用 office 應用程式或 Power App 整合的可擴展平臺。</span><span class="sxs-lookup"><span data-stu-id="36826-178">Using Teams offers a number of advantages, including shared file storage and chat between agents, a common mailbox where voicemails can be received, and an extensible platform that can include integration with your line of business applications or Power Apps.</span></span>

<span data-ttu-id="36826-179">我們建議您選擇一個策略，在開始進行設定之前，將呼叫代理程式新增到佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-179">We recommend choosing a strategy for adding call agents to queues before you start your configuration.</span></span>

<span data-ttu-id="36826-180">如果您有現有的自動語音應答及呼叫佇列基礎結構，且您要遷移至小組，您需要將現有的電話號碼轉移到新的自動語音應答及呼叫佇列的方案。</span><span class="sxs-lookup"><span data-stu-id="36826-180">If you have an existing auto attendant and call queue infrastructure and you're migrating to Teams, you'll need a plan to transfer your existing phone numbers to the new auto attendants and call queues.</span></span> <span data-ttu-id="36826-181">您可能需要建立 [埠順序](phone-number-calling-plans/port-order-overview.md) ，才能從其他提供者移動您的號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-181">You might need to create a [port order](phone-number-calling-plans/port-order-overview.md) to move your numbers from another providers.</span></span> <span data-ttu-id="36826-182">我們建議您暫時取得一或多個新的電話號碼，並測試您的自動語音應答及呼叫佇列流程，然後再切換到您目前已提供服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-182">We recommend that you temporarily acquire one or more new phone numbers and test your auto attendant and call queue flows before switching them over the numbers you currently have in service.</span></span>

<span data-ttu-id="36826-183">[*會議模式*] 是通話佇列中的一個選項，可大幅減少將小組 VOIP 通話和 PSTN 呼叫連線至代理程式所需的時間量。</span><span class="sxs-lookup"><span data-stu-id="36826-183">*Conference mode* is an option in call queues that significantly reduces the amount of time it takes to connect Teams VOIP calls and PSTN calls to an agent.</span></span> <span data-ttu-id="36826-184">若要使用會議模式，通話佇列中的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="36826-184">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

- <span data-ttu-id="36826-185">最新版本的 Microsoft 團隊桌面用戶端、Android 應用程式或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="36826-185">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="36826-186">Microsoft 團隊手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="36826-186">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="36826-187">將代理的小群組帳戶設定為 [僅限團隊模式]。</span><span class="sxs-lookup"><span data-stu-id="36826-187">Set Agents' Teams accounts to Teams-only mode.</span></span> <span data-ttu-id="36826-188">不符合需求的工程師不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="36826-188">Agents who don't meet the requirements aren't included in the call routing list.</span></span>

<span data-ttu-id="36826-189">如果您的代理全部使用相容的用戶端，我們建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="36826-189">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

## <a name="plan-your-call-routing-flow"></a><span data-ttu-id="36826-190">規劃通話路由流程</span><span class="sxs-lookup"><span data-stu-id="36826-190">Plan your call routing flow</span></span>

<span data-ttu-id="36826-191">在規劃程式中，我們建議您在圖表中處理貴組織的通話路由。</span><span class="sxs-lookup"><span data-stu-id="36826-191">As part of the planning process, we recommend that you work out the call routing for your organization in a diagram.</span></span> <span data-ttu-id="36826-192">此圖表可協助您判斷在您的組織中呼叫人員的最有效路由。</span><span class="sxs-lookup"><span data-stu-id="36826-192">The diagram helps determine the most efficient routing for people calling in to your organization.</span></span> <span data-ttu-id="36826-193">您也可以使用圖表來判斷您需要建立的自動語音應答及呼叫佇列，以及服務號碼、授權及資源帳戶等相關需求。</span><span class="sxs-lookup"><span data-stu-id="36826-193">You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.</span></span>

<span data-ttu-id="36826-194">讓我們來看看自動語音應答及呼叫佇列路由通話的方式。</span><span class="sxs-lookup"><span data-stu-id="36826-194">Let's look at how auto attendants and call queues route calls.</span></span>

<span data-ttu-id="36826-195">自動回應會以下列其中一種方式路由所有呼叫：</span><span class="sxs-lookup"><span data-stu-id="36826-195">Auto attendants route all calls in one of the following ways:</span></span>

- <span data-ttu-id="36826-196">[**立即重新導向**]-通話可能會被重新導向至下列其中一個呼叫路由目標 () 在您接聽或初始問候語後立即顯示。</span><span class="sxs-lookup"><span data-stu-id="36826-196">**Redirect immediately** - calls can be redirected to one of the call routing destinations (listed below) immediately upon answering or after an initial greeting.</span></span>
- <span data-ttu-id="36826-197">**根據撥號選項重新導向** -來電者可在指派給電話鍵台（0-9）號碼的選項之間進行選擇。</span><span class="sxs-lookup"><span data-stu-id="36826-197">**Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad, 0-9.</span></span> <span data-ttu-id="36826-198">您可以為每個撥號鍵指派呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="36826-198">Each dial key can be assigned a call routing destinations.</span></span>
- <span data-ttu-id="36826-199">透過 **名稱或分機號碼撥打人員**：您可以將來電者的分機號碼撥打給您組織的目錄，或使用拼寫給人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="36826-199">**Dial people by name or extension** - callers can be directed to dial the extension number of the person they're trying to reach in your organization's directory, or by spelling the person's name.</span></span>
- <span data-ttu-id="36826-200">**中斷** 連線-自動語音應答可能會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="36826-200">**Disconnect** - an auto attendant can hang up the call.</span></span>

> [!NOTE]
> <span data-ttu-id="36826-201">單一自動語音應答只支援單一 "撥號方式" 方法。</span><span class="sxs-lookup"><span data-stu-id="36826-201">A single Auto attendant can only support a single "dial by" method.</span></span>  <span data-ttu-id="36826-202">若要允許呼叫者以名稱和依號碼撥號，您必須建立一個自動語音應答，讓它有撥打電話給撥號選項，另一種是透過分機撥打電話。</span><span class="sxs-lookup"><span data-stu-id="36826-202">To allow callers to dial by name and by number, you will need to create an auto attendant that has an option for dial by name and the another for dial by extension.</span></span>  <span data-ttu-id="36826-203">每個選項都會路由到針對這些「撥號者」案例設定的個別自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="36826-203">Each of these options will route to separate auto attendants configured for these "dial by" scenarios.</span></span>

<span data-ttu-id="36826-204">當來電由自動回應或通話佇列重新導向時，您可以從下列通話路由目的地選擇：</span><span class="sxs-lookup"><span data-stu-id="36826-204">When calls are redirected by an auto attendant or call queue, you can choose from the following call routing destinations:</span></span>

- <span data-ttu-id="36826-205">**組織中的人員** -您組織中能夠接聽語音通話的人員。</span><span class="sxs-lookup"><span data-stu-id="36826-205">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="36826-206">這可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="36826-206">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="36826-207">**語音 app** -另一個自動語音應答或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-207">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="36826-208">選擇與目的地相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="36826-208">Choose the resource account associated with the destination.</span></span>
- <span data-ttu-id="36826-209">**外部電話號碼** -任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-209">**External phone number** - any phone number.</span></span> <span data-ttu-id="36826-210"> (查看 [外部轉接技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。</span><span class="sxs-lookup"><span data-stu-id="36826-210">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="36826-211">**語音信箱** -與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="36826-211">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="36826-212">**運營商** (僅限自動助理) -為自動語音應答定義的操作員。</span><span class="sxs-lookup"><span data-stu-id="36826-212">**Operator** (auto attendant only) - the operator defined for the auto attendant.</span></span> <span data-ttu-id="36826-213">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="36826-213">Defining an operator is optional.</span></span> <span data-ttu-id="36826-214">運算子可以是此清單中的任何其他目的地。</span><span class="sxs-lookup"><span data-stu-id="36826-214">An operator can be any of the other destinations in this list.</span></span>

<span data-ttu-id="36826-215">自動語音應答會提供單獨的呼叫路由選項，用於在上班時間以外的電話和假日上接收的通話。</span><span class="sxs-lookup"><span data-stu-id="36826-215">Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.</span></span> <span data-ttu-id="36826-216">[下班後] 呼叫路由可允許上述所有選項，而 [假日通話路由] 只允許重新導向通話或中斷通話，但沒有撥號鍵選項。</span><span class="sxs-lookup"><span data-stu-id="36826-216">After-hours call routing allows all the options listed above, while holiday call routing allows only redirecting or disconnecting a call, but no dial key options.</span></span>

<span data-ttu-id="36826-217">[通話佇列] 會將呼叫者放在 [保留]，直到指派給該佇列的代理程式可用於接聽電話。</span><span class="sxs-lookup"><span data-stu-id="36826-217">Call queues place the caller on hold until an agent assigned to the queue is available to take their call.</span></span> <span data-ttu-id="36826-218">在兩種情況下，可能會將來電者導向到佇列：</span><span class="sxs-lookup"><span data-stu-id="36826-218">There are two situations where a caller might be directed out of the queue:</span></span>

- <span data-ttu-id="36826-219">**呼叫溢出** -如果佇列中的呼叫數量超過您設定的限制，新的呼叫者就會從佇列中重新導向。</span><span class="sxs-lookup"><span data-stu-id="36826-219">**Call overflow** - if the number of calls in the queue exceeds the limit that you set, then new callers are redirected out of the queue.</span></span>
- <span data-ttu-id="36826-220">**通話超時** -如果來電者在佇列中的時間超過設定的超時設定，就會從佇列中重新導向。</span><span class="sxs-lookup"><span data-stu-id="36826-220">**Call timeout** - if a caller has been in the queue longer than the configured timeout setting, they're redirected out of the queue.</span></span>

<span data-ttu-id="36826-221">除了操作員之外，您可以將呼叫已重新導向的通話傳送至上述任何呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="36826-221">Calls redirected out of a queue can be sent to any of the call routing destinations listed above except for an operator.</span></span> <span data-ttu-id="36826-222"> (通話佇列沒有操作員，但您可以將呼叫者重新導向至與您已為自動語音應答設定的操作員相同的目的地。 ) </span><span class="sxs-lookup"><span data-stu-id="36826-222">(Call queues don't have operators, but you can redirect callers to the same destination as an operator that you've configured for an auto attendant.)</span></span>

<span data-ttu-id="36826-223">下列範例顯示使用 [自動語音應答] 和 [通話佇列] 呼叫路由的範例。</span><span class="sxs-lookup"><span data-stu-id="36826-223">The example below shows an example of call routing using auto attendants and call queues.</span></span>

![使用自動語音應答呼叫路由的圖表與通話佇列](media/attendant-and-queue-call-routing.png)

<span data-ttu-id="36826-225">在上述範例中：</span><span class="sxs-lookup"><span data-stu-id="36826-225">In the example above:</span></span>

- <span data-ttu-id="36826-226">零 (0) 金鑰會將呼叫者重新導向到操作員。</span><span class="sxs-lookup"><span data-stu-id="36826-226">The zero (0) key redirects callers to an operator.</span></span> <span data-ttu-id="36826-227">該自動語音應答的操作員已設定為 **組織中的人員**。</span><span class="sxs-lookup"><span data-stu-id="36826-227">The operator for that auto attendant has been configured as a **Person in the organization**.</span></span>
- <span data-ttu-id="36826-228">一 (1) 金鑰會將呼叫者重新導向至 sales 通話佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-228">The one (1) key redirects callers to the sales call queue.</span></span> <span data-ttu-id="36826-229">此通話佇列已連接至包含指派給該佇列之銷售小組的小組。</span><span class="sxs-lookup"><span data-stu-id="36826-229">This call queue is connected to a team that contains the sales team assigned to the queue.</span></span>
- <span data-ttu-id="36826-230">兩個 (2) 金鑰會將呼叫者重新導向至支援電話列隊。</span><span class="sxs-lookup"><span data-stu-id="36826-230">The two (2) key redirects callers to the support call queue.</span></span> <span data-ttu-id="36826-231">此通話佇列已連接至包含指派給該小組之支援小組的小組。</span><span class="sxs-lookup"><span data-stu-id="36826-231">This call queue is connected to a team that contains the support team assigned to the team.</span></span>
- <span data-ttu-id="36826-232">支援通話佇列有一個透過中間自動語音應答的直接電話號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-232">The support call queue has a direct phone number via an intervening auto attendant.</span></span> <span data-ttu-id="36826-233">讓自動語音應答能接聽支援行，就能分隔下班時間與假期通話路線。</span><span class="sxs-lookup"><span data-stu-id="36826-233">Having an auto attendant answer the support line allows for separate off hours and holiday call routing.</span></span>
- <span data-ttu-id="36826-234">這三個 (3) 金鑰會將使用者重新導向至公司目錄的另一個自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="36826-234">The three (3) key redirects users to another auto attendant for the company directory.</span></span> <span data-ttu-id="36826-235">公司目錄自動語音應答可讓呼叫者撥打電話給組織中的人員，方法是撥打他們的名稱或分機號碼。</span><span class="sxs-lookup"><span data-stu-id="36826-235">The company directory auto attendant allows callers to call individuals in the organization by dialing their name or extension.</span></span>

<span data-ttu-id="36826-236">我們建議您建立一個或多個類似上方的圖表，以對應您的通話路線。</span><span class="sxs-lookup"><span data-stu-id="36826-236">We recommend that you create one or more diagrams similar to the one above to map out your call routing.</span></span> <span data-ttu-id="36826-237">請務必在您的圖表或隨附的檔中包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="36826-237">Be sure to include the following in your diagram or accompanying documentation:</span></span>

- <span data-ttu-id="36826-238">哪些自動語音應答會透過電話號碼直接存取？</span><span class="sxs-lookup"><span data-stu-id="36826-238">Which auto attendants will have direct access via phone numbers?</span></span>
- <span data-ttu-id="36826-239">每個自動語音應答的時間和假日路由需求為何？</span><span class="sxs-lookup"><span data-stu-id="36826-239">What are the off-hours and holiday routing requirements for each auto attendants?</span></span>
- <span data-ttu-id="36826-240">每個通話佇列的成員資格。</span><span class="sxs-lookup"><span data-stu-id="36826-240">The membership for each call queue.</span></span> <span data-ttu-id="36826-241"> (您可以個別新增使用者，或將佇列對應到不同類型的群組。</span><span class="sxs-lookup"><span data-stu-id="36826-241">(You can add users individually or map the queue to different kinds of groups.</span></span> <span data-ttu-id="36826-242">將佇列對應至團隊可提供最廣泛的使用體驗。 ) </span><span class="sxs-lookup"><span data-stu-id="36826-242">Mapping a queue to a team provides the most versatile experience.)</span></span>

<span data-ttu-id="36826-243">以下是一些呼叫路由最佳做法：</span><span class="sxs-lookup"><span data-stu-id="36826-243">Here are some call routing best practices:</span></span>

- <span data-ttu-id="36826-244">查看您現有的電話系統，並分析來電的類型和頻率。</span><span class="sxs-lookup"><span data-stu-id="36826-244">Look at your existing calling system and analyze the types and frequency of incoming calls.</span></span> <span data-ttu-id="36826-245">使用此資訊來協助通知您的自動語音應答及呼叫佇列結構。</span><span class="sxs-lookup"><span data-stu-id="36826-245">Use this information to help inform your auto attendant and call queue structure.</span></span>
- <span data-ttu-id="36826-246">將最常見的選項放在功能表中，盡可能快速地路由通話。</span><span class="sxs-lookup"><span data-stu-id="36826-246">Put the most common options earliest in the menu to route calls as quickly as possible.</span></span>
- <span data-ttu-id="36826-247">除非有可用的佇列24/7，否則請避免直接將服務號碼連線至呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-247">Avoid connecting service numbers directly to call queues unless the queues are available 24/7.</span></span> <span data-ttu-id="36826-248">通話佇列不允許個別通話處理的時間或假期。</span><span class="sxs-lookup"><span data-stu-id="36826-248">Call queues don't allow for separate call handling for off hours or holidays.</span></span> <span data-ttu-id="36826-249">如果您想要使用直接號碼的佇列，請將該號碼指派給自動語音應答，該自動語音應答會在營業期間自動重新導向至該佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-249">If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.</span></span>
- <span data-ttu-id="36826-250">如果您收到許多要求您公司的基本資訊（例如，商務用時數、位置或網站位址）的來電，請考慮建立自動語音應答，以針對錄製的訊息回答這些問題。</span><span class="sxs-lookup"><span data-stu-id="36826-250">If you receive numerous calls requesting basic information about your company, such as business hours, location, or web site address, consider creating an auto attendant to answer these questions with recorded messages.</span></span>
- <span data-ttu-id="36826-251">讓功能表項目目清單保持在5個或更少。</span><span class="sxs-lookup"><span data-stu-id="36826-251">Keep the list of menu items to five or fewer.</span></span> <span data-ttu-id="36826-252">呼叫者可能無法記住五個以上的選項。</span><span class="sxs-lookup"><span data-stu-id="36826-252">Callers can have trouble remembering more than five options.</span></span> <span data-ttu-id="36826-253">如果需要更多選項才能正確路由通話，請使用嵌套的自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="36826-253">Use nested auto attendants if more options are needed to properly route a call.</span></span>
- <span data-ttu-id="36826-254">首先描述服務，然後再按下 (的選項：針對 Sales 按 1) ，而不是 (例如的其他方式。</span><span class="sxs-lookup"><span data-stu-id="36826-254">Describe the service first, followed by the option to press (eg: For Sales press 1) rather than the other way around (eg.</span></span> <span data-ttu-id="36826-255">按1以取得銷售) 。</span><span class="sxs-lookup"><span data-stu-id="36826-255">Press 1 for Sales).</span></span>
- <span data-ttu-id="36826-256">您的呼叫者將瞭解的使用者術語，而不是您在內部使用的專案。</span><span class="sxs-lookup"><span data-stu-id="36826-256">User terminology your callers will understand rather than what you may use internally.</span></span>
- <span data-ttu-id="36826-257">避免經常更新通話路由。</span><span class="sxs-lookup"><span data-stu-id="36826-257">Avoid frequent updates to call routing.</span></span> <span data-ttu-id="36826-258">如果您在將來變更自動語音應答的功能表選項，請在前30天撥打電話給語音提示。</span><span class="sxs-lookup"><span data-stu-id="36826-258">If you change your menu options for an auto attendant in the future, call that out in the voice prompts for the first 30 days.</span></span>

## <a name="getting-started"></a><span data-ttu-id="36826-259">快速入門</span><span class="sxs-lookup"><span data-stu-id="36826-259">Getting started</span></span>

<span data-ttu-id="36826-260">完成本文中的規劃工作後，請遵循下列步驟來取得自動語音應答及通話佇列設定：</span><span class="sxs-lookup"><span data-stu-id="36826-260">Once you've completed the planning tasks in this article, follow these steps to get your auto attendants and call queues set up:</span></span>

1. <span data-ttu-id="36826-261">取得您想要的自動語音應答及呼叫佇列所需的服務號碼，以便透過直接撥號從貴組織以外的電話進行存取。</span><span class="sxs-lookup"><span data-stu-id="36826-261">Get the service numbers that you need for the auto attendants and call queues that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="36826-262">這可能包括 [從另一個提供者轉移號碼](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或 [要求新的服務號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="36826-262">This might include [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](getting-service-phone-numbers.md).</span></span>

2. <span data-ttu-id="36826-263">取得您打算建立的每個資源帳戶的 [電話系統-虛擬使用者授權](teams-add-on-licensing/virtual-user.md) 。</span><span class="sxs-lookup"><span data-stu-id="36826-263">Get a [Phone System - Virtual User license](teams-add-on-licensing/virtual-user.md) for each resource account that you plan to create.</span></span> <span data-ttu-id="36826-264">這些授權是免費的，因此我們建議您先取得幾個額外的案例，以備日後決定變更您的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="36826-264">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.</span></span>

3. <span data-ttu-id="36826-265">針對您要建立的每個自動語音應答和通話佇列[建立資源帳戶](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="36826-265">[Create a resource account](manage-resource-accounts.md) for each auto attendant and call queue that you want to create.</span></span> <span data-ttu-id="36826-266">將每個帳戶指派給電話系統-虛擬使用者授權，並選擇服務號碼（選擇性）。</span><span class="sxs-lookup"><span data-stu-id="36826-266">Assign each account a Phone System - Virtual User license and, optionally, a service number.</span></span>

4. <span data-ttu-id="36826-267">在自動語音應答中，建立您想要單獨撥打通話路線的[假日](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="36826-267">[Create the holidays](set-up-holidays-in-teams.md) for which you want to have separate call routing in your auto attendants.</span></span>

5. <span data-ttu-id="36826-268">或者，如果您想要使用此功能協助來電轉接 [，請設定 [通話停](call-park-and-retrieve.md) 用] 和 [檢索]。</span><span class="sxs-lookup"><span data-stu-id="36826-268">Optionally, [set up call parking and retrieval](call-park-and-retrieve.md) if you want to use this feature to help with call transfers.</span></span>

6. <span data-ttu-id="36826-269">建立您想要用來包含通話佇列之通話代理程式的群組。</span><span class="sxs-lookup"><span data-stu-id="36826-269">Create the groups that you want to use to contain the call agents for the call queues.</span></span>

7. <span data-ttu-id="36826-270">如果您打算允許透過分機撥打，請確定您已將使用者的分機號碼新增至其 Azure Active Directory 設定檔。</span><span class="sxs-lookup"><span data-stu-id="36826-270">If you plan to allow dial by extension, ensure that you've added your users' extension number to their Azure Active Directory profile.</span></span>

<span data-ttu-id="36826-271">完成上述步驟之後，您就可以開始建立自動語音應答及呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-271">Once you've completed the steps above, you're ready to create your auto attendants and call queues.</span></span> <span data-ttu-id="36826-272">因為自動語音應答及呼叫佇列可以重新導向來電，所以請參閱您建立的工作流程圖表，以判斷應該首先建立哪個自動語音應答或呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="36826-272">Because auto attendants and call queues can redirect calls to each other, refer to the workflow diagram that you created to determine which auto attendant or call queue should be created first.</span></span> <span data-ttu-id="36826-273">在上圖中的範例中，您會在建立 Contoso 主自動語音應答前，建立 [銷售及支援電話] 佇列，因為主要自動語音應答必須將呼叫者指引至銷售和支援電話列隊。</span><span class="sxs-lookup"><span data-stu-id="36826-273">In the example in the diagram above, you would create the sales and support call queues before you create the Contoso main auto attendant because the main auto attendant needs to direct callers to the sales and support call queues.</span></span>

<span data-ttu-id="36826-274">如需如何建立自動語音應答及呼叫佇列的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="36826-274">See the following articles for information on how to create auto attendants and call queues:</span></span>

- [<span data-ttu-id="36826-275">設定自動語音應答</span><span class="sxs-lookup"><span data-stu-id="36826-275">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="36826-276">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="36826-276">Create a call queue</span></span>](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a><span data-ttu-id="36826-277">相關主題</span><span class="sxs-lookup"><span data-stu-id="36826-277">Related topics</span></span>

[<span data-ttu-id="36826-278">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="36826-278">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="36826-279">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="36826-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="36826-280">建立通話佇列-小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="36826-280">Create a call queue - small business tutorial</span></span>](business-voice/create-a-phone-system-call-queue-smb.md)

[<span data-ttu-id="36826-281">設定自動語音應答-小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="36826-281">Set up an auto attendant - small business tutorial</span></span>](business-voice/create-a-phone-system-auto-attendant-smb.md)
