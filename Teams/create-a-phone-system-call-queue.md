---
title: 在 Microsoft 團隊中建立通話佇列
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
description: 瞭解如何在 Microsoft 團隊中設定電話聯絡佇列，提供問候語、等候音樂、呼叫重新導向及其他功能。
ms.openlocfilehash: 0253fb15a8672d83e672e3e3e18f8455d292214c
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145890"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="0bc41-103">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="0bc41-103">Create a call queue</span></span>

<span data-ttu-id="0bc41-104">通話佇列提供將呼叫者路由給組織中的人員的方法，可協助您解決特定問題。</span><span class="sxs-lookup"><span data-stu-id="0bc41-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="0bc41-105">呼叫會一次散佈給佇列中的人員， (稱為 [ *代理* 程式]) 。</span><span class="sxs-lookup"><span data-stu-id="0bc41-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="0bc41-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="0bc41-106">Call queues provide:</span></span>

- <span data-ttu-id="0bc41-107">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="0bc41-107">A greeting message.</span></span>

- <span data-ttu-id="0bc41-108">當人員在佇列中等待保留時，請使用音樂。</span><span class="sxs-lookup"><span data-stu-id="0bc41-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="0bc41-109">呼叫路由-先進先 *出* (FIFO) 訂單至代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="0bc41-110">[佇列溢出] 和 [超時] 的處理選項。</span><span class="sxs-lookup"><span data-stu-id="0bc41-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="0bc41-111">請確定您已閱讀 [小組自動語音應答] [和 [呼叫佇列](plan-auto-attendant-call-queue.md) ] 的 [規劃]，然後依照本文中的程式執行 [步驟](plan-auto-attendant-call-queue.md#getting-started) 。</span><span class="sxs-lookup"><span data-stu-id="0bc41-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="0bc41-112">若要設定通話佇列，請在 [團隊管理中心] 中，展開 [ **語音**]，按一下 [ **通話佇列**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="0bc41-113">資源帳戶和語言</span><span class="sxs-lookup"><span data-stu-id="0bc41-113">Resource account and language</span></span>

![資源帳戶和語言設定的螢幕擷取畫面](media/call-queue-name-language.png)

1. <span data-ttu-id="0bc41-115">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="0bc41-115">Type a name for the call queue.</span></span> <span data-ttu-id="0bc41-116">當代理程式從佇列接收來電時，就會看到這個名稱。</span><span class="sxs-lookup"><span data-stu-id="0bc41-116">Agents will see this name when they receive an incoming call from the queue.</span></span>

2. <span data-ttu-id="0bc41-117">按一下 [ **新增帳戶**]，搜尋您要與此通話佇列搭配使用的資源帳戶，按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-117">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span>

3. <span data-ttu-id="0bc41-118">選擇語言。</span><span class="sxs-lookup"><span data-stu-id="0bc41-118">Choose a language.</span></span> <span data-ttu-id="0bc41-119">此語言將用於系統產生的語音提示，以及語音信箱操作 (如果您) 啟用這些語言。</span><span class="sxs-lookup"><span data-stu-id="0bc41-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="0bc41-120">[在佇列中保留問候語] 和 [音樂]</span><span class="sxs-lookup"><span data-stu-id="0bc41-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="0bc41-121">指定是否要在來電者到達佇列時，向呼叫者播放問候語。</span><span class="sxs-lookup"><span data-stu-id="0bc41-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="0bc41-122">您必須上傳包含您要播放之問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="0bc41-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="0bc41-123">當來電者在佇列中保留時，小組會將預設音樂提供給呼叫者。</span><span class="sxs-lookup"><span data-stu-id="0bc41-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="0bc41-124">如果您想要播放特定音訊檔案，請選擇 [ **播放音訊** 檔案]，然後上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="0bc41-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="0bc41-125">上傳的錄製不能超過 5 MB。</span><span class="sxs-lookup"><span data-stu-id="0bc41-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="0bc41-126">小組通話佇列中提供的預設音樂，由貴組織所提供的任何版稅免費提供。</span><span class="sxs-lookup"><span data-stu-id="0bc41-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="0bc41-127">撥號代理程式</span><span class="sxs-lookup"><span data-stu-id="0bc41-127">Call agents</span></span>

<span data-ttu-id="0bc41-128">請參考 [必備元件](plan-auto-attendant-call-queue.md#prerequisites) ，以便能夠將代理新增至通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0bc41-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![通話佇列之使用者與群組設定的螢幕擷取畫面](media/call-queue-users-groups.png)

<span data-ttu-id="0bc41-130">您可以透過群組新增最多20個代理程式，以及最多200個代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="0bc41-131">若要將使用者新增至佇列，請按一下 [ **新增使用者**]，搜尋使用者，按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="0bc41-132">若要在佇列中新增群組，請按一下 [ **新增群組**]，搜尋群組，按一下 [ **新增**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="0bc41-133">您可以使用通訊群組清單、安全性群組，以及 Microsoft 365 群組或 Microsoft 團隊小組。</span><span class="sxs-lookup"><span data-stu-id="0bc41-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0bc41-134">新增至群組的新使用者最多可能需要八個小時的時間，才能讓初次通話到達。</span><span class="sxs-lookup"><span data-stu-id="0bc41-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="0bc41-135">通話路由</span><span class="sxs-lookup"><span data-stu-id="0bc41-135">Call routing</span></span>

![[會議模式] 與 [路由方法] 設定的螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="0bc41-137">在工程師接受通話之後，**會議模式** 會大大減少呼叫者連線至代理程式所需的時間長度。</span><span class="sxs-lookup"><span data-stu-id="0bc41-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="0bc41-138">若要使用會議模式，通話佇列中的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="0bc41-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="0bc41-139">最新版本的 Microsoft 團隊桌面用戶端、Android 應用程式或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="0bc41-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="0bc41-140">Microsoft 團隊手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="0bc41-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="0bc41-141">必須將代理的小群組帳戶設定為 [僅限團隊模式]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="0bc41-142">不符合需求的工程師不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="0bc41-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="0bc41-143">如果您的代理全部使用相容的用戶端，我們建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="0bc41-144">**路由方法** 決定了代理從佇列接收呼叫的順序。</span><span class="sxs-lookup"><span data-stu-id="0bc41-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="0bc41-145">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="0bc41-145">Choose from these options:</span></span>

- <span data-ttu-id="0bc41-146">[**助理路由**] 會同時響鈴佇列中的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="0bc41-147">第一個呼叫代理程式接聽電話，即可取得通話。</span><span class="sxs-lookup"><span data-stu-id="0bc41-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="0bc41-148">**串列路由** 依 **來電代理** 程式清單中指定的順序，逐一響鈴所有呼叫代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="0bc41-149">如果代理程式關閉或沒接聽來電，該通話會撥打下一個代理程式，並嘗試所有的代理程式，直到它被挑選或超時為止。</span><span class="sxs-lookup"><span data-stu-id="0bc41-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="0bc41-150">**迴圈法** 會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bc41-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="0bc41-151">這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="0bc41-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="0bc41-152">閒置時間最長的 **閒置** 路由，每個呼叫都是閒置時間最長的代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="0bc41-153">如果工程師的目前狀態為 [空閒] 或其目前狀態已離開10分鐘以內，則會被視為空閒。</span><span class="sxs-lookup"><span data-stu-id="0bc41-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="0bc41-154">目前狀態為已離開超過10分鐘的代理程式不會被視為空閒，而且將無法接收來電，直到它們變更其目前狀態。</span><span class="sxs-lookup"><span data-stu-id="0bc41-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![[路由]、[選擇外移] 及 [提醒時間] 設定的螢幕擷取畫面](media/call-queue-presence-agents-time.png)


<span data-ttu-id="0bc41-156">目前 **狀態路由** 會使用呼叫代理程式的可用性狀態，判斷是否應將工程師納入所選路由方法的通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="0bc41-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="0bc41-157">[通話傳送] 清單中包含 [ **提供給可用** ] 的呼叫代理程式，並可接聽來電。</span><span class="sxs-lookup"><span data-stu-id="0bc41-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="0bc41-158">其可用性狀態設定為任何其他狀態的代理會從 [呼叫傳送清單] 中排除，而且在其可用性狀態變更回 [ **可用**] 之前，將不會收到來電。</span><span class="sxs-lookup"><span data-stu-id="0bc41-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="0bc41-159">您可以使用任何一種路由方法來啟用目前狀態的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="0bc41-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="0bc41-160">如果代理程式無法取得來電，無論其可用性狀態為何，都不會包含在通話傳送清單中。</span><span class="sxs-lookup"><span data-stu-id="0bc41-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="0bc41-161">啟用商務用 Skype 用戶端的代理程式不會包含在 [通話] 路由清單中（如果已啟用目前狀態路由的話）。</span><span class="sxs-lookup"><span data-stu-id="0bc41-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="0bc41-162">如果您有使用商務用 Skype 的代理商，請不要啟用目前狀態的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="0bc41-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="0bc41-163">**Agent 警示時間** 指定在佇列將呼叫重新導向至下一個代理程式之前，該電話會響鈴的時間。</span><span class="sxs-lookup"><span data-stu-id="0bc41-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="0bc41-164">建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="0bc41-164">The following settings are recommended:</span></span>

- <span data-ttu-id="0bc41-165">**自動** 進行 **會議模式**</span><span class="sxs-lookup"><span data-stu-id="0bc41-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="0bc41-166">**傳送方式** 是 **迴圈或\*\*\*\*最長空閒**</span><span class="sxs-lookup"><span data-stu-id="0bc41-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="0bc41-167">[目前 **狀態] 路由** 至 [**開啟**]</span><span class="sxs-lookup"><span data-stu-id="0bc41-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="0bc41-168">**Agent 提醒時間：** **20 秒**</span><span class="sxs-lookup"><span data-stu-id="0bc41-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="0bc41-169">如果未啟用目前狀態的路由，且佇列中有多個通話，系統會同時將這些來電加入到工程師，而不管其目前狀態為何。</span><span class="sxs-lookup"><span data-stu-id="0bc41-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="0bc41-170">這將會導致多個代理程式呼叫通知，特別是在某些代理程式沒有應答提供給他們的初始呼叫時。</span><span class="sxs-lookup"><span data-stu-id="0bc41-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="0bc41-171">呼叫溢出處理</span><span class="sxs-lookup"><span data-stu-id="0bc41-171">Call overflow handling</span></span>

![通話溢出設定的螢幕擷取畫面](media/call-queue-overflow-handling.png)

<span data-ttu-id="0bc41-173">**佇列中的最大通話** 數指定可在任何指定時間在佇列中等待的呼叫數量上限。</span><span class="sxs-lookup"><span data-stu-id="0bc41-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="0bc41-174">預設值為50，但範圍可以是0到200。</span><span class="sxs-lookup"><span data-stu-id="0bc41-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="0bc41-175">達到這個限制之後，就會按照在 **達到最大通話數設定時** 所指定的方式來處理通話。</span><span class="sxs-lookup"><span data-stu-id="0bc41-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="0bc41-176">您可以選擇中斷通話，或將它重新導向至任何呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="0bc41-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="0bc41-177">例如，您可能會有來電者在佇列中留下代理程式的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0bc41-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="0bc41-178">如需外部轉接，請參閱 [先決條件](plan-auto-attendant-call-queue.md#prerequisites) 與 [外部電話號碼轉接-技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) ，瞭解數位格式設定。</span><span class="sxs-lookup"><span data-stu-id="0bc41-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="0bc41-179">如果 [呼叫數量上限] 設定為0，則不會播放問候語訊息。</span><span class="sxs-lookup"><span data-stu-id="0bc41-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="0bc41-180">通話超時處理</span><span class="sxs-lookup"><span data-stu-id="0bc41-180">Call timeout handling</span></span>

![通話超時設定的螢幕擷取畫面](media/call-queue-timeout-handling.png)

<span data-ttu-id="0bc41-182">[**通話超時]： [最長等候時間**] 指定在電話重新導向或中斷前，可以在佇列中保留的最長時間。</span><span class="sxs-lookup"><span data-stu-id="0bc41-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="0bc41-183">您可以指定0秒到45分鐘的值。</span><span class="sxs-lookup"><span data-stu-id="0bc41-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="0bc41-184">您可以選擇中斷通話，或將它重新導向至其中一個呼叫路由目標。</span><span class="sxs-lookup"><span data-stu-id="0bc41-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="0bc41-185">例如，您可能會有來電者在佇列中留下代理程式的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0bc41-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="0bc41-186">如需外部轉接，請參閱 [先決條件](plan-auto-attendant-call-queue.md#prerequisites) 與 [外部電話號碼轉接-技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) ，瞭解數位格式設定。</span><span class="sxs-lookup"><span data-stu-id="0bc41-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="0bc41-187">選取您的通話超時選項之後，按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0bc41-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="0bc41-188">撥出電話的本機號碼</span><span class="sxs-lookup"><span data-stu-id="0bc41-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="0bc41-189">由於呼叫佇列中的代理程式可能會撥出以傳回客戶電話，因此請考慮將呼叫佇列成員的本機號碼設定為適當的自動語音應答的服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0bc41-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="0bc41-190">如需詳細資訊，請參閱 [在 Microsoft 團隊中管理本機號碼原則](caller-id-policies.md) 。</span><span class="sxs-lookup"><span data-stu-id="0bc41-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="0bc41-191">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="0bc41-191">Supported clients</span></span>

<span data-ttu-id="0bc41-192">通話佇列中的呼叫代理程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="0bc41-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="0bc41-193">商務用 Skype desktop 用戶端 2016 (32 位與64位版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0bc41-194">Lync 桌面用戶端 2013 (32 位與64位版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0bc41-195">Microsoft 團隊支援的所有 IP 電話模型。</span><span class="sxs-lookup"><span data-stu-id="0bc41-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="0bc41-196">請參閱 [取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="0bc41-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="0bc41-197">Mac 版商務用 Skype 用戶端 (版本16.8.196 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="0bc41-198">Android 版商務用 Skype 用戶端 (版本6.16.0.9 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="0bc41-199">iPhone 版商務用 Skype 用戶端 (版本6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="0bc41-200">iPad 版商務用 Skype 用戶端 (版本6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="0bc41-201">Microsoft 團隊 Windows 用戶端 (32 位與64位版本) </span><span class="sxs-lookup"><span data-stu-id="0bc41-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0bc41-202">Microsoft 團隊 Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="0bc41-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="0bc41-203">Microsoft 團隊 iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="0bc41-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="0bc41-204">Microsoft 團隊 Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="0bc41-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bc41-205">指派直接傳送號碼的呼叫佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 手機做為代理程式。</span><span class="sxs-lookup"><span data-stu-id="0bc41-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="0bc41-206">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0bc41-206">Call queue cmdlets</span></span>

<span data-ttu-id="0bc41-207">您也可以使用 Windows PowerShell 來建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0bc41-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="0bc41-208">以下是您用來管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0bc41-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="0bc41-209">新-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0bc41-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="0bc41-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0bc41-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="0bc41-211">CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0bc41-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="0bc41-212">移除-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0bc41-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="0bc41-213">相關主題</span><span class="sxs-lookup"><span data-stu-id="0bc41-213">Related topics</span></span>

[<span data-ttu-id="0bc41-214">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="0bc41-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="0bc41-215">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="0bc41-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="0bc41-216">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="0bc41-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="0bc41-217">新-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="0bc41-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="0bc41-218">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="0bc41-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
