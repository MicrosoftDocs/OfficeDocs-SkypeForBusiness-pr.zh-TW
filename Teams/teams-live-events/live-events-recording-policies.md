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
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739653"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="f89d2-103">即時活動錄製Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f89d2-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="f89d2-104">您有幾個錄製即時活動Microsoft Teams選項。</span><span class="sxs-lookup"><span data-stu-id="f89d2-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="f89d2-105">錄製選項是使用錄製策略來設定。</span><span class="sxs-lookup"><span data-stu-id="f89d2-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="f89d2-106">本文將說明各種設定。</span><span class="sxs-lookup"><span data-stu-id="f89d2-106">This article describes the various settings.</span></span>

<span data-ttu-id="f89d2-107">錄製選項是使用 PowerShell 命令 [Set-CsTeamsMeetingBroadcastPolicy 來設定](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f89d2-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="f89d2-108">排程和選項行為</span><span class="sxs-lookup"><span data-stu-id="f89d2-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="f89d2-109">排程即時活動錄製時，有兩個召集人選項：</span><span class="sxs-lookup"><span data-stu-id="f89d2-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="f89d2-110">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="f89d2-111">錄製檔案：提供錄製檔案，製作者和簡報者可在活動結束後下載。</span><span class="sxs-lookup"><span data-stu-id="f89d2-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="f89d2-112">出席者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-112">Recording available for attendees</span></span>

  - <span data-ttu-id="f89d2-113">DVR：DVR (DVR) 可讓出席者在活動期間倒帶和暫停</span><span class="sxs-lookup"><span data-stu-id="f89d2-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="f89d2-114">VOD：視訊 (VOD) 可讓出席者在活動結束後觀看</span><span class="sxs-lookup"><span data-stu-id="f89d2-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="f89d2-115">廣播錄製政策設定</span><span class="sxs-lookup"><span data-stu-id="f89d2-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="f89d2-116">在廣播政策中，您可以切換設定來開啟或關閉即時活動的錄製。</span><span class="sxs-lookup"><span data-stu-id="f89d2-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="f89d2-117">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="f89d2-118">出席者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="f89d2-119">永遠錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-119">Always record</span></span>               | <span data-ttu-id="f89d2-120">已停用並選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-120">Disabled and selected</span></span>                                | <span data-ttu-id="f89d2-121">已啟用並選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-121">Enabled and selected</span></span>         |
| <span data-ttu-id="f89d2-122">召集人可以錄製或無法錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-122">Organizer can record or not</span></span> | <span data-ttu-id="f89d2-123">預設為啟用和選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="f89d2-124">預設為啟用和選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="f89d2-125">永不錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-125">Never record</span></span>               | <span data-ttu-id="f89d2-126">已停用且未選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-126">Disabled and not selected</span></span>                            | <span data-ttu-id="f89d2-127">已停用且未選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="f89d2-128">儲存體和持續性行為</span><span class="sxs-lookup"><span data-stu-id="f89d2-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="f89d2-129">選項</span><span class="sxs-lookup"><span data-stu-id="f89d2-129">Option</span></span>                                       | <span data-ttu-id="f89d2-130">狀態</span><span class="sxs-lookup"><span data-stu-id="f89d2-130">State</span></span>   | <span data-ttu-id="f89d2-131">Dvr</span><span class="sxs-lookup"><span data-stu-id="f89d2-131">DVR</span></span>                                                   | <span data-ttu-id="f89d2-132">Vod</span><span class="sxs-lookup"><span data-stu-id="f89d2-132">VOD</span></span>                                                     | <span data-ttu-id="f89d2-133">錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="f89d2-134">出席者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-134">Recording available for attendees</span></span> | <span data-ttu-id="f89d2-135">選擇</span><span class="sxs-lookup"><span data-stu-id="f89d2-135">Selected</span></span>     | <span data-ttu-id="f89d2-136">DVR 可供使用，AZURE 媒體服務 (AMS) 資產儲存 180 天</span><span class="sxs-lookup"><span data-stu-id="f89d2-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="f89d2-137">出席者可以存取並觀看活動</span><span class="sxs-lookup"><span data-stu-id="f89d2-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="f89d2-138">未選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-138">Not Selected</span></span> | <span data-ttu-id="f89d2-139">DVR 可供使用，且 AMS 資產儲存 180 天</span><span class="sxs-lookup"><span data-stu-id="f89d2-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="f89d2-140">活動結束後，出席者無法存取活動</span><span class="sxs-lookup"><span data-stu-id="f89d2-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="f89d2-141">已停用 (未選取) </span><span class="sxs-lookup"><span data-stu-id="f89d2-141">Disabled (Not selected)</span></span>|<span data-ttu-id="f89d2-142">DVR 可供使用，事件之後會刪除 AMS 資產</span><span class="sxs-lookup"><span data-stu-id="f89d2-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="f89d2-143">活動結束後，出席者無法存取活動</span><span class="sxs-lookup"><span data-stu-id="f89d2-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="f89d2-144">錄製者與簡報者可以使用錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="f89d2-145">選擇</span><span class="sxs-lookup"><span data-stu-id="f89d2-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="f89d2-146">已建立並儲存 MP4</span><span class="sxs-lookup"><span data-stu-id="f89d2-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="f89d2-147">未選取</span><span class="sxs-lookup"><span data-stu-id="f89d2-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="f89d2-148">未建立檔案</span><span class="sxs-lookup"><span data-stu-id="f89d2-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="f89d2-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="f89d2-149">Related topics</span></span>

- [<span data-ttu-id="f89d2-150">什麼是 Teams 即時活動？</span><span class="sxs-lookup"><span data-stu-id="f89d2-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="f89d2-151">Teams 即時活動的方案</span><span class="sxs-lookup"><span data-stu-id="f89d2-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="f89d2-152">在 Teams 中設定即時活動設定</span><span class="sxs-lookup"><span data-stu-id="f89d2-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="f89d2-153">Teams雲端會議錄製</span><span class="sxs-lookup"><span data-stu-id="f89d2-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
