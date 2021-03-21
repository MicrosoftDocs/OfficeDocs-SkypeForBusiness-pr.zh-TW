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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875053"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="de9a3-103">Teams 僅供檢視會議體驗</span><span class="sxs-lookup"><span data-stu-id="de9a3-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="de9a3-104">在 Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供僅供檢視廣播。</span><span class="sxs-lookup"><span data-stu-id="de9a3-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="de9a3-105">此功能將於 2021 年 3 月 1 日啟用，但預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="de9a3-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="de9a3-106">Microsoft 365 政府社群雲端 (GCC) 中的功能將於 2021 年 3 月底開始推出。</span><span class="sxs-lookup"><span data-stu-id="de9a3-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="de9a3-107">政府社群雲端 High (GCCH) 和美國國防部 (DoD) 將於稍後推出。</span><span class="sxs-lookup"><span data-stu-id="de9a3-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="de9a3-108">如果您想要將功能設定為預設開啟，您必須在此日期之後變更預設原則。</span><span class="sxs-lookup"><span data-stu-id="de9a3-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="de9a3-109">使用 PowerShell 啟用原則 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。</span><span class="sxs-lookup"><span data-stu-id="de9a3-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="de9a3-110">如果您的會議或網路研討會達到容量限制，Teams 將會無縫調整，以容納 10,000 人僅供檢視廣播體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="de9a3-111">此外，在遠端工作數量增加的這段時間裡，到今年年底，請利用 20,000 人的更大廣播容量。</span><span class="sxs-lookup"><span data-stu-id="de9a3-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="de9a3-112">Microsoft Teams 允許最多 10,000 位出席者加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="de9a3-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="de9a3-113">達到主要會議的容量限制後，其他出席者將透過僅供檢視體驗加入。</span><span class="sxs-lookup"><span data-stu-id="de9a3-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="de9a3-114">第一次加入會議的出席者，直到達到會議容量限制前，都可獲得完整的 Teams 會議體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="de9a3-115">他們可以分享音訊和視訊、查看分享的視訊以及參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="de9a3-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="de9a3-116">主要會議容量到達後加入的出席者將擁有僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="de9a3-117">我們擁有完整的 Android 和 iOS 行動裝置支援，可讓出席者加入。</span><span class="sxs-lookup"><span data-stu-id="de9a3-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="de9a3-118">目前在會議中可聊天和通話的人數限制，WW 為 300 人，而 GCC、GCC High 和 DoD 為 250 人。</span><span class="sxs-lookup"><span data-stu-id="de9a3-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="de9a3-119">對於擁有 E3/E5/A3/A5 SKU 的任何召集人，預設會停用僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="de9a3-120">不需要進一步設定。</span><span class="sxs-lookup"><span data-stu-id="de9a3-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="de9a3-121">停用 Teams 僅供檢視體驗</span><span class="sxs-lookup"><span data-stu-id="de9a3-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="de9a3-122">系統管理員可以使用 PowerShell 停用僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="de9a3-123">未來，系統管理員也可以在 Teams 系統管理中心中停用的僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="de9a3-124">對使用者的影響</span><span class="sxs-lookup"><span data-stu-id="de9a3-124">Impact to users</span></span>

<span data-ttu-id="de9a3-125">使用者的體驗會根據數個因素而不同。</span><span class="sxs-lookup"><span data-stu-id="de9a3-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="de9a3-126">達到主要會議的容量限制後，如果下列任一情況成立，出席者將無法加入會議：</span><span class="sxs-lookup"><span data-stu-id="de9a3-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="de9a3-127">系統管理員已停用 Teams 僅供檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="de9a3-128">出席者沒有略過大廳的權限。</span><span class="sxs-lookup"><span data-stu-id="de9a3-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="de9a3-129">達到主要會議的容量限制後，會議召集人和簡報者會看到一個橫幅，通知他們已達到會議容量限制，新的出席者將加入僅供檢視會議。</span><span class="sxs-lookup"><span data-stu-id="de9a3-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![適用於召集者和簡報者的 Teams 用戶端和橫幅訊息](media/chat-and-banner-message.png)

<span data-ttu-id="de9a3-131">達到主要會議的容量限制後，系統將在加入前的畫面上通知會議出席者他們正在以僅供檢視模式加入。</span><span class="sxs-lookup"><span data-stu-id="de9a3-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 加入前畫面以及顯示給參與者的訊息，告知他們將以僅供檢視模式加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="de9a3-133">如果有空間，使用者一律可以加入主要會議。</span><span class="sxs-lookup"><span data-stu-id="de9a3-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="de9a3-134">達到主要會議容量限制後，如果一或多位出席者離開主要會議，則主要會議會釋出容量可供加入。</span><span class="sxs-lookup"><span data-stu-id="de9a3-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="de9a3-135">加入 (或重新加入) 會議的出席者將加入主要會議，直到再次達到容量限制。</span><span class="sxs-lookup"><span data-stu-id="de9a3-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="de9a3-136">處於僅供檢視體驗的出席者無法自動升級到主要會議，且目前無法手動將他們升級到主要會議。</span><span class="sxs-lookup"><span data-stu-id="de9a3-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="de9a3-137">如果尚未設定簡報者/出席者角色，主要會議的空間會採用先到先入的原則。</span><span class="sxs-lookup"><span data-stu-id="de9a3-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="de9a3-138">達到會議容量限制後，所有其他使用者將以僅供檢視體驗加入。</span><span class="sxs-lookup"><span data-stu-id="de9a3-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="de9a3-139">對會議簡報者的影響</span><span class="sxs-lookup"><span data-stu-id="de9a3-139">Impact to meeting presenters</span></span>

<span data-ttu-id="de9a3-140">對會議簡報者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="de9a3-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="de9a3-141">您沒有僅供檢視出席者的資訊。</span><span class="sxs-lookup"><span data-stu-id="de9a3-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="de9a3-142">我們不支援僅供檢視出席者使用電子文件探索。</span><span class="sxs-lookup"><span data-stu-id="de9a3-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="de9a3-143">使用者看不到僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="de9a3-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="de9a3-144">您無法從會議移除僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="de9a3-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="de9a3-145">出席者數只會反映會議中的人員，不會反映僅供檢視會議室中的人員。</span><span class="sxs-lookup"><span data-stu-id="de9a3-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="de9a3-146">因此，簡報者無法取得使用僅供檢視體驗的確切人數。</span><span class="sxs-lookup"><span data-stu-id="de9a3-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="de9a3-147">僅供檢視出席者的體驗</span><span class="sxs-lookup"><span data-stu-id="de9a3-147">Experience for view-only attendees</span></span>

<span data-ttu-id="de9a3-148">Teams 僅供檢視體驗可讓出席者：</span><span class="sxs-lookup"><span data-stu-id="de9a3-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="de9a3-149">聆聽 Teams 主要會議的參與者發言。</span><span class="sxs-lookup"><span data-stu-id="de9a3-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="de9a3-150">觀看目前主講人的視訊摘要 (如果目前主講人有分享視訊)。</span><span class="sxs-lookup"><span data-stu-id="de9a3-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="de9a3-151">使用共用桌面功能查看共用的內容。</span><span class="sxs-lookup"><span data-stu-id="de9a3-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="de9a3-152">僅供檢視出席者將無法在會議中體驗下列選項：</span><span class="sxs-lookup"><span data-stu-id="de9a3-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="de9a3-153">如果根據設定的大廳原則或選項，出席者沒有略過大廳的權限，則無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="de9a3-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="de9a3-154">無法使用音訊會議加入僅供檢視會議室。</span><span class="sxs-lookup"><span data-stu-id="de9a3-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="de9a3-155">無法使用 Microsoft Teams 會議室系統或雲端視訊 Interop (CVI) 服務加入僅供檢視會議室。</span><span class="sxs-lookup"><span data-stu-id="de9a3-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="de9a3-156">無法分享他們的音訊或視訊。</span><span class="sxs-lookup"><span data-stu-id="de9a3-156">Share their audio or video.</span></span>
- <span data-ttu-id="de9a3-157">無法查看或參與會議聊天。</span><span class="sxs-lookup"><span data-stu-id="de9a3-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="de9a3-158">無法觀看會議參與者的視訊摘要，除非參與者是目前的主講人。</span><span class="sxs-lookup"><span data-stu-id="de9a3-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="de9a3-159">無法查看使用原生共用 PowerPoint 功能或個別應用程式共用 (桌面共用除外) 共用的 PowerPoint 檔案。</span><span class="sxs-lookup"><span data-stu-id="de9a3-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="de9a3-160">僅供檢視功能限制</span><span class="sxs-lookup"><span data-stu-id="de9a3-160">View-only feature limitations</span></span>

- <span data-ttu-id="de9a3-161">無論該會議的即時輔助字幕設定如何，僅供檢視出席者將一律看到即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="de9a3-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="de9a3-162">目前僅支援英文字輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="de9a3-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="de9a3-163">串流技術將支援僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="de9a3-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="de9a3-164">出席報告中不會包含僅供檢視出席者。</span><span class="sxs-lookup"><span data-stu-id="de9a3-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="de9a3-165">僅供檢視出席者將擁有單一視訊體驗。</span><span class="sxs-lookup"><span data-stu-id="de9a3-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="de9a3-166">他們可以看到目前主講人或正在共用的內容，但不能同時看到兩者。</span><span class="sxs-lookup"><span data-stu-id="de9a3-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="de9a3-167">我們目前不支援僅供檢視出席者使用 **圖庫**、**大型圖庫** 或 **在一起模式** 版面配置。</span><span class="sxs-lookup"><span data-stu-id="de9a3-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="de9a3-168">僅供檢視出席者不會與一般出席者一樣有相同的延遲。</span><span class="sxs-lookup"><span data-stu-id="de9a3-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="de9a3-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="de9a3-169"><sup>1</sup></span></span>

  <span data-ttu-id="de9a3-170"><sup>1</sup> 僅供檢視出席者在會議中會有 30 秒的視訊和音訊延遲。</span><span class="sxs-lookup"><span data-stu-id="de9a3-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
