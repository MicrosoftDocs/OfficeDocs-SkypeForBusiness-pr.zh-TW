---
title: 在 Microsoft Teams 中建立通話佇列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 瞭解如何使用 Microsoft Teams 為通話佇列設定電話系統，提供問候語、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919023"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="bf22a-103">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="bf22a-103">Create a call queue</span></span>

<span data-ttu-id="bf22a-104">通話佇列提供將來電者路由給組織中可協助解決特定問題之人員的方法。</span><span class="sxs-lookup"><span data-stu-id="bf22a-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="bf22a-105">通話會一次分配一個給佇列 (代理程式 *人員) 。*</span><span class="sxs-lookup"><span data-stu-id="bf22a-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="bf22a-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="bf22a-106">Call queues provide:</span></span>

- <span data-ttu-id="bf22a-107">問候語訊息。</span><span class="sxs-lookup"><span data-stu-id="bf22a-107">A greeting message.</span></span>

- <span data-ttu-id="bf22a-108">當人員正在等候佇列時播放音樂。</span><span class="sxs-lookup"><span data-stu-id="bf22a-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="bf22a-109">呼叫路由 - *在 First In， First Out (* FIFO) - 到代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="bf22a-110">佇列溢出和超時的處理選項。</span><span class="sxs-lookup"><span data-stu-id="bf22a-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="bf22a-111">按照本文中的程式操作之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動撥打和通話[](plan-auto-attendant-call-queue.md#getting-started)佇列的規劃，並遵循入門步驟。</span><span class="sxs-lookup"><span data-stu-id="bf22a-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="bf22a-112">若要設定通話佇列，請在 Teams 系統管理中心展開[語音，按一下通話 **佇列**，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="bf22a-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="bf22a-113">資源帳戶及語言</span><span class="sxs-lookup"><span data-stu-id="bf22a-113">Resource account and language</span></span>

![資源帳戶和語言設定螢幕擷取畫面](media/call-queue-name-language.png)

1. <span data-ttu-id="bf22a-115">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="bf22a-115">Type a name for the call queue.</span></span> <span data-ttu-id="bf22a-116">當代理人收到來自佇列的來電時，會看到此名稱。</span><span class="sxs-lookup"><span data-stu-id="bf22a-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="bf22a-117">按一下 **[新增** 帳戶，搜尋要用於此通話佇列的資源帳戶;按一下 [新增，然後按一下 **新增。**</span><span class="sxs-lookup"><span data-stu-id="bf22a-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="bf22a-118">選擇語言。</span><span class="sxs-lookup"><span data-stu-id="bf22a-118">Choose a language.</span></span> <span data-ttu-id="bf22a-119">如果您啟用系統產生的語音提示和語音信箱抄 (，就會使用這個) 。</span><span class="sxs-lookup"><span data-stu-id="bf22a-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="bf22a-120">佇列中保留的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="bf22a-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="bf22a-121">指定是否要在來電者到達佇列時播放問候語。</span><span class="sxs-lookup"><span data-stu-id="bf22a-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="bf22a-122">您必須上傳包含要播放之問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="bf22a-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="bf22a-123">當來電者排入佇列時，Teams 會提供預設音樂給來電者。</span><span class="sxs-lookup"><span data-stu-id="bf22a-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="bf22a-124">如果您想要播放特定的音訊檔案，請選擇播放音訊檔案，然後上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="bf22a-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="bf22a-125">上傳的錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="bf22a-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="bf22a-126">Teams 通話佇列提供的預設音樂可免收貴組織應付的任何權利金。</span><span class="sxs-lookup"><span data-stu-id="bf22a-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="bf22a-127">通話代理程式</span><span class="sxs-lookup"><span data-stu-id="bf22a-127">Call agents</span></span>

<span data-ttu-id="bf22a-128">請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以將代理人新增到通話佇列。</span><span class="sxs-lookup"><span data-stu-id="bf22a-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

<span data-ttu-id="bf22a-130">您可以透過群組個別新增最多 20 個代理程式，以及最多 200 個代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="bf22a-131">若要將使用者新增到佇列，請按一下[新增使用者，搜尋使用者，按一下 [**新增**，然後按一下新增 **。**</span><span class="sxs-lookup"><span data-stu-id="bf22a-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="bf22a-132">若要將群組新增到佇列，請按一下 [**新增** 群組;搜尋群組;按一下[新增，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="bf22a-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="bf22a-133">您可以使用通訊群組清單、安全性群組，以及 Microsoft 365 群組或 Microsoft Teams 團隊。</span><span class="sxs-lookup"><span data-stu-id="bf22a-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="bf22a-134">新加入群組的新使用者最多可能需要八小時的時間，才能到達第一個通話。</span><span class="sxs-lookup"><span data-stu-id="bf22a-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="bf22a-135">通話路由</span><span class="sxs-lookup"><span data-stu-id="bf22a-135">Call routing</span></span>

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="bf22a-137">**在代理人** 接受通話後，會議模式可大幅縮短來電者與代理人聯繫的時間。</span><span class="sxs-lookup"><span data-stu-id="bf22a-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="bf22a-138">若要讓會議模式運作，通話佇列中的代理人必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="bf22a-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="bf22a-139">最新版本的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="bf22a-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="bf22a-140">Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="bf22a-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="bf22a-141">代理人的 Teams 帳戶必須設定為 Teams-only 模式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="bf22a-142">不符合需求的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="bf22a-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="bf22a-143">如果您的代理人都使用相容的用戶端，建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="bf22a-144">會議模式不支援忙碌中。</span><span class="sxs-lookup"><span data-stu-id="bf22a-144">Busy on Busy is not supported by conference mode.</span></span> <span data-ttu-id="bf22a-145">若未啟用目前狀態式路由，非通話佇列通話的代理程式仍可能會顯示通話佇列通話。</span><span class="sxs-lookup"><span data-stu-id="bf22a-145">Agents on non-call queue calls may still be presented with a call queue call if presence-based routing is not enabled.</span></span>

<span data-ttu-id="bf22a-146">**路由方法** 會決定代理程式從佇列接收呼叫的順序。</span><span class="sxs-lookup"><span data-stu-id="bf22a-146">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="bf22a-147">請從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="bf22a-147">Choose from these options:</span></span>

- <span data-ttu-id="bf22a-148">**Attendant 路由** 會同時呼叫佇列的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-148">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="bf22a-149">第一位接電話的代理人會接到來電。</span><span class="sxs-lookup"><span data-stu-id="bf22a-149">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="bf22a-150">**串連路由** 會以通話代理程式清單中指定的順序，一個接一個撥打 **給所有通話** 代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-150">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="bf22a-151">如果代理人拒絕或不接電話，來電會撥打給下一位代理人，並嘗試所有代理人，直到來電接回或停止通話。</span><span class="sxs-lookup"><span data-stu-id="bf22a-151">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="bf22a-152">**圓形平衡** 呼叫的路由，讓每個通話代理程式從佇列獲得相同數目的通話。</span><span class="sxs-lookup"><span data-stu-id="bf22a-152">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="bf22a-153">這是在內入銷售環境中確保所有通話代理人均能有相等機會的做法。</span><span class="sxs-lookup"><span data-stu-id="bf22a-153">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="bf22a-154">**最長閒置** 時間路由每個通話給閒置時間最長之代理人。</span><span class="sxs-lookup"><span data-stu-id="bf22a-154">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="bf22a-155">如果代理人的目前狀態為線上，或者其目前狀態已離開少於 10 分鐘，則視為閒置中。</span><span class="sxs-lookup"><span data-stu-id="bf22a-155">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="bf22a-156">目前狀態超過 10 分鐘的代理程式視為閒置中，且除非其目前狀態變更為線上，才能接聽來電。</span><span class="sxs-lookup"><span data-stu-id="bf22a-156">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![路由、退出宣告及警示時間設定的螢幕擷取畫面](media/call-queue-presence-agents-time.png)


<span data-ttu-id="bf22a-158">**目前狀態式路由** 會使用通話代理程式的可用性狀態，來判斷所選路由方法的通話路由清單中是否應該包含代理人。</span><span class="sxs-lookup"><span data-stu-id="bf22a-158">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="bf22a-159">其顯示狀態設定為可用的通話代理程式會包含在通話路由清單中，而且可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="bf22a-159">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="bf22a-160">其可用性狀態設定為任何其他狀態的代理人會排除在通話路由清單中，而且不會接聽來電，直到其顯示狀態變更回可用 **。**</span><span class="sxs-lookup"><span data-stu-id="bf22a-160">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="bf22a-161">您可以使用任何路由方法啟用目前狀態式通話路由。</span><span class="sxs-lookup"><span data-stu-id="bf22a-161">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="bf22a-162">如果代理人選擇不接聽來電，無論其顯示狀態設定為何種狀態，他們將不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="bf22a-162">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="bf22a-163">啟用目前狀態式路由時，使用商務用 Skype 用戶端的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="bf22a-163">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="bf22a-164">如果您有使用商務用 Skype 的代理人，請勿啟用目前狀態通話路由。</span><span class="sxs-lookup"><span data-stu-id="bf22a-164">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="bf22a-165">**代理人警示** 時間會指定代理人的電話在佇列將來電重新導向到下一個代理人前會響鈴多久。</span><span class="sxs-lookup"><span data-stu-id="bf22a-165">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="bf22a-166">針對大量佇列，我們建議進行下列設定：</span><span class="sxs-lookup"><span data-stu-id="bf22a-166">For high volume queues, we recommend the following settings:</span></span>

- <span data-ttu-id="bf22a-167">**會議模式** 為 **自動**</span><span class="sxs-lookup"><span data-stu-id="bf22a-167">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="bf22a-168">**Attendant** 路由 **的路由方法**</span><span class="sxs-lookup"><span data-stu-id="bf22a-168">**Routing method** to **Attendant routing**</span></span>
- <span data-ttu-id="bf22a-169">**以目前狀態為基礎的路由** 至 **On**</span><span class="sxs-lookup"><span data-stu-id="bf22a-169">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="bf22a-170">**代理人警示時間\*\*\*\*：20 秒**</span><span class="sxs-lookup"><span data-stu-id="bf22a-170">**Agent alert time:** to **20 seconds**</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="bf22a-171">呼叫溢出處理</span><span class="sxs-lookup"><span data-stu-id="bf22a-171">Call overflow handling</span></span>

![通話溢位設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

<span data-ttu-id="bf22a-173">**佇列中的通話數目上限** 指定在任何指定時間都可以在佇列中等候的通話數目上限。</span><span class="sxs-lookup"><span data-stu-id="bf22a-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="bf22a-174">預設值為 50，但範圍從 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="bf22a-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="bf22a-175">達到此限制時，會依照達到通話數上限設定所指定的處理 **通話。**</span><span class="sxs-lookup"><span data-stu-id="bf22a-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="bf22a-176">您可以選擇中斷通話的中斷，或是將電話重新導向至任何通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bf22a-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="bf22a-177">例如，您可能會要求來電者在佇列中為代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="bf22a-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="bf22a-178">針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)號碼格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bf22a-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="bf22a-179">如果通話數上限設定為 0，將不會播放問候語訊息。</span><span class="sxs-lookup"><span data-stu-id="bf22a-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="bf22a-180">通話超時處理</span><span class="sxs-lookup"><span data-stu-id="bf22a-180">Call timeout handling</span></span>

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

<span data-ttu-id="bf22a-182">**通話超時：最大等待時間** 可指定通話在重新導向或中斷連接前可保留佇列中的時間上限。</span><span class="sxs-lookup"><span data-stu-id="bf22a-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="bf22a-183">您可以指定 0 秒到 45 分鐘的值。</span><span class="sxs-lookup"><span data-stu-id="bf22a-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="bf22a-184">您可以選擇中斷通話的中斷，或是將電話重新導向至其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="bf22a-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="bf22a-185">例如，您可能會要求來電者在佇列中為代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="bf22a-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="bf22a-186">針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)號碼格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bf22a-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="bf22a-187">當您已選取通話超時選項時，請按一下 **[儲存**。</span><span class="sxs-lookup"><span data-stu-id="bf22a-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="bf22a-188">外電來電的本機號碼</span><span class="sxs-lookup"><span data-stu-id="bf22a-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="bf22a-189">由於通話佇列的代理人可以撥出以傳回客戶電話，因此請考慮將通話佇列成員的本機號碼設定為適當自動語音回應的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="bf22a-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="bf22a-190">詳細資訊 [請參閱 Microsoft Teams 中的管理來電](caller-id-policies.md) 顯示政策。</span><span class="sxs-lookup"><span data-stu-id="bf22a-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="bf22a-191">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="bf22a-191">Supported clients</span></span>

<span data-ttu-id="bf22a-192">通話佇列的通話代理程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="bf22a-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="bf22a-193">商務用 Skype 桌面用戶端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="bf22a-194">Lync 桌面用戶端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="bf22a-195">Microsoft Teams 支援的所有 IP 電話型號。</span><span class="sxs-lookup"><span data-stu-id="bf22a-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="bf22a-196">請參閱 [取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="bf22a-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="bf22a-197">Mac 商務用 Skype 用戶端 (版本 16.8.196 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="bf22a-198">Android 商務用 Skype 用戶端 (6.16.0.9 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="bf22a-199">iPhone 商務用 Skype 用戶端 (6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="bf22a-200">iPad 商務用 Skype 用戶端 (6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="bf22a-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="bf22a-201"> (32 位和 64 位版本的 Microsoft Teams Windows 用戶端) </span><span class="sxs-lookup"><span data-stu-id="bf22a-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="bf22a-202">Microsoft Teams Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="bf22a-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="bf22a-203">Microsoft Teams iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="bf22a-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="bf22a-204">Microsoft Teams Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="bf22a-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf22a-205">指派直接路由號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 電話代理程式。</span><span class="sxs-lookup"><span data-stu-id="bf22a-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="bf22a-206">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf22a-206">Call queue cmdlets</span></span>

<span data-ttu-id="bf22a-207">您也可以使用 Windows PowerShell 來建立和設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="bf22a-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="bf22a-208">以下是您用於管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bf22a-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="bf22a-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bf22a-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="bf22a-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bf22a-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="bf22a-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bf22a-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="bf22a-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bf22a-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="bf22a-213">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf22a-213">Related topics</span></span>

[<span data-ttu-id="bf22a-214">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="bf22a-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="bf22a-215">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="bf22a-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="bf22a-216">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="bf22a-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="bf22a-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="bf22a-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="bf22a-218">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="bf22a-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
