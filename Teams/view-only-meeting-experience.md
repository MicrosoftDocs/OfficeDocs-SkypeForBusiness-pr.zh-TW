---
title: 僅供檢視會議體驗
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解適用於系統管理員、簡報者和出席者的 Teams 僅供檢視會議體驗
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25cd674e5f93e4f52f0a2cecd2acff97e4844834
ms.sourcegitcommit: f4393657584666842e874d526a08cfa1137b911d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215328"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="e4e6e-103">Teams 僅供檢視會議體驗</span><span class="sxs-lookup"><span data-stu-id="e4e6e-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="e4e6e-104">在 Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供僅供檢視廣播。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="e4e6e-105">此功能將於 2021 年 3 月 1 日啟用，但預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="e4e6e-106">Microsoft 365 政府社群雲端 (GCC) 中的功能將於 2021 年 3 月底開始推出。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="e4e6e-107">政府社群雲端 High (GCCH) 和美國國防部 (DoD) 將於稍後推出。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="e4e6e-108">如果您想要將功能設定為預設開啟，您必須在此日期之後變更預設原則。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="e4e6e-109">使用 PowerShell 啟用原則 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="e4e6e-110">如果您的會議或網路研討會達到容量限制，Teams 將會無縫調整，以容納 10,000 人僅供檢視廣播體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="e4e6e-111">此外，在遠端工作數量增加的這段時間裡，到今年年底，請利用 20,000 人的更大廣播容量。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="e4e6e-112">Microsoft Teams 允許最多 10,000 位出席者加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="e4e6e-113">達到主要會議容量之後 (在 WW 中 300 人或 GCC 使用者有 250 人進入會議) 之後，其他出席者會以僅查看體驗加入會議。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-113">After the capacity of the main meeting has been reached (which is when 300 in WW or 250 in GCC users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="e4e6e-114">第一次加入會議的出席者，最多可取得主要會議的容量，並取得完整的 Teams 會議體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="e4e6e-115">他們可以分享音訊和視訊、查看分享的視訊以及參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="e4e6e-116">主要會議容量到達後加入的出席者將擁有僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="e4e6e-117">出席者將能透過 Android 和 iOS 版桌上出版、Web 版和 Teams 行動 (加入) 。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="e4e6e-118">「主要會議」或換句話說，「完全互動」使用者數目的目前限制為 WW 為 300，GCC、GCC High 和 DoD 為 250。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="e4e6e-119">Teams 只能查看體驗控制項</span><span class="sxs-lookup"><span data-stu-id="e4e6e-119">Teams view-only experience controls</span></span>

<span data-ttu-id="e4e6e-120">您可以使用 PowerShell 啟用僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="e4e6e-121">若要停用僅以視圖顯示的體驗，您也可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="e4e6e-122">您日後將能夠啟用或停用 Teams 系統管理中心中的僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="e4e6e-123">對使用者的影響</span><span class="sxs-lookup"><span data-stu-id="e4e6e-123">Impact to users</span></span>

<span data-ttu-id="e4e6e-124">使用者的體驗會根據數個因素而不同。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="e4e6e-125">達到主要會議的容量限制後，如果下列任一情況成立，出席者將無法加入會議：</span><span class="sxs-lookup"><span data-stu-id="e4e6e-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="e4e6e-126">系統管理員已停用召集人或整個租使用者的 Teams 僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="e4e6e-127">只能觀看的出席者無法跳過大廳。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="e4e6e-128">舉個例說，如果會議的召集人選擇只讓組織中的人員跳過大廳，而組織外部的出席者嘗試以僅以唯一的出席者加入，就會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they'll be rejected.</span></span>

<span data-ttu-id="e4e6e-129">當達到主要會議的容量時，會議召集人和簡報者會看到橫幅，通知他們新的出席者會以僅觀看的出席者加入。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![適用於召集者和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

<span data-ttu-id="e4e6e-131">達到主要會議的容量限制後，系統將在加入前的畫面上通知會議出席者他們正在以僅供檢視模式加入。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 加入前畫面以及顯示給參與者的訊息，告知他們將以僅供檢視模式加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="e4e6e-133">如果有空間，使用者一律可以加入主要會議。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="e4e6e-134">達到主要會議容量限制後，如果一或多位出席者離開主要會議，則主要會議會釋出容量可供加入。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="e4e6e-135">加入 (或重新加入) 會議的出席者將加入主要會議，直到再次達到容量限制。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="e4e6e-136">處於僅供檢視體驗的出席者無法自動升級到主要會議，且目前無法手動將他們升級到主要會議。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="e4e6e-137">如果簡報者與出席者角色已設定，且簡報者在主要會議達到容量後嘗試加入會議，他們將以僅觀看出席者的方式加入會議，而且與其他唯一的出席者有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting of has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="e4e6e-138">支援確保所有簡報者加入主要會議，稍後推出。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="e4e6e-139">主會議一定會保證召集人有空間。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="e4e6e-140">對會議簡報者的影響</span><span class="sxs-lookup"><span data-stu-id="e4e6e-140">Impact to meeting presenters</span></span>

<span data-ttu-id="e4e6e-141">對會議簡報者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="e4e6e-141">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="e4e6e-142">您沒有僅供檢視出席者的資訊。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="e4e6e-143">我們不支援僅供檢視出席者使用電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="e4e6e-144">主要會議中的使用者看不到僅查看出席者。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="e4e6e-145">您無法從會議移除僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="e4e6e-146">出席者計數只會反映主要會議中的人員，而非僅顯示會議室中的人員。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="e4e6e-147">因此，簡報者無法取得使用僅供檢視體驗的確切人數。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="e4e6e-148">僅供檢視出席者的體驗</span><span class="sxs-lookup"><span data-stu-id="e4e6e-148">Experience for view-only attendees</span></span>

<span data-ttu-id="e4e6e-149">Teams 僅供檢視體驗可讓出席者：</span><span class="sxs-lookup"><span data-stu-id="e4e6e-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="e4e6e-150">聆聽 Teams 主要會議的參與者發言。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="e4e6e-151">觀看目前主講人的視訊摘要 (如果目前主講人有分享視訊)。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="e4e6e-152">查看使用共用桌面或螢幕功能共用的內容。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="e4e6e-153">僅供檢視出席者將無法在會議中體驗下列選項：</span><span class="sxs-lookup"><span data-stu-id="e4e6e-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="e4e6e-154">如果根據設定的大廳原則或選項，出席者沒有略過大廳的權限，則無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="e4e6e-155">無法使用音訊會議加入僅供檢視會議室。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="e4e6e-156">使用 Microsoft Teams Room 系統，或使用雲端視 (CVI) 聊天室。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="e4e6e-157">無法分享他們的音訊或視訊。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-157">Share their audio or video.</span></span>
- <span data-ttu-id="e4e6e-158">無法查看或參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-158">See or participate in the meeting chat.</span></span>
  - <span data-ttu-id="e4e6e-159">前 1000 (或 300 視您的主要會議限制) 受邀加入會議的使用者將會新加入聊天。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-159">The first 1000 (or 300 depending on your main meeting limit) users invited to the meeting will be added to the chat.</span></span>
  - <span data-ttu-id="e4e6e-160">雖然只有視視圖的使用者不會在會議看到聊天，但如果他們是第一個受邀的 350 人，他們仍然可以在主要 App 上聊天。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-160">While view-only users won't see the chat in the meeting, they might still be able to chat on the main app if they were the first 350 people invited.</span></span>
  - <span data-ttu-id="e4e6e-161">相反地，如果互動式使用者不是前 350 位受邀加入會議的使用者的一部分，他們無法存取主要 Teams App 和會議中的會議聊天。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-161">Conversely, if an interactive user wasn't part of the first 350 users invited to the meeting, they'll not get access to the meeting chat both on the main Teams App and in the meeting.</span></span>
- <span data-ttu-id="e4e6e-162">無法觀看會議參與者的視訊摘要，除非參與者是目前的主講人。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-162">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="e4e6e-163">請參閱使用 PowerPoint Live 功能共用的 PowerPoint 檔案或個別應用程式共用 (桌面或螢幕共用功能) 。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-163">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="e4e6e-164">在會議中舉手。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-164">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="e4e6e-165">傳送或查看反應。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-165">Send or see reactions.</span></span>
- <span data-ttu-id="e4e6e-166">與整合至 Teams 會議的任何 3P App 互動，包括投票。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-166">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="e4e6e-167">僅供檢視功能限制</span><span class="sxs-lookup"><span data-stu-id="e4e6e-167">View-only feature limitations</span></span>

- <span data-ttu-id="e4e6e-168">只有只能觀看的出席者才能在桌面和 Web 上看到即時字幕。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-168">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="e4e6e-169">目前僅支援英文字輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-169">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="e4e6e-170">串流技術將支援僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-170">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="e4e6e-171">出席報告中不會包含僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-171">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="e4e6e-172">僅供檢視出席者將擁有單一視訊體驗。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-172">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="e4e6e-173">他們可以看到目前主講人或正在共用的內容，但不能同時看到兩者。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-173">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="e4e6e-174">我們目前不支援僅供檢視出席者使用 **圖庫**、**大型圖庫** 或 **在一起模式** 版面配置。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-174">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="e4e6e-175">僅供檢視出席者不會與一般出席者一樣有相同的延遲。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-175">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="e4e6e-176"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e4e6e-176"><sup>1</sup></span></span>

  <span data-ttu-id="e4e6e-177"><sup>1</sup> 僅供檢視出席者在會議中會有 30 秒的視訊和音訊延遲。</span><span class="sxs-lookup"><span data-stu-id="e4e6e-177"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
