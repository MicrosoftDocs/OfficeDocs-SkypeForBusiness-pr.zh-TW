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
description: 瞭解如何使用 Microsoft Teams 設定電話佇列的電話系統，提供問候訊息、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: 1202de31beddb8f70391d40d4e6218942c59cba1
ms.sourcegitcommit: 4e1f5d99c1d0612dc5b50f850280983867ff53d8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51874449"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="b9a10-103">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="b9a10-103">Create a call queue</span></span>

<span data-ttu-id="b9a10-104">通話佇列提供將來電者路由給組織中可協助處理特定問題或問題的人的方法。</span><span class="sxs-lookup"><span data-stu-id="b9a10-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="b9a10-105">通話會一次一次分散給佇列中 (稱為 *代理人) 。*</span><span class="sxs-lookup"><span data-stu-id="b9a10-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

<span data-ttu-id="b9a10-106">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="b9a10-106">Call queues provide:</span></span>

- <span data-ttu-id="b9a10-107">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="b9a10-107">A greeting message.</span></span>

- <span data-ttu-id="b9a10-108">當其他人在佇列中等候時播放音樂。</span><span class="sxs-lookup"><span data-stu-id="b9a10-108">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="b9a10-109">呼叫路由 - 在 *FIFO (* 中，) 呼叫路由 - 給代理人。</span><span class="sxs-lookup"><span data-stu-id="b9a10-109">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="b9a10-110">處理佇列溢出和超時的選項。</span><span class="sxs-lookup"><span data-stu-id="b9a10-110">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="b9a10-111">請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動電話機和通話佇列的規劃，並遵循[](plan-auto-attendant-call-queue.md#getting-started)開始使用的步驟，然後再遵循本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-111">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="b9a10-112">若要設定通話佇列，請在 Teams 系統管理中心展開 [**語音** 與通話佇列>，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="b9a10-112">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

## <a name="resource-account-and-language"></a><span data-ttu-id="b9a10-113">資源帳戶和語言</span><span class="sxs-lookup"><span data-stu-id="b9a10-113">Resource account and language</span></span>

![資源帳戶和語言設定螢幕擷取畫面](media/call-queue-name-language.png)

1. <span data-ttu-id="b9a10-115">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="b9a10-115">Type a name for the call queue.</span></span>

2. <span data-ttu-id="b9a10-116">按一下 **[新增帳戶**，搜尋要用於此通話佇列的資源帳戶;按一下 [ **新增**，然後按一下 [ **新增**> 。</span><span class="sxs-lookup"><span data-stu-id="b9a10-116">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="b9a10-117"> (代理人收到來電時，會看到資源帳戶名稱。) </span><span class="sxs-lookup"><span data-stu-id="b9a10-117">(Agents will see the resource account name when they receive an incoming call.)</span></span>

3. <span data-ttu-id="b9a10-118">選擇支援 [的語言](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="b9a10-118">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="b9a10-119">如果您啟用語音提示，系統產生的語音提示和語音信箱 (會) 。</span><span class="sxs-lookup"><span data-stu-id="b9a10-119">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="b9a10-120">佇列中保留的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="b9a10-120">Greetings and music on hold in queue</span></span>

<span data-ttu-id="b9a10-121">指定當來電者抵達佇列時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="b9a10-121">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="b9a10-122">您必須上傳包含您想要播放的問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="b9a10-122">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span>

<span data-ttu-id="b9a10-123">當來電者在佇列中保留時，Teams 會提供預設音樂。</span><span class="sxs-lookup"><span data-stu-id="b9a10-123">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="b9a10-124">如果您想要播放特定的音訊檔案，請選擇播放音訊檔案並上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="b9a10-124">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a10-125">上傳的錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="b9a10-125">The uploaded recording can be no larger than 5 MB.</span></span>
> <span data-ttu-id="b9a10-126">Teams 通話佇列中提供的預設音樂，不含貴組織支付的任何版稅。</span><span class="sxs-lookup"><span data-stu-id="b9a10-126">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> 

## <a name="call-agents"></a><span data-ttu-id="b9a10-127">通話代理人</span><span class="sxs-lookup"><span data-stu-id="b9a10-127">Call agents</span></span>

<span data-ttu-id="b9a10-128">檢查 [將代理人新加入通話佇列的先決條件](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="b9a10-128">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="b9a10-130">Teams 頻道</span><span class="sxs-lookup"><span data-stu-id="b9a10-130">Teams channel</span></span>

<span data-ttu-id="b9a10-131">您可以透過 Teams 頻道新增最多 200 個代理程式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-131">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="b9a10-132">如果您想要使用 Teams 頻道 [來管理](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)佇列，請選取 [選擇團隊 **選項** ，然後按一下 [ **新增頻道**> 。</span><span class="sxs-lookup"><span data-stu-id="b9a10-132">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="b9a10-133">搜尋您想要使用的團隊，選取該團隊，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="b9a10-133">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="b9a10-134">選取您想要使用的頻道，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="b9a10-134">Select the channel that you want to use and click **Apply**.</span></span>

<span data-ttu-id="b9a10-135">使用 Teams 頻道進行通話佇列時，支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="b9a10-135">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="b9a10-136">Microsoft Teams Windows 用戶端</span><span class="sxs-lookup"><span data-stu-id="b9a10-136">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="b9a10-137">Microsoft Teams Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="b9a10-137">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="b9a10-138">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="b9a10-138">Users and groups</span></span>

<span data-ttu-id="b9a10-139">您可以個別新增最多 20 個代理程式，並透過群組新增最多 200 個代理程式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-139">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="b9a10-140">如果您想要將個別使用者或群組新排入佇列，請選取選擇 **使用者和群組** 選項。</span><span class="sxs-lookup"><span data-stu-id="b9a10-140">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="b9a10-141">若要將使用者新增到佇列，請按一下 **[新增** 使用者，搜尋使用者，按一下 [ **新增**，然後按一下 **[新增**> 。</span><span class="sxs-lookup"><span data-stu-id="b9a10-141">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="b9a10-142">若要將群組新增到佇列，請按一下 [ **新增** 群組、搜尋群組、按一下 [ **新增**」，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="b9a10-142">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="b9a10-143">您可以使用通訊群組清單、安全性群組和 Microsoft 365 群組或 Microsoft Teams 團隊。</span><span class="sxs-lookup"><span data-stu-id="b9a10-143">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a10-144">新加入群組的使用者最多可能需要八小時，才能第一次通話到達。</span><span class="sxs-lookup"><span data-stu-id="b9a10-144">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="b9a10-145">通話路由</span><span class="sxs-lookup"><span data-stu-id="b9a10-145">Call routing</span></span>

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="b9a10-147">**會議模式** 可大幅縮短在代理人接受通話後，來電者與代理人連上的時間量。</span><span class="sxs-lookup"><span data-stu-id="b9a10-147">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="b9a10-148">若要讓會議模式運作，通話佇列中的代理人必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="b9a10-148">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="b9a10-149">最新版的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="b9a10-149">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="b9a10-150">Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="b9a10-150">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="b9a10-151">代理人的 Teams 帳戶必須設定為 Teams-only 模式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-151">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="b9a10-152">不符合要求的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="b9a10-152">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="b9a10-153">如果您的代理人都使用相容的用戶端，我們建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-153">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a10-154">如果電話從已啟用位置路由的直接路由閘道路由至佇列，則不支援會議模式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-154">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

<span data-ttu-id="b9a10-155">**路由方法** 會決定代理程式從佇列接收來電的順序。</span><span class="sxs-lookup"><span data-stu-id="b9a10-155">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="b9a10-156">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="b9a10-156">Choose from these options:</span></span>

- <span data-ttu-id="b9a10-157">**話務員路由** 會同時響鈴佇列中的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-157">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="b9a10-158">第一個接電話的代理人會接到電話。</span><span class="sxs-lookup"><span data-stu-id="b9a10-158">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="b9a10-159">**連續路由** 會以呼叫代理程式清單中指定的順序，一個接一個地撥打所有 **呼叫** 代理程式。</span><span class="sxs-lookup"><span data-stu-id="b9a10-159">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="b9a10-160">如果客服人員關閉或不接電話，來電會撥打下一個代理人，並嘗試所有代理人，直到被接回或打出電話。</span><span class="sxs-lookup"><span data-stu-id="b9a10-160">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="b9a10-161">**輪循** 機制會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的通話。</span><span class="sxs-lookup"><span data-stu-id="b9a10-161">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="b9a10-162">在內入銷售環境中，這一點可能相當理想，以確保所有通話代理人之間享有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="b9a10-162">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="b9a10-163">**最長空閒** 時間會路由每個通話給閒置時間最長的代理人。</span><span class="sxs-lookup"><span data-stu-id="b9a10-163">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="b9a10-164">如果代理的目前狀態為可用，或其目前狀態為離開狀態少於 10 分鐘，則視為閒置狀態。</span><span class="sxs-lookup"><span data-stu-id="b9a10-164">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="b9a10-165">目前狀態超過 10 分鐘的代理人不會被視為閒置狀態，且在將目前狀態變更為可用之前，將不符合接聽通話資格。</span><span class="sxs-lookup"><span data-stu-id="b9a10-165">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

![路由、退出宣告和通知時間設定螢幕擷取畫面](media/call-queue-presence-agents-time.png)


<span data-ttu-id="b9a10-167">**目前狀態路由** 會使用呼叫代理程式的可用性狀態，判斷該代理人是否應該包含在所選路由方法的通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="b9a10-167">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="b9a10-168">其可用性狀態設為可用的通話 **代理人會包含在** 通話路由清單中，而且可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="b9a10-168">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="b9a10-169">其可用性狀態設定為任何其他狀態的代理人會排除在通話路由清單中，且不會接聽來電，直到其可用性狀態變更回可用 **。**</span><span class="sxs-lookup"><span data-stu-id="b9a10-169">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="b9a10-170">您可以使用任何路由方法啟用目前狀態型通話路由。</span><span class="sxs-lookup"><span data-stu-id="b9a10-170">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="b9a10-171">如果代理人選擇不接聽來電，無論他們的可用性狀態設定為什麼，通話路由清單也不會包含他們。</span><span class="sxs-lookup"><span data-stu-id="b9a10-171">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9a10-172">啟用目前狀態路由時，使用商務用 Skype 用戶端的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="b9a10-172">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="b9a10-173">如果您有使用商務用 Skype 的代理人，請勿啟用目前狀態型通話路由。</span><span class="sxs-lookup"><span data-stu-id="b9a10-173">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

<span data-ttu-id="b9a10-174">**代理人通知** 時間會指定在佇列將通話重新導向至下一個代理人之前，代理人的電話會響鈴多久。</span><span class="sxs-lookup"><span data-stu-id="b9a10-174">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

<span data-ttu-id="b9a10-175">建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="b9a10-175">The following settings are recommended:</span></span>

- <span data-ttu-id="b9a10-176">**會議模式** 至 **自動**</span><span class="sxs-lookup"><span data-stu-id="b9a10-176">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="b9a10-177">**將路由方法\*\*\*\*路由到 Round robin** 或 **最長閒置時間**</span><span class="sxs-lookup"><span data-stu-id="b9a10-177">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="b9a10-178">**目前狀態路由至** **On**</span><span class="sxs-lookup"><span data-stu-id="b9a10-178">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="b9a10-179">**代理人警示時間：\*\*\*\*至 20 秒**</span><span class="sxs-lookup"><span data-stu-id="b9a10-179">**Agent alert time:** to **20 seconds**</span></span>

> [!NOTE]
> <span data-ttu-id="b9a10-180">如果未啟用目前狀態路由，且佇列中有多個通話，系統會同時向代理人顯示這些通話，而不管其目前狀態如何。</span><span class="sxs-lookup"><span data-stu-id="b9a10-180">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="b9a10-181">這將會有多個通知給代理人，尤其是當某些代理人沒有接聽他們收到的初始通話時。</span><span class="sxs-lookup"><span data-stu-id="b9a10-181">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="b9a10-182">呼叫溢出處理</span><span class="sxs-lookup"><span data-stu-id="b9a10-182">Call overflow handling</span></span>

![通話溢出設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

<span data-ttu-id="b9a10-184">**佇列中的通話上限** 會指定在任何指定時間可在佇列中等候的通話數上限。</span><span class="sxs-lookup"><span data-stu-id="b9a10-184">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="b9a10-185">預設值為 50，但範圍從 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="b9a10-185">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="b9a10-186">達到此限制時，通話會依照達到通話次數上限設定所 **指定的方式處理** 。</span><span class="sxs-lookup"><span data-stu-id="b9a10-186">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="b9a10-187">您可以選擇中斷通話，或重新導向到任何通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="b9a10-187">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="b9a10-188">例如，您可能讓來電者為佇列中的代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b9a10-188">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="b9a10-189">如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b9a10-189">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a10-190">如果通話次數上限設為 0，則問候語訊息將不會播放。</span><span class="sxs-lookup"><span data-stu-id="b9a10-190">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="b9a10-191">通話超時處理</span><span class="sxs-lookup"><span data-stu-id="b9a10-191">Call timeout handling</span></span>

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

<span data-ttu-id="b9a10-193">**通話超時：最長等待時間** 會指定通話在重新導向或中斷連接前，在佇列中可以保留的最大時間。</span><span class="sxs-lookup"><span data-stu-id="b9a10-193">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="b9a10-194">您可以指定 0 秒到 45 分鐘的值。</span><span class="sxs-lookup"><span data-stu-id="b9a10-194">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="b9a10-195">您可以選擇中斷通話，或重新導向到其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="b9a10-195">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="b9a10-196">例如，您可能讓來電者為佇列中的代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b9a10-196">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="b9a10-197">如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b9a10-197">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="b9a10-198">當您已選取通話超時選項時，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="b9a10-198">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="caller-id-for-outbound-calls"></a><span data-ttu-id="b9a10-199">外線通話的本機號碼</span><span class="sxs-lookup"><span data-stu-id="b9a10-199">Caller ID for outbound calls</span></span>

<span data-ttu-id="b9a10-200">由於通話佇列中的代理人可能會撥出以傳回客戶電話，請考慮將通話佇列成員的本機號碼設定為適當的自動語音機服務號碼。</span><span class="sxs-lookup"><span data-stu-id="b9a10-200">Since agents in a call queue may dial out to return a customer call, consider setting the caller ID for members of a call queue to the service number of an appropriate auto attendant.</span></span> <span data-ttu-id="b9a10-201">請參閱 [在 Microsoft Teams 中管理來電](caller-id-policies.md) 顯示政策以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="b9a10-201">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="b9a10-202">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="b9a10-202">Supported clients</span></span>

<span data-ttu-id="b9a10-203">通話佇列中的通話代理程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="b9a10-203">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="b9a10-204">商務用 Skype 桌面用戶端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-204">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b9a10-205">Lync 桌面用戶端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-205">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b9a10-206">Microsoft Teams 支援的所有 IP 電話型號。</span><span class="sxs-lookup"><span data-stu-id="b9a10-206">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="b9a10-207">請參閱 [取得商務用 Skype Online 的手機](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="b9a10-207">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="b9a10-208">Mac 商務用 Skype 用戶端 (版本 16.8.196 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-208">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="b9a10-209">Android 商務用 Skype 用戶端 (版本 6.16.0.9 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-209">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="b9a10-210">iPhone 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-210">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="b9a10-211">iPad 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-211">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="b9a10-212">Microsoft Teams Windows 用戶端 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="b9a10-212">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="b9a10-213">Microsoft Teams Mac 用戶端</span><span class="sxs-lookup"><span data-stu-id="b9a10-213">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="b9a10-214">Microsoft Teams iPhone 應用程式</span><span class="sxs-lookup"><span data-stu-id="b9a10-214">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="b9a10-215">Microsoft Teams Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="b9a10-215">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9a10-216">指派直接路由號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 電話代理。</span><span class="sxs-lookup"><span data-stu-id="b9a10-216">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="b9a10-217">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b9a10-217">Call queue cmdlets</span></span>

<span data-ttu-id="b9a10-218">您也可以使用 Windows PowerShell 建立和設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="b9a10-218">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="b9a10-219">以下是您用於管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9a10-219">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="b9a10-220">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9a10-220">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="b9a10-221">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9a10-221">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="b9a10-222">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9a10-222">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="b9a10-223">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9a10-223">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="b9a10-224">相關主題</span><span class="sxs-lookup"><span data-stu-id="b9a10-224">Related topics</span></span>

[<span data-ttu-id="b9a10-225">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="b9a10-225">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b9a10-226">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="b9a10-226">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="b9a10-227">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="b9a10-227">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b9a10-228">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="b9a10-228">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="b9a10-229">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="b9a10-229">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
