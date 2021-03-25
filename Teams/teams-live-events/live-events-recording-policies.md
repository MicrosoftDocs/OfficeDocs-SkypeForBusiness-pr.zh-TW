---
title: 即時活動錄製政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解即時活動錄製政策。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a5f793230798c68f0a39e2d9a3500eab9791065
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119162"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="30698-103">Microsoft Teams 中的即時活動錄製政策</span><span class="sxs-lookup"><span data-stu-id="30698-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="30698-104">您有幾個選項可以錄製 Microsoft Teams 即時活動。</span><span class="sxs-lookup"><span data-stu-id="30698-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="30698-105">錄製選項是使用錄製策略來設定。</span><span class="sxs-lookup"><span data-stu-id="30698-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="30698-106">本文將說明各種設定。</span><span class="sxs-lookup"><span data-stu-id="30698-106">This article describes the various settings.</span></span>

<span data-ttu-id="30698-107">錄製選項是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 設定](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="30698-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="30698-108">排程和選項行為</span><span class="sxs-lookup"><span data-stu-id="30698-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="30698-109">排程即時活動錄製時，有兩個召集人選項：</span><span class="sxs-lookup"><span data-stu-id="30698-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="30698-110">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="30698-111">錄製檔案：提供錄製檔案，製作者和簡報者可在活動結束後下載。</span><span class="sxs-lookup"><span data-stu-id="30698-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="30698-112">出席者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-112">Recording available for attendees</span></span>

  - <span data-ttu-id="30698-113">DVR：DVR (DVR) 可讓出席者在活動期間倒帶和暫停</span><span class="sxs-lookup"><span data-stu-id="30698-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="30698-114">VOD：視訊 (VOD) 可讓出席者在活動結束後觀看</span><span class="sxs-lookup"><span data-stu-id="30698-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="30698-115">廣播錄製政策設定</span><span class="sxs-lookup"><span data-stu-id="30698-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="30698-116">在廣播政策中，您可以切換設定來開啟或關閉即時活動的錄製。</span><span class="sxs-lookup"><span data-stu-id="30698-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="30698-117">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="30698-118">出席者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="30698-119">永遠錄製</span><span class="sxs-lookup"><span data-stu-id="30698-119">Always record</span></span>               | <span data-ttu-id="30698-120">已停用並選取</span><span class="sxs-lookup"><span data-stu-id="30698-120">Disabled and selected</span></span>                                | <span data-ttu-id="30698-121">已停用並選取</span><span class="sxs-lookup"><span data-stu-id="30698-121">Disabled and selected</span></span>         |
| <span data-ttu-id="30698-122">召集人可以錄製或無法錄製</span><span class="sxs-lookup"><span data-stu-id="30698-122">Organizer can record or not</span></span> | <span data-ttu-id="30698-123">預設為已啟用且未選取</span><span class="sxs-lookup"><span data-stu-id="30698-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="30698-124">預設為已啟用且未選取</span><span class="sxs-lookup"><span data-stu-id="30698-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="30698-125">永不錄製</span><span class="sxs-lookup"><span data-stu-id="30698-125">Never record</span></span>               | <span data-ttu-id="30698-126">已停用且未選取</span><span class="sxs-lookup"><span data-stu-id="30698-126">Disabled and not selected</span></span>                            | <span data-ttu-id="30698-127">已停用且未選取</span><span class="sxs-lookup"><span data-stu-id="30698-127">Disabled and not selected</span></span>      |

<span data-ttu-id="30698-128">當策略設定為永遠記錄 **時，** 該策略頁面具有下列選取選項：</span><span class="sxs-lookup"><span data-stu-id="30698-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="30698-129">![即時事件策略設定](../media/live-event-recording-policy.png "Microsoft Teams 系統管理中心即時活動原則設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="30698-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="30698-130">儲存空間和持續性行為</span><span class="sxs-lookup"><span data-stu-id="30698-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="30698-131">選項</span><span class="sxs-lookup"><span data-stu-id="30698-131">Option</span></span>                                       | <span data-ttu-id="30698-132">狀態</span><span class="sxs-lookup"><span data-stu-id="30698-132">State</span></span>   | <span data-ttu-id="30698-133">Dvr</span><span class="sxs-lookup"><span data-stu-id="30698-133">DVR</span></span>                                                   | <span data-ttu-id="30698-134">Vod</span><span class="sxs-lookup"><span data-stu-id="30698-134">VOD</span></span>                                                     | <span data-ttu-id="30698-135">錄製</span><span class="sxs-lookup"><span data-stu-id="30698-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="30698-136">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="30698-137">選擇</span><span class="sxs-lookup"><span data-stu-id="30698-137">Selected</span></span>     | <span data-ttu-id="30698-138">DVR 可供使用，而 AZURE Media Services (AMS) 資產會儲存 180 天</span><span class="sxs-lookup"><span data-stu-id="30698-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="30698-139">出席者可以存取並觀看活動</span><span class="sxs-lookup"><span data-stu-id="30698-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="30698-140">未選取</span><span class="sxs-lookup"><span data-stu-id="30698-140">Not Selected</span></span> | <span data-ttu-id="30698-141">DVR 可供使用，且 AMS 資產儲存 180 天</span><span class="sxs-lookup"><span data-stu-id="30698-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="30698-142">活動結束後，出席者無法存取活動</span><span class="sxs-lookup"><span data-stu-id="30698-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="30698-143">已停用 (未選取) </span><span class="sxs-lookup"><span data-stu-id="30698-143">Disabled (Not selected)</span></span>|<span data-ttu-id="30698-144">DVR 可供使用，事件之後會刪除 AMS 資產</span><span class="sxs-lookup"><span data-stu-id="30698-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="30698-145">活動結束後，出席者無法存取活動</span><span class="sxs-lookup"><span data-stu-id="30698-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="30698-146">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="30698-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="30698-147">選擇</span><span class="sxs-lookup"><span data-stu-id="30698-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="30698-148">已建立並儲存 MP4</span><span class="sxs-lookup"><span data-stu-id="30698-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="30698-149">未選取</span><span class="sxs-lookup"><span data-stu-id="30698-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="30698-150">未建立檔案</span><span class="sxs-lookup"><span data-stu-id="30698-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="30698-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="30698-151">Related topics</span></span>

- [<span data-ttu-id="30698-152">什麼是 Teams 即時活動？</span><span class="sxs-lookup"><span data-stu-id="30698-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="30698-153">Teams 即時活動的方案</span><span class="sxs-lookup"><span data-stu-id="30698-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="30698-154">在 Teams 中設定即時活動設定</span><span class="sxs-lookup"><span data-stu-id="30698-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="30698-155">Teams 雲端會議錄製</span><span class="sxs-lookup"><span data-stu-id="30698-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)