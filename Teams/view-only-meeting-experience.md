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
ms.openlocfilehash: ca53c75d12964de2d4d458b240878b14fd2ad04b
ms.sourcegitcommit: ea9a0119d184179300e51f58ca4fee249c12d00a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/28/2021
ms.locfileid: "52699344"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="01fbf-103">Teams 僅供檢視會議體驗</span><span class="sxs-lookup"><span data-stu-id="01fbf-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="01fbf-104">在 Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供僅供檢視廣播。</span><span class="sxs-lookup"><span data-stu-id="01fbf-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="01fbf-105">此功能將於 2021 年 3 月 1 日啟用，但預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="01fbf-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="01fbf-106">Microsoft 365 政府社群雲端 (GCC) 中的功能將於 2021 年 3 月底開始推出。</span><span class="sxs-lookup"><span data-stu-id="01fbf-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="01fbf-107">政府社群雲端 High (GCCH) 和美國國防部 (DoD) 將於稍後推出。</span><span class="sxs-lookup"><span data-stu-id="01fbf-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="01fbf-108">如果您想要將功能設定為預設開啟，您必須在此日期之後變更預設原則。</span><span class="sxs-lookup"><span data-stu-id="01fbf-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="01fbf-109">使用 PowerShell 啟用原則 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。</span><span class="sxs-lookup"><span data-stu-id="01fbf-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="01fbf-110">如果您的會議達到容量，Teams可順暢縮放，以容納 10，000 人只能觀看的廣播體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-110">If your meeting hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="01fbf-111">此外，在遠端工作數量增加的這段時間裡，到今年年底，請利用 20,000 人的更大廣播容量。</span><span class="sxs-lookup"><span data-stu-id="01fbf-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="01fbf-112">Microsoft Teams 允許最多 10,000 位出席者加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="01fbf-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="01fbf-113">在達到主要會議容量之後 (1000 個使用者進入會議) 其他出席者會以僅查看體驗加入會議。</span><span class="sxs-lookup"><span data-stu-id="01fbf-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="01fbf-114">第一次加入會議的出席者，最多可取得主要會議Teams會議體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="01fbf-115">他們可以分享音訊和視訊、查看分享的視訊以及參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="01fbf-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="01fbf-116">主要會議容量到達後加入的出席者將擁有僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="01fbf-117">出席者將能透過 Android 和 iOS Teams和 iOS (使用桌面、web 和) 。</span><span class="sxs-lookup"><span data-stu-id="01fbf-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="01fbf-118">「主要會議」或換句話說，完全互動使用者數目的目前限制容量為 1000 個，包括GCC。</span><span class="sxs-lookup"><span data-stu-id="01fbf-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="01fbf-119">Teams只顯示體驗控制項</span><span class="sxs-lookup"><span data-stu-id="01fbf-119">Teams view-only experience controls</span></span>

<span data-ttu-id="01fbf-120">您可以使用 PowerShell 啟用僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="01fbf-121">若要停用僅以視圖顯示的體驗，您也可以使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="01fbf-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="01fbf-122">日後，您可以在系統管理中心啟用或停用Teams體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="01fbf-123">對使用者的影響</span><span class="sxs-lookup"><span data-stu-id="01fbf-123">Impact to users</span></span>

<span data-ttu-id="01fbf-124">使用者的體驗會根據數個因素而不同。</span><span class="sxs-lookup"><span data-stu-id="01fbf-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="01fbf-125">達到主要會議的容量限制後，如果下列任一情況成立，出席者將無法加入會議：</span><span class="sxs-lookup"><span data-stu-id="01fbf-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="01fbf-126">系統管理員已停用Teams或整個租使用者的僅查看體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="01fbf-127">只能觀看的出席者無法跳過大廳。</span><span class="sxs-lookup"><span data-stu-id="01fbf-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="01fbf-128">舉個例說，如果會議的召集人選擇只讓組織中的人員跳過大廳，而組織外部的出席者嘗試以僅以唯一的出席者加入，他們將無法加入。</span><span class="sxs-lookup"><span data-stu-id="01fbf-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="01fbf-129">當達到主要會議的容量時，會議召集人和簡報者會看到橫幅，通知他們新的出席者會以僅觀看的出席者加入。</span><span class="sxs-lookup"><span data-stu-id="01fbf-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![適用於召集者和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

<span data-ttu-id="01fbf-131">達到主要會議的容量限制後，系統將在加入前的畫面上通知會議出席者他們正在以僅供檢視模式加入。</span><span class="sxs-lookup"><span data-stu-id="01fbf-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 加入前畫面以及顯示給參與者的訊息，告知他們將以僅供檢視模式加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="01fbf-133">如果有空間，使用者一律可以加入主要會議。</span><span class="sxs-lookup"><span data-stu-id="01fbf-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="01fbf-134">達到主要會議容量限制後，如果一或多位出席者離開主要會議，則主要會議會釋出容量可供加入。</span><span class="sxs-lookup"><span data-stu-id="01fbf-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="01fbf-135">加入 (或重新加入) 會議的出席者將加入主要會議，直到再次達到容量限制。</span><span class="sxs-lookup"><span data-stu-id="01fbf-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="01fbf-136">只有觀看體驗的出席者不會自動升級至主要會議，且無法手動升級至主要會議。</span><span class="sxs-lookup"><span data-stu-id="01fbf-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="01fbf-137">如果已設定簡報者與出席者角色，且簡報者在主要會議達到容量後嘗試加入會議，他們將以只能觀看的出席者加入，而且與其他只有視圖的出席者有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="01fbf-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="01fbf-138">支援確保所有簡報者加入主要會議，稍後推出。</span><span class="sxs-lookup"><span data-stu-id="01fbf-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="01fbf-139">主會議一定會保證召集人有空間。</span><span class="sxs-lookup"><span data-stu-id="01fbf-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="01fbf-140">對會議簡報者和召集人的影響</span><span class="sxs-lookup"><span data-stu-id="01fbf-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="01fbf-141">會議簡報者和召集人的限制包括：</span><span class="sxs-lookup"><span data-stu-id="01fbf-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="01fbf-142">您沒有僅供檢視出席者的資訊。</span><span class="sxs-lookup"><span data-stu-id="01fbf-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="01fbf-143">我們不支援僅供檢視出席者使用電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="01fbf-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="01fbf-144">主要會議中的使用者看不到僅查看出席者。</span><span class="sxs-lookup"><span data-stu-id="01fbf-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="01fbf-145">您無法從會議移除僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="01fbf-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="01fbf-146">出席者計數只會反映主要會議中的人員，而非僅顯示會議室中的人員。</span><span class="sxs-lookup"><span data-stu-id="01fbf-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="01fbf-147">因此，簡報者無法取得使用僅供檢視體驗的確切人數。</span><span class="sxs-lookup"><span data-stu-id="01fbf-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="01fbf-148">僅供檢視出席者的體驗</span><span class="sxs-lookup"><span data-stu-id="01fbf-148">Experience for view-only attendees</span></span>

<span data-ttu-id="01fbf-149">Teams 僅供檢視體驗可讓出席者：</span><span class="sxs-lookup"><span data-stu-id="01fbf-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="01fbf-150">聆聽 Teams 主要會議的參與者發言。</span><span class="sxs-lookup"><span data-stu-id="01fbf-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="01fbf-151">觀看目前主講人的視訊摘要 (如果目前主講人有分享視訊)。</span><span class="sxs-lookup"><span data-stu-id="01fbf-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="01fbf-152">查看使用共用桌面或螢幕功能共用的內容。</span><span class="sxs-lookup"><span data-stu-id="01fbf-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="01fbf-153">僅供檢視出席者將無法在會議中體驗下列選項：</span><span class="sxs-lookup"><span data-stu-id="01fbf-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="01fbf-154">如果根據設定的大廳原則或選項，出席者沒有略過大廳的權限，則無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="01fbf-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="01fbf-155">無法使用音訊會議加入僅供檢視會議室。</span><span class="sxs-lookup"><span data-stu-id="01fbf-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="01fbf-156">使用雲端視Microsoft Teams 會議室使用雲端視 (CVI) 聊天室。</span><span class="sxs-lookup"><span data-stu-id="01fbf-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="01fbf-157">無法分享他們的音訊或視訊。</span><span class="sxs-lookup"><span data-stu-id="01fbf-157">Share their audio or video.</span></span>
- <span data-ttu-id="01fbf-158">無法查看或參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="01fbf-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="01fbf-159">無法觀看會議參與者的視訊摘要，除非參與者是目前的主講人。</span><span class="sxs-lookup"><span data-stu-id="01fbf-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="01fbf-160">請參閱PowerPoint即時功能或個別應用程式共用PowerPoint桌面或螢幕共用功能 (共用檔案) 。</span><span class="sxs-lookup"><span data-stu-id="01fbf-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="01fbf-161">在會議中舉手。</span><span class="sxs-lookup"><span data-stu-id="01fbf-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="01fbf-162">傳送或查看反應。</span><span class="sxs-lookup"><span data-stu-id="01fbf-162">Send or see reactions.</span></span>
- <span data-ttu-id="01fbf-163">與整合至會議的任何 3P App 互動Teams包括投票。</span><span class="sxs-lookup"><span data-stu-id="01fbf-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="01fbf-164">僅供檢視功能限制</span><span class="sxs-lookup"><span data-stu-id="01fbf-164">View-only feature limitations</span></span>

- <span data-ttu-id="01fbf-165">只有只能觀看的出席者才能在桌面和 Web 上看到即時字幕。</span><span class="sxs-lookup"><span data-stu-id="01fbf-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="01fbf-166">目前僅支援英文字輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="01fbf-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="01fbf-167">串流技術將支援僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="01fbf-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="01fbf-168">出席報告中不會包含僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="01fbf-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="01fbf-169">僅供檢視出席者將擁有單一視訊體驗。</span><span class="sxs-lookup"><span data-stu-id="01fbf-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="01fbf-170">他們可以看到目前主講人或正在共用的內容，但不能同時看到兩者。</span><span class="sxs-lookup"><span data-stu-id="01fbf-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="01fbf-171">我們目前不支援僅供檢視出席者使用 **圖庫**、**大型圖庫** 或 **在一起模式** 版面配置。</span><span class="sxs-lookup"><span data-stu-id="01fbf-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="01fbf-172">僅供檢視出席者不會與一般出席者一樣有相同的延遲。</span><span class="sxs-lookup"><span data-stu-id="01fbf-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="01fbf-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="01fbf-173"><sup>1</sup></span></span>

  <span data-ttu-id="01fbf-174"><sup>1</sup> 僅供檢視出席者在會議中會有 30 秒的視訊和音訊延遲。</span><span class="sxs-lookup"><span data-stu-id="01fbf-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
