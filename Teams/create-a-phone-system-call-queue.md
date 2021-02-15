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
description: 瞭解如何使用 Microsoft Teams 針對通話佇列設定電話系統，提供問候語訊息、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: cc0995a6355157de1b43a04caf7814e588232c48
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196747"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="0246e-103">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="0246e-103">Create a call queue</span></span>

<span data-ttu-id="0246e-104">通話佇列提供將來電者路由給組織中可協助處理特定問題或問題的人的方法。</span><span class="sxs-lookup"><span data-stu-id="0246e-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="0246e-105">通話會一次一次發佈給佇列 (稱為代理 *程式) 。*</span><span class="sxs-lookup"><span data-stu-id="0246e-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="0246e-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="0246e-106">Call queues provide:</span></span>

- <span data-ttu-id="0246e-107">問候語訊息。</span><span class="sxs-lookup"><span data-stu-id="0246e-107">A greeting message.</span></span>

- <span data-ttu-id="0246e-108">當人員在佇列中等候時播放音樂。</span><span class="sxs-lookup"><span data-stu-id="0246e-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="0246e-109">呼叫路由 - *在 FIFO (* 中，先) - 到代理程式。</span><span class="sxs-lookup"><span data-stu-id="0246e-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="0246e-110">佇列溢位和超時的處理選項。</span><span class="sxs-lookup"><span data-stu-id="0246e-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="0246e-111">遵循本文中的程式之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動 Attendant 和[](plan-auto-attendant-call-queue.md#getting-started)通話佇列的規劃，並遵循開始使用的步驟。</span><span class="sxs-lookup"><span data-stu-id="0246e-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this articles.</span></span>

<span data-ttu-id="0246e-112">若要設定通話佇列，請在 Teams 系統管理中心展開 **語音**，按一下通話 **佇列**，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="0246e-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="0246e-113">資源帳戶和語言</span><span class="sxs-lookup"><span data-stu-id="0246e-113">Resource account and language</span></span>

![資源帳戶和語言設定螢幕擷取畫面](media/call-queue-name-language.png)

1. <span data-ttu-id="0246e-115">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="0246e-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="0246e-116">按一下 **[新增** 帳戶;搜尋要用於此通話佇列的資源帳戶;按一下 **[** 新增，然後按一下 **新增。**</span><span class="sxs-lookup"><span data-stu-id="0246e-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="0246e-117"> (代理程式收到來電時，會看到資源帳戶名稱。) </span><span class="sxs-lookup"><span data-stu-id="0246e-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="0246e-118">選擇 [支援的語言](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="0246e-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="0246e-119">如果您啟用系統產生的語音提示和語音 (，就會使用這個) 。</span><span class="sxs-lookup"><span data-stu-id="0246e-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="0246e-120">佇列等候的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="0246e-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="0246e-121">指定當來電者到達佇列時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="0246e-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="0246e-122">您必須上傳包含要播放之問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="0246e-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="0246e-123">當來電者在佇列中等候時，Teams 會提供預設音樂。</span><span class="sxs-lookup"><span data-stu-id="0246e-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="0246e-124">如果您想要播放特定的音訊檔案，請選擇播放音訊檔案，然後上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="0246e-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="0246e-125">上傳的錄製內容不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="0246e-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="0246e-126">Teams 通話佇列提供的預設音樂是免費的，貴組織可支付任何權利金。</span><span class="sxs-lookup"><span data-stu-id="0246e-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="0246e-127">通話代理程式</span><span class="sxs-lookup"><span data-stu-id="0246e-127">Call agents</span></span>

<span data-ttu-id="0246e-128">請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以將代理程式新增到通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0246e-128">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to be able to add agents to a call queue.</span></span>

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

<span data-ttu-id="0246e-130">您可以個別新增最多 20 個代理程式，並透過群組新增最多 200 個代理程式。</span><span class="sxs-lookup"><span data-stu-id="0246e-130">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="0246e-131">若要將使用者新增到佇列，請按一下[新增使用者;搜尋使用者;按一下 **[新增**，然後按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="0246e-131">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="0246e-132">若要將群組新增到佇列，請按一下 [ **新增** 群組;搜尋群組;按一下 **[新增**，再按一下 **新增**。</span><span class="sxs-lookup"><span data-stu-id="0246e-132">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="0246e-133">您可以使用通訊群組清單、安全性群組和 Microsoft 365 群組或 Microsoft Teams 團隊。</span><span class="sxs-lookup"><span data-stu-id="0246e-133">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0246e-134">新加入群組的使用者最多可能需要八小時的時間，才能第一次通話到達。</span><span class="sxs-lookup"><span data-stu-id="0246e-134">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="0246e-135">通話路由</span><span class="sxs-lookup"><span data-stu-id="0246e-135">Call routing</span></span>

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="0246e-137">**會議模式** 可大幅縮短當代理人接受來電後，來電者與代理人連上的時間。</span><span class="sxs-lookup"><span data-stu-id="0246e-137">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="0246e-138">若要讓會議模式運作，通話佇列中的代理程式必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="0246e-138">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="0246e-139">最新版本的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="0246e-139">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="0246e-140">Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="0246e-140">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="0246e-141">代理人的 Teams 帳戶必須設定為 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="0246e-141">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="0246e-142">不符合需求的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="0246e-142">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="0246e-143">如果您的代理人都使用相容的用戶端，建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="0246e-143">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

<span data-ttu-id="0246e-144">**路由方法** 會決定代理程式從佇列接收呼叫的順序。</span><span class="sxs-lookup"><span data-stu-id="0246e-144">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="0246e-145">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="0246e-145">Choose from these options:</span></span>

- <span data-ttu-id="0246e-146">**Attendant 路由** 會同時為佇列中的所有代理程式響鈴。</span><span class="sxs-lookup"><span data-stu-id="0246e-146">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="0246e-147">第一個接電話的代理人會接到來電。</span><span class="sxs-lookup"><span data-stu-id="0246e-147">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="0246e-148">**連續路由** 會以呼叫代理程式清單中指定的順序，一個接一個地撥打所有 **呼叫** 代理程式。</span><span class="sxs-lookup"><span data-stu-id="0246e-148">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="0246e-149">如果客服人員拒絕或未接電話，來電會撥打給下一位客服人員，並嘗試所有代理人，直到電話取貨或打退。</span><span class="sxs-lookup"><span data-stu-id="0246e-149">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="0246e-150">**四輪** 路由會平衡來電的路由，讓每個通話代理程式從佇列獲得相同的通話數目。</span><span class="sxs-lookup"><span data-stu-id="0246e-150">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="0246e-151">在內入銷售環境中，這是理想的情況，以確保所有呼叫代理程式之間有相同的機會。</span><span class="sxs-lookup"><span data-stu-id="0246e-151">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="0246e-152">**最長閒置** 時間會路由每通電話給閒置時間最長的代理人。</span><span class="sxs-lookup"><span data-stu-id="0246e-152">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="0246e-153">如果代理人的目前狀態為線上，或者其目前狀態在離開狀態不到 10 分鐘，則視為閒置中。</span><span class="sxs-lookup"><span data-stu-id="0246e-153">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="0246e-154">目前狀態超過 10 分鐘的代理人不視為閒置中，且在將目前狀態變更為線上之前，將不符合接聽來電資格。</span><span class="sxs-lookup"><span data-stu-id="0246e-154">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![路由、退出宣告和警示時間設定螢幕擷取畫面](media/call-queue-presence-agents-time.png)


<span data-ttu-id="0246e-156">**目前狀態式路由** 會使用呼叫代理程式的可用性狀態，來判斷所選路由方法的呼叫路由清單中是否應該包含代理程式。</span><span class="sxs-lookup"><span data-stu-id="0246e-156">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="0246e-157">將顯示狀態設為可用的呼叫代理程式會包含在通話路由清單中，而且可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="0246e-157">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="0246e-158">其顯示狀態設定為任何其他狀態的代理人會從通話路由清單中排除，而且不會接收通話，直到其顯示狀態變更回可用 **。**</span><span class="sxs-lookup"><span data-stu-id="0246e-158">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="0246e-159">您可以使用任何路由方法啟用目前狀態型呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="0246e-159">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="0246e-160">如果代理人選擇不接聽電話，無論他們的顯示狀態設定為什麼，通話路由清單不會包含他們。</span><span class="sxs-lookup"><span data-stu-id="0246e-160">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="0246e-161">啟用目前狀態式路由時，使用商務用 Skype 用戶端的代理程式不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="0246e-161">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="0246e-162">如果您有使用商務用 Skype 的代理程式，請勿啟用目前狀態型通話路由。</span><span class="sxs-lookup"><span data-stu-id="0246e-162">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="0246e-163">**代理人通知** 時間會指定在佇列將來電重新導向到下一個代理人之前，代理人的電話會響鈴多久。</span><span class="sxs-lookup"><span data-stu-id="0246e-163">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="0246e-164">建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="0246e-164">The following settings are recommended:</span></span>

- <span data-ttu-id="0246e-165">**會議模式** 為 **自動**</span><span class="sxs-lookup"><span data-stu-id="0246e-165">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="0246e-166">**將路由方式** 四 **分位或\*\*\*\*最長閒置時間**</span><span class="sxs-lookup"><span data-stu-id="0246e-166">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="0246e-167">**以目前狀態為基礎的路由** 到 **On**</span><span class="sxs-lookup"><span data-stu-id="0246e-167">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="0246e-168">**代理人警示時間\*\*\*\*：20 秒**</span><span class="sxs-lookup"><span data-stu-id="0246e-168">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="0246e-169">如果未啟用目前狀態路由，且佇列中有多個通話，無論代理程式目前狀態如何，系統都會同時向代理程式顯示這些呼叫。</span><span class="sxs-lookup"><span data-stu-id="0246e-169">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="0246e-170">這會導致多個來電通知給代理程式，特別是當某些代理程式無法接聽他們接到的初始通話時。</span><span class="sxs-lookup"><span data-stu-id="0246e-170">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="0246e-171">呼叫溢位處理</span><span class="sxs-lookup"><span data-stu-id="0246e-171">Call overflow handling</span></span>

![通話溢位設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

<span data-ttu-id="0246e-173">**佇列中的通話上限** 會指定在任何指定時間可在佇列中等候的通話數量上限。</span><span class="sxs-lookup"><span data-stu-id="0246e-173">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="0246e-174">預設值為 50，但範圍從 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="0246e-174">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="0246e-175">達到此限制時，會依照達到通話數量上限的設定來處理 **通話** 。</span><span class="sxs-lookup"><span data-stu-id="0246e-175">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="0246e-176">您可以選擇中斷通話，或重新導向至任何通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0246e-176">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="0246e-177">例如，您可能會讓來電者在佇列中為代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0246e-177">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="0246e-178">針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0246e-178">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="0246e-179">如果通話數量上限設定為 0，則問候語訊息將不會播放。</span><span class="sxs-lookup"><span data-stu-id="0246e-179">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="0246e-180">通話超時處理</span><span class="sxs-lookup"><span data-stu-id="0246e-180">Call timeout handling</span></span>

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

<span data-ttu-id="0246e-182">**通話超時：最長等待時間** 會指定在重新導向或中斷連接前，通話在佇列中可以保留的最大時間。</span><span class="sxs-lookup"><span data-stu-id="0246e-182">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="0246e-183">您可以指定 0 秒到 45 分鐘的值。</span><span class="sxs-lookup"><span data-stu-id="0246e-183">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="0246e-184">您可以選擇中斷通話，或重新導向到其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="0246e-184">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="0246e-185">例如，您可能會讓來電者在佇列中為代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0246e-185">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="0246e-186">針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0246e-186">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="0246e-187">當您選取通話超時選項時，請按一下 **[儲存**。</span><span class="sxs-lookup"><span data-stu-id="0246e-187">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="0246e-188">外線通話的本機號碼</span><span class="sxs-lookup"><span data-stu-id="0246e-188">Caller ID for outbound calls</span></span>

<span data-ttu-id="0246e-189">由於通話佇列的代理程式可能會撥出電話以傳回客戶電話，因此請考慮將通話佇列成員的本機號碼設定為適當的自動語音機服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0246e-189">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="0246e-190">請參閱 [在 Microsoft Teams 中管理本機號碼](caller-id-policies.md) 政策以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="0246e-190">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="0246e-191">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="0246e-191">Supported clients</span></span>

<span data-ttu-id="0246e-192">通話佇列中的呼叫代理程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="0246e-192">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="0246e-193">商務用 Skype 桌面用戶端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-193">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0246e-194">Lync 桌面用戶端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-194">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0246e-195">Microsoft Teams 支援的所有 IP 電話型號。</span><span class="sxs-lookup"><span data-stu-id="0246e-195">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="0246e-196">請參閱 [取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="0246e-196">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="0246e-197">Mac 商務用 Skype 用戶端 (版本 16.8.196 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-197">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="0246e-198">Android 商務用 Skype 用戶端 (版本 6.16.0.9 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-198">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="0246e-199">iPhone 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-199">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="0246e-200">iPad 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-200">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="0246e-201">Microsoft Teams Windows 用戶端 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="0246e-201">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="0246e-202">Microsoft Teams Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="0246e-202">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="0246e-203">Microsoft Teams iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="0246e-203">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="0246e-204">Microsoft Teams Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="0246e-204">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="0246e-205">指派直接路由號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 電話代理程式。</span><span class="sxs-lookup"><span data-stu-id="0246e-205">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="0246e-206">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0246e-206">Call queue cmdlets</span></span>

<span data-ttu-id="0246e-207">您也可以使用 Windows PowerShell 建立及設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="0246e-207">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="0246e-208">以下是您用於管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0246e-208">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="0246e-209">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0246e-209">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="0246e-210">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0246e-210">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="0246e-211">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0246e-211">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="0246e-212">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="0246e-212">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="0246e-213">相關主題</span><span class="sxs-lookup"><span data-stu-id="0246e-213">Related topics</span></span>

[<span data-ttu-id="0246e-214">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="0246e-214">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="0246e-215">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="0246e-215">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="0246e-216">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="0246e-216">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="0246e-217">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="0246e-217">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="0246e-218">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="0246e-218">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
