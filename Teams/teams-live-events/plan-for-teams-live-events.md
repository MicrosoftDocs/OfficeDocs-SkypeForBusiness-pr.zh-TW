---
title: 在 Microsoft Teams 中規劃即時活動
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-meetings
- enabler-strategic
search.appverid: MET150
description: 在本文章中，您將瞭解在 Microsoft Teams 中設定即時活動之前需考量的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1cfcf52531e5a3a0cecafe5310304a299bf04c5
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682402"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a><span data-ttu-id="81a08-103">在 Microsoft Teams 中規劃即時活動</span><span class="sxs-lookup"><span data-stu-id="81a08-103">Plan for live events in Microsoft Teams</span></span>

<span data-ttu-id="81a08-104">當您規劃使用 Teams 即時活動來舉辦組織中的大型會議時，必須先考量幾個因素，再開始進行設定。</span><span class="sxs-lookup"><span data-stu-id="81a08-104">When you're planning Teams live events to hold large meetings in your organization, there are several factors that you need to consider before starting the setup.</span></span>

> [!Note]
> <span data-ttu-id="81a08-p101">如需有關不同平台上 Teams 即時活動的詳細資訊，請參閱 [依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。請參閱 [[為您的組織做好準備]](../prepare-network.md) 以瞭解 Teams 即時活動的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="81a08-p101">For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.</span></span>

## <a name="who-can-attend-create-and-schedule-live-events"></a><span data-ttu-id="81a08-107">哪些人可以參加、建立及排定即時活動？</span><span class="sxs-lookup"><span data-stu-id="81a08-107">Who can attend, create, and schedule live events</span></span>

<span data-ttu-id="81a08-p102">任何人都可以在沒有授權的情況下參加即時活動。請閱讀[系統管理員快速入門 - 會議與即時活動](../quick-start-meetings-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="81a08-p102">Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).</span></span>

<span data-ttu-id="81a08-110">使用者需要具備下列必要條件，才能排定 Teams 即時活動。</span><span class="sxs-lookup"><span data-stu-id="81a08-110">The following prerequisites are required for the user to schedule a Teams live event.</span></span>

<span data-ttu-id="81a08-111">若要產生或出席 Teams 即時活動，您必須獲派以下授權：</span><span class="sxs-lookup"><span data-stu-id="81a08-111">Here are the licenses that must be assigned to produce or present a Teams live event:</span></span>  

- <span data-ttu-id="81a08-p103">Microsoft 或 Office 365 企業版 E1、E3 或 E5 授權，或 Office 365 教育版 A3 或 A5 授權。這項需求的例外情況是，如果符合[來賓使用者](plan-for-teams-live-events.md#guest-to-present)的其他準則，來賓使用者就可以不使用授權出席。</span><span class="sxs-lookup"><span data-stu-id="81a08-p103">A Microsoft or Office 365 Enterprise E1, E3, or E5 license or an Office 365 Education A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.</span></span>
- <span data-ttu-id="81a08-114">Microsoft Teams 授權：這包含在第一個項目符號列出的授權中。</span><span class="sxs-lookup"><span data-stu-id="81a08-114">A Microsoft Teams license - this is included in the licenses listed in the first bullet.</span></span>
- <span data-ttu-id="81a08-115">Microsoft Stream 授權 - 如果您打算將內容共用給外部應用程式或裝置，就必須有此授權；請參閱 [Microsoft Stream 授權](https://docs.microsoft.com/stream/license-overview)。</span><span class="sxs-lookup"><span data-stu-id="81a08-115">A Microsoft Stream license - is required if you are planning to share the content to an external app or device; see [Microsoft Stream licensing](https://docs.microsoft.com/stream/license-overview).</span></span>

  <span data-ttu-id="81a08-p104">如果您只想讓使用者錄影及下載錄製檔，則使用者不需獲指派 Microsoft Stream 授權。這表示，錄製檔不會儲存在 Microsoft Stream 而是會儲存在 Azure Media Services (AMS) 中，並將於 180 天的時間限制後刪除。目前系統管理員並無法控制或管理此機制，以包括刪除它的功能。</span><span class="sxs-lookup"><span data-stu-id="81a08-p104">Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.</span></span>

>[!Note]
> <span data-ttu-id="81a08-p105">從使用 Microsoft Stream 到變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](../tmr-meeting-recording-change.md)，將會採取階段性的方式。剛開始時，您可以加入這項體驗，在 11 月如果您想要繼續使用 Stream，則必須退出體驗，而在 2021 年初的某刻，我們將要求所有客戶使用商務用 OneDrive 和 SharePoint 來進行會議錄製。</span><span class="sxs-lookup"><span data-stu-id="81a08-p105">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.</span></span>

> [!NOTE]
> <span data-ttu-id="81a08-121">目前，沒有任何 Microsoft 365 小型企業方案可供用來建立及保留 Teams 即時活動。</span><span class="sxs-lookup"><span data-stu-id="81a08-121">At this time there aren't any Microsoft 365 Small Business plans that can be used to create and hold Teams live events.</span></span>

<span data-ttu-id="81a08-122">請務必知道，若要以已驗證的使用者身分參與即時活動，必須要具備 Microsoft 365 或 Office 365 授權，但這項需求視使用的生產方法而定：</span><span class="sxs-lookup"><span data-stu-id="81a08-122">It's important to know that a Microsoft 365 or Office 365 license is required to participate in a live event as an authenticated user, but this requirement depends on the production method used:</span></span>

- <span data-ttu-id="81a08-123">**針對 Teams 中產生的活動**，使用者必須取得指派的 Teams 授權。</span><span class="sxs-lookup"><span data-stu-id="81a08-123">**For events produced in Teams**  The user must be assigned a Teams license.</span></span>
- <span data-ttu-id="81a08-124">**針對外部應用程式或裝置所產生的活動**，使用者必須取得指派的 Stream 授權。</span><span class="sxs-lookup"><span data-stu-id="81a08-124">**For events produced with an external app or device** The user must be assigned a Stream license.</span></span>

> [!NOTE]
> <span data-ttu-id="81a08-125">Teams 即時活動現在適用於美國政府社群雲端 (GCC) 組織。</span><span class="sxs-lookup"><span data-stu-id="81a08-125">Teams live events is now available for US Government Cloud Community (GCC) organizations.</span></span>

<span data-ttu-id="81a08-126">如需授權的詳細資訊，請參閱 [Microsoft Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="81a08-126">For more information about licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="81a08-127">使用者必須：</span><span class="sxs-lookup"><span data-stu-id="81a08-127">The user must have:</span></span>

- <span data-ttu-id="81a08-128">已啟用 Teams 中的私人會議排程 (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 參數 = True*)。</span><span class="sxs-lookup"><span data-stu-id="81a08-128">Private meeting scheduling in Teams enabled (*The TeamsMeetingPolicy -AllowPrivateMeetingScheduling parameter = True*).</span></span>
- <span data-ttu-id="81a08-129">在 Teams 會議中啟用影片共用 (*TeamsMeetingPolicy -AllowIPVideo 參數 = True*)。</span><span class="sxs-lookup"><span data-stu-id="81a08-129">Video sharing enabled in Teams meetings (*The TeamsMeetingPolicy -AllowIPVideo parameter = True*).</span></span>
- <span data-ttu-id="81a08-130">在 Teams 會議中啟用螢幕共用 (*TeamsMeetingPolicy -ScreenSharingMode 參數 = EntireScreen*)。</span><span class="sxs-lookup"><span data-stu-id="81a08-130">Screen sharing enabled in Teams meetings (*The TeamsMeetingPolicy -ScreenSharingMode parameter = EntireScreen*).</span></span>
- <span data-ttu-id="81a08-131">已啟用 Teams 中的即時活動 (*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 參數 = True*)。</span><span class="sxs-lookup"><span data-stu-id="81a08-131">Live event scheduling in Teams enabled (*The TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling parameter = True*).</span></span>
- <span data-ttu-id="81a08-132">在 Stream 中建立即時活動的權限 (適用於外部應用程式或裝置生產)。</span><span class="sxs-lookup"><span data-stu-id="81a08-132">Permissions to create live events in Stream (for external app or device production).</span></span>
- <span data-ttu-id="81a08-133">已設定共存模式，以便排程 Teams 會議 (*孤島、會議優先或僅 Teams*)。</span><span class="sxs-lookup"><span data-stu-id="81a08-133">Coexistence mode configured to be able to schedule Teams meetings (*Islands, Meeting First, or Teams Only*).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81a08-134">未經驗證的匿名使用者無法受邀為 Teams 即時活動製作人或簡報者。</span><span class="sxs-lookup"><span data-stu-id="81a08-134">Non-authenticated anonymous users can't be invited as producers or presenters in Teams live events.</span></span>

### <a name="guest-to-present"></a>[<span data-ttu-id="81a08-135">出席來賓</span><span class="sxs-lookup"><span data-stu-id="81a08-135">Guest to present</span></span>](#guest-to-present)

<span data-ttu-id="81a08-136">若要讓來賓在即時活動中簡報，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="81a08-136">For a guest to present in a live event, do the following:</span></span>

1. <span data-ttu-id="81a08-137">[將使用者新增為團隊的來賓](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="81a08-137">[Add the user as a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="81a08-138">讓使用者接受來賓邀請並加入團隊。</span><span class="sxs-lookup"><span data-stu-id="81a08-138">Have the user accept the guest invitation and join the team.</span></span>
3. <span data-ttu-id="81a08-139">[排程即時活動，並將來賓新增至您的活動群組](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="81a08-139">[Schedule the live event and add the guest to your event group](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

<span data-ttu-id="81a08-p106">最佳做法是，建議您為即時活動的製作人和簡報者建立頻道，使得他們可以在活動前交談和共用資訊。沒有 Microsoft 365 認證的來賓就不會看到 Teams 中的行事曆。若要讓他們能夠輕鬆加入活動，製作人可以將活動連結張貼到頻道。然後，簡報者可以開啟 Teams，前往頻道，然後按一下連結以加入活動。</span><span class="sxs-lookup"><span data-stu-id="81a08-p106">As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then click the link to join the event.</span></span>

## <a name="who-can-watch-live-events"></a><span data-ttu-id="81a08-144">誰可以觀看即時活動？</span><span class="sxs-lookup"><span data-stu-id="81a08-144">Who can watch live events</span></span>

| <span data-ttu-id="81a08-145">出席者可見度</span><span class="sxs-lookup"><span data-stu-id="81a08-145">Attendee visibility</span></span> | <span data-ttu-id="81a08-146">Teams 產生</span><span class="sxs-lookup"><span data-stu-id="81a08-146">Teams production</span></span> | <span data-ttu-id="81a08-147">外部應用程式或裝置產生</span><span class="sxs-lookup"><span data-stu-id="81a08-147">External app or device production</span></span> |
|------------------------------|-----------------|----------------------|
|<span data-ttu-id="81a08-148">公用 (匿名使用者)</span><span class="sxs-lookup"><span data-stu-id="81a08-148">Public (anonymous users)</span></span>      |  <span data-ttu-id="81a08-149">是</span><span class="sxs-lookup"><span data-stu-id="81a08-149">Yes</span></span>            |  <span data-ttu-id="81a08-150">否</span><span class="sxs-lookup"><span data-stu-id="81a08-150">No</span></span>                  |
|<span data-ttu-id="81a08-151">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="81a08-151">Guest users</span></span>                   |  <span data-ttu-id="81a08-152">是</span><span class="sxs-lookup"><span data-stu-id="81a08-152">Yes</span></span>            |  <span data-ttu-id="81a08-153">否</span><span class="sxs-lookup"><span data-stu-id="81a08-153">No</span></span>                  |
|<span data-ttu-id="81a08-154">外部存取 (同盟) 公司中的每個人</span><span class="sxs-lookup"><span data-stu-id="81a08-154">Everyone in external access (federation) company</span></span> |  <span data-ttu-id="81a08-155">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-155">Yes<sup>1</sup></span></span>|  <span data-ttu-id="81a08-156">否</span><span class="sxs-lookup"><span data-stu-id="81a08-156">No</span></span>                  |
|<span data-ttu-id="81a08-157">公司中的每個人</span><span class="sxs-lookup"><span data-stu-id="81a08-157">Everyone in company</span></span>           |  <span data-ttu-id="81a08-158">是</span><span class="sxs-lookup"><span data-stu-id="81a08-158">Yes</span></span>            |  <span data-ttu-id="81a08-159">是</span><span class="sxs-lookup"><span data-stu-id="81a08-159">Yes</span></span>                 |
|<span data-ttu-id="81a08-160">特定群組/人員</span><span class="sxs-lookup"><span data-stu-id="81a08-160">Specific groups / people</span></span>      |  <span data-ttu-id="81a08-161">是</span><span class="sxs-lookup"><span data-stu-id="81a08-161">Yes</span></span>            |  <span data-ttu-id="81a08-162">是</span><span class="sxs-lookup"><span data-stu-id="81a08-162">Yes</span></span>                 |

<span data-ttu-id="81a08-163"><sup>1</sup> 外部存取 (同盟) 的出席者只能透過人員與群組邀請</span><span class="sxs-lookup"><span data-stu-id="81a08-163"><sup>1</sup> External access (federation) attendees can only be invited through People & Group</span></span> <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a><span data-ttu-id="81a08-164">Teams 即時活動和 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="81a08-164">Teams live events and Skype Meeting Broadcast</span></span>

<span data-ttu-id="81a08-165">下表醒目提示即時活動中提供的核心功能和功能，以及它們與 Skype 會議廣播有何差異。</span><span class="sxs-lookup"><span data-stu-id="81a08-165">The following table highlights core capabilities and features offered in live events and how they differ from Skype Meeting Broadcast.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81a08-166">**Microsoft 365 的即時活動限制增加**</span><span class="sxs-lookup"><span data-stu-id="81a08-166">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="81a08-167">**為能持續支援我們客戶的需求，直到 2021 年 6 月 30 日，我們將延長即時活動的暫時性限制增加**：</span><span class="sxs-lookup"><span data-stu-id="81a08-167">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="81a08-168">活動支援最多達 20000 個出席者</span><span class="sxs-lookup"><span data-stu-id="81a08-168">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="81a08-169">不同租用戶可以同時進行 50 個活動</span><span class="sxs-lookup"><span data-stu-id="81a08-169">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="81a08-170">每個廣播的活動持續時間 (16 小時)</span><span class="sxs-lookup"><span data-stu-id="81a08-170">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="81a08-171">此外，可透過 Microsoft 365 即時活動輔助計畫來規劃最多 100,000 位出席者參與的即時活動。</span><span class="sxs-lookup"><span data-stu-id="81a08-171">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program.</span></span> <span data-ttu-id="81a08-172">小組會評估每個要求，並與您一起判斷可用的選項。</span><span class="sxs-lookup"><span data-stu-id="81a08-172">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="81a08-173">[深入了解](https://aka.ms/Stream/Blog/LiveEventOptions)。</span><span class="sxs-lookup"><span data-stu-id="81a08-173">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

| <span data-ttu-id="81a08-174">功能</span><span class="sxs-lookup"><span data-stu-id="81a08-174">Capability</span></span> | <span data-ttu-id="81a08-175">Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="81a08-175">Skype Meeting Broadcast</span></span> | <span data-ttu-id="81a08-176">Teams 中產生的活動</span><span class="sxs-lookup"><span data-stu-id="81a08-176">Events produced in Teams</span></span> | <span data-ttu-id="81a08-177">外部應用程式或裝置中產生的活動</span><span class="sxs-lookup"><span data-stu-id="81a08-177">Events produced in external app or device</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="81a08-178">對象數目上限</span><span class="sxs-lookup"><span data-stu-id="81a08-178">Maximum audience size</span></span> |<span data-ttu-id="81a08-179">10,000 位出席者</span><span class="sxs-lookup"><span data-stu-id="81a08-179">10,000 attendees</span></span> |<span data-ttu-id="81a08-180">10,000 位出席者<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-180">10,000 attendees<sup>1</sup></span></span> |<span data-ttu-id="81a08-181">10,000 位出席者<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-181">10,000 attendees<sup>1</sup></span></span> |
|<span data-ttu-id="81a08-182">即時活動的持續時間上限</span><span class="sxs-lookup"><span data-stu-id="81a08-182">Maximum duration of live event</span></span> |<span data-ttu-id="81a08-183">4 小時</span><span class="sxs-lookup"><span data-stu-id="81a08-183">4 hours</span></span> |<span data-ttu-id="81a08-184">4 小時</span><span class="sxs-lookup"><span data-stu-id="81a08-184">4 hours</span></span> |<span data-ttu-id="81a08-185">4 小時</span><span class="sxs-lookup"><span data-stu-id="81a08-185">4 hours</span></span> |
|<span data-ttu-id="81a08-186">即時活動中簡報者和製作人人數上限</span><span class="sxs-lookup"><span data-stu-id="81a08-186">Maximum number of presenters and producers in a live event</span></span> |<span data-ttu-id="81a08-187">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-187">10 <sup>2</sup></span></span> |<span data-ttu-id="81a08-188">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-188">10 <sup>2</sup></span></span> |<span data-ttu-id="81a08-189">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="81a08-189">10 <sup>2</sup></span></span> |
|<span data-ttu-id="81a08-190">每個 Microsoft 365 或 Office 365 組織的並行即時活動數量上限</span><span class="sxs-lookup"><span data-stu-id="81a08-190">Maximum number of concurrent live events per Microsoft 365 or Office 365 organization</span></span> |<span data-ttu-id="81a08-191">15</span><span class="sxs-lookup"><span data-stu-id="81a08-191">15</span></span>  | <span data-ttu-id="81a08-192">15</span><span class="sxs-lookup"><span data-stu-id="81a08-192">15</span></span>  | <span data-ttu-id="81a08-193">15</span><span class="sxs-lookup"><span data-stu-id="81a08-193">15</span></span>  |
|<span data-ttu-id="81a08-194">即時活動建立</span><span class="sxs-lookup"><span data-stu-id="81a08-194">Live event creation</span></span> |   <span data-ttu-id="81a08-195">Skype 會議廣播入口網站</span><span class="sxs-lookup"><span data-stu-id="81a08-195">Skype Meeting Broadcast Portal</span></span> |<span data-ttu-id="81a08-196">Teams，透過 Teams 的 Yammer</span><span class="sxs-lookup"><span data-stu-id="81a08-196">Teams, Yammer via Teams</span></span> | <span data-ttu-id="81a08-197">Teams，透過 Teams 的 Yammer，Stream</span><span class="sxs-lookup"><span data-stu-id="81a08-197">Teams, Yammer via Teams, Stream</span></span> |
|<span data-ttu-id="81a08-198">對象參與 – Yammer</span><span class="sxs-lookup"><span data-stu-id="81a08-198">Audience engagement – Yammer</span></span> |<span data-ttu-id="81a08-199">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-199">&#x2714;</span></span> |<span data-ttu-id="81a08-200">&#x2714; (整合式體驗)</span><span class="sxs-lookup"><span data-stu-id="81a08-200">&#x2714; (integrated experience)</span></span> |<span data-ttu-id="81a08-201">&#x2714; (整合式體驗)</span><span class="sxs-lookup"><span data-stu-id="81a08-201">&#x2714; (integrated experience)</span></span> |
|<span data-ttu-id="81a08-202">對象參與 – 仲裁常見問題集</span><span class="sxs-lookup"><span data-stu-id="81a08-202">Audience engagement – Moderated Q & A</span></span> |<span data-ttu-id="81a08-203">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-203">&#x2714;</span></span>  |<span data-ttu-id="81a08-204">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-204">&#x2714;</span></span> |<span data-ttu-id="81a08-205">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-205">&#x2714;</span></span> |
|<span data-ttu-id="81a08-206">Windows 上的製作人用戶端</span><span class="sxs-lookup"><span data-stu-id="81a08-206">Producer client on Windows</span></span> |<span data-ttu-id="81a08-207">&#x2714; (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="81a08-207">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="81a08-208">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-208">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-209">&#x2714; (Stream，透過內嵌 Stream 的 Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-209">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="81a08-210">Mac 上的製作人用戶端</span><span class="sxs-lookup"><span data-stu-id="81a08-210">Producer client on Mac</span></span> |<span data-ttu-id="81a08-211">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-211">&#x274C;</span></span>  | <span data-ttu-id="81a08-212">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-212">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-213">&#x2714; (Stream，透過內嵌 Stream 的 Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-213">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="81a08-214">製作人 UI 中的出席者計數</span><span class="sxs-lookup"><span data-stu-id="81a08-214">Attendee count in Producer UI</span></span> |<span data-ttu-id="81a08-215">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-215">&#x274C;</span></span>  |<span data-ttu-id="81a08-216">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-216">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-217">&#x2714; (Stream，透過內嵌 Stream 的 Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-217">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="81a08-218">允許多個簡報者</span><span class="sxs-lookup"><span data-stu-id="81a08-218">Allows multiple presenters</span></span> |<span data-ttu-id="81a08-219">&#x2714; (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="81a08-219">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="81a08-220">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-220">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-221">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-221">N/A</span></span>  |
|<span data-ttu-id="81a08-222">在會議期間邀請簡報者</span><span class="sxs-lookup"><span data-stu-id="81a08-222">Invite a presenter during the meeting</span></span> |<span data-ttu-id="81a08-223">&#x2714; (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="81a08-223">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="81a08-224">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-224">&#x274C;</span></span> |<span data-ttu-id="81a08-225">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-225">N/A</span></span> |
|<span data-ttu-id="81a08-226">網路和行動裝置上的簡報者加入</span><span class="sxs-lookup"><span data-stu-id="81a08-226">Presenter join on Web and Mobile</span></span> |<span data-ttu-id="81a08-227">&#x2714; (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="81a08-227">&#x2714; (Skype for Business)</span></span>  |<span data-ttu-id="81a08-228">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-228">&#x274C;</span></span> |<span data-ttu-id="81a08-229">N/A</span><span class="sxs-lookup"><span data-stu-id="81a08-229">N/A</span></span> |
|<span data-ttu-id="81a08-230">外部存取 (同盟) 和來賓簡報者/出席者</span><span class="sxs-lookup"><span data-stu-id="81a08-230">External access (federation) & Guest presenters/attendees</span></span> |<span data-ttu-id="81a08-231">&#x2714; (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="81a08-231">&#x2714; (Skype for Business)</span></span>  |  <span data-ttu-id="81a08-232">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-232">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-233">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-233">N/A</span></span> |
|<span data-ttu-id="81a08-234">簡報者 - PSTN 存取</span><span class="sxs-lookup"><span data-stu-id="81a08-234">Presenter – PSTN access</span></span> |<span data-ttu-id="81a08-235">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-235">&#x274C;</span></span> |<span data-ttu-id="81a08-236">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-236">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-237">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-237">N/A</span></span> |
|<span data-ttu-id="81a08-238">展示畫面</span><span class="sxs-lookup"><span data-stu-id="81a08-238">Present a screen</span></span> |<span data-ttu-id="81a08-239">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-239">&#x274C;</span></span> |<span data-ttu-id="81a08-240">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-240">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-241">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-241">N/A</span></span> |
|<span data-ttu-id="81a08-242">在 Windows 上共用系統音訊 (僅適用於螢幕共用時)</span><span class="sxs-lookup"><span data-stu-id="81a08-242">Share system audio on Windows (available only when screen sharing)</span></span>|<span data-ttu-id="81a08-243">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-243">&#x274C;</span></span> |<span data-ttu-id="81a08-244">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="81a08-244">&#x2714; (Teams)</span></span> |<span data-ttu-id="81a08-245">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-245">&#x2714;</span></span> |
|<span data-ttu-id="81a08-246">展示 PowerPoint (PPT 共用)</span><span class="sxs-lookup"><span data-stu-id="81a08-246">Present a PowerPoint (PPT sharing)</span></span> |<span data-ttu-id="81a08-247">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-247">&#x2714;</span></span> |<span data-ttu-id="81a08-248">&#x274C; (透過螢幕畫面分享緩解)</span><span class="sxs-lookup"><span data-stu-id="81a08-248">&#x274C; (mitigated via screen sharing)</span></span> |<span data-ttu-id="81a08-249">不適用</span><span class="sxs-lookup"><span data-stu-id="81a08-249">N/A</span></span> |
|<span data-ttu-id="81a08-250">雲端式會議錄製</span><span class="sxs-lookup"><span data-stu-id="81a08-250">Cloud based meeting recording</span></span> |<span data-ttu-id="81a08-251">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-251">&#x2714;</span></span> |<span data-ttu-id="81a08-252">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-252">&#x2714;</span></span> |<span data-ttu-id="81a08-253">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-253">&#x2714;</span></span> |
|<span data-ttu-id="81a08-254">自動發佈錄製到 Stream</span><span class="sxs-lookup"><span data-stu-id="81a08-254">Auto publish recording to Stream</span></span> |<span data-ttu-id="81a08-255">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-255">&#x274C;</span></span> |<span data-ttu-id="81a08-256">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-256">&#x274C;</span></span> |<span data-ttu-id="81a08-257">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-257">&#x2714;</span></span> |
|<span data-ttu-id="81a08-258">即時輔助字幕和翻譯字幕</span><span class="sxs-lookup"><span data-stu-id="81a08-258">Live captions and subtitles</span></span> |<span data-ttu-id="81a08-259">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-259">&#x2714;</span></span> |<span data-ttu-id="81a08-260">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-260">&#x2714;</span></span> |<span data-ttu-id="81a08-261">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-261">&#x274C;</span></span> |
|<span data-ttu-id="81a08-262">即時活動錄製中的輔助字幕</span><span class="sxs-lookup"><span data-stu-id="81a08-262">Captions in live event recordings</span></span> |<span data-ttu-id="81a08-263">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-263">&#x2714;</span></span> |<span data-ttu-id="81a08-264">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-264">&#x2714;</span></span> |<span data-ttu-id="81a08-265">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-265">&#x2714;</span></span> |
|<span data-ttu-id="81a08-266">出席者 DVR 控制項 (暫停、倒轉)</span><span class="sxs-lookup"><span data-stu-id="81a08-266">Attendee DVR controls (pause, rewind)</span></span> |<span data-ttu-id="81a08-267">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-267">&#x2714;</span></span> |<span data-ttu-id="81a08-268">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-268">&#x2714;</span></span> |<span data-ttu-id="81a08-269">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-269">&#x2714;</span></span> |
|<span data-ttu-id="81a08-270">合作夥伴 eCDN 支援</span><span class="sxs-lookup"><span data-stu-id="81a08-270">Partner eCDN Support</span></span> |<span data-ttu-id="81a08-271">&#x2714; (Kollective, Hive, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="81a08-271">&#x2714; (Kollective, Hive, Riverbed)</span></span> |<span data-ttu-id="81a08-272">&#x2714; (Kollective, Hive, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="81a08-272">&#x2714; (Kollective, Hive, Riverbed)</span></span> |<span data-ttu-id="81a08-273">&#x2714; (Hive, Kollective, Ramp, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="81a08-273">&#x2714; (Hive, Kollective, Ramp, Riverbed)</span></span> |
|<span data-ttu-id="81a08-274">適用於製作人的廣播後出席報告</span><span class="sxs-lookup"><span data-stu-id="81a08-274">Post-broadcast attendance report for Producers</span></span> |<span data-ttu-id="81a08-275">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-275">&#x2714;</span></span> |<span data-ttu-id="81a08-276">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="81a08-276">&#x2714;</span></span> |<span data-ttu-id="81a08-277">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-277">&#x274C;</span></span> |
|<span data-ttu-id="81a08-278">對象人氣分析 - 即時投票與票選</span><span class="sxs-lookup"><span data-stu-id="81a08-278">Audience Sentiment Analysis – Live voting & polls</span></span> |<span data-ttu-id="81a08-279">&#x2714; (Microsoft Pulse)</span><span class="sxs-lookup"><span data-stu-id="81a08-279">&#x2714; (Microsoft Pulse)</span></span> |<span data-ttu-id="81a08-280">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-280">&#x274C;</span></span> |<span data-ttu-id="81a08-281">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="81a08-281">&#x274C;</span></span> |

<span data-ttu-id="81a08-p108"><sup>1</sup> 設定的限制可能會變更。查看 [Teams 的限制和規格](../limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="81a08-p108"><sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).</span></span><br/>
<span data-ttu-id="81a08-284"><sup>2</sup> 您最多可以在即時活動中擁有 100 位簡報者和製作人，但只會在清單中顯示最後 10 位發言者。</span><span class="sxs-lookup"><span data-stu-id="81a08-284"><sup>2</sup> You can have up to 100 presenters and producers in a live event, but only the last 10 who spoke show up in the list.</span></span>

## <a name="regional-availability"></a><span data-ttu-id="81a08-285">區域可用性</span><span class="sxs-lookup"><span data-stu-id="81a08-285">Regional availability</span></span>

<span data-ttu-id="81a08-p109">您可以在世界各地多個區域中使用 Teams 即時活動。下列資訊顯示事件小組成員和出席者的可用性。</span><span class="sxs-lookup"><span data-stu-id="81a08-p109">You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81a08-288">系統會根據召集人和 Microsoft 365 租用戶位置，自動選取活動的區域。</span><span class="sxs-lookup"><span data-stu-id="81a08-288">The region for the event is automatically selected depending on the organizer and the Microsoft 365 tenant location.</span></span>

<span data-ttu-id="81a08-289">**可在這些地區資料中心使用**</span><span class="sxs-lookup"><span data-stu-id="81a08-289">**Available in these regional data centers**</span></span>

- <span data-ttu-id="81a08-290">北美</span><span class="sxs-lookup"><span data-stu-id="81a08-290">North America</span></span>
- <span data-ttu-id="81a08-291">中美洲</span><span class="sxs-lookup"><span data-stu-id="81a08-291">Central America</span></span>
- <span data-ttu-id="81a08-292">南美洲</span><span class="sxs-lookup"><span data-stu-id="81a08-292">South America</span></span>
- <span data-ttu-id="81a08-293">亞太地區</span><span class="sxs-lookup"><span data-stu-id="81a08-293">Asia Pacific</span></span>
- <span data-ttu-id="81a08-294">歐洲/非洲</span><span class="sxs-lookup"><span data-stu-id="81a08-294">Europe/Africa</span></span>

<span data-ttu-id="81a08-295">**這些國家/地區的資料位置 (支援)**</span><span class="sxs-lookup"><span data-stu-id="81a08-295">**Data location for these countries/regions (supported)**</span></span>

- <span data-ttu-id="81a08-296">澳洲</span><span class="sxs-lookup"><span data-stu-id="81a08-296">Australia</span></span>
- <span data-ttu-id="81a08-297">加拿大</span><span class="sxs-lookup"><span data-stu-id="81a08-297">Canada</span></span>
- <span data-ttu-id="81a08-298">印度</span><span class="sxs-lookup"><span data-stu-id="81a08-298">India</span></span>
- <span data-ttu-id="81a08-299">日本</span><span class="sxs-lookup"><span data-stu-id="81a08-299">Japan</span></span>
- <span data-ttu-id="81a08-300">英國</span><span class="sxs-lookup"><span data-stu-id="81a08-300">United Kingdom</span></span>

<span data-ttu-id="81a08-301">**不支援這些國家/地區和雲端**</span><span class="sxs-lookup"><span data-stu-id="81a08-301">**These countries/regions and clouds aren't supported**</span></span>

- <span data-ttu-id="81a08-302">德國</span><span class="sxs-lookup"><span data-stu-id="81a08-302">Germany</span></span>
- <span data-ttu-id="81a08-303">法國</span><span class="sxs-lookup"><span data-stu-id="81a08-303">France</span></span>
- <span data-ttu-id="81a08-304">挪威</span><span class="sxs-lookup"><span data-stu-id="81a08-304">Norway</span></span>
- <span data-ttu-id="81a08-305">南非</span><span class="sxs-lookup"><span data-stu-id="81a08-305">South Africa</span></span>
- <span data-ttu-id="81a08-306">南韓</span><span class="sxs-lookup"><span data-stu-id="81a08-306">South Korea</span></span>
- <span data-ttu-id="81a08-307">瑞士</span><span class="sxs-lookup"><span data-stu-id="81a08-307">Switzerland</span></span>
- <span data-ttu-id="81a08-308">阿拉伯聯合大公國</span><span class="sxs-lookup"><span data-stu-id="81a08-308">UAE</span></span>
- <span data-ttu-id="81a08-309">政府社群雲端 (GCC)-H</span><span class="sxs-lookup"><span data-stu-id="81a08-309">Government Community Cloud (GCC)-H</span></span>
- <span data-ttu-id="81a08-310">美國國防部</span><span class="sxs-lookup"><span data-stu-id="81a08-310">DOD</span></span>

<span data-ttu-id="81a08-311">**排除和考量**</span><span class="sxs-lookup"><span data-stu-id="81a08-311">**Exclusions and considerations**</span></span>

- <span data-ttu-id="81a08-312">**資料位置：** Teams 資料位置，目前不支援上述以外的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="81a08-312">**Data location:** Teams data locations, outside of the ones listed above, are not currently supported.</span></span>
- <span data-ttu-id="81a08-p110">**中國：** 活動小組成員和出席者無法使用 Teams 即時活動，因為無法在中國存取 Azure CDN。因應措施是使用公司 VPN 連線，透過客戶的公司網路，讓用戶端連線到 CDN。</span><span class="sxs-lookup"><span data-stu-id="81a08-p110">**China:** Event team members and attendees will not be able to use Teams live events because Azure CDN is not accessible in China. A workaround is to use a company VPN connection, which gets the client connected to CDN via the customer's corporate network.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81a08-315">後續步驟</span><span class="sxs-lookup"><span data-stu-id="81a08-315">Next steps</span></span>

<span data-ttu-id="81a08-316">移至[設定 Teams 即時活動](set-up-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="81a08-316">Go to [Set up for Teams live events](set-up-for-teams-live-events.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="81a08-317">相關主題</span><span class="sxs-lookup"><span data-stu-id="81a08-317">Related topics</span></span>

- [<span data-ttu-id="81a08-318">什麼是 Teams 即時活動？</span><span class="sxs-lookup"><span data-stu-id="81a08-318">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="81a08-319">設定 Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="81a08-319">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="81a08-320">在 Teams 中設定即時活動設定</span><span class="sxs-lookup"><span data-stu-id="81a08-320">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
