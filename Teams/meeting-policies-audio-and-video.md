---
title: 管理音訊和視音訊的會議政策
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: 瞭解如何在音訊和視Teams中管理會議策略設定。
ms.openlocfilehash: e599948a78baa96849e9ddaedf6eb2a4a131ebf4
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004184"
---
# <a name="meeting-policy-settings-for-audio--video"></a><span data-ttu-id="3d7d0-103">音訊和視&設定</span><span class="sxs-lookup"><span data-stu-id="3d7d0-103">Meeting policy settings for audio & video</span></span>

<span data-ttu-id="3d7d0-104"><a name="bkaudioandvideo"> </a>
<a name="ndi"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7d0-104"><a name="bkaudioandvideo"> </a>
<a name="ndi"> </a></span></span>

<span data-ttu-id="3d7d0-105">本文將說明音訊和視音訊特有的會議策略設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-105">This article describes the meeting policy settings specific to audio and video.</span></span> <span data-ttu-id="3d7d0-106">這些包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="3d7d0-106">These include the following:</span></span>

- [<span data-ttu-id="3d7d0-107">允許轉錄</span><span class="sxs-lookup"><span data-stu-id="3d7d0-107">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="3d7d0-108">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="3d7d0-108">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="3d7d0-109">IP 音訊的模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-109">Mode for IP audio</span></span>](#mode-for-ip-audio)
- [<span data-ttu-id="3d7d0-110">IP 視訊的模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-110">Mode for IP video</span></span>](#mode-for-ip-video)
- [<span data-ttu-id="3d7d0-111">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-111">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="3d7d0-112">媒體位元速率 (KB)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-112">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="3d7d0-113">視像篩選模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-113">Video filters mode</span></span>](#video-filters-mode)
- [<span data-ttu-id="3d7d0-114">允許自訂背景設定</span><span class="sxs-lookup"><span data-stu-id="3d7d0-114">Allow custom background settings</span></span>](#allow-custom-background-settings)

### <a name="allow-transcription"></a><span data-ttu-id="3d7d0-115">允許轉錄</span><span class="sxs-lookup"><span data-stu-id="3d7d0-115">Allow transcription</span></span>

<span data-ttu-id="3d7d0-116">這是每個召集人和每個使用者策略的組合。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-116">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3d7d0-117">此設定可控制在播放會議錄製內容期間是否提供字幕和謄寫功能。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-117">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="3d7d0-118">如果您關閉此功能，則 [**錄製**] 和 [**CC**] 選項在播放會議錄製內容期間無法使用。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-118">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="3d7d0-119">開始錄製的人員需要開啟此設定，讓錄製也包含謄寫。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-119">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="3d7d0-120">請注意，錄製的會議目前僅支援將語言設定為英文Teams以及會議中使用英文時的使用者。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-120">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

### <a name="allow-cloud-recording"></a><span data-ttu-id="3d7d0-121">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="3d7d0-121">Allow cloud recording</span></span>

<span data-ttu-id="3d7d0-122">這是每個召集人和每個使用者策略的組合。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-122">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3d7d0-123">此設定可控制是否可以錄製此使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-123">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="3d7d0-124">如果參與者已開啟該策略設定，且他們是來自同一個組織的已驗證使用者，會議召集人或其他會議參與者可以開始錄製。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-124">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="3d7d0-125">組織外部人員 (例如，同盟和匿名使用者) 無法開始錄製。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-125">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="3d7d0-126">來賓使用者無法開始或停止錄製。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-126">Guest users can't start or stop the recording.</span></span>

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

<span data-ttu-id="3d7d0-128">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-128">Let's look at the following example.</span></span>

|<span data-ttu-id="3d7d0-129">使用者</span><span class="sxs-lookup"><span data-stu-id="3d7d0-129">User</span></span> |<span data-ttu-id="3d7d0-130">會議原則</span><span class="sxs-lookup"><span data-stu-id="3d7d0-130">Meeting policy</span></span>  |<span data-ttu-id="3d7d0-131">允許雲端錄製</span><span class="sxs-lookup"><span data-stu-id="3d7d0-131">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3d7d0-132">Daniela</span><span class="sxs-lookup"><span data-stu-id="3d7d0-132">Daniela</span></span> | <span data-ttu-id="3d7d0-133">全域</span><span class="sxs-lookup"><span data-stu-id="3d7d0-133">Global</span></span>   | <span data-ttu-id="3d7d0-134">關閉</span><span class="sxs-lookup"><span data-stu-id="3d7d0-134">Off</span></span> |
|<span data-ttu-id="3d7d0-135">Amanda</span><span class="sxs-lookup"><span data-stu-id="3d7d0-135">Amanda</span></span> | <span data-ttu-id="3d7d0-136">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d7d0-136">Location1MeetingPolicy</span></span> | <span data-ttu-id="3d7d0-137">開啟</span><span class="sxs-lookup"><span data-stu-id="3d7d0-137">On</span></span>|
|<span data-ttu-id="3d7d0-138">John (外部使用者)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-138">John (external user)</span></span> | <span data-ttu-id="3d7d0-139">不適用</span><span class="sxs-lookup"><span data-stu-id="3d7d0-139">Not applicable</span></span> | <span data-ttu-id="3d7d0-140">不適用</span><span class="sxs-lookup"><span data-stu-id="3d7d0-140">Not applicable</span></span>|

<span data-ttu-id="3d7d0-141">無法錄製由 Daniela 組織的會議，已啟用策略設定的 Amanda 無法錄製由 Daniela 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-141">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="3d7d0-142">不過，您可以錄製由 Amanda 組織的會議，但已停用策略設定且 John 是外部使用者的 Daniela 無法錄製由 Amanda 組織的會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-142">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="3d7d0-143">若要深入了解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-143">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="mode-for-ip-audio"></a><span data-ttu-id="3d7d0-144">IP 音訊的模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-144">Mode for IP audio</span></span>

<span data-ttu-id="3d7d0-145">這是每一使用者原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-145">This is a per-user policy.</span></span> <span data-ttu-id="3d7d0-146">此設定可控制是否可以在會議和群組通話中開啟音訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-146">This setting controls whether audio can be turned on in meetings and group calls.</span></span> <span data-ttu-id="3d7d0-147">以下是此設定的值。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-147">Here are the values for this setting.</span></span>

|<span data-ttu-id="3d7d0-148">設定值</span><span class="sxs-lookup"><span data-stu-id="3d7d0-148">Setting value</span></span> |<span data-ttu-id="3d7d0-149">行為</span><span class="sxs-lookup"><span data-stu-id="3d7d0-149">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3d7d0-150">**已啟用傳出和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-150">**Outgoing and incoming audio enabled**</span></span>    |<span data-ttu-id="3d7d0-p107">會議中允許傳出和傳入音訊。這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-p107">Outgoing and incoming audio is allowed in the meeting. This is the default setting.</span></span> |
|<span data-ttu-id="3d7d0-153">**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-153">**Disabled**</span></span>     |<span data-ttu-id="3d7d0-154">會議中已關閉傳出和傳入音訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-154">Outgoing and incoming audio is turned off in the meeting.</span></span>     |

<span data-ttu-id="3d7d0-155">如果使用者設為 **已** 停用，該使用者仍然可以排程和組織會議，但他們無法使用音訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-155">If set to **Disabled** for a user, that user can still schedule and organize meetings but they can't use audio.</span></span> <span data-ttu-id="3d7d0-156">若要加入會議，他們必須透過公用交換電話網路 (PSTN) 或透過電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-156">To join a meeting, they have to dial in through the Public Switched Telephone Network (PSTN) or have the meeting call and join them by phone.</span></span> <span data-ttu-id="3d7d0-157">未獲指派任何原則的會議參與者 (例如匿名參與者)，預設會將此設定為 [已啟用傳出和傳入音訊 **]**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-157">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming audio enabled** by default.</span></span> <span data-ttu-id="3d7d0-158">在 Teams 行動用戶端上，如果已停用此設定，使用者必須透過 PSTN 撥入會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-158">On Teams mobile clients, if this setting is disabled, the user has to dial in to the meeting through the PSTN.</span></span>

<span data-ttu-id="3d7d0-159">此設定不適用一對一通話。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-159">This setting doesn't apply to 1:1 calls.</span></span> <span data-ttu-id="3d7d0-160">若要限制一對一通話，請設定 Teams [通話原則 []](teams-calling-policy.md) 並關閉 [撥打私人通話 **]** 設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-160">To restrict 1:1 calls, configure a Teams [calling policy](teams-calling-policy.md) and turn off the **Make private calls** setting.</span></span> <span data-ttu-id="3d7d0-161">此設定也不適用會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-161">This setting also doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="3d7d0-162">此設定尚無法於 Microsoft 365 政府社群雲端 (GCC)、GCC High 或美國國防部 (DoD) 環境中取得。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-162">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

<span data-ttu-id="3d7d0-163">若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-163">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="mode-for-ip-video"></a><span data-ttu-id="3d7d0-164">IP 視訊的模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-164">Mode for IP video</span></span>

<span data-ttu-id="3d7d0-165">這是每一使用者原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-165">This is a per-user policy.</span></span> <span data-ttu-id="3d7d0-166">此設定可控制是否可以在會議和群組通話中開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-166">This setting controls whether video can be turned on in meetings and group calls.</span></span> <span data-ttu-id="3d7d0-167">以下是此設定的值。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-167">Here are the values for this setting.</span></span>

|<span data-ttu-id="3d7d0-168">設定值</span><span class="sxs-lookup"><span data-stu-id="3d7d0-168">Setting value</span></span> |<span data-ttu-id="3d7d0-169">行為</span><span class="sxs-lookup"><span data-stu-id="3d7d0-169">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3d7d0-170">**已啟用傳出和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-170">**Outgoing and incoming video enabled**</span></span>    | <span data-ttu-id="3d7d0-171">會議允許外發和傳入視像。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-171">Outgoing and incoming video is allowed in the meeting.</span></span> <span data-ttu-id="3d7d0-172">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-172">This is the default setting.</span></span> |
|<span data-ttu-id="3d7d0-173">**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-173">**Disabled**</span></span>     | <span data-ttu-id="3d7d0-174">會議中已關閉傳出和傳入視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-174">Outgoing and incoming video is turned off in the meeting.</span></span> <span data-ttu-id="3d7d0-175">在 Teams 行動用戶端上，使用者無法分享會議中的視訊或相片。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-175">On Teams mobile clients, users can't share videos or photos in the meeting.</span></span> <br><br><span data-ttu-id="3d7d0-176">請注意，如果 **IP 音訊模式** 已停用， **則 IP 視** 障模式也會維持停用狀態。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-176">Note that if **Mode for IP audio** is disabled, then **Mode for IP video** will also remain disabled.</span></span>  |

<span data-ttu-id="3d7d0-177">如果設為 [已停用 **]**，該使用者無法開啟或檢視由其他會議參與者共用的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-177">If set to **Disabled** for a  user, that user can't turn on video or view videos shared by other meeting participants.</span></span> <span data-ttu-id="3d7d0-178">未獲指派任何原則的會議參與者 (例如匿名參與者)，預設會將此設定為 [已啟用傳出和傳入視訊 **]**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-178">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming video enabled** by default.</span></span>

<span data-ttu-id="3d7d0-179">此設定不適用會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-179">This setting doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="3d7d0-180">此設定尚無法於 Microsoft 365 政府社群雲端 (GCC)、GCC High 或美國國防部 (DoD) 環境中取得。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-180">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7d0-181">請記住，此設定可同時控制傳出和傳入視訊，而 [允許 IP 視訊 **]** 設定則可控制傳出視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-181">Keep in mind that this setting controls both outgoing and incoming video whereas the **Allow IP video** setting controls outgoing video.</span></span> <span data-ttu-id="3d7d0-182">若要深入了解，請參閱[哪個 IP 視訊原則設定優先？](#which-ip-video-policy-setting-takes-precedence)和[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-182">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

<span data-ttu-id="3d7d0-183">若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-183">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="3d7d0-184">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-184">Allow IP video</span></span>

<span data-ttu-id="3d7d0-185">這是每個召集人和每個使用者策略的組合。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-185">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3d7d0-186">視訊是會議的重要元件。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-186">Video is a key component to meetings.</span></span> <span data-ttu-id="3d7d0-187">在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議有視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-187">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="3d7d0-188">此設定可控制是否可以在使用者主持的會議以及在使用者啟動的一對一和群組通話中開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-188">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.</span></span> <span data-ttu-id="3d7d0-189">在Teams用戶端上，此設定可控制使用者是否可以在會議中共用相片和影片。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-189">On Teams mobile clients, this setting controls whether users can share photos and videos in a meeting.</span></span>

<span data-ttu-id="3d7d0-190">由已啟用此原則設定的使用者所召集的會議，如果參與者也已啟用此原則設定，則會允許由會議參與者在會議中分享視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-190">Meetings organized by a user who has this policy setting enabled, allow video sharing in the meeting by the meeting participants, if the participants also have the policy setting enabled.</span></span> <span data-ttu-id="3d7d0-191">未獲指派任何原則的會議參與者 (例如匿名和同盟參與者) 會繼承會議召集人的原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-191">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7d0-192">請記住，此設定可控制傳出視訊，而 [IP 視訊的模式 **]** 設定則可同時控制傳出和傳入視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-192">Keep in mind that this setting controls outgoing video whereas the **Mode for IP video** setting controls both outgoing and incoming video.</span></span> <span data-ttu-id="3d7d0-193">若要深入了解，請參閱[哪個 IP 視訊原則設定優先？](#which-ip-video-policy-setting-takes-precedence)和[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-193">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

| <span data-ttu-id="3d7d0-194">Teams 桌面和 Web 用戶端</span><span class="sxs-lookup"><span data-stu-id="3d7d0-194">Teams desktop and web client</span></span> |<span data-ttu-id="3d7d0-195">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="3d7d0-195">Teams mobile client</span></span>  |
|:-------:|:-------:|
|![螢幕擷取畫面顯示在桌面上加入會議與音訊/視訊設定](media/meeting-policies-audio-video-settings.png)    |![螢幕擷取畫面顯示在行動裝置上加入會議與音訊/視訊設定](media/meeting-policies-mobile-join.png)          |

<span data-ttu-id="3d7d0-198">讓我們看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-198">Let's look at the following example.</span></span>

|<span data-ttu-id="3d7d0-199">使用者</span><span class="sxs-lookup"><span data-stu-id="3d7d0-199">User</span></span> |<span data-ttu-id="3d7d0-200">會議原則</span><span class="sxs-lookup"><span data-stu-id="3d7d0-200">Meeting policy</span></span>  |<span data-ttu-id="3d7d0-201">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-201">Allow IP video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3d7d0-202">Daniela</span><span class="sxs-lookup"><span data-stu-id="3d7d0-202">Daniela</span></span>   | <span data-ttu-id="3d7d0-203">全域</span><span class="sxs-lookup"><span data-stu-id="3d7d0-203">Global</span></span>   | <span data-ttu-id="3d7d0-204">開啟</span><span class="sxs-lookup"><span data-stu-id="3d7d0-204">On</span></span>       |
|<span data-ttu-id="3d7d0-205">Amanda</span><span class="sxs-lookup"><span data-stu-id="3d7d0-205">Amanda</span></span>    | <span data-ttu-id="3d7d0-206">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3d7d0-206">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3d7d0-207">關閉</span><span class="sxs-lookup"><span data-stu-id="3d7d0-207">Off</span></span>      |

<span data-ttu-id="3d7d0-208">由 Daniela 主持的會議允許開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-208">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="3d7d0-209">Daniela 可以加入會議並開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-209">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="3d7d0-210">Amanda 無法開啟 Daniela 會議中的視像，因為 Amanda 的政策設定為不允許視音訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-210">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="3d7d0-211">Amanda 可以查看會議中由其他參與者分享的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-211">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="3d7d0-212">在 Amanda 主持的會議中，沒有任何人可以開啟視訊，而無論指派給他們的視訊原則為何。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-212">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="3d7d0-213">這表示 Daniela 無法在 Amanda 會議中開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-213">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="3d7d0-214">如果 Daniela 呼叫 Amanda 時有開啟視訊，Amanda 只能用音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-214">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="3d7d0-215">當通話連接時，Amanda 可以看見 Daniela 的視訊，但無法開啟視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-215">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="3d7d0-216">如果 Amanda 呼叫 Daniela，Daniela 可以使用視訊和音訊接聽通話。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-216">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="3d7d0-217">當通話連接時，Daniela 可以視需要開啟或關閉其視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-217">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

<span data-ttu-id="3d7d0-218">若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-218">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

#### <a name="which-ip-video-policy-setting-takes-precedence"></a><span data-ttu-id="3d7d0-219">哪一個 IP 視視策略設定優先？</span><span class="sxs-lookup"><span data-stu-id="3d7d0-219">Which IP video policy setting takes precedence?</span></span>

<span data-ttu-id="3d7d0-p121">若為使用者，針對視訊最具限制性的原則設定會優先。以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-p121">For a user, the most restrictive policy setting for video takes precedence. Here's some examples.</span></span>

|<span data-ttu-id="3d7d0-222">允許 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-222">Allow IP video</span></span>|<span data-ttu-id="3d7d0-223">IP 視訊的模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-223">Mode for IP video</span></span>|<span data-ttu-id="3d7d0-224">會議體驗</span><span class="sxs-lookup"><span data-stu-id="3d7d0-224">Meeting experience</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3d7d0-225">召集人：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-225">Organizer: **On**</span></span><br><br><span data-ttu-id="3d7d0-226">參與者：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-226">Participant: **On**</span></span> |<span data-ttu-id="3d7d0-227">參與者：**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-227">Participant: **Disabled**</span></span>        |<span data-ttu-id="3d7d0-228">[IP 視訊的模式 **]** 設定優先。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-228">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="3d7d0-229">獲指派此原則的參與者無法開啟或檢視由其他人分享的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-229">The participant who is assigned this policy can't turn on or view videos shared by others.</span></span>|
|<span data-ttu-id="3d7d0-230">召集人：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-230">Organizer: **On**</span></span><br><br><span data-ttu-id="3d7d0-231">參與者：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-231">Participant: **On**</span></span> |<span data-ttu-id="3d7d0-232">參與者：**已啟用傳出和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-232">Participant: **Outgoing and incoming video enabled**</span></span>          |<span data-ttu-id="3d7d0-233">獲指派此原則的參與者可以開啟或檢視由其他人分享的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-233">The participant who is assigned this policy can turn on or view videos shared by others.</span></span>         |
|<span data-ttu-id="3d7d0-234">召集人：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-234">Organizer: **On**</span></span><br><br><span data-ttu-id="3d7d0-235">參與者：**關閉**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-235">Participant: **Off**</span></span> |<span data-ttu-id="3d7d0-236">參與者：**已啟用傳出和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-236">Participant: **Outgoing and incoming video enabled**</span></span>         |<span data-ttu-id="3d7d0-237">[允許 IP 視訊 **]** 設定優先。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-237">The **Allow IP video** setting takes precedence.</span></span> <span data-ttu-id="3d7d0-238">參與者只能看到傳入視訊，而且無法傳送傳出視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-238">Participants can only see incoming video and can't send outgoing video.</span></span>         |
|<span data-ttu-id="3d7d0-239">召集人：**開啟**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-239">Organizer: **On**</span></span><br><br><span data-ttu-id="3d7d0-240">參與者：**關閉**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-240">Participant: **Off**</span></span> |<span data-ttu-id="3d7d0-241">參與者：**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-241">Participant: **Disabled**</span></span>         |<span data-ttu-id="3d7d0-242">[IP 視訊的模式 **]** 設定優先。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-242">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="3d7d0-243">參與者看不到傳入或傳出視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-243">The participant can't see incoming or outgoing video.</span></span>|
|<span data-ttu-id="3d7d0-244">召集人：**關閉**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-244">Organizer: **Off**</span></span>    |       |<span data-ttu-id="3d7d0-245">[允許 IP 視訊 **]** 設定優先，因為它已針對召集人關閉。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-245">The **Allow IP video** setting takes precedence because it's turned off for the organizer.</span></span> <span data-ttu-id="3d7d0-246">沒有人可以開啟由獲指派此原則的使用者所召集的會議中的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-246">No one can turn on video in meetings organized by the user who is assigned this policy.</span></span>         |

### <a name="manage-audiovideo-for-meeting-participants"></a><span data-ttu-id="3d7d0-247">管理會議參與者的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-247">Manage audio/video for meeting participants</span></span>

|<span data-ttu-id="3d7d0-248">如果您想要...</span><span class="sxs-lookup"><span data-stu-id="3d7d0-248">If you want to...</span></span>  |<span data-ttu-id="3d7d0-249">設定下列原則設定</span><span class="sxs-lookup"><span data-stu-id="3d7d0-249">Set the following policy settings</span></span>  |
|---------|---------|
|<span data-ttu-id="3d7d0-250">為會議中參與者停用音訊和視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-250">Disable audio and video for participants in meetings</span></span>  |<span data-ttu-id="3d7d0-251">IP 音訊的模式：**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-251">Mode for IP audio: **Disabled**</span></span><br> <span data-ttu-id="3d7d0-252">IP 視訊的模式：**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-252">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="3d7d0-253">允許 IP 視訊：不適用</span><span class="sxs-lookup"><span data-stu-id="3d7d0-253">Allow IP video: N/A</span></span>       |
|<span data-ttu-id="3d7d0-254">僅為會議的參與者啟用傳入音訊和視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-254">Enable only incoming video and audio for participants in meetings</span></span>  |<span data-ttu-id="3d7d0-255">IP 音訊的模式：**已啟用傳出和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-255">Mode for IP audio: **Outgoing and incoming audio enabled**</span></span><br> <span data-ttu-id="3d7d0-256">IP 視訊的模式：**已啟用傳出和傳入視訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-256">Mode for IP video: **Outgoing and incoming video enabled**</span></span><br><span data-ttu-id="3d7d0-257">允許 IP 視訊：**關閉**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-257">Allow IP video: **Off**</span></span>       |
|<span data-ttu-id="3d7d0-258">為會議中的參與者停用視訊 (參與者僅有音訊)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-258">Disable video for participants in meetings (participants have audio only)</span></span>|  <span data-ttu-id="3d7d0-259">IP 音訊的模式：**啟用傳出和傳入音訊**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-259">Mode for IP audio: **Enable outgoing and incoming audio**</span></span><br> <span data-ttu-id="3d7d0-260">IP 視訊的模式：**已停用**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-260">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="3d7d0-261">允許 IP 視訊：不適用</span><span class="sxs-lookup"><span data-stu-id="3d7d0-261">Allow IP video: N/A</span></span>
|<span data-ttu-id="3d7d0-262">為會議中參與者啟用音訊和視訊</span><span class="sxs-lookup"><span data-stu-id="3d7d0-262">Enable audio and video for participants in meetings</span></span>    |<span data-ttu-id="3d7d0-263">IP 音訊的模式：**已啟用傳出和傳入音訊** (預設值)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-263">Mode for IP audio: **Outgoing and incoming audio enabled** (default)</span></span><br> <span data-ttu-id="3d7d0-264">IP 視訊的模式：**已啟用傳出和傳入視訊** (預設值)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-264">Mode for IP video: **Outgoing and incoming video enabled** (default)</span></span><br><span data-ttu-id="3d7d0-265">允許 IP 視訊：**開啟** (預設值)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-265">Allow IP video: **On** (default)</span></span>    |

<span data-ttu-id="3d7d0-266">將套用會議召集人的原則與使用者原則之間最具限制性的原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-266">The most restrictive policy between the meeting organizer’s policy and the user’s policy applies.</span></span> <span data-ttu-id="3d7d0-267">例如，如果召集人有一個原則會限制視訊，而使用者的原則不會限制視訊，則會議參與者會繼承會議召集人的原則，且無法存取會議中的視訊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-267">For example, if an organizer has a policy that restricts video and a user’s policy doesn't restrict video, meeting participants inherit the policy of the meeting organizer and don't have access to video in meetings.</span></span> <span data-ttu-id="3d7d0-268">這表示他們只能使用音訊加入會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-268">This means that they can join the meeting with audio only.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7d0-269">當使用者開始群組通話以使用電話加入時，不會出現 [使用手機的音訊 **]** 畫面。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-269">When a user starts a group call to join by phone, the **Use phone for audio** screen doesn't appear.</span></span> <span data-ttu-id="3d7d0-270">這是已知問題，我們正在努力解決。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-270">This is a known issue that we're working to resolve.</span></span> <span data-ttu-id="3d7d0-271">若要解決此問題，請在 [其他加入選項 **]** 下選取 [手機音訊 **]**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-271">To work around this issue, select **Phone audio** under **Other join options**.</span></span>  

#### <a name="teams-mobile-clients"></a><span data-ttu-id="3d7d0-272">Teams 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="3d7d0-272">Teams mobile clients</span></span>

<span data-ttu-id="3d7d0-273">對於使用Teams用戶端的使用者，會議期間共用相片和視像的能力也取決於允許 **IP 視** 像或 **IP 視像模式** 設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-273">For users on Teams mobile clients, the ability to share photos and videos during a meeting is also determined by the **Allow IP video** or **IP video mode** setting.</span></span> <span data-ttu-id="3d7d0-274">根據設定的優先原則為何，分享視訊和相片的功能均無法使用。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-274">Depending on which policy setting takes precedence, the ability to share videos and photos won't be available.</span></span> <span data-ttu-id="3d7d0-275">這不會影響螢幕畫面分享，這是您使用個別的 [螢幕畫面分享模式[]](meeting-policies-content-sharing.md#screen-sharing-mode) 設定進行的設定。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-275">This doesn't affect screen sharing, which you configure using a separate [Screen sharing mode](meeting-policies-content-sharing.md#screen-sharing-mode) setting.</span></span> <span data-ttu-id="3d7d0-276">此外，您可以設定 [Teams 行動性原則](/powershell/module/skype/new-csteamsmobilitypolicy)，以防止行動裝置使用者透過行動數據連線使用 IP 視訊，這表示他們必須使用 WiFi 連線。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-276">Additionally, you can set a [Teams mobility policy](/powershell/module/skype/new-csteamsmobilitypolicy) to prevent mobile users from using IP video over a cellular connection, which means they must use a WiFi connection.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="3d7d0-277">媒體位元速率 (KB)</span><span class="sxs-lookup"><span data-stu-id="3d7d0-277">Media bit rate (Kbs)</span></span>

<span data-ttu-id="3d7d0-278">這是每一使用者原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-278">This is a per-user policy.</span></span> <span data-ttu-id="3d7d0-279">此設定會決定使用者在通話和會議中進行音訊、視視和視視應用程式共用傳輸的媒體位元速率。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-279">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="3d7d0-280">它會同時套用於通話或會議使用者的上行連結和下行媒體周遊。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-280">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="3d7d0-281">此設定會提供您對組織中頻寬管理的細微控制。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-281">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="3d7d0-282">根據使用者需要的會議案例而定，我們建議有足夠的頻寬，以便擁有良好的品質體驗。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-282">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="3d7d0-283">最小值為 30 Kbps，而最大值取決於會議案例。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-283">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="3d7d0-284">若要深入了解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-284">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="3d7d0-285">如果會議頻寬不足，參與者會看到一則訊息，指出網路品質不佳。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-285">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="3d7d0-286">對於需要最高品質視訊體驗的會議 (例如 CEO 委員會會議和 Teams 即時活動)，建議您將頻寬設定為 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-286">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="3d7d0-287">即使已設定體驗上限，視案例而定，Teams 媒體堆疊會在偵測到特定網路狀況時適應低頻寬情況。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-287">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="video-filters-mode"></a><span data-ttu-id="3d7d0-288">視像篩選模式</span><span class="sxs-lookup"><span data-stu-id="3d7d0-288">Video filters mode</span></span>

<span data-ttu-id="3d7d0-289"><a name="bkvideofilters"> </a></span><span class="sxs-lookup"><span data-stu-id="3d7d0-289"><a name="bkvideofilters"> </a></span></span>

<span data-ttu-id="3d7d0-p131">這是每一使用者原則。此設定可控制使用者是否可以自訂其會議中的視訊背景。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-p131">This is a per-user policy. This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="3d7d0-292">目前，您僅能使用 PowerShell 來設定此原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-292">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="3d7d0-293">您可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的 Teams 會議原則。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-293">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="3d7d0-294">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議原則，然後將該原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-294">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="3d7d0-295">若要指定使用者是否可以自訂會議中的視訊背景，請設定 **VideoFiltersMode** 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d7d0-295">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="3d7d0-296">在 PowerShell 中設定值</span><span class="sxs-lookup"><span data-stu-id="3d7d0-296">Setting value in PowerShell</span></span> |<span data-ttu-id="3d7d0-297">行為</span><span class="sxs-lookup"><span data-stu-id="3d7d0-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3d7d0-298">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-298">**NoFilters**</span></span>     |<span data-ttu-id="3d7d0-299">使用者無法自訂其視訊背景。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-299">User can't customize their video background.</span></span>|
|<span data-ttu-id="3d7d0-300">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-300">**BlurOnly**</span></span>     |<span data-ttu-id="3d7d0-301">使用者可以選擇模糊其視音訊背景。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-301">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="3d7d0-302">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-302">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="3d7d0-303">使用者可以選擇模糊其視訊背景，或從預設的影像集中選擇，以用作其背景。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-303">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="3d7d0-304">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="3d7d0-304">**AllFilters**</span></span>     |<span data-ttu-id="3d7d0-305">Use 可以選擇模糊其視像背景、選擇預設的影像集，或上傳自訂影像做為背景。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-305">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="3d7d0-306">Teams 不會篩選由使用者上傳的影像。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-306">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="3d7d0-307">使用 **AllFilters** 設定時，您應該有內部組織原則，以防止使用者上傳冒犯性或不適當的影像，或組織無權用於 Teams 會議背景的影像。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-307">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

### <a name="allow-custom-background-settings"></a><span data-ttu-id="3d7d0-308">允許自訂背景設定</span><span class="sxs-lookup"><span data-stu-id="3d7d0-308">Allow custom background settings</span></span>

<span data-ttu-id="3d7d0-309">您可以新增自訂背景影像，以用於每個租使用者。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-309">You can add custom background images to be used per tenant.</span></span> <span data-ttu-id="3d7d0-310">此功能可讓公司將公司商標用於Teams會議。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-310">This feature allows companies to apply corporate branding to Teams meetings.</span></span>

1. <span data-ttu-id="3d7d0-311">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-311">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="3d7d0-312">選取 **會議策略**  >  **自訂會議影像**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-312">Select **Meeting Policies** > **Customize meeting images**.</span></span>

   ![會議政策選取專案，畫面上會以強調的自訂會議影像按鈕](media/custom-background-image-button.png)

3. <span data-ttu-id="3d7d0-314">從 **組織** 背景 **影像選取 On**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-314">Select **On** from **Org wide background images**.</span></span>

4. <span data-ttu-id="3d7d0-315">選取 **+ 新增影像**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-315">Select **+ Add images**.</span></span>

5. <span data-ttu-id="3d7d0-316">在管理背景面板中，選取 新增 **影像**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-316">In the Managing backgrounds panel, select **Add image**.</span></span>

6. <span data-ttu-id="3d7d0-317">確保影像符合以下需求：</span><span class="sxs-lookup"><span data-stu-id="3d7d0-317">Ensure that the images meet these requirements:</span></span>
  
   - <span data-ttu-id="3d7d0-318">最小大小 360 px</span><span class="sxs-lookup"><span data-stu-id="3d7d0-318">Minimum size 360 px</span></span>
   - <span data-ttu-id="3d7d0-319">最大大小 2048 px</span><span class="sxs-lookup"><span data-stu-id="3d7d0-319">Maximum size 2048 px</span></span>
   - <span data-ttu-id="3d7d0-320">PNG、JPG 或 BMP 的檔案類型</span><span class="sxs-lookup"><span data-stu-id="3d7d0-320">File type of PNG, JPG, or BMP</span></span>
   - <span data-ttu-id="3d7d0-321">最多可上傳 50 張影像</span><span class="sxs-lookup"><span data-stu-id="3d7d0-321">Maximum 50 images can be uploaded</span></span>

7. <span data-ttu-id="3d7d0-322">預覽您選取的影像，然後選取 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-322">Preview the images that you've selected, and then select **Close**.</span></span>

8. <span data-ttu-id="3d7d0-323">請檢查影像，並根據需要新增更多內容。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-323">Review the images and add more as needed.</span></span>

9. <span data-ttu-id="3d7d0-324">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-324">Select **Save**.</span></span>

<span data-ttu-id="3d7d0-325">會議出席者會看到一系列背景影像，可在他們參加會議時使用。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-325">The meeting attendees will see a selection of background images that they can use when they attend a meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7d0-326">變更最多可能需要 24 小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="3d7d0-326">It could take up to 24 hours for the changes to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d7d0-327">相關主題</span><span class="sxs-lookup"><span data-stu-id="3d7d0-327">Related topics</span></span>

- [<span data-ttu-id="3d7d0-328">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="3d7d0-328">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="3d7d0-329">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="3d7d0-329">Assign policies to your users in Teams</span></span>](assign-policies.md)
