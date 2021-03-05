---
title: 規劃 Teams 自動 Attendant 和通話佇列
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
description: 瞭解自動語音機和通話佇列，以及如何使用它們協助來電者在功能表系統中移動，以聯繫您組織的人或部門。
ms.openlocfilehash: 2944f7b4add49b136d56620f41a2a1afb1a30a92
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460723"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a><span data-ttu-id="59eee-103">規劃 Teams 自動 Attendant 和通話佇列</span><span class="sxs-lookup"><span data-stu-id="59eee-103">Plan for Teams auto attendants and call queues</span></span>

<span data-ttu-id="59eee-104">自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-104">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="59eee-105">功能表選項，例如「針對銷售，按 1。</span><span class="sxs-lookup"><span data-stu-id="59eee-105">Menu options, such as "For Sales, press 1.</span></span>  <span data-ttu-id="59eee-106">針對服務按 2"，針對自動語音機，讓組織提供一系列選項，引導來電者快速前往目的地，而不需要依賴人力運算子來處理來電。</span><span class="sxs-lookup"><span data-stu-id="59eee-106">For Services press 2", for an auto attendant let an organization provide a series of choices that guide callers to their destination quickly, without relying on a human operator to handle incoming calls.</span></span>

<span data-ttu-id="59eee-107">通話佇列正在等候來電者的區域。</span><span class="sxs-lookup"><span data-stu-id="59eee-107">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="59eee-108">如果來電者需要與具有特定專長的人聯繫 ，例如銷售或服務，而非特定人員，您可以使用通話佇列將來電者與可協助他們的代理人群組聯繫。</span><span class="sxs-lookup"><span data-stu-id="59eee-108">For situations where callers need to reach someone with a particular specialty - such as sales or service - rather than a specific person, you can use call queues to connect callers to the group of agents who can assist them.</span></span> <span data-ttu-id="59eee-109">來電者會保留，直到指派給該佇列的代理人可以進行通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-109">Callers are put on hold until an agent assigned to the queue is available to take their call.</span></span>

<span data-ttu-id="59eee-110">自動語音機和通話佇列可以一起使用，輕鬆地將來電者路由給貴組織的適當人員或部門。</span><span class="sxs-lookup"><span data-stu-id="59eee-110">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

## <a name="auto-attendants"></a><span data-ttu-id="59eee-111">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="59eee-111">Auto attendants</span></span>

<span data-ttu-id="59eee-112">自動語音機的主要用途是依據來電者對所提供的功能表選項的輸入，將來電者引導至適當的人員或部門。</span><span class="sxs-lookup"><span data-stu-id="59eee-112">The primary purpose of an auto attendant is to direct a caller to an appropriate person or department based on the caller's input to the provided menu options.</span></span> <span data-ttu-id="59eee-113">來電者可以被導向到貴組織內的特定人員、撥打等候與下一個可用代理人通話的佇列，或撥打語音信箱。</span><span class="sxs-lookup"><span data-stu-id="59eee-113">Callers can be directed to specific people within your organization, to call queues where they wait to talk to the next available agent, or to voicemail.</span></span> <span data-ttu-id="59eee-114">您可以針對上班時間、休假時間及假日指定不同的呼叫路由選項。</span><span class="sxs-lookup"><span data-stu-id="59eee-114">Different call routing options can be specified for business hours, off hours, and holidays.</span></span>

<span data-ttu-id="59eee-115">功能表提示可以使用文字到語音 (系統產生的提示) 上傳錄製的音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="59eee-115">Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading a recorded audio file.</span></span> <span data-ttu-id="59eee-116">語音辨識可接受免用手流覽的語音命令，但來電者也可使用電話鍵台流覽功能表。</span><span class="sxs-lookup"><span data-stu-id="59eee-116">Speech recognition accepts voice commands for hands-free navigation, but people calling in can also use the phone keypad to navigate menus.</span></span>

<span data-ttu-id="59eee-117">每個自動 Attendant 都有特定的語言和時區。</span><span class="sxs-lookup"><span data-stu-id="59eee-117">Each auto attendant has a specific language and time zone.</span></span> <span data-ttu-id="59eee-118">如果您以多種語言或世界多個地區進行商務，您可以建立許多不同的自動語音機，以容納來電者。</span><span class="sxs-lookup"><span data-stu-id="59eee-118">If you do business in multiple languages or multiple parts of the world, you can create as many different auto attendants as you need to accommodate your callers.</span></span>

<span data-ttu-id="59eee-119">您可以針對每個自動 attendant 設定運算子。</span><span class="sxs-lookup"><span data-stu-id="59eee-119">For each auto attendant, you can configure an operator.</span></span> <span data-ttu-id="59eee-120">雖然您可以將運算子電話設定為前往各種目的地，但運算子功能的設計目的是讓來電者與貴組織中可以協助的某個人通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-120">While you can configure operator calls to go to a variety of destinations, the operator feature is designed to allow callers to talk to a specific person in your organization who can help them.</span></span>

<span data-ttu-id="59eee-121">您可以根據名稱或分機號碼，將自動語音機進行配置以允許來電者搜尋貴組織的目錄。</span><span class="sxs-lookup"><span data-stu-id="59eee-121">Auto attendants can be configured to allow callers to search your organization's directory, either by name or by extension number.</span></span> <span data-ttu-id="59eee-122">在自動 attendant 中，您可以選擇要包含或排除的使用者群組，指定哪些人可以使用目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="59eee-122">Within an auto attendant, you can specify who is available for the directory search by choosing groups of users to include or exclude.</span></span> <span data-ttu-id="59eee-123"> (這稱為撥號 *範圍*.) </span><span class="sxs-lookup"><span data-stu-id="59eee-123">(This is known as *dial scope*.)</span></span>

<span data-ttu-id="59eee-124">來電者可以撥打自動語音機，方法可以是直接電話號碼 、已進行配置，或是重新導向另一個自動語音機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-124">Callers can reach an auto attendant either by direct phone number, if configured, or by being redirected from another auto attendant or a call queue.</span></span>

## <a name="call-queues"></a><span data-ttu-id="59eee-125">通話佇列</span><span class="sxs-lookup"><span data-stu-id="59eee-125">Call queues</span></span>

<span data-ttu-id="59eee-126">通話佇列與實體建築物中的等候室類似。</span><span class="sxs-lookup"><span data-stu-id="59eee-126">A call queue is analogous to a waiting room in a physical building.</span></span> <span data-ttu-id="59eee-127">來電者等候等候，而來電會路由至佇列中的代理程式。</span><span class="sxs-lookup"><span data-stu-id="59eee-127">Callers wait on hold while calls are routed to the agents in the queue.</span></span> <span data-ttu-id="59eee-128">通話佇列通常用於銷售和服務功能。</span><span class="sxs-lookup"><span data-stu-id="59eee-128">Call queues are commonly used for sales and service functions.</span></span> <span data-ttu-id="59eee-129">不過，通話佇列可用於通話數量超過您內部容量的任何情況，例如忙碌設施中的接聽者。</span><span class="sxs-lookup"><span data-stu-id="59eee-129">However, call queues can be used for any situation where the number of calls exceeds your internal capacity, such as a receptionist in a busy facility.</span></span>

<span data-ttu-id="59eee-130">當佇列中的來電者總數或等待時間超過您指定的限制時，通話佇列允許特定呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="59eee-130">Call queues allow for specific routing of calls in cases where the total number of callers in the queue or the wait time exceeds the limits that you specify.</span></span> <span data-ttu-id="59eee-131">通話可以路由至特定人員、語音信箱、其他通話佇列或自動語音留言。</span><span class="sxs-lookup"><span data-stu-id="59eee-131">Calls can be routed to specific people, voicemail, other call queues, or auto attendants.</span></span>

<span data-ttu-id="59eee-132">與自動 Attendant 一樣，通話佇列每一個都有語言設定。</span><span class="sxs-lookup"><span data-stu-id="59eee-132">Like auto attendants, call queues each have a language setting.</span></span> <span data-ttu-id="59eee-133">如果您以多種語言進行商務，可以使用不同的通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-133">You can use different call queues if you do business in multiple languages.</span></span> <span data-ttu-id="59eee-134">代理程式可以是多個佇列的成員 ，如果他們是多語言的。</span><span class="sxs-lookup"><span data-stu-id="59eee-134">Agents can be members of more than one queue if they're multi-lingual.</span></span>

<span data-ttu-id="59eee-135">針對每個通話佇列，您可以指定佇列中的代理人是否可以退出宣告接聽電話，以及通話是否根據 Teams 中的目前狀態指示路由給他們。</span><span class="sxs-lookup"><span data-stu-id="59eee-135">For each call queue, you can specify if agents in the queue can opt out of taking calls and if calls should be routed to them based on their presence indication in Teams.</span></span>

<span data-ttu-id="59eee-136">您可以將電話號碼指派給通話佇列，但通話佇列不會針對休假和假日提供個別的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="59eee-136">You can assign a phone number to a call queue, however call queues do not provide separate call routing for off hours and holidays.</span></span> <span data-ttu-id="59eee-137">除非您的通話佇列是每天 24 小時 7 天，否則建議您將電話號碼指派給自動電話機，該電話機在上班時間內會重新導向到通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-137">Unless your call queue is staffed 24/7, we recommend assigning the phone number to an auto attendant that redirects to the call queue during business hours.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59eee-138">必要條件</span><span class="sxs-lookup"><span data-stu-id="59eee-138">Prerequisites</span></span>

<span data-ttu-id="59eee-139">若要設定自動 Attendant 和通話佇列，您需要下列資源：</span><span class="sxs-lookup"><span data-stu-id="59eee-139">To configure auto attendants and call queues, you need the following resources:</span></span>

- <span data-ttu-id="59eee-140">每個自動 Attendant 和每個通話佇列的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="59eee-140">A resource account for each auto attendant and each call queue</span></span>
- <span data-ttu-id="59eee-141">免費的電話系統 - 每個資源帳戶的虛擬使用者授權</span><span class="sxs-lookup"><span data-stu-id="59eee-141">A free Phone System - Virtual User license for each resource account</span></span>
- <span data-ttu-id="59eee-142">針對您想要直接 [撥號](getting-service-phone-numbers.md)的每個資源帳戶，至少一個 Microsoft 服務號碼、直接路由號碼或混合式號碼</span><span class="sxs-lookup"><span data-stu-id="59eee-142">At least one [Microsoft service number](getting-service-phone-numbers.md), direct routing number, or a hybrid number for each resource account that you want to be directly dialable</span></span>
 - <span data-ttu-id="59eee-143">服務號碼可能是付費或免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="59eee-143">The service number may be a toll or toll-free number</span></span>

<span data-ttu-id="59eee-144">從通話佇列接聽來電的代理程式必須是已啟用企業語音的線上或內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="59eee-144">Agents who receive calls from the call queues must be Enterprise Voice enabled online or on-premise users.</span></span> <span data-ttu-id="59eee-145">此外，如果通話佇列使用直接路由號碼，需要電話會議或轉接電話的代理人也需要：</span><span class="sxs-lookup"><span data-stu-id="59eee-145">In addition, if the call queues are using Direct Routing numbers, agents who need to conference or transfer calls also require:</span></span>

- <span data-ttu-id="59eee-146">如果通話佇列使用轉接模式，則指派的線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="59eee-146">An online voice routing policy assigned if the call queue uses transfer mode</span></span>
- <span data-ttu-id="59eee-147">如果通話佇列使用會議模式，則指派的音訊會議授權或線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="59eee-147">An Audio Conferencing license or online voice routing policy assigned if the call queue uses conference mode</span></span>

<span data-ttu-id="59eee-148">如果您的代理人使用 Microsoft Teams 應用程式進行通話佇列通話，他們必須在 TeamsOnly 模式中。</span><span class="sxs-lookup"><span data-stu-id="59eee-148">If your agents are using the Microsoft Teams app for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="59eee-149">將電話轉接到外部電話號碼時，執行轉接的資源帳戶 (也就是說，與自動電話機或通話佇列相關聯的帳戶) 必須擁有 Microsoft 365 電話系統虛擬使用者授權，並指派下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="59eee-149">When transferring calls to an external phone number, the resource account performing the transfer (that is, the one associated with the auto attendant or call queue) must have a Microsoft 365 Phone System Virtual User license and one of the following assigned:</span></span>

- <span data-ttu-id="59eee-150">通話 [方案](calling-plans-for-office-365.md) 授權</span><span class="sxs-lookup"><span data-stu-id="59eee-150">A [Calling Plan](calling-plans-for-office-365.md) license</span></span>
- <span data-ttu-id="59eee-151">線上 [語音路由策略](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="59eee-151">An [online voice routing policy](manage-voice-routing-policies.md)</span></span>

> [!NOTE]
> <span data-ttu-id="59eee-152">Microsoft Teams 使用者和通話代理程式僅支援自動電話機和通話佇列的直接路由服務號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-152">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and call agents only.</span></span><br>
> <span data-ttu-id="59eee-153">不支援在通話方案樹線與直接路由中繼線之間傳輸。</span><span class="sxs-lookup"><span data-stu-id="59eee-153">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span><br>
> <span data-ttu-id="59eee-154">在混合式情況下，必須在內部部署建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="59eee-154">In a Hybrid scenario, the resource account must be created on-premises.</span></span> <span data-ttu-id="59eee-155">詳細資訊請參閱規劃 [雲端通話佇列](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="59eee-155">For more information, see [Plan Cloud call queues](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-queue).</span></span>

## <a name="business-decisions"></a><span data-ttu-id="59eee-156">商務決策</span><span class="sxs-lookup"><span data-stu-id="59eee-156">Business decisions</span></span>

<span data-ttu-id="59eee-157">在設定自動電話機和通話佇列之前，應該先決定如何在企業使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="59eee-157">Before you set up your auto attendants and call queues, there are some decisions that you should make about how to use these features in your business.</span></span> <span data-ttu-id="59eee-158">這些決定會決定您設定自動電話機和通話佇列時所選取的設定。</span><span class="sxs-lookup"><span data-stu-id="59eee-158">These decisions will determine the settings that you choose when you configure your auto attendants and call queues.</span></span>

<span data-ttu-id="59eee-159">請記錄您對於這些問題的回答，並提供執行這項配置的系統管理員資訊。</span><span class="sxs-lookup"><span data-stu-id="59eee-159">Document your answers to these questions and provide the information to the administrator doing the configuration.</span></span>

- <span data-ttu-id="59eee-160">您需要哪些語言？</span><span class="sxs-lookup"><span data-stu-id="59eee-160">What languages do you need?</span></span> <span data-ttu-id="59eee-161">這些語言需要在哪裡 ？哪個部門或群組？</span><span class="sxs-lookup"><span data-stu-id="59eee-161">Where are these languages needed - which department or group?</span></span>
- <span data-ttu-id="59eee-162">您想要允許來電者的語音輸入或僅允許撥號輸入？</span><span class="sxs-lookup"><span data-stu-id="59eee-162">Do you want to allow voice inputs from callers or only dialing inputs?</span></span>
- <span data-ttu-id="59eee-163">您是否需要針對休假時間或假日分別進行通話路由？</span><span class="sxs-lookup"><span data-stu-id="59eee-163">Do you need separate call routing for off hours or holidays?</span></span> <span data-ttu-id="59eee-164">小時和假日是什麼？</span><span class="sxs-lookup"><span data-stu-id="59eee-164">What are the hours and holidays?</span></span>
- <span data-ttu-id="59eee-165">您想要允許通話佇列中的代理人退出宣告接聽電話嗎？</span><span class="sxs-lookup"><span data-stu-id="59eee-165">Do you want to allow agents in a call queue to opt out of taking calls?</span></span>
- <span data-ttu-id="59eee-166">您希望通話佇列的代理人或接線員撥出時，擁有特定的本機號碼？</span><span class="sxs-lookup"><span data-stu-id="59eee-166">Do you want agents in your call queues or your operator to have a specific caller ID if they dial out?</span></span>
- <span data-ttu-id="59eee-167">您想要在貴組織中啟用通話停 [駐和](call-park-and-retrieve.md) 取回功能，以協助人員或部門之間的呼叫交會嗎？</span><span class="sxs-lookup"><span data-stu-id="59eee-167">Do you want to enable [call parking and retrieval](call-park-and-retrieve.md) in your organization to assist in call handoffs between people or departments?</span></span>
- <span data-ttu-id="59eee-168">針對語音提示，您想要錄製您自己的語音或使用系統產生的語音嗎？</span><span class="sxs-lookup"><span data-stu-id="59eee-168">For the voice prompts, do you want to record your own or use the system-generated voice?</span></span> <span data-ttu-id="59eee-169"> (系統產生的語音很容易更新。) </span><span class="sxs-lookup"><span data-stu-id="59eee-169">(The system-generated voice is easy to update.)</span></span>

## <a name="technical-decisions"></a><span data-ttu-id="59eee-170">技術決策</span><span class="sxs-lookup"><span data-stu-id="59eee-170">Technical decisions</span></span>

<span data-ttu-id="59eee-171">使用自動語音回應和通話佇列將來電者與貴組織人員聯繫時，在開始進行組配置之前，需要做出一些技術決策。</span><span class="sxs-lookup"><span data-stu-id="59eee-171">When using auto attendants and call queues to connect callers to people in your organization, there are some technical decisions to make before you start the configuration.</span></span>

<span data-ttu-id="59eee-172">您可以用下列方式將代理程式新增到呼叫佇列：</span><span class="sxs-lookup"><span data-stu-id="59eee-172">Agents can be added to call queues in the following ways:</span></span>

- <span data-ttu-id="59eee-173">個別使用者</span><span class="sxs-lookup"><span data-stu-id="59eee-173">Individual users</span></span>
- <span data-ttu-id="59eee-174">通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="59eee-174">Distribution lists</span></span>
- <span data-ttu-id="59eee-175">安全性群組，包括已啟用郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="59eee-175">Security groups, including mail-enabled security groups</span></span>
- <span data-ttu-id="59eee-176">Microsoft 365 群組或 Teams</span><span class="sxs-lookup"><span data-stu-id="59eee-176">Microsoft 365 Groups or Teams</span></span>

<span data-ttu-id="59eee-177">如果需要，您可以針對每個佇列使用這些選項的組合。</span><span class="sxs-lookup"><span data-stu-id="59eee-177">You can use a combination of these options for each queue if needed.</span></span> <span data-ttu-id="59eee-178">具有電子郵件地址的群組可用於語音信箱。</span><span class="sxs-lookup"><span data-stu-id="59eee-178">Groups that have an email address can be used for voicemail.</span></span> <span data-ttu-id="59eee-179">使用 Teams 有許多優點，包括共用檔案儲存空間和代理程式之間的聊天、可接收語音信箱的一般信箱，以及可包含與商務應用程式或 Power Apps 整合的可擴展平臺。</span><span class="sxs-lookup"><span data-stu-id="59eee-179">Using Teams offers a number of advantages, including shared file storage and chat between agents, a common mailbox where voicemails can be received, and an extensible platform that can include integration with your line of business applications or Power Apps.</span></span>

<span data-ttu-id="59eee-180">建議您在開始進行組組之前，選擇將呼叫代理程式新排入佇列的策略。</span><span class="sxs-lookup"><span data-stu-id="59eee-180">We recommend choosing a strategy for adding call agents to queues before you start your configuration.</span></span>

<span data-ttu-id="59eee-181">如果您有現有的自動電話機和通話佇列基礎結構，而且要移轉至 Teams，您需要一個計畫，將現有的電話號碼轉移到新的自動電話機和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-181">If you have an existing auto attendant and call queue infrastructure and you're migrating to Teams, you'll need a plan to transfer your existing phone numbers to the new auto attendants and call queues.</span></span> <span data-ttu-id="59eee-182">您可能需要建立移轉訂單 [，](phone-number-calling-plans/port-order-overview.md) 才能將號碼從其他提供者移轉。</span><span class="sxs-lookup"><span data-stu-id="59eee-182">You might need to create a [port order](phone-number-calling-plans/port-order-overview.md) to move your numbers from another providers.</span></span> <span data-ttu-id="59eee-183">建議您先暫時取得一或多個新電話號碼，並測試自動電話機和通話佇列流量，再將它們切換至您目前使用中的號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-183">We recommend that you temporarily acquire one or more new phone numbers and test your auto attendant and call queue flows before switching them over the numbers you currently have in service.</span></span>

<span data-ttu-id="59eee-184">*會議模式* 是通話佇列的選項，可大幅縮短將 Teams VOIP 通話和 PSTN 通話連接到代理人所花的時間。</span><span class="sxs-lookup"><span data-stu-id="59eee-184">*Conference mode* is an option in call queues that significantly reduces the amount of time it takes to connect Teams VOIP calls and PSTN calls to an agent.</span></span> <span data-ttu-id="59eee-185">若要讓會議模式運作，通話佇列中的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="59eee-185">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

- <span data-ttu-id="59eee-186">最新版本的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="59eee-186">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="59eee-187">Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="59eee-187">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="59eee-188">將代理程式 Teams 帳戶設定為 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="59eee-188">Set Agents' Teams accounts to Teams-only mode.</span></span> <span data-ttu-id="59eee-189">不符合需求的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="59eee-189">Agents who don't meet the requirements aren't included in the call routing list.</span></span>

<span data-ttu-id="59eee-190">如果您的代理人都使用相容的用戶端，建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="59eee-190">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

## <a name="plan-your-call-routing-flow"></a><span data-ttu-id="59eee-191">規劃您的通話路由流程</span><span class="sxs-lookup"><span data-stu-id="59eee-191">Plan your call routing flow</span></span>

<span data-ttu-id="59eee-192">在規劃程式過程中，建議您在圖表中針對貴組織的通話路由進行規劃。</span><span class="sxs-lookup"><span data-stu-id="59eee-192">As part of the planning process, we recommend that you work out the call routing for your organization in a diagram.</span></span> <span data-ttu-id="59eee-193">此圖表可協助決定來電至貴組織之人員最有效率的路由。</span><span class="sxs-lookup"><span data-stu-id="59eee-193">The diagram helps determine the most efficient routing for people calling in to your organization.</span></span> <span data-ttu-id="59eee-194">您也可以使用圖表來判斷您需要建立自動 Attendant 和通話佇列，以及服務號碼、授權和資源帳戶等相關需求。</span><span class="sxs-lookup"><span data-stu-id="59eee-194">You can also use the diagram to determine the auto attendants and call queues that you need to create, along with related requirements such as service numbers, licenses, and resource accounts.</span></span>

<span data-ttu-id="59eee-195">讓我們看看自動 Attendant 和通話佇列如何路由通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-195">Let's look at how auto attendants and call queues route calls.</span></span>

<span data-ttu-id="59eee-196">自動電話機會以下列其中一種方式路由所有通話：</span><span class="sxs-lookup"><span data-stu-id="59eee-196">Auto attendants route all calls in one of the following ways:</span></span>

- <span data-ttu-id="59eee-197">**立即重新** 導向 - 通話可以重新導向到下列其中一個 (通話路由目的地) 接聽或初始問候之後立即列出。</span><span class="sxs-lookup"><span data-stu-id="59eee-197">**Redirect immediately** - calls can be redirected to one of the call routing destinations (listed below) immediately upon answering or after an initial greeting.</span></span>
- <span data-ttu-id="59eee-198">**根據撥號選項** 重新導向 - 來電者可以在電話鍵台 0-9 上指派給號碼的選項之間選擇。</span><span class="sxs-lookup"><span data-stu-id="59eee-198">**Redirect based on dial options** - callers can be directed to choose between options that are assigned to the numbers on their telephone keypad, 0-9.</span></span> <span data-ttu-id="59eee-199">每個撥號鍵都可以指派一個呼叫路由目的地。</span><span class="sxs-lookup"><span data-stu-id="59eee-199">Each dial key can be assigned a call routing destinations.</span></span>
- <span data-ttu-id="59eee-200">**按名稱或** 分機撥號 - 來電者可以撥打他們嘗試在組織目錄中聯繫的人的分機號碼，或拼字檢查人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="59eee-200">**Dial people by name or extension** - callers can be directed to dial the extension number of the person they're trying to reach in your organization's directory, or by spelling the person's name.</span></span>
- <span data-ttu-id="59eee-201">**中斷** 連接 - 自動 ATTENDANT 可能會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-201">**Disconnect** - an auto attendant can hang up the call.</span></span>

> [!NOTE]
> <span data-ttu-id="59eee-202">單一自動 attendant 只能支援單一「撥號方式」方法。</span><span class="sxs-lookup"><span data-stu-id="59eee-202">A single Auto attendant can only support a single "dial by" method.</span></span>  <span data-ttu-id="59eee-203">若要允許來電者按名稱和號碼撥號，您必須建立自動語音機，該語音機有一個選項可按名稱撥號，另一個則提供分機號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-203">To allow callers to dial by name and by number, you will need to create an auto attendant that has an option for dial by name and the another for dial by extension.</span></span>  <span data-ttu-id="59eee-204">這些選項會路由到針對這些「撥號方式」案例所配置的個別自動 attendant。</span><span class="sxs-lookup"><span data-stu-id="59eee-204">Each of these options will route to separate auto attendants configured for these "dial by" scenarios.</span></span>

<span data-ttu-id="59eee-205">當自動電話機或通話佇列重新導向通話時，您可以從下列通話路由目的地中選擇：</span><span class="sxs-lookup"><span data-stu-id="59eee-205">When calls are redirected by an auto attendant or call queue, you can choose from the following call routing destinations:</span></span>

- <span data-ttu-id="59eee-206">**組織中可以接聽** 語音通話的人。</span><span class="sxs-lookup"><span data-stu-id="59eee-206">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="59eee-207">這可以是線上使用者，或使用商務用 Skype Server 託管于內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="59eee-207">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="59eee-208">**語音應用程式** - 另一個自動語音留言機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-208">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="59eee-209">選擇與目的地相關聯的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="59eee-209">Choose the resource account associated with the destination.</span></span>
- <span data-ttu-id="59eee-210">**外部電話號碼** - 任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-210">**External phone number** - any phone number.</span></span> <span data-ttu-id="59eee-211"> (外部[移轉技術詳細資料) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="59eee-211">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="59eee-212">**語音** 信箱 - 與您指定的 Microsoft 365 群組相關聯的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="59eee-212">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="59eee-213">**運算子** (自動) -為自動 attendant 定義的運算子。</span><span class="sxs-lookup"><span data-stu-id="59eee-213">**Operator** (auto attendant only) - the operator defined for the auto attendant.</span></span> <span data-ttu-id="59eee-214">定義運算子是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="59eee-214">Defining an operator is optional.</span></span> <span data-ttu-id="59eee-215">運算子可以是此清單的其他目的地。</span><span class="sxs-lookup"><span data-stu-id="59eee-215">An operator can be any of the other destinations in this list.</span></span>

<span data-ttu-id="59eee-216">自動電話機針對在上班時間外和假日時接到的來電，提供個別的通話路由選項。</span><span class="sxs-lookup"><span data-stu-id="59eee-216">Auto attendants offer separate call routing options for calls received outside of business hours and on holidays.</span></span> <span data-ttu-id="59eee-217">上班時間通話路由允許上述所有選項，而假日通話路由僅允許重新導向或中斷連接通話，但無撥號鍵選項。</span><span class="sxs-lookup"><span data-stu-id="59eee-217">After-hours call routing allows all the options listed above, while holiday call routing allows only redirecting or disconnecting a call, but no dial key options.</span></span>

<span data-ttu-id="59eee-218">通話佇列會保留來電者，直到指派給該佇列的代理人可以進行通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-218">Call queues place the caller on hold until an agent assigned to the queue is available to take their call.</span></span> <span data-ttu-id="59eee-219">有兩種情況可能會將來電者從佇列外導向：</span><span class="sxs-lookup"><span data-stu-id="59eee-219">There are two situations where a caller might be directed out of the queue:</span></span>

- <span data-ttu-id="59eee-220">**通話溢位** - 如果佇列中的通話數超過您設定的限制，則新的來電者會重新導向到佇列外。</span><span class="sxs-lookup"><span data-stu-id="59eee-220">**Call overflow** - if the number of calls in the queue exceeds the limit that you set, then new callers are redirected out of the queue.</span></span>
- <span data-ttu-id="59eee-221">**通話超時** - 如果來電者在佇列中的時間超過設定超時設定的時間，來電者會被重新導向到佇列外。</span><span class="sxs-lookup"><span data-stu-id="59eee-221">**Call timeout** - if a caller has been in the queue longer than the configured timeout setting, they're redirected out of the queue.</span></span>

<span data-ttu-id="59eee-222">重新導向到佇列以外的通話可以傳送至上述所列的任何通話路由目的地，但運算子除外。</span><span class="sxs-lookup"><span data-stu-id="59eee-222">Calls redirected out of a queue can be sent to any of the call routing destinations listed above except for an operator.</span></span> <span data-ttu-id="59eee-223"> (通話佇列沒有運算子，但您可以將來電者重新導向至與自動語音機.) </span><span class="sxs-lookup"><span data-stu-id="59eee-223">(Call queues don't have operators, but you can redirect callers to the same destination as an operator that you've configured for an auto attendant.)</span></span>

<span data-ttu-id="59eee-224">以下範例顯示使用自動電話機和通話佇列進行通話路由的範例。</span><span class="sxs-lookup"><span data-stu-id="59eee-224">The example below shows an example of call routing using auto attendants and call queues.</span></span>

![使用自動電話機和通話佇列進行通話路由的圖表](media/attendant-and-queue-call-routing.png)

<span data-ttu-id="59eee-226">在上例中：</span><span class="sxs-lookup"><span data-stu-id="59eee-226">In the example above:</span></span>

- <span data-ttu-id="59eee-227">0 (0) 會將來電者重新導向至運算子。</span><span class="sxs-lookup"><span data-stu-id="59eee-227">The zero (0) key redirects callers to an operator.</span></span> <span data-ttu-id="59eee-228">該自動 Attendant 的運算子已配置為組織中 **的人**。</span><span class="sxs-lookup"><span data-stu-id="59eee-228">The operator for that auto attendant has been configured as a **Person in the organization**.</span></span>
- <span data-ttu-id="59eee-229">一個 (1) 鍵會將來電者重新導向到銷售通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-229">The one (1) key redirects callers to the sales call queue.</span></span> <span data-ttu-id="59eee-230">此通話佇列會連接至包含指派給該佇列的銷售團隊的團隊。</span><span class="sxs-lookup"><span data-stu-id="59eee-230">This call queue is connected to a team that contains the sales team assigned to the queue.</span></span>
- <span data-ttu-id="59eee-231">兩個 (2) 鍵會將來電者重新導向至支援通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-231">The two (2) key redirects callers to the support call queue.</span></span> <span data-ttu-id="59eee-232">此通話佇列會連接至包含指派給該團隊的支援小組的團隊。</span><span class="sxs-lookup"><span data-stu-id="59eee-232">This call queue is connected to a team that contains the support team assigned to the team.</span></span>
- <span data-ttu-id="59eee-233">支援通話佇列會透過中間的自動助理提供直接電話號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-233">The support call queue has a direct phone number via an intervening auto attendant.</span></span> <span data-ttu-id="59eee-234">讓自動回應接聽支援行，可讓上班時間和假日通話路由分開。</span><span class="sxs-lookup"><span data-stu-id="59eee-234">Having an auto attendant answer the support line allows for separate off hours and holiday call routing.</span></span>
- <span data-ttu-id="59eee-235">三個 (3) 鍵會將使用者重新導向至公司目錄的另一個自動 attendant。</span><span class="sxs-lookup"><span data-stu-id="59eee-235">The three (3) key redirects users to another auto attendant for the company directory.</span></span> <span data-ttu-id="59eee-236">公司目錄自動語音回應可讓來電者撥打組織人員的名稱或分機，來撥打電話給組織人員。</span><span class="sxs-lookup"><span data-stu-id="59eee-236">The company directory auto attendant allows callers to call individuals in the organization by dialing their name or extension.</span></span>

<span data-ttu-id="59eee-237">建議您建立一或多個類似上述圖表的圖表，以繪製您的通話路由。</span><span class="sxs-lookup"><span data-stu-id="59eee-237">We recommend that you create one or more diagrams similar to the one above to map out your call routing.</span></span> <span data-ttu-id="59eee-238">請務必在圖表或隨附檔中包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="59eee-238">Be sure to include the following in your diagram or accompanying documentation:</span></span>

- <span data-ttu-id="59eee-239">哪些自動電話機會透過電話號碼直接存取？</span><span class="sxs-lookup"><span data-stu-id="59eee-239">Which auto attendants will have direct access via phone numbers?</span></span>
- <span data-ttu-id="59eee-240">每個自動 Attendant 的休假和假日路由需求是什麼？</span><span class="sxs-lookup"><span data-stu-id="59eee-240">What are the off-hours and holiday routing requirements for each auto attendants?</span></span>
- <span data-ttu-id="59eee-241">每個通話佇列的成員資格。</span><span class="sxs-lookup"><span data-stu-id="59eee-241">The membership for each call queue.</span></span> <span data-ttu-id="59eee-242"> (您可以個別新增使用者，或將佇列與不同類型的群組進行地圖。</span><span class="sxs-lookup"><span data-stu-id="59eee-242">(You can add users individually or map the queue to different kinds of groups.</span></span> <span data-ttu-id="59eee-243">將佇列與團隊進行比對，可提供最多用的體驗。) </span><span class="sxs-lookup"><span data-stu-id="59eee-243">Mapping a queue to a team provides the most versatile experience.)</span></span>

<span data-ttu-id="59eee-244">以下是一些通話路由最佳做法：</span><span class="sxs-lookup"><span data-stu-id="59eee-244">Here are some call routing best practices:</span></span>

- <span data-ttu-id="59eee-245">查看您現有的通話系統，並分析來電類型和頻率。</span><span class="sxs-lookup"><span data-stu-id="59eee-245">Look at your existing calling system and analyze the types and frequency of incoming calls.</span></span> <span data-ttu-id="59eee-246">使用這項資訊來協助通知您的自動 Attendant 和通話佇列結構。</span><span class="sxs-lookup"><span data-stu-id="59eee-246">Use this information to help inform your auto attendant and call queue structure.</span></span>
- <span data-ttu-id="59eee-247">將最常見的選項最早放在功能表中，以儘快路由通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-247">Put the most common options earliest in the menu to route calls as quickly as possible.</span></span>
- <span data-ttu-id="59eee-248">除非佇列是 24 小時無間，否則請避免將服務號碼直接連接到通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-248">Avoid connecting service numbers directly to call queues unless the queues are available 24/7.</span></span> <span data-ttu-id="59eee-249">通話佇列不允許在休假時段或假日期間個別處理通話。</span><span class="sxs-lookup"><span data-stu-id="59eee-249">Call queues don't allow for separate call handling for off hours or holidays.</span></span> <span data-ttu-id="59eee-250">如果您想要有一個具有直接號碼的佇列，請指派號碼給自動 Attendant，自動在上班時間重新導向至該佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-250">If you want to have a queue with a direct number, assign the number to an auto attendant that automatically redirects to the queue during business hours.</span></span>
- <span data-ttu-id="59eee-251">如果您接到許多要求公司基本資訊的電話 ，例如上班時間、位置或網址，請考慮建立自動回應，以錄製的郵件回答這些問題。</span><span class="sxs-lookup"><span data-stu-id="59eee-251">If you receive numerous calls requesting basic information about your company, such as business hours, location, or web site address, consider creating an auto attendant to answer these questions with recorded messages.</span></span>
- <span data-ttu-id="59eee-252">將功能表項目清單保持在五個或五個以下。</span><span class="sxs-lookup"><span data-stu-id="59eee-252">Keep the list of menu items to five or fewer.</span></span> <span data-ttu-id="59eee-253">來電者可能難以記住五種以上選項。</span><span class="sxs-lookup"><span data-stu-id="59eee-253">Callers can have trouble remembering more than five options.</span></span> <span data-ttu-id="59eee-254">如果需要更多選項來正確路由通話，請使用巢式自動助理員。</span><span class="sxs-lookup"><span data-stu-id="59eee-254">Use nested auto attendants if more options are needed to properly route a call.</span></span>
- <span data-ttu-id="59eee-255">先描述服務，然後按 (選項，例如：針對銷售人員按 1) ，而不是以其他方式按 (。</span><span class="sxs-lookup"><span data-stu-id="59eee-255">Describe the service first, followed by the option to press (eg: For Sales press 1) rather than the other way around (eg.</span></span> <span data-ttu-id="59eee-256">按 1 表示銷售) 。</span><span class="sxs-lookup"><span data-stu-id="59eee-256">Press 1 for Sales).</span></span>
- <span data-ttu-id="59eee-257">來電者會瞭解的使用者術語，而不是您內部可能使用哪些術語。</span><span class="sxs-lookup"><span data-stu-id="59eee-257">User terminology your callers will understand rather than what you may use internally.</span></span>
- <span data-ttu-id="59eee-258">避免經常更新通話路由。</span><span class="sxs-lookup"><span data-stu-id="59eee-258">Avoid frequent updates to call routing.</span></span> <span data-ttu-id="59eee-259">如果您日後變更自動語音機的功能表選項，在前 30 天內，在語音提示中呼叫自動語音機。</span><span class="sxs-lookup"><span data-stu-id="59eee-259">If you change your menu options for an auto attendant in the future, call that out in the voice prompts for the first 30 days.</span></span>

## <a name="getting-started"></a><span data-ttu-id="59eee-260">快速入門</span><span class="sxs-lookup"><span data-stu-id="59eee-260">Getting started</span></span>

<span data-ttu-id="59eee-261">完成本文中的規劃工作後，請遵循下列步驟來設定自動 Attendant 和通話佇列：</span><span class="sxs-lookup"><span data-stu-id="59eee-261">Once you've completed the planning tasks in this article, follow these steps to get your auto attendants and call queues set up:</span></span>

1. <span data-ttu-id="59eee-262">取得自動電話機和通話佇列所需的服務號碼，以從組織外部直接撥號以易於取得。</span><span class="sxs-lookup"><span data-stu-id="59eee-262">Get the service numbers that you need for the auto attendants and call queues that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="59eee-263">這可能包括 [從另一個提供者移](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 轉號碼， [或要求新的服務號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="59eee-263">This might include [transferring numbers from another provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](getting-service-phone-numbers.md).</span></span>

2. <span data-ttu-id="59eee-264">取得 [電話系統 - 您](teams-add-on-licensing/virtual-user.md) 計畫建立的每個資源帳戶的虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="59eee-264">Get a [Phone System - Virtual User license](teams-add-on-licensing/virtual-user.md) for each resource account that you plan to create.</span></span> <span data-ttu-id="59eee-265">這些授權是免費的，因此我們建議您在日後決定變更資源帳戶時多取得一些授權。</span><span class="sxs-lookup"><span data-stu-id="59eee-265">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your resource accounts in the future.</span></span>

3. <span data-ttu-id="59eee-266">[針對您想要建立的每個](manage-resource-accounts.md) 自動 attendant 和通話佇列，建立資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="59eee-266">[Create a resource account](manage-resource-accounts.md) for each auto attendant and call queue that you want to create.</span></span> <span data-ttu-id="59eee-267">為每個帳戶指派電話系統 - 虛擬使用者授權，也可以指派服務號碼。</span><span class="sxs-lookup"><span data-stu-id="59eee-267">Assign each account a Phone System - Virtual User license and, optionally, a service number.</span></span>

4. <span data-ttu-id="59eee-268">[建立您希望](set-up-holidays-in-teams.md) 在自動電話機中分別進行通話路由的假日。</span><span class="sxs-lookup"><span data-stu-id="59eee-268">[Create the holidays](set-up-holidays-in-teams.md) for which you want to have separate call routing in your auto attendants.</span></span>

5. <span data-ttu-id="59eee-269">如果您想要使用 [此功能來](call-park-and-retrieve.md) 協助來電轉接，也可以設定通話停駐和取回。</span><span class="sxs-lookup"><span data-stu-id="59eee-269">Optionally, [set up call parking and retrieval](call-park-and-retrieve.md) if you want to use this feature to help with call transfers.</span></span>

6. <span data-ttu-id="59eee-270">建立您想要用於包含通話佇列通話代理程式之群組。</span><span class="sxs-lookup"><span data-stu-id="59eee-270">Create the groups that you want to use to contain the call agents for the call queues.</span></span>

7. <span data-ttu-id="59eee-271">如果您打算允許以分機號碼撥號，請確保您已新增使用者的分機號碼至他們的 Azure Active Directory 設定檔。</span><span class="sxs-lookup"><span data-stu-id="59eee-271">If you plan to allow dial by extension, ensure that you've added your users' extension number to their Azure Active Directory profile.</span></span>

<span data-ttu-id="59eee-272">完成上述步驟後，就可以建立自動電話機和通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-272">Once you've completed the steps above, you're ready to create your auto attendants and call queues.</span></span> <span data-ttu-id="59eee-273">由於自動電話機和通話佇列可以彼此重新導向通話，因此請參閱您建立工作流程圖表，以決定應該先建立哪一個自動電話機或通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-273">Because auto attendants and call queues can redirect calls to each other, refer to the workflow diagram that you created to determine which auto attendant or call queue should be created first.</span></span> <span data-ttu-id="59eee-274">在上圖中的範例中，您可以在建立 Contoso 主自動語音機之前，先建立銷售及支援通話佇列，因為主自動語音機需要將來電者引導至銷售和支援通話佇列。</span><span class="sxs-lookup"><span data-stu-id="59eee-274">In the example in the diagram above, you would create the sales and support call queues before you create the Contoso main auto attendant because the main auto attendant needs to direct callers to the sales and support call queues.</span></span>

<span data-ttu-id="59eee-275">請參閱下列文章，以瞭解如何建立自動 Attendant 和通話佇列：</span><span class="sxs-lookup"><span data-stu-id="59eee-275">See the following articles for information on how to create auto attendants and call queues:</span></span>

- [<span data-ttu-id="59eee-276">設定自動 attendant</span><span class="sxs-lookup"><span data-stu-id="59eee-276">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="59eee-277">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="59eee-277">Create a call queue</span></span>](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a><span data-ttu-id="59eee-278">相關主題</span><span class="sxs-lookup"><span data-stu-id="59eee-278">Related topics</span></span>

[<span data-ttu-id="59eee-279">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="59eee-279">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="59eee-280">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="59eee-280">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="59eee-281">建立通話佇列 - 小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="59eee-281">Create a call queue - small business tutorial</span></span>](business-voice/create-a-phone-system-call-queue-smb.md)

[<span data-ttu-id="59eee-282">設定自動 Attendant - 小型企業教學課程</span><span class="sxs-lookup"><span data-stu-id="59eee-282">Set up an auto attendant - small business tutorial</span></span>](business-voice/create-a-phone-system-auto-attendant-smb.md)
