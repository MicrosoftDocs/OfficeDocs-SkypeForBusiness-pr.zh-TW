---
title: 系統管理員快速入門 - Microsoft Teams 的會議和即時活動
ms.reviewer: ''
description: 快速上手 Microsoft Teams 的會議和即時活動。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a990b62e6479e44308f65920c4f49264b4a131a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814393"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="96777-103">系統管理員快速入門 - Microsoft Teams 的會議和即時活動</span><span class="sxs-lookup"><span data-stu-id="96777-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="96777-104">Microsoft Teams 有 2 個集會方式 - 會議和即時活動。</span><span class="sxs-lookup"><span data-stu-id="96777-104">There are 2 ways to meet in Microsoft Teams - meetings and live events.</span></span> <span data-ttu-id="96777-105">請使用此文章來快速推出和設定貴組織的會議和即時活動。</span><span class="sxs-lookup"><span data-stu-id="96777-105">Use this article to quickly roll out and configure meetings and live events for your organization.</span></span> 

 - <span data-ttu-id="96777-106">Teams 的**會議**包括音訊、視訊，且畫面可共用人數最多可達 300 人。</span><span class="sxs-lookup"><span data-stu-id="96777-106">**Meetings** in Teams include audio, video, and screen sharing for up to 300\* people.</span></span> <span data-ttu-id="96777-107">這些是在 Teams 中共同作業的重要方法之一。</span><span class="sxs-lookup"><span data-stu-id="96777-107">They're one of the key ways to collaborate in Teams.</span></span> <span data-ttu-id="96777-108">而且，您不必一定要具備組織的成員資格 (或甚至不需要 Teams 帳戶！) 才能加入 Teams 會議，只要查看邀請中有關撥入會議的指示即可。</span><span class="sxs-lookup"><span data-stu-id="96777-108">And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span> 

 - <span data-ttu-id="96777-109">**即時活動**是 Teams 會議的延伸，可讓您排程並產生活動，向大量線上觀眾串流播放，最多可讓 10,000 人參與。</span><span class="sxs-lookup"><span data-stu-id="96777-109">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people.</span></span> <span data-ttu-id="96777-110">如果您的會議參與人數會超過 300 人，請使用即時活動。</span><span class="sxs-lookup"><span data-stu-id="96777-110">If you need a meeting for more than 300 people, use a live event.</span></span>
<br><br><span data-ttu-id="96777-111">**附註：** 針對政府用 Teams (GCC、GCC、DoD)，其限制仍為 250。</span><span class="sxs-lookup"><span data-stu-id="96777-111">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 250.</span></span> <span data-ttu-id="96777-112">當政府用雲端限制從 250 增加至 300，我們就會更新本文章。</span><span class="sxs-lookup"><span data-stu-id="96777-112">We'll update this article when the government cloud limit increases from 250 to 300.</span></span>
## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="96777-113">取得會議和即時活動的授權</span><span class="sxs-lookup"><span data-stu-id="96777-113">Get licenses for meetings and live events</span></span>

<span data-ttu-id="96777-114">任何人都可以免費參加 Teams 會議或公開即時活動，不需要授權。</span><span class="sxs-lookup"><span data-stu-id="96777-114">Anyone can attend a Teams meeting or public live event for free - no license is required.</span></span> <span data-ttu-id="96777-115">出席者按一下 Teams 或會議邀請中的 [加入]\*\*\*\* 就能加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="96777-115">Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation.</span></span> <span data-ttu-id="96777-116">會議的音訊是 Teams 會議的一部分，但是如果您希望人員能夠以電話撥入會議，則您必須提供撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="96777-116">Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span> 

<span data-ttu-id="96777-117">若是召集、排程和舉辦會議或即時活動的人員，這些人員需要下表列出的 Microsoft 365 或 Office 365 授權之一。</span><span class="sxs-lookup"><span data-stu-id="96777-117">For the people who will organize, schedule, and host meetings or live events, they'll need one of the Microsoft 365 or Office 365 licenses listed in the table below.</span></span> <span data-ttu-id="96777-118">如果您已經在使用 Teams，您可能已經擁有召集和舉辦會議和即時活動所需的授權。</span><span class="sxs-lookup"><span data-stu-id="96777-118">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span> 

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Teams 會議和即時活動所需授權的表格":::

> <span data-ttu-id="96777-120"><sup>1</sup>  會議召集人必須擁有[音訊會議附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)才能傳送內含電話撥入式會議的邀請。</span><span class="sxs-lookup"><span data-stu-id="96777-120"><sup>1</sup>  Meeting organizers need to have an [Audio Conferencing add-on license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) to send an invite that includes dial-in conferencing.</span></span>
>
> <span data-ttu-id="96777-121"><sup>2</sup>  若是撥出至[**用下列電話號碼連絡我**號碼](set-up-the-call-me-feature-for-your-users.md)的會議，召集人必須擁有 E5 或[音訊會議附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="96777-121"><sup>2</sup>  Meeting dial out to a [**Call me at** number](set-up-the-call-me-feature-for-your-users.md) requires organizers to have an E5 or [Audio Conference add-in license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> <span data-ttu-id="96777-122">[撥號對應表](what-are-dial-plans.md)可能也在必要項目之列。</span><span class="sxs-lookup"><span data-stu-id="96777-122">A [dial plan](what-are-dial-plans.md) may also be needed.</span></span> 

 > [!Note]
 > <span data-ttu-id="96777-123">如需詳細資料，請參閱[依平台的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="96777-123">See [Team features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) for more information.</span></span>

<span data-ttu-id="96777-124">若要深入瞭解授權，請參閱 [Microsoft Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="96777-124">To learn more about licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span> 

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="96777-125">確定網路已準備就緒</span><span class="sxs-lookup"><span data-stu-id="96777-125">Make sure your network's ready</span></span>

<span data-ttu-id="96777-126">如果您的網路在推出 Microsoft 365 或 Office 365 時已準備就緒，則表示您已完成所有準備。</span><span class="sxs-lookup"><span data-stu-id="96777-126">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set.</span></span> <span data-ttu-id="96777-127">無論如何，尤其是您要快速推出 Teams 做為您支援**遠端工作者**的第一個 Office 365 工作負載的話，請參閱[針對 Teams 準備組織的網路](prepare-network.md)，確保您已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="96777-127">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="96777-128">會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="96777-128">Meetings and conferencing</span></span>

- <span data-ttu-id="96777-129">身為系統管理員，您要設定每個人的[會議設定](meeting-settings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="96777-129">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone.</span></span> <span data-ttu-id="96777-130">接著，您可以使用[會議原則](meeting-policies-in-teams.md)控制使用者可以使用 (和不可以使用) 哪些會議功能。</span><span class="sxs-lookup"><span data-stu-id="96777-130">Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span> 

- <span data-ttu-id="96777-131">若要了解如何管理會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="96777-131">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="96777-132">如果使用者是 Teams 會議的新手，請與新手們共用[管理會議](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)訓練。</span><span class="sxs-lookup"><span data-stu-id="96777-132">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them.</span></span> <span data-ttu-id="96777-133">請查看由講師帶領的線上課程，[透過 Teams 進行有效會議](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)。</span><span class="sxs-lookup"><span data-stu-id="96777-133">Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="96777-134">若要深入了解管理會議的選項，請參閱[變更團隊會議的參與者設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="96777-134">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="96777-135">別忘了[管理使用者的裝置](device-management.md) - 電話、耳機、相機。</span><span class="sxs-lookup"><span data-stu-id="96777-135">Don't forget about [managing your users' devices](device-management.md) - phones, headsets, cameras.</span></span> <span data-ttu-id="96777-136">若要取得有關經過 Teams 認證的裝置最新資訊，請移至 [Teams 裝置](https://office.com/teamsdevices)。</span><span class="sxs-lookup"><span data-stu-id="96777-136">To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="96777-137">即時活動</span><span class="sxs-lookup"><span data-stu-id="96777-137">Live events</span></span>

- <span data-ttu-id="96777-138">就像會議一樣，您身為系統管理員，您要針對每個人[設定即時活動](teams-live-events/configure-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="96777-138">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone.</span></span> <span data-ttu-id="96777-139">然後設定 (和指派) [即時事件原則](teams-live-events/set-up-for-teams-live-events.md)，控制使用者可以執行 (和不可以執行) 的動作。</span><span class="sxs-lookup"><span data-stu-id="96777-139">Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="96777-140">請確認您的即時活動製作人和召集人受過訓練，也就是將他們送去參加[開始使用即時活動](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)課程。</span><span class="sxs-lookup"><span data-stu-id="96777-140">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="96777-141">如果您剛開始使用即時活動，請參閱[什麼是 Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)和 [Teams 即時活動的方案](teams-live-events/plan-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="96777-141">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="96777-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="96777-142">Related topics</span></span>

[<span data-ttu-id="96777-143">Teams 的會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="96777-143">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="96777-144">Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="96777-144">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="96777-145">Teams 的即時活動</span><span class="sxs-lookup"><span data-stu-id="96777-145">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="96777-146">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="96777-146">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="96777-147">Microsoft 技術社群：Microsoft 365 中的即時活動</span><span class="sxs-lookup"><span data-stu-id="96777-147">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
