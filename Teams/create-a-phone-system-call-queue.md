---
title: 在 Microsoft Teams
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
description: 瞭解如何在 Microsoft Teams 中為大型組織設定通話佇列，提供問候訊息、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: b3a17343b21f0dcb35ba2f2d6bb99178bdafffd0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420848"
---
# <a name="create-a-call-queue"></a><span data-ttu-id="d6c87-103">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="d6c87-103">Create a call queue</span></span>

<span data-ttu-id="d6c87-104">通話佇列提供將來電者路由給組織中可協助處理特定問題或問題的人的方法。</span><span class="sxs-lookup"><span data-stu-id="d6c87-104">Call queues provide a method of routing callers to people in your organization who can help with a particular issue or question.</span></span> <span data-ttu-id="d6c87-105">通話會一次一次分散給佇列中 (稱為 *代理人) 。*</span><span class="sxs-lookup"><span data-stu-id="d6c87-105">Calls are distributed one at a time to the people in the queue (who are known as *agents*).</span></span> 

> [!TIP]
> <span data-ttu-id="d6c87-106">本文適用于大型組織。</span><span class="sxs-lookup"><span data-stu-id="d6c87-106">This article is for large organizations.</span></span> <span data-ttu-id="d6c87-107">如果貴組織是小型企業，請改為閱讀建立通話 [佇列 - 小型企業](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 教學課程。</span><span class="sxs-lookup"><span data-stu-id="d6c87-107">If your organization is a small business, read [Create a call queue - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) instead.</span></span>

<span data-ttu-id="d6c87-108">通話佇列提供：</span><span class="sxs-lookup"><span data-stu-id="d6c87-108">Call queues provide:</span></span>

- <span data-ttu-id="d6c87-109">問候訊息。</span><span class="sxs-lookup"><span data-stu-id="d6c87-109">A greeting message.</span></span>

- <span data-ttu-id="d6c87-110">當其他人在佇列中等候時播放音樂。</span><span class="sxs-lookup"><span data-stu-id="d6c87-110">Music while people are waiting on hold in a queue.</span></span>

- <span data-ttu-id="d6c87-111">呼叫路由 - 在 *FIFO (* 中，) 呼叫路由 - 給代理人。</span><span class="sxs-lookup"><span data-stu-id="d6c87-111">Call routing - in *First In, First Out* (FIFO) order - to agents.</span></span>

- <span data-ttu-id="d6c87-112">處理佇列溢出和超時的選項。</span><span class="sxs-lookup"><span data-stu-id="d6c87-112">Handling options for queue overflow and timeout.</span></span>

<span data-ttu-id="d6c87-113">請務必先閱讀自動Teams[](plan-auto-attendant-call-queue.md)和通話佇列的規劃，並遵循開始使用的步驟，然後再遵循本文[](plan-auto-attendant-call-queue.md#getting-started)中的程式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-113">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="d6c87-114">影片示範</span><span class="sxs-lookup"><span data-stu-id="d6c87-114">Video demonstration</span></span>

<span data-ttu-id="d6c87-115">這段影片顯示如何在 Teams 中建立通話佇列的基本Teams。</span><span class="sxs-lookup"><span data-stu-id="d6c87-115">This video shows a basic example of how to create a call queue in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a><span data-ttu-id="d6c87-116">建立通話佇列</span><span class="sxs-lookup"><span data-stu-id="d6c87-116">Create the call queue</span></span>

<span data-ttu-id="d6c87-117">若要設定通話佇列，請在系統管理中心Teams[**語音** 與通話佇列>，然後按一下 [**新增**。</span><span class="sxs-lookup"><span data-stu-id="d6c87-117">To set up a call queue, in the Teams admin center, expand **Voice**, click **Call queues**, and then click **Add**.</span></span>

<span data-ttu-id="d6c87-118">輸入通話佇列的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6c87-118">Type a name for the call queue.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="d6c87-119">資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d6c87-119">Resource accounts</span></span>

![資源帳戶設定螢幕擷取畫面](media/call-queue-name-language.png)

<span data-ttu-id="d6c87-121">按一下 **[新增帳戶**，搜尋要用於此通話佇列的資源帳戶;按一下 [ **新增**，然後按一下 [ **新增**> 。</span><span class="sxs-lookup"><span data-stu-id="d6c87-121">Click **Add accounts**, search for the resource account that you want to use with this call queue, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="d6c87-122"> (代理人收到來電時，會看到資源帳戶名稱。) </span><span class="sxs-lookup"><span data-stu-id="d6c87-122">(Agents will see the resource account name when they receive an incoming call.)</span></span>

### <a name="assign-calling-id"></a><span data-ttu-id="d6c87-123">指派通話識別碼</span><span class="sxs-lookup"><span data-stu-id="d6c87-123">Assign calling ID</span></span>

![通話識別碼設定螢幕擷取畫面](media/call-queue-assign-calling-id.png)

<span data-ttu-id="d6c87-125">如果您打算為呼叫代理Teams通道，您可以指定一或多個具有電話號碼的資源帳戶，為代理人指派外發本機號碼號碼。</span><span class="sxs-lookup"><span data-stu-id="d6c87-125">If you plan to use a Teams channel for your call agents, you can assign an outbound caller ID number for the agents by specifying one or more resource accounts with a phone number.</span></span>

<span data-ttu-id="d6c87-126">按一下 **[新增**，搜尋您想要允許代理人在撥打外線通話時用於通話識別碼的資源帳戶;按一下 [ **新增**，然後按一下 [ **新增**> 。</span><span class="sxs-lookup"><span data-stu-id="d6c87-126">Click **Add**, search for the resource accounts that you want to allow agents to for calling ID purposes when making outbound calls, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="d6c87-127">如果您不是使用 Teams通道來控制代理人成員資格，請考慮將通話佇列成員的本機號碼直接設定為通話佇列的服務號碼或適當的自動語音回應。</span><span class="sxs-lookup"><span data-stu-id="d6c87-127">If you are not using a Teams channel to control agent membership, consider directly setting the caller ID for members of the call queue to the service number of the call queue or appropriate auto attendant.</span></span> <span data-ttu-id="d6c87-128">請參閱[在 Microsoft Teams](caller-id-policies.md)管理本機號碼政策以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="d6c87-128">See [Manage caller ID policies in Microsoft Teams](caller-id-policies.md) for more information.</span></span>

## <a name="language"></a><span data-ttu-id="d6c87-129">語言</span><span class="sxs-lookup"><span data-stu-id="d6c87-129">Language</span></span>

![語言設定螢幕擷取畫面](media/call-queue-language.png)

<span data-ttu-id="d6c87-131">選擇支援 [的語言](create-a-phone-system-call-queue-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c87-131">Choose a [supported language](create-a-phone-system-call-queue-languages.md).</span></span> <span data-ttu-id="d6c87-132">如果您啟用語音提示，系統產生的語音提示和語音信箱 (語音信箱) 。</span><span class="sxs-lookup"><span data-stu-id="d6c87-132">This language will be used for system-generated voice prompts and voicemail transcription (if you enable them).</span></span>

## <a name="greetings-and-music-on-hold-in-queue"></a><span data-ttu-id="d6c87-133">佇列中保留的問候語和音樂</span><span class="sxs-lookup"><span data-stu-id="d6c87-133">Greetings and music on hold in queue</span></span>

![佇列設定中問候語和音樂保留的螢幕擷取畫面](media/call-queue-greetings-music.png)

<span data-ttu-id="d6c87-135">指定當來電者抵達佇列時，是否要播放問候語。</span><span class="sxs-lookup"><span data-stu-id="d6c87-135">Specify if you want to play a greeting to callers when they arrive in the queue.</span></span> <span data-ttu-id="d6c87-136">您必須上傳包含您想要播放的問候語的 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="d6c87-136">You must upload an MP3, WAV, or WMA file containing the greeting that you want to play.</span></span> <span data-ttu-id="d6c87-137">上傳的錄製不能大於 5 MB。</span><span class="sxs-lookup"><span data-stu-id="d6c87-137">The uploaded recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="d6c87-138">Teams在佇列中保留來電者時，提供預設音樂。</span><span class="sxs-lookup"><span data-stu-id="d6c87-138">Teams provides default music to callers while they are on hold in a queue.</span></span> <span data-ttu-id="d6c87-139">在通話佇列Teams中提供的預設音樂，不含貴組織支付的任何版稅。</span><span class="sxs-lookup"><span data-stu-id="d6c87-139">The default music supplied in Teams call queues is free of any royalties payable by your organization.</span></span> <span data-ttu-id="d6c87-140">如果您想要播放特定的音訊檔案，請選擇播放音訊檔案並上傳 MP3、WAV 或 WMA 檔案。</span><span class="sxs-lookup"><span data-stu-id="d6c87-140">If you want to play a specific audio file, choose **Play an audio file** and upload an MP3, WAV, or WMA file.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c87-141">您負責獨立清除及保護使用任何音樂或音訊檔案與您的Microsoft Teams許可權， 其中可能包含來自所有相關權利擁有者之任何音樂、音效、音訊、品牌、名稱及其他內容中的智慧財產權及其他權利，包括美術家、參與者、演出者、音樂人、歌曲作者、作曲者、記錄標籤、音樂發行者、聯合企業、版權協會、集體管理組織，以及擁有、控制或授權音樂著作權、音效、音訊和其他智慧財產權的其他各方。</span><span class="sxs-lookup"><span data-stu-id="d6c87-141">You are responsible for independently clearing and securing all necessary rights and permissions to use any music or audio file with your Microsoft Teams service, which may include intellectual property and other rights in any music, sound effects, audio, brands, names, and other content in the audio file from all relevant rights holders, which may include artists, actors, performers, musicians, songwriters, composers, record labels, music publishers, unions, guilds, rights societies, collective management organizations and any other parties who own, control or license the music copyrights, sound effects, audio and other intellectual property rights.</span></span>

## <a name="call-agents"></a><span data-ttu-id="d6c87-142">通話代理人</span><span class="sxs-lookup"><span data-stu-id="d6c87-142">Call agents</span></span>

<span data-ttu-id="d6c87-143">檢查 [將代理人新加入通話佇列的先決條件](plan-auto-attendant-call-queue.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="d6c87-143">Review the [prerequisites for adding agents to a call queue](plan-auto-attendant-call-queue.md#prerequisites).</span></span>

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a><span data-ttu-id="d6c87-145">Teams頻道</span><span class="sxs-lookup"><span data-stu-id="d6c87-145">Teams channel</span></span>

<span data-ttu-id="d6c87-146">您可以透過頻道新增最多 200 Teams代理。</span><span class="sxs-lookup"><span data-stu-id="d6c87-146">You can add up to 200 agents via a Teams channel.</span></span>

<span data-ttu-id="d6c87-147">如果您想要使用頻道 [Teams](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)佇列，請選取 [選擇團隊選項，然後按一下 [**新增頻道**> 。 </span><span class="sxs-lookup"><span data-stu-id="d6c87-147">If you want to [use a Teams channel to manage the queue](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e), select the **Choose a team** option and click **Add a channel**.</span></span> <span data-ttu-id="d6c87-148">搜尋您想要使用的團隊，選取該團隊，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="d6c87-148">Search for the team that you want to use, select it, and click **Add**.</span></span> <span data-ttu-id="d6c87-149">選取您想要使用的頻道，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="d6c87-149">Select the channel that you want to use and click **Apply**.</span></span> <span data-ttu-id="d6c87-150">您必須是團隊的成員，或是頻道的建立者或擁有者。</span><span class="sxs-lookup"><span data-stu-id="d6c87-150">You must be a member of the team or the creator of or an owner of the channel.</span></span>

<span data-ttu-id="d6c87-151">在通話佇列使用Teams支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="d6c87-151">The following clients are supported when using a Teams channel for call queues:</span></span> 

  - <span data-ttu-id="d6c87-152">Microsoft Teams Windows用戶端</span><span class="sxs-lookup"><span data-stu-id="d6c87-152">Microsoft Teams Windows client</span></span>
  - <span data-ttu-id="d6c87-153">Microsoft TeamsMac 用戶端</span><span class="sxs-lookup"><span data-stu-id="d6c87-153">Microsoft Teams Mac client</span></span>

##### <a name="users-and-groups"></a><span data-ttu-id="d6c87-154">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="d6c87-154">Users and groups</span></span>

<span data-ttu-id="d6c87-155">您可以個別新增最多 20 個代理程式，並透過群組最多新增 200 個代理程式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-155">You can add up to 20 agents individually and up to 200 agents via groups.</span></span>

<span data-ttu-id="d6c87-156">如果您想要將個別使用者或群組新排入佇列，請選取選擇 **使用者和群組** 選項。</span><span class="sxs-lookup"><span data-stu-id="d6c87-156">If you want to add individual users or groups to the queue, select the **Choose users and groups** option.</span></span> 

<span data-ttu-id="d6c87-157">若要將使用者新增到佇列，請按一下 **[新增** 使用者，搜尋使用者，按一下 [ **新增**，然後按一下 **[新增**> 。</span><span class="sxs-lookup"><span data-stu-id="d6c87-157">To add a user to the queue, click **Add users**, search for the user, click **Add**, and then click **Add**.</span></span>

<span data-ttu-id="d6c87-158">若要將群組新增到佇列，請按一下 [ **新增** 群組、搜尋群組、按一下 [ **新增**」，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="d6c87-158">To add a group to the queue, click **Add groups**, search for the group, click **Add**, and then click **Add**.</span></span> <span data-ttu-id="d6c87-159">您可以使用通訊群組清單、安全性群組及Microsoft 365群組或Microsoft Teams小組。</span><span class="sxs-lookup"><span data-stu-id="d6c87-159">You can use distribution lists, security groups, and Microsoft 365 groups or Microsoft Teams teams.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c87-160">新使用者新加入群組最多可能需要八小時，才能第一次通話到達。</span><span class="sxs-lookup"><span data-stu-id="d6c87-160">New users added to a group can take up to eight hours for their first call to arrive.</span></span>

## <a name="call-routing"></a><span data-ttu-id="d6c87-161">通話路由</span><span class="sxs-lookup"><span data-stu-id="d6c87-161">Call routing</span></span>

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

<span data-ttu-id="d6c87-163">**會議模式** 可大幅縮短在代理人接受通話後，來電者與代理人連上的時間量。</span><span class="sxs-lookup"><span data-stu-id="d6c87-163">**Conference mode** significantly reduces the amount of time it takes for a caller to be connected to an agent, after the agent accepts the call.</span></span> <span data-ttu-id="d6c87-164">若要讓會議模式運作，通話佇列中的代理人必須使用下列其中一個用戶端：</span><span class="sxs-lookup"><span data-stu-id="d6c87-164">For conference mode to work, agents in the call queue must use one of the following clients:</span></span>

  - <span data-ttu-id="d6c87-165">最新版桌面Microsoft Teams Android App 或 iOS 應用程式</span><span class="sxs-lookup"><span data-stu-id="d6c87-165">The latest version of the Microsoft Teams desktop client, Android app, or iOS app</span></span>
  - <span data-ttu-id="d6c87-166">Microsoft Teams 1449/1.0.94.2020051601 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d6c87-166">Microsoft Teams phone version 1449/1.0.94.2020051601 or later</span></span>
  
<span data-ttu-id="d6c87-167">代理人Teams帳戶必須設為Teams模式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-167">Agents' Teams accounts need to be set to Teams-only mode.</span></span> <span data-ttu-id="d6c87-168">不符合要求的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="d6c87-168">Agents who don't meet the requirements aren't included in the call routing list.</span></span> <span data-ttu-id="d6c87-169">如果您的代理人都使用相容的用戶端，我們建議您為通話佇列啟用會議模式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-169">We recommend enabling conference mode for your call queues if your agents are all using compatible clients.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c87-170">如果電話從已啟用位置路由的直接路由閘道路由至佇列，則不支援會議模式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-170">Conference mode is not supported if phone calls are routed to the queue from a Direct Routing gateway that is enabled for Location Based Routing.</span></span>

> [!TIP]
> <span data-ttu-id="d6c87-171">建議 **將會議模式\*\*\*\*設定為** 自動。</span><span class="sxs-lookup"><span data-stu-id="d6c87-171">Setting **Conference mode** to **Auto** is the recommended setting.</span></span>

<span data-ttu-id="d6c87-172">**路由方法** 會決定代理程式從佇列接收來電的順序。</span><span class="sxs-lookup"><span data-stu-id="d6c87-172">**Routing method** determines the order in which agents receive calls from the queue.</span></span> <span data-ttu-id="d6c87-173">從這些選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="d6c87-173">Choose from these options:</span></span>

- <span data-ttu-id="d6c87-174">**話務員路由** 會同時響鈴佇列中的所有代理程式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-174">**Attendant routing** rings all agents in the queue at the same time.</span></span> <span data-ttu-id="d6c87-175">第一個接電話的代理人會接到電話。</span><span class="sxs-lookup"><span data-stu-id="d6c87-175">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="d6c87-176">**連續路由** 會以呼叫代理程式清單中指定的順序，一個接一個地撥打所有 **呼叫** 代理程式。</span><span class="sxs-lookup"><span data-stu-id="d6c87-176">**Serial routing** rings all call agents one by one in the order specified in the **Call agents** list.</span></span> <span data-ttu-id="d6c87-177">如果客服人員關閉或不接電話，來電會撥打給下一個代理人，並嘗試所有代理人，直到被接回或打出電話。</span><span class="sxs-lookup"><span data-stu-id="d6c87-177">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>

- <span data-ttu-id="d6c87-178">**輪循** 機制會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的通話。</span><span class="sxs-lookup"><span data-stu-id="d6c87-178">**Round robin** balances the routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="d6c87-179">在內入銷售環境中，這一點可能相當理想，以確保所有通話代理人之間享有同等的機會。</span><span class="sxs-lookup"><span data-stu-id="d6c87-179">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

- <span data-ttu-id="d6c87-180">**最長空閒** 時間會路由每個通話給閒置時間最長的代理人。</span><span class="sxs-lookup"><span data-stu-id="d6c87-180">**Longest idle** routes each call to the agent who has been idle the longest time.</span></span> <span data-ttu-id="d6c87-181">如果代理的目前狀態為可用，或其目前狀態為離開狀態少於 10 分鐘，則視為閒置狀態。</span><span class="sxs-lookup"><span data-stu-id="d6c87-181">An agent is considered idle if their presence state is Available or if their presence state has been Away for less than 10 minutes.</span></span> <span data-ttu-id="d6c87-182">目前狀態超過 10 分鐘的代理人不會被視為閒置狀態，且在將目前狀態變更為可用之前，將不符合接聽電話資格。</span><span class="sxs-lookup"><span data-stu-id="d6c87-182">Agents whose presence state has been Away for more than 10 minutes are not considered idle and will not be eligible to receive calls until they change their presence to Available.</span></span> 

> [!TIP]
> <span data-ttu-id="d6c87-183">建議 **將路由方法** 設定 **為 Round robin** 或 **最長** 閒置時間。</span><span class="sxs-lookup"><span data-stu-id="d6c87-183">Setting **Routing Method** to **Round robin** or **Longest idle** is the recommended setting.</span></span>

![路由、退出宣告和通知時間設定螢幕擷取畫面](media/call-queue-presence-agents-time.png)

<span data-ttu-id="d6c87-185">**目前狀態路由** 會使用呼叫代理程式的可用性狀態來判斷代理人是否應該包含在所選路由方法的呼叫路由清單中。</span><span class="sxs-lookup"><span data-stu-id="d6c87-185">**Presence-based routing** uses the availability status of call agents to determine whether an agent should be included in the call routing list for the selected routing method.</span></span> <span data-ttu-id="d6c87-186">其可用性狀態設為可用的通話 **代理人會包含在** 通話路由清單中，而且可以接聽來電。</span><span class="sxs-lookup"><span data-stu-id="d6c87-186">Call agents whose availability status is set to **Available** are included in the call routing list and can receive calls.</span></span> <span data-ttu-id="d6c87-187">其可用性狀態設定為任何其他狀態的代理人會排除在通話路由清單中，且不會接聽來電，直到其可用性狀態變更回可用 **。**</span><span class="sxs-lookup"><span data-stu-id="d6c87-187">Agents whose availability status is set to any other status are excluded from the call routing list and won't receive calls until their availability status changes back to **Available**.</span></span> 

<span data-ttu-id="d6c87-188">您可以使用任何路由方法啟用目前狀態型通話路由。</span><span class="sxs-lookup"><span data-stu-id="d6c87-188">You can enable presence-based call routing with any of the routing methods.</span></span>

<span data-ttu-id="d6c87-189">如果代理人選擇不接聽來電，無論他們的可用性狀態設定為什麼，他們將不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="d6c87-189">If an agent opts out of getting calls, they won't be included in the call routing list regardless of what their availability status is set to.</span></span> 

> [!NOTE]
> <span data-ttu-id="d6c87-190">當 **選取了最** 長時間空閒作為路由方法時，需要以目前狀態為基礎的路由並自動啟用，即使目前狀態型路由切換開關會關閉且呈灰色。</span><span class="sxs-lookup"><span data-stu-id="d6c87-190">When **Longest idle** is selected as the routing method, presence-based routing is required and automatically enabled even though the Presence-based routing toggle will be **Off** and grayed out.</span></span>
>
> <span data-ttu-id="d6c87-191">如果未啟用目前狀態路由，且佇列中有多個通話，系統會同時向代理人顯示這些通話，而不管其目前狀態如何。</span><span class="sxs-lookup"><span data-stu-id="d6c87-191">If presence-based routing is not enabled and there are multiple calls in the queue, the system will present these calls simultaneously to the agents regardless of their presence status.</span></span> <span data-ttu-id="d6c87-192">這將會有多個通知給代理人，尤其是當某些代理人沒有接聽他們收到的初始通話時。</span><span class="sxs-lookup"><span data-stu-id="d6c87-192">This will result in multiple call notifications to agents, particularly if some agents don’t answer the initial call presented to them.</span></span>
> 
> <span data-ttu-id="d6c87-193">啟用目前狀態商務用 Skype用戶端的代理人不會包含在通話路由清單中。</span><span class="sxs-lookup"><span data-stu-id="d6c87-193">Agents who use the Skype for Business client aren't included in the call routing list when presence-based routing is enabled.</span></span> <span data-ttu-id="d6c87-194">如果您有使用電話商務用 Skype，請勿啟用目前狀態型通話路由。</span><span class="sxs-lookup"><span data-stu-id="d6c87-194">If you have agents who use Skype for Business, don't enable presence-based call routing.</span></span>

> [!TIP]
> <span data-ttu-id="d6c87-195">建議 **將目前狀態路由設定** 為 **On。**</span><span class="sxs-lookup"><span data-stu-id="d6c87-195">Setting **Presence-based routing** to **On** is the recommended setting.</span></span>

<span data-ttu-id="d6c87-196">**代理人通知** 時間會指定在佇列將通話重新導向至下一個代理人之前，代理人的電話會響鈴多久。</span><span class="sxs-lookup"><span data-stu-id="d6c87-196">**Agent alert time** specifies how long an agent's phone will ring before the queue redirects the call to the next agent.</span></span>

> [!TIP]
> <span data-ttu-id="d6c87-197">建議 **將代理程式警示時間** 設定為 **20** 秒。</span><span class="sxs-lookup"><span data-stu-id="d6c87-197">Setting **Agent alert time** to **20 seconds** is the recommended setting.</span></span>

## <a name="call-overflow-handling"></a><span data-ttu-id="d6c87-198">呼叫溢出處理</span><span class="sxs-lookup"><span data-stu-id="d6c87-198">Call overflow handling</span></span>

![通話溢出設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

<span data-ttu-id="d6c87-200">**佇列中的通話上限** 會指定在任何指定時間可在佇列中等候的通話數上限。</span><span class="sxs-lookup"><span data-stu-id="d6c87-200">**Maximum calls in the queue** specifies the maximum number of calls that can wait in the queue at any given time.</span></span> <span data-ttu-id="d6c87-201">預設值為 50，但範圍為 0 到 200。</span><span class="sxs-lookup"><span data-stu-id="d6c87-201">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="d6c87-202">達到此限制時，通話會依照達到通話次數上限設定所 **指定的方式處理** 。</span><span class="sxs-lookup"><span data-stu-id="d6c87-202">When this limit is reached, the call is handled as specified by the **When the maximum number of calls is reached** setting.</span></span>

<span data-ttu-id="d6c87-203">您可以選擇中斷通話，或重新導向到任何通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="d6c87-203">You can choose to disconnect the call or redirect it to any of the call routing destinations.</span></span> <span data-ttu-id="d6c87-204">例如，您可能讓來電者為佇列中的代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d6c87-204">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="d6c87-205">如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d6c87-205">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

> [!NOTE]
> <span data-ttu-id="d6c87-206">如果通話次數上限設為 0，則問候語訊息將不會播放。</span><span class="sxs-lookup"><span data-stu-id="d6c87-206">If the maximum number of calls is set to 0 then the greeting message will not play.</span></span>

## <a name="call-timeout-handling"></a><span data-ttu-id="d6c87-207">通話超時處理</span><span class="sxs-lookup"><span data-stu-id="d6c87-207">Call timeout handling</span></span>

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

<span data-ttu-id="d6c87-209">**通話超時：最長等待時間** 會指定通話在重新導向或中斷連接前，在佇列中可以保留的最大時間。</span><span class="sxs-lookup"><span data-stu-id="d6c87-209">**Call Timeout: maximum wait time** specifies the maximum time a call can be on hold in the queue before it is redirected or disconnected.</span></span> <span data-ttu-id="d6c87-210">您可以指定 0 秒到 45 分鐘的值。</span><span class="sxs-lookup"><span data-stu-id="d6c87-210">You can specify a value from 0 seconds to 45 minutes.</span></span>

<span data-ttu-id="d6c87-211">您可以選擇中斷通話，或重新導向到其中一個通話路由目的地。</span><span class="sxs-lookup"><span data-stu-id="d6c87-211">You can choose to disconnect the call or redirect it to one of the call routing destinations.</span></span> <span data-ttu-id="d6c87-212">例如，您可能讓來電者為佇列中的代理人留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="d6c87-212">For example, you might have the caller leave a voicemail for the agents in the queue.</span></span> <span data-ttu-id="d6c87-213">如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d6c87-213">For external transfers, please refer to [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) and the [external phone number transfers - technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) for number formatting.</span></span>

<span data-ttu-id="d6c87-214">當您已選取通話超時選項時，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="d6c87-214">When you have selected your call timeout options, click **Save**.</span></span>

## <a name="summary-of-recommended-call-queue-settings"></a><span data-ttu-id="d6c87-215">建議的通話佇列設定摘要</span><span class="sxs-lookup"><span data-stu-id="d6c87-215">Summary of recommended call queue settings</span></span>

<span data-ttu-id="d6c87-216">建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="d6c87-216">The following settings are recommended:</span></span>

- <span data-ttu-id="d6c87-217">**會議模式** 為 **自動**</span><span class="sxs-lookup"><span data-stu-id="d6c87-217">**Conference mode** to **Auto**</span></span>
- <span data-ttu-id="d6c87-218">**將路由方法\*\*\*\*路由到 Round robin** 或 **最長閒置時間**</span><span class="sxs-lookup"><span data-stu-id="d6c87-218">**Routing method** to **Round robin** or **Longest idle**</span></span>
- <span data-ttu-id="d6c87-219">**目前狀態路由至** **On**</span><span class="sxs-lookup"><span data-stu-id="d6c87-219">**Presence-based routing** to **On**</span></span>
- <span data-ttu-id="d6c87-220">**代理人警示時間：\*\*\*\*至 20 秒**</span><span class="sxs-lookup"><span data-stu-id="d6c87-220">**Agent alert time:** to **20 seconds**</span></span>

## <a name="supported-clients"></a><span data-ttu-id="d6c87-221">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="d6c87-221">Supported clients</span></span>

<span data-ttu-id="d6c87-222">通話佇列中的通話代理程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="d6c87-222">The following clients are supported for call agents in a call queue:</span></span>

  - <span data-ttu-id="d6c87-223">商務用 Skype桌面用戶端 2016 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-223">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d6c87-224">Lync 桌面用戶端 2013 (32 位和 64 位版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-224">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d6c87-225">支援所有 IP 電話Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="d6c87-225">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="d6c87-226">請參閱[取得適用于 商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="d6c87-226">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>
  - <span data-ttu-id="d6c87-227">Mac 商務用 Skype用戶端 (版本 16.8.196 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-227">Mac Skype for Business Client (version 16.8.196 and later)</span></span>
  - <span data-ttu-id="d6c87-228">Android 商務用 Skype用戶端 (版本 6.16.0.9 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-228">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
  - <span data-ttu-id="d6c87-229">iPhone 商務用 Skype用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-229">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d6c87-230">iPad 商務用 Skype用戶端 (版本 6.16.0 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="d6c87-230">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
  - <span data-ttu-id="d6c87-231">Microsoft Teams Windows 32 位 (64 位版本的用戶端) </span><span class="sxs-lookup"><span data-stu-id="d6c87-231">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>
  - <span data-ttu-id="d6c87-232">Microsoft TeamsMac 用戶端</span><span class="sxs-lookup"><span data-stu-id="d6c87-232">Microsoft Teams Mac client</span></span>
  - <span data-ttu-id="d6c87-233">Microsoft Teams[虛擬](/microsoftteams/teams-for-vdi)桌面基礎結構上的 (Windows虛擬桌面、奇思和 V3) </span><span class="sxs-lookup"><span data-stu-id="d6c87-233">Microsoft Teams on [Virtualized Desktop Infrastructure](/microsoftteams/teams-for-vdi) (Windows Virtual Desktop, Citrix, and VMware)</span></span>
  - <span data-ttu-id="d6c87-234">Microsoft Teams iPhone應用程式</span><span class="sxs-lookup"><span data-stu-id="d6c87-234">Microsoft Teams iPhone app</span></span>
  - <span data-ttu-id="d6c87-235">Microsoft TeamsAndroid 應用程式</span><span class="sxs-lookup"><span data-stu-id="d6c87-235">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6c87-236">指派直接路由號碼的通話佇列不支援商務用 Skype、Lync 用戶端或 IP 電話商務用 Skype代理。</span><span class="sxs-lookup"><span data-stu-id="d6c87-236">Call queues that are assigned a direct routing number don't support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="d6c87-237">通話佇列 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d6c87-237">Call queue cmdlets</span></span>

<span data-ttu-id="d6c87-238">您也可以使用Windows PowerShell來建立和設定通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d6c87-238">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="d6c87-239">以下是您用於管理通話佇列的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d6c87-239">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="d6c87-240">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d6c87-240">New-CsCallQueue</span></span>](/powershell/module/skype/new-CsCallQueue)

- [<span data-ttu-id="d6c87-241">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d6c87-241">Set-CsCallQueue</span></span>](/powershell/module/skype/set-CsCallQueue)

- [<span data-ttu-id="d6c87-242">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d6c87-242">Get-CsCallQueue</span></span>](/powershell/module/skype/get-CsCallQueue)

- [<span data-ttu-id="d6c87-243">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="d6c87-243">Remove-CsCallQueue</span></span>](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a><span data-ttu-id="d6c87-244">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6c87-244">Related topics</span></span>

[<span data-ttu-id="d6c87-245">以下是可透過電話系統獲得的功能</span><span class="sxs-lookup"><span data-stu-id="d6c87-245">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d6c87-246">取得服務電話號碼</span><span class="sxs-lookup"><span data-stu-id="d6c87-246">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="d6c87-247">音訊會議與通話方案的適用國家/地區</span><span class="sxs-lookup"><span data-stu-id="d6c87-247">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="d6c87-248">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="d6c87-248">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance)

[<span data-ttu-id="d6c87-249">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="d6c87-249">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
