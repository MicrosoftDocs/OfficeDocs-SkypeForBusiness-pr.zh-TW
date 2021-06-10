---
title: 管理參與者和來賓的會議政策
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 瞭解如何在會議Teams中管理會議政策設定。
ms.openlocfilehash: bec3f82c66984147f109dc68cc97376c502dd9a6
ms.sourcegitcommit: f5b6a0fe055e42e06eee21ce311813b5127474ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52741052"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="24440-103">會議原則設定 - 參與者與來賓</span><span class="sxs-lookup"><span data-stu-id="24440-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="24440-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="24440-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="24440-105">這些設定可控制哪些會議參與者在獲准加入會議之前在大廳等候，以及允許他們在會議中允許的參與層級。</span><span class="sxs-lookup"><span data-stu-id="24440-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="24440-106">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="24440-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="24440-107">自動准許人員</span><span class="sxs-lookup"><span data-stu-id="24440-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="24440-108">允許撥入使用者無需先在大廳等候</span><span class="sxs-lookup"><span data-stu-id="24440-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="24440-109">啟用即時輔助字幕</span><span class="sxs-lookup"><span data-stu-id="24440-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="24440-110">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="24440-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="24440-111">加入會議的選項會因每個 Teams 群組的設定和連線方法而有所不同。</span><span class="sxs-lookup"><span data-stu-id="24440-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="24440-112">如果您的群組有音訊會議，並且使用它來連線，請參閱[音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="24440-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="24440-113">如果您的 Teams 群組沒有音訊會議，請參閱[在 Teams 中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。</span><span class="sxs-lookup"><span data-stu-id="24440-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="24440-114">讓匿名人員開始會議</span><span class="sxs-lookup"><span data-stu-id="24440-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="24440-115">此設定是每個召集人的策略，可讓無主席電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="24440-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="24440-116">此設定可控制撥入使用者是否可以加入會議，而組織沒有經過驗證的使用者出席。</span><span class="sxs-lookup"><span data-stu-id="24440-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="24440-117">根據預設，此設定會關閉，這表示撥入使用者會等候在大廳中，直到組織經過驗證的使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="24440-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="24440-118">如果這項設定已關閉，且撥入使用者會先加入會議，並置於大廳中，組織使用者必須使用 Teams 用戶端加入會議，以從大廳准許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="24440-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="24440-119">撥入的使用者沒有可用的大廳控制項。</span><span class="sxs-lookup"><span data-stu-id="24440-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="24440-120">自動准許人員</span><span class="sxs-lookup"><span data-stu-id="24440-120">Automatically admit people</span></span>

<span data-ttu-id="24440-121">這是每一召集人原則。</span><span class="sxs-lookup"><span data-stu-id="24440-121">This is a per-organizer policy.</span></span> <span data-ttu-id="24440-122">此設定可控制人員是直接加入會議，還是在大廳中等候，直到由已驗證的使用者准許其加入會議為止。</span><span class="sxs-lookup"><span data-stu-id="24440-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="24440-123">此設定不適用撥入使用者。</span><span class="sxs-lookup"><span data-stu-id="24440-123">This setting does not apply to dial-in users.</span></span>

![螢幕擷取畫面顯示有使用者在大廳中的會議](media/meeting-policies-lobby.png)

 <span data-ttu-id="24440-125">會議召集人可以按一下 **會議** 邀請中的 [會議選項>，針對他們排定的每一個會議變更此設定。</span><span class="sxs-lookup"><span data-stu-id="24440-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="24440-p105">在會議選項中，設定會標示為「誰無需先在大廳等候」。如果您變更任何使用者的預設設定，它將會套用至該使用者召集的所有新會議，以及使用者未修改會議選項的任何先前會議。</span><span class="sxs-lookup"><span data-stu-id="24440-p105">In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="24440-128">設定值</span><span class="sxs-lookup"><span data-stu-id="24440-128">Setting value</span></span>  |<span data-ttu-id="24440-129">加入行為</span><span class="sxs-lookup"><span data-stu-id="24440-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="24440-130">**每個人**</span><span class="sxs-lookup"><span data-stu-id="24440-130">**Everyone**</span></span>   |<span data-ttu-id="24440-131">所有會議參與者會直接加入會議，而不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="24440-132">這包括已驗證的使用者、來自信任組織 (同盟) 的外部使用者、來賓和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="24440-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="24440-133">**組織中的人員和來賓**</span><span class="sxs-lookup"><span data-stu-id="24440-133">**People in my organization and guests**</span></span>     |<span data-ttu-id="24440-134">組織中經過驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-134">Authenticated users within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="24440-135">匿名使用者在大廳中等候。</span><span class="sxs-lookup"><span data-stu-id="24440-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="24440-136">**組織中的人員、信任的組織和來賓**</span><span class="sxs-lookup"><span data-stu-id="24440-136">**People in my organization, trusted organizations, and guests**</span></span>     |<span data-ttu-id="24440-137">組織內已驗證的使用者 (包括來賓使用者和來自信任組織的使用者) 可直接加入會議，而不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-137">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="24440-138">匿名使用者在大廳中等候。</span><span class="sxs-lookup"><span data-stu-id="24440-138">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="24440-139">**我組織中所有人**</span><span class="sxs-lookup"><span data-stu-id="24440-139">**Everyone in my organization**</span></span>    |<span data-ttu-id="24440-140">來自組織內已驗證的使用者 (包括來賓使用者) 會直接加入會議，而不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-140">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="24440-141">來自信任組織的使用者和匿名使用者會在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-141">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="24440-142">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="24440-142">This is the default setting.</span></span>           |
|<span data-ttu-id="24440-143">**僅限召集人**</span><span class="sxs-lookup"><span data-stu-id="24440-143">**Organizer only**</span></span>    |<span data-ttu-id="24440-144">只有會議召集人可直接加入會議，而不需在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-144">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="24440-145">其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者，以及匿名使用者，都必須在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-145">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations, and anonymous users must wait in the lobby.</span></span>           |
|<span data-ttu-id="24440-146">**僅受邀使用者**</span><span class="sxs-lookup"><span data-stu-id="24440-146">**Invited users only**</span></span>    |<span data-ttu-id="24440-147">只有受邀的使用者和會議召集人可以直接加入會議，而不必在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-147">Only invited users and meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="24440-148">其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者，以及匿名使用者，都必須在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="24440-148">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations, and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="24440-149">允許撥入使用者無需先在大廳等候</span><span class="sxs-lookup"><span data-stu-id="24440-149">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="24440-150">這是每一召集人原則。</span><span class="sxs-lookup"><span data-stu-id="24440-150">This is a per-organizer policy.</span></span> <span data-ttu-id="24440-151">此設定可控制透過電話撥入的人員是否直接加入會議，或是在大廳中等候，而不論 [自動准許人員 **]** 的設定為何。</span><span class="sxs-lookup"><span data-stu-id="24440-151">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="24440-152">此設定預設會關閉。</span><span class="sxs-lookup"><span data-stu-id="24440-152">By default, this setting is turned off.</span></span> <span data-ttu-id="24440-153">關閉此設定時，撥入使用者將在大廳中等候，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入為止。</span><span class="sxs-lookup"><span data-stu-id="24440-153">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="24440-154">開啟此設定時，撥入使用者會在組織使用者加入會議時自動加入會議。</span><span class="sxs-lookup"><span data-stu-id="24440-154">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="24440-155">如果撥入使用者在組織使用者加入會議之前加入會議，他們將會停留在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入會議為止。</span><span class="sxs-lookup"><span data-stu-id="24440-155">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="24440-156">如果您變更任何使用者的預設設定，它將會套用至該使用者召集的所有新會議，以及使用者未修改會議選項的任何先前會議。</span><span class="sxs-lookup"><span data-stu-id="24440-156">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="24440-157">啟用即時輔助字幕</span><span class="sxs-lookup"><span data-stu-id="24440-157">Enable live captions</span></span>

<span data-ttu-id="24440-158">此設定是每個使用者原則，並適用于會議期間。</span><span class="sxs-lookup"><span data-stu-id="24440-158">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="24440-159">此設定可控制使用者是否可使用 [開啟即時輔助字幕 **]** 選項，以在使用者出席的會議中開啟和關閉即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="24440-159">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![顯示開啟即時輔助字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|<span data-ttu-id="24440-161">設定值</span><span class="sxs-lookup"><span data-stu-id="24440-161">Setting value</span></span> |<span data-ttu-id="24440-162">行為</span><span class="sxs-lookup"><span data-stu-id="24440-162">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="24440-163">**已停用，但使用者可以覆寫**</span><span class="sxs-lookup"><span data-stu-id="24440-163">**Disabled but the user can override**</span></span>     | <span data-ttu-id="24440-164">在會議期間不會自動為使用者開啟即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="24440-164">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="24440-165">使用者會在溢位 **(...)** 功能表中看到 [開啟即時輔助字幕 **]** 選項，以將其開啟。</span><span class="sxs-lookup"><span data-stu-id="24440-165">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="24440-166">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="24440-166">This is the default setting.</span></span> |
|<span data-ttu-id="24440-167">**已停用**</span><span class="sxs-lookup"><span data-stu-id="24440-167">**Disabled**</span></span>     | <span data-ttu-id="24440-168">在會議期間會為使用者停用即時輔助字幕。</span><span class="sxs-lookup"><span data-stu-id="24440-168">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="24440-169">使用者沒有開啟它們的選項。</span><span class="sxs-lookup"><span data-stu-id="24440-169">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="24440-170"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="24440-170"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="24440-171">允許在會議中聊天</span><span class="sxs-lookup"><span data-stu-id="24440-171">Allow chat in meetings</span></span>

<span data-ttu-id="24440-172">此設定是每個參與者的設定。</span><span class="sxs-lookup"><span data-stu-id="24440-172">This setting is a per-participant setting.</span></span> <span data-ttu-id="24440-173">此設定可控制是否在使用者的會議中允許會議聊天。</span><span class="sxs-lookup"><span data-stu-id="24440-173">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="24440-174"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="24440-174"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="24440-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="24440-175">Related topics</span></span>

- [<span data-ttu-id="24440-176">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="24440-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="24440-177">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="24440-177">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="24440-178">從使用者移除 RestrictedAnonymousAccess Teams 會議原則</span><span class="sxs-lookup"><span data-stu-id="24440-178">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
