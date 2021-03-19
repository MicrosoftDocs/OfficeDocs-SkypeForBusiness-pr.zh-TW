---
title: 僅查看會議體驗
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解適用于系統管理員、簡報者和出席者的 Teams 僅查看會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875053"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="6e7ee-103">Teams 只能查看會議體驗</span><span class="sxs-lookup"><span data-stu-id="6e7ee-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="6e7ee-104">Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 提供僅觀看廣播。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="6e7ee-105">此功能將于 2021 年 3 月 1 日啟用為預設關閉。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="6e7ee-106">Microsoft 365 政府社群雲端 (GCC) 將于 2021 年 3 月底開始推出。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="6e7ee-107">政府社群雲端高 (GCCH) 和 (DoD) 將于稍後推出。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="6e7ee-108">如果您想要將功能預設為 ON，您必須在此日期之後變更預設政策。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="6e7ee-109">使用 PowerShell 啟用該策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="6e7ee-110">如果您的會議或網路研討會達到容量，Teams 將會順暢地縮放，以容納 10，000 人只能觀看的廣播體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="6e7ee-111">此外，在增加遠端工作的這一期間，利用到今年年底超過 20，000 人的廣播。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="6e7ee-112">Microsoft Teams 最多允許 10，000 位出席者加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="6e7ee-113">達到主要會議的容量後，其他出席者會以僅以視點功能加入會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="6e7ee-114">第一次加入會議的出席者，最多達會議容量，將會獲得完整的 Teams 會議體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="6e7ee-115">他們可以共用音訊和視音訊、查看共用影片，以及參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="6e7ee-116">到達主要會議容量後加入的出席者將享有僅以視圖顯示的體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="6e7ee-117">我們有完整的 Android 和 iOS 行動支援，讓出席者加入。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="6e7ee-118">目前，在 WW 中可以聊天和通話的會議人數上限為 300 人，GCC、GCC High 和 DoD 為 250 人。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="6e7ee-119">任何擁有 E3/E5/A3/A5 SKU 的召集人，預設會停用僅顯示模式體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="6e7ee-120">不需要進一步設定或設定。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="6e7ee-121">停用 Teams 只能查看體驗</span><span class="sxs-lookup"><span data-stu-id="6e7ee-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="6e7ee-122">系統管理員可以使用 PowerShell 停用僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="6e7ee-123">未來，系統管理員也可以停用 Teams 系統管理中心的僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="6e7ee-124">對使用者的影響</span><span class="sxs-lookup"><span data-stu-id="6e7ee-124">Impact to users</span></span>

<span data-ttu-id="6e7ee-125">使用者的體驗會因數個因素而異。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="6e7ee-126">當達到主要會議的容量時，如果下列任一項為 True，出席者將無法加入會議：</span><span class="sxs-lookup"><span data-stu-id="6e7ee-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="6e7ee-127">系統管理員已停用 Teams 只能查看體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="6e7ee-128">出席者沒有跳過大廳的許可權。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="6e7ee-129">當達到主要會議的容量時，會議召集人和簡報者會看到橫幅，告知他們會議容量已達，且新的出席者會加入僅觀看的出席者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![適用于召集人和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

<span data-ttu-id="6e7ee-131">當達到主要會議的容量時，會議出席者會以加入前畫面通知他們以僅查看模式加入。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 加入前畫面，以及參與者的訊息，告知他們將以僅以模式加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="6e7ee-133">如果有空間，使用者一定會加入主會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="6e7ee-134">如果主要會議達到容量，且一或多個出席者離開主會議，則主會議具有可用的容量。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="6e7ee-135">加入會議 (或重新加入) 出席者會加入主會議，直到會議再次達到容量。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="6e7ee-136">只有使用模式體驗的出席者不會自動升級至主要會議，目前無法手動升級至主要會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="6e7ee-137">如果尚未設定簡報者/出席者角色，主會議的空格會先到先得。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="6e7ee-138">達到會議容量後，所有其他使用者都會以僅以視圖為體驗加入會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="6e7ee-139">對會議簡報者的影響</span><span class="sxs-lookup"><span data-stu-id="6e7ee-139">Impact to meeting presenters</span></span>

<span data-ttu-id="6e7ee-140">會議簡報者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="6e7ee-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="6e7ee-141">您沒有僅查看出席者的資訊。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="6e7ee-142">我們不支援僅供出席者使用 E-discovery。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="6e7ee-143">使用者無法看到僅查看出席者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="6e7ee-144">您無法從會議移除只能查看的出席者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="6e7ee-145">出席者計數只會反映會議中的人員，而非僅顯示會議室中的人員。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="6e7ee-146">因此，簡報者無法確切計算誰在僅觀看體驗中。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="6e7ee-147">只有觀看的出席者體驗</span><span class="sxs-lookup"><span data-stu-id="6e7ee-147">Experience for view-only attendees</span></span>

<span data-ttu-id="6e7ee-148">Teams 只能查看體驗可讓出席者：</span><span class="sxs-lookup"><span data-stu-id="6e7ee-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="6e7ee-149">聆聽 Teams 主要會議的參與者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="6e7ee-150">如果使用中喇叭正在共用視 (，請參閱使用中喇叭的視) 。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="6e7ee-151">查看使用共用桌面功能共用的內容。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="6e7ee-152">只有觀看的出席者將無法在會議中體驗下列選項：</span><span class="sxs-lookup"><span data-stu-id="6e7ee-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="6e7ee-153">如果出席者沒有許可權根據設定大廳政策或選項來跳過大廳，請加入會議。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="6e7ee-154">使用音訊會議加入唯一的會議室。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="6e7ee-155">使用 Microsoft Teams Room 系統，或使用雲端視 (CVI) 聊天室。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="6e7ee-156">分享他們的音訊或視音訊。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-156">Share their audio or video.</span></span>
- <span data-ttu-id="6e7ee-157">查看或參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="6e7ee-158">請參閱會議參與者的視音訊源，除非參與者是使用中的演講者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="6e7ee-159">請參閱使用原生共用 PowerPoint 功能共用的 PowerPoint 檔案，或桌面共用功能 (個別應用程式共用) 。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="6e7ee-160">僅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="6e7ee-160">View-only feature limitations</span></span>

- <span data-ttu-id="6e7ee-161">無論會議的即時字幕設定如何，只有視點出席者一定會看到即時字幕。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="6e7ee-162">目前僅支援英文標題。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="6e7ee-163">串流技術會支援僅觀看的出席者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="6e7ee-164">出席報告不會包含僅顯示出席者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="6e7ee-165">僅觀看的出席者將享有單一影片體驗。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="6e7ee-166">他們可以看到使用中的喇叭或正在共用的內容，但無法同時看到兩者。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="6e7ee-167">我們目前不支援僅供出席者使用圖庫、大型圖庫或共同模式版面配置。 </span><span class="sxs-lookup"><span data-stu-id="6e7ee-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="6e7ee-168">只有觀看的出席者不會有與一般出席者相同的延遲。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="6e7ee-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6e7ee-169"><sup>1</sup></span></span>

  <span data-ttu-id="6e7ee-170"><sup>1</sup> 僅觀看的出席者將在會議進行 30 秒的視像和音訊延遲。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
