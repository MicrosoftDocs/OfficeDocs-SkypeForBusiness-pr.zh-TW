---
title: 系統管理員快速入門 - Microsoft Teams 的會議和即時活動
ms.reviewer: ''
description: 適用於系統管理員的快速入門指南，以取得 Microsoft Teams 的授權、推出 Microsoft Teams 和設定線上會議和即時事件。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03611f2d166883ce960e272e2f3b11300cd20c54
ms.sourcegitcommit: 616b6d0d5be2b333519b79ab59a4117036ba647e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363578"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="69c09-103">系統管理員快速入門 - Microsoft Teams 的會議和即時活動</span><span class="sxs-lookup"><span data-stu-id="69c09-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="69c09-p101">Microsoft Teams 有 2 個集會方式 - 會議和即時活動。請使用此文章來快速推出和設定組織的會議和即時活動。</span><span class="sxs-lookup"><span data-stu-id="69c09-p101">There are 2 ways to meet in Microsoft Teams - meetings and live events. Use this article to quickly roll out and configure meetings and live events for your organization.</span></span>

> [!Note]
> <span data-ttu-id="69c09-106">如需有關快速設定不同平台上 Teams 會議和活動的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="69c09-106">For details about quickly configuring Teams meetings and events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

 - <span data-ttu-id="69c09-p102">Teams 的 **會議** 包括音訊、視訊，且畫面可共用人數最多可達 1000 人。這些是在 Teams 中共同作業的重要方法之一。而且，您不一定要是組織的成員 (或甚至不需要 Teams 帳戶！)，也可以加入 Teams 會議，只要查看邀請中有關撥入會議的指示即可。</span><span class="sxs-lookup"><span data-stu-id="69c09-p102">**Meetings** in Teams include audio, video, and screen sharing for up to 1000 people. They're one of the key ways to collaborate in Teams. And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span>

 - <span data-ttu-id="69c09-p103">**即時活動** 是 Teams 會議的延伸，可讓您排程並產生活動，向大量線上對象串流播放，最多可讓 10,000 人參與。如果您的會議需要超過 1000 人參與，請使用即時活動。</span><span class="sxs-lookup"><span data-stu-id="69c09-p103">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people. If you need a meeting for more than 1000 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="69c09-112">取得會議和即時活動的授權</span><span class="sxs-lookup"><span data-stu-id="69c09-112">Get licenses for meetings and live events</span></span>

<span data-ttu-id="69c09-p104">任何人都可以免費參加 Teams 會議或公開即時活動，不需要授權。出席者按一下 Teams 或會議邀請中的 [加入 **]** 就能加入 Teams 會議。會議的音訊是 Teams 會議的一部分，但是如果您希望人員能夠以電話撥入會議，則您必須提供撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="69c09-p104">Anyone can attend a Teams meeting or public live event for free - no license is required. Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation. Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span>

<span data-ttu-id="69c09-116">對於召集、排程和舉辦會議或即時活動的人員，這些人員需要 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)中所列的授權計畫之一。</span><span class="sxs-lookup"><span data-stu-id="69c09-116">For the people who will organize, schedule, and host meetings or live events, they'll need one of the licensing plans described in the [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span> 

<span data-ttu-id="69c09-117">如果您已經在使用 Teams，您可能已經擁有召集和舉辦會議和即時活動所需的授權。</span><span class="sxs-lookup"><span data-stu-id="69c09-117">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span>

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="69c09-118">確定網路已準備就緒</span><span class="sxs-lookup"><span data-stu-id="69c09-118">Make sure your network's ready</span></span>

<span data-ttu-id="69c09-p105">如果您的網路在推出 Microsoft 365 或 Office 365 時已準備就緒，則表示您已完成所有準備。無論如何，尤其是您要快速推出 Teams 做為您支援 **遠端工作者** 的第一個 Office 365 工作負載的話，請參閱 [針對 Teams 準備組織的網路](prepare-network.md)，確保您已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="69c09-p105">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set. In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="69c09-121">會議和研討會</span><span class="sxs-lookup"><span data-stu-id="69c09-121">Meetings and conferencing</span></span>

- <span data-ttu-id="69c09-p106">身為系統管理員，您要設定每個人的[會議設定](meeting-settings-in-teams.md)。接著，您可以使用[會議原則](meeting-policies-in-teams.md)控制使用者可以使用 (和不可以使用) 哪些會議功能。</span><span class="sxs-lookup"><span data-stu-id="69c09-p106">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone. Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span>

- <span data-ttu-id="69c09-124">若要了解如何管理會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="69c09-124">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="69c09-p107">如果使用者是 Teams 會議的新手，請與新手們共用[管理會議](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)訓練。請查看由講師帶領的線上課程，[透過 Teams 進行有效會議](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)。</span><span class="sxs-lookup"><span data-stu-id="69c09-p107">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them. Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="69c09-127">若要深入了解管理會議的選項，請參閱[變更 Teams 會議的參與者設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="69c09-127">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="69c09-p108">別忘了[管理使用者的裝置](./devices/device-management.md) - 電話、耳機、相機。若要取得有關經過 Teams 認證的裝置最新資訊，請移至 [Teams 裝置](https://office.com/teamsdevices)。</span><span class="sxs-lookup"><span data-stu-id="69c09-p108">Don't forget about [managing your users' devices](./devices/device-management.md) - phones, headsets, cameras. To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="69c09-130">即時事件</span><span class="sxs-lookup"><span data-stu-id="69c09-130">Live events</span></span>

- <span data-ttu-id="69c09-p109">就像會議一樣，您身為系統管理員，您要針對每個人[設定即時活動](teams-live-events/configure-teams-live-events.md)。然後設定 (和指派) [即時事件原則](teams-live-events/set-up-for-teams-live-events.md)，控制使用者可以執行 (和不可以執行) 的動作。</span><span class="sxs-lookup"><span data-stu-id="69c09-p109">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone. Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="69c09-133">請確認您的即時活動製作人和召集人受過訓練，請讓他們參與[開始使用即時活動](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)課程。</span><span class="sxs-lookup"><span data-stu-id="69c09-133">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="69c09-134">如果您剛開始使用即時活動，請參閱[什麼是 Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)和 [Teams 即時活動的方案](teams-live-events/plan-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="69c09-134">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="69c09-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="69c09-135">Related topics</span></span>

[<span data-ttu-id="69c09-136">Teams 的會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="69c09-136">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="69c09-137">Teams 的音訊會議</span><span class="sxs-lookup"><span data-stu-id="69c09-137">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="69c09-138">Teams 的即時活動</span><span class="sxs-lookup"><span data-stu-id="69c09-138">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="69c09-139">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="69c09-139">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="69c09-140">Microsoft 技術社群：Microsoft 365 中的即時活動</span><span class="sxs-lookup"><span data-stu-id="69c09-140">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
