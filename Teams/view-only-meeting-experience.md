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
description: 瞭解系統管理員、簡報者和出席者的 Teams 唯一查看會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f65e1ff47caefd61a9b2753b12da23fd2184e9
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401317"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="86fce-103">Teams 只能查看會議體驗</span><span class="sxs-lookup"><span data-stu-id="86fce-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="86fce-104">將于 2021 年 3 月初提供只能觀看的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-104">View-only meeting experience will be available in early March 2021.</span></span> <span data-ttu-id="86fce-105">這項功能將于 2021 年 3 月 1 日啟用為預設關閉。</span><span class="sxs-lookup"><span data-stu-id="86fce-105">This feature will be enabled on March 1,2021 as default OFF.</span></span> <span data-ttu-id="86fce-106">如果您希望功能為預設 ON，您必須在日期之後變更預設政策。</span><span class="sxs-lookup"><span data-stu-id="86fce-106">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="86fce-107">使用 PowerShell 啟用該策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="86fce-107">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="86fce-108">如果您的會議或網路研討會達到容量，Teams 將會順暢地調整規模，以容納 10，000 人只能觀看的廣播體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-108">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="86fce-109">此外，在增加遠端工作的時間，到今年底，利用更大的 20，000 人廣播。</span><span class="sxs-lookup"><span data-stu-id="86fce-109">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="86fce-110">Microsoft Teams 允許最多 10，000 位出席者加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="86fce-110">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="86fce-111">達到主要會議容量後，其他出席者會以只能觀看的體驗加入。</span><span class="sxs-lookup"><span data-stu-id="86fce-111">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="86fce-112">先加入會議的出席者 ，最多可取得會議容量，獲得完整的 Teams 會議體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-112">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="86fce-113">他們可以共用音訊和視音訊、查看共用視視，以及參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="86fce-113">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="86fce-114">在達到主要會議容量後加入的出席者將享有只能觀看的體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-114">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="86fce-115">我們有完整的 Android 和 iOS 行動支援，讓出席者加入。</span><span class="sxs-lookup"><span data-stu-id="86fce-115">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="86fce-116">在 WW 中，聊天和通話可參與會議人數目前限制為 300 人，GCC、GCC High 和 DoD 為 250 人。</span><span class="sxs-lookup"><span data-stu-id="86fce-116">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="86fce-117">任何擁有 E3/E5/A3/A5 SKU 的召集人，預設會停用只能觀看的體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-117">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="86fce-118">無需進一步設定或設定。</span><span class="sxs-lookup"><span data-stu-id="86fce-118">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="86fce-119">停用 Teams 只能查看體驗</span><span class="sxs-lookup"><span data-stu-id="86fce-119">Disable Teams view-only experience</span></span>

<span data-ttu-id="86fce-120">系統管理員可以使用 PowerShell 停用只能查看的體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-120">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="86fce-121">未來系統管理員也可以停用 Teams 系統管理中心的只能查看體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-121">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="86fce-122">影響使用者</span><span class="sxs-lookup"><span data-stu-id="86fce-122">Impact to users</span></span>

<span data-ttu-id="86fce-123">使用者的體驗會因幾項因素而異。</span><span class="sxs-lookup"><span data-stu-id="86fce-123">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="86fce-124">當達到主要會議容量時，如果下列任一項為 True，出席者將無法加入會議：</span><span class="sxs-lookup"><span data-stu-id="86fce-124">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="86fce-125">系統管理員已停用 Teams 只能查看的體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-125">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="86fce-126">出席者沒有跳過大廳的許可權。</span><span class="sxs-lookup"><span data-stu-id="86fce-126">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="86fce-127">當達到主要會議容量時，會議召集人和簡報者會看到橫幅，通知他們已達會議容量，且新的出席者將加入只能觀看的出席者。</span><span class="sxs-lookup"><span data-stu-id="86fce-127">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![適用于召集人和簡報者的 Teams 用戶端和橫幅亂七八糟](media/chat-and-banner-message.png)

<span data-ttu-id="86fce-129">當達到主要會議容量時，會議出席者在加入前畫面上會通知他們以僅以唯一模式加入。</span><span class="sxs-lookup"><span data-stu-id="86fce-129">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 加入前畫面，以及參與者的訊息，告知他們將在僅以只能觀看模式加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="86fce-131">如果有空間，使用者一定會加入主要會議。</span><span class="sxs-lookup"><span data-stu-id="86fce-131">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="86fce-132">如果主要會議達到容量，且有一或多個出席者離開主要會議，則主會議具有可用的容量。</span><span class="sxs-lookup"><span data-stu-id="86fce-132">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="86fce-133">加入會議 (或重新加入會議) 會加入主要會議，直到會議再次到達容量。</span><span class="sxs-lookup"><span data-stu-id="86fce-133">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="86fce-134">只有觀看體驗的出席者不會自動升級至主要會議，目前無法手動升級至主要會議。</span><span class="sxs-lookup"><span data-stu-id="86fce-134">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="86fce-135">如果尚未設定簡報者/出席者角色，主會議的空格會先到先用。</span><span class="sxs-lookup"><span data-stu-id="86fce-135">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="86fce-136">一旦達到會議容量，所有其他使用者就會以只能查看的體驗加入。</span><span class="sxs-lookup"><span data-stu-id="86fce-136">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="86fce-137">對會議簡報者的影響</span><span class="sxs-lookup"><span data-stu-id="86fce-137">Impact to meeting presenters</span></span>

<span data-ttu-id="86fce-138">會議簡報者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="86fce-138">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="86fce-139">您沒有僅查看出席者的資訊。</span><span class="sxs-lookup"><span data-stu-id="86fce-139">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="86fce-140">我們不支援只有視圖的出席者使用 E-discovery。</span><span class="sxs-lookup"><span data-stu-id="86fce-140">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="86fce-141">使用者看不到只能查看的出席者。</span><span class="sxs-lookup"><span data-stu-id="86fce-141">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="86fce-142">無法從會議移除只能查看的出席者。</span><span class="sxs-lookup"><span data-stu-id="86fce-142">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="86fce-143">出席者計數只會反映會議中的人員，不會反映溢位會議室中的人員。</span><span class="sxs-lookup"><span data-stu-id="86fce-143">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="86fce-144">因此，簡報者無法精確計算誰在只能觀看的體驗中。</span><span class="sxs-lookup"><span data-stu-id="86fce-144">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="86fce-145">僅供觀看的出席者使用體驗</span><span class="sxs-lookup"><span data-stu-id="86fce-145">Experience for view-only attendees</span></span>

<span data-ttu-id="86fce-146">Teams 只能查看體驗可讓出席者：</span><span class="sxs-lookup"><span data-stu-id="86fce-146">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="86fce-147">聆聽 Teams 主要會議的參與者。</span><span class="sxs-lookup"><span data-stu-id="86fce-147">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="86fce-148">如果使用中喇叭正在分享視 (，請觀看使用中喇叭的視) 。</span><span class="sxs-lookup"><span data-stu-id="86fce-148">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="86fce-149">查看使用共用桌面功能共用的內容。</span><span class="sxs-lookup"><span data-stu-id="86fce-149">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="86fce-150">只有看視圖的出席者將無法在會議中體驗下列選項：</span><span class="sxs-lookup"><span data-stu-id="86fce-150">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="86fce-151">如果出席者沒有許可權根據設定大廳政策或選項來避開大廳，請加入會議。</span><span class="sxs-lookup"><span data-stu-id="86fce-151">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="86fce-152">透過音訊會議加入溢位會議室。</span><span class="sxs-lookup"><span data-stu-id="86fce-152">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="86fce-153">透過 Microsoft Teams Room 系統或透過雲端視 (CVI 服務加入溢位) 聊天室。</span><span class="sxs-lookup"><span data-stu-id="86fce-153">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="86fce-154">分享他們的音訊或視視。</span><span class="sxs-lookup"><span data-stu-id="86fce-154">Share their audio or video.</span></span>
- <span data-ttu-id="86fce-155">查看或參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="86fce-155">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="86fce-156">除非參與者是活動演講者，否則請觀看會議參與者的影片來源。</span><span class="sxs-lookup"><span data-stu-id="86fce-156">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="86fce-157">查看使用原生共用 PowerPoint 功能共用的 PowerPoint 檔案，或桌面共用應用程式 (共用應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="86fce-157">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="86fce-158">僅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="86fce-158">View-only feature limitations</span></span>

- <span data-ttu-id="86fce-159">不論會議的即時字幕設定如何，只有觀看的出席者一定會看到即時字幕。</span><span class="sxs-lookup"><span data-stu-id="86fce-159">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="86fce-160">目前僅支援英文標題。</span><span class="sxs-lookup"><span data-stu-id="86fce-160">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="86fce-161">串流技術將支援只有觀看的出席者。</span><span class="sxs-lookup"><span data-stu-id="86fce-161">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="86fce-162">只有查看的出席者不會包含在出席報告中。</span><span class="sxs-lookup"><span data-stu-id="86fce-162">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="86fce-163">只有觀看的出席者將擁有單一影片體驗。</span><span class="sxs-lookup"><span data-stu-id="86fce-163">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="86fce-164">他們可以看到使用中的喇叭或共用的內容，但無法同時看到兩者。</span><span class="sxs-lookup"><span data-stu-id="86fce-164">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="86fce-165">我們目前不支援只有觀看的出席者使用圖庫、大型圖庫或共聚模式版面配置。 </span><span class="sxs-lookup"><span data-stu-id="86fce-165">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="86fce-166">只有觀看的出席者不會有與一般出席者相同的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="86fce-166">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="86fce-167"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="86fce-167"><sup>1</sup></span></span>

  <span data-ttu-id="86fce-168"><sup>1</sup> 只有觀看的出席者在會議進行 30 秒的視像和音訊延遲。</span><span class="sxs-lookup"><span data-stu-id="86fce-168"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="86fce-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="86fce-169">Related topics</span></span>

- [<span data-ttu-id="86fce-170">Teams 的進級通訊附加元件</span><span class="sxs-lookup"><span data-stu-id="86fce-170">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="86fce-171">Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="86fce-171">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
