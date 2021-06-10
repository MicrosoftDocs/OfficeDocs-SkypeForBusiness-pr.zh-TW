---
title: Teams 用戶端體驗和遵從共存模式
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 瞭解Teams模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119252"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="d4def-103">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="d4def-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="d4def-104">商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的目的是在組織從 商務用 Skype 轉換到 Teams 時，為使用者提供簡單且可預測的體驗。</span><span class="sxs-lookup"><span data-stu-id="d4def-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="d4def-105">對於移往 Teams 的組織 **，Teams** 只有模式是每個使用者的最終目的地，但並非所有使用者都需要同時指派 **Teams** (或任何其他模式) 。</span><span class="sxs-lookup"><span data-stu-id="d4def-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="d4def-106">在使用者到達 TeamsOnly 模式之前，組織可以使用任何 商務用 Skype 共存模式，以確保只有 Teams 使用者與尚未使用的使用者之間可以預測通訊。</span><span class="sxs-lookup"><span data-stu-id="d4def-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="d4def-107">當使用者在任一模式商務用 Skype，所有傳入的聊天和通話會路由至使用者的商務用 Skype用戶端。</span><span class="sxs-lookup"><span data-stu-id="d4def-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="d4def-108">為了避免使用者混淆並確保正確的路由，當使用者處於任何一種Teams模式時，用戶端中的通話和聊天功能會商務用 Skype停用。</span><span class="sxs-lookup"><span data-stu-id="d4def-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="d4def-109">同樣地，當使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時，Teams 中的會議排程會明確停用，且當使用者處於 SfBWithTeamsCollabAndMeetings 模式時，明確啟用。</span><span class="sxs-lookup"><span data-stu-id="d4def-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="d4def-110">由於目前狀態是透過聊天和通話的可及性表示，因此當聊天和通話停用時，Teams (中的自我目前狀態，亦即使用者圖片) 中的 Teams 用戶端中顯示自己的目前狀態也會隱藏。</span><span class="sxs-lookup"><span data-stu-id="d4def-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="d4def-111">用戶端中的可用功能Teams模式變更</span><span class="sxs-lookup"><span data-stu-id="d4def-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="d4def-112">系統Teams的功能取決於使用者的共存模式，如 TeamsUpgradePolicy 所設定。</span><span class="sxs-lookup"><span data-stu-id="d4def-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="d4def-113">下表摘要列出行為：</span><span class="sxs-lookup"><span data-stu-id="d4def-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="d4def-114">使用者的有效模式</span><span class="sxs-lookup"><span data-stu-id="d4def-114">User's effective mode</span></span>|<span data-ttu-id="d4def-115">用戶端Teams體驗</span><span class="sxs-lookup"><span data-stu-id="d4def-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="d4def-116">任何商務用 Skype模式</span><span class="sxs-lookup"><span data-stu-id="d4def-116">Any Skype for Business mode</span></span>|<span data-ttu-id="d4def-117">通話、聊天和自我目前狀態已停用。</span><span class="sxs-lookup"><span data-stu-id="d4def-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="d4def-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="d4def-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="d4def-119">會議排程可供使用</span><span class="sxs-lookup"><span data-stu-id="d4def-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="d4def-120">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d4def-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="d4def-121">會議排程不可用</span><span class="sxs-lookup"><span data-stu-id="d4def-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="d4def-122">下列螢幕擷取畫面說明唯一模式Teams **群島** 模式與所有其他模式的差異。</span><span class="sxs-lookup"><span data-stu-id="d4def-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="d4def-123">請注意，聊天和通話圖示預設可以使用 **Teams** Only 或 **Islands** 模式 (左側螢幕擷取畫面) ，但不適用於其他模式 (螢幕擷取畫面) ：</span><span class="sxs-lookup"><span data-stu-id="d4def-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![兩種模式並排比較Teams比較](media/teams-mode-comparison.png)

<span data-ttu-id="d4def-125">此外，無法在其他模式中使用自我目前狀態，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d4def-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![會議第一次中的自我目前狀態螢幕擷取畫面](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="d4def-127">**注意：** 
<sup>1</sup>目前，SfBwithTeamsCollab 和 SfBOnly 的行為相同，但目的在 SfBOnly 模式也會停用 Teams 中的頻道和檔案功能。</span><span class="sxs-lookup"><span data-stu-id="d4def-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="d4def-128">在期間，您可以使用應用程式許可權政策隱藏頻道。</span><span class="sxs-lookup"><span data-stu-id="d4def-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="d4def-129">模式對其他策略設定的影響</span><span class="sxs-lookup"><span data-stu-id="d4def-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="d4def-130">如上述所述，使用者的共存模式影響是使用者的用戶端Teams功能。</span><span class="sxs-lookup"><span data-stu-id="d4def-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="d4def-131">這表示模式的值可能會優先于其他策略設定的值 ，視模式而不同。</span><span class="sxs-lookup"><span data-stu-id="d4def-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="d4def-132">具體來說，共存模式會影響是否遵循下列原則設定：</span><span class="sxs-lookup"><span data-stu-id="d4def-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="d4def-133">**應用程式 (模式)**</span><span class="sxs-lookup"><span data-stu-id="d4def-133">**Modality (App)**</span></span>|<span data-ttu-id="d4def-134">**Policy.setting**</span><span class="sxs-lookup"><span data-stu-id="d4def-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="d4def-135">聊天</span><span class="sxs-lookup"><span data-stu-id="d4def-135">Chat</span></span>|<span data-ttu-id="d4def-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="d4def-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="d4def-137">通話</span><span class="sxs-lookup"><span data-stu-id="d4def-137">Calling</span></span>|<span data-ttu-id="d4def-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d4def-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="d4def-139">會議排程</span><span class="sxs-lookup"><span data-stu-id="d4def-139">Meeting scheduling</span></span>|<span data-ttu-id="d4def-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4def-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="d4def-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4def-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="d4def-142">系統管理員在使用 *共存* 模式時不需要明確設定這些策略設定，但必須瞭解這些設定在指定模式中的行為方式如下。</span><span class="sxs-lookup"><span data-stu-id="d4def-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="d4def-143">模式</span><span class="sxs-lookup"><span data-stu-id="d4def-143">Mode</span></span>|<span data-ttu-id="d4def-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="d4def-144">AllowUserChat</span></span>|<span data-ttu-id="d4def-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d4def-145">AllowPrivateCalling</span></span>|<span data-ttu-id="d4def-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4def-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="d4def-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4def-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="d4def-148">TeamsOnly 或 Islands</span><span class="sxs-lookup"><span data-stu-id="d4def-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="d4def-149">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-149">Enabled</span></span>|<span data-ttu-id="d4def-150">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-150">Enabled</span></span>|<span data-ttu-id="d4def-151">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-151">Enabled</span></span>|<span data-ttu-id="d4def-152">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-152">Enabled</span></span>|
|<span data-ttu-id="d4def-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="d4def-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="d4def-154">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-154">Disabled</span></span>|<span data-ttu-id="d4def-155">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-155">Disabled</span></span>|<span data-ttu-id="d4def-156">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-156">Enabled</span></span>|<span data-ttu-id="d4def-157">啟用</span><span class="sxs-lookup"><span data-stu-id="d4def-157">Enabled</span></span>|
|<span data-ttu-id="d4def-158">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="d4def-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="d4def-159">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-159">Disabled</span></span>|<span data-ttu-id="d4def-160">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-160">Disabled</span></span>|<span data-ttu-id="d4def-161">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-161">Disabled</span></span>|<span data-ttu-id="d4def-162">已停用</span><span class="sxs-lookup"><span data-stu-id="d4def-162">Disabled</span></span>|
||||||

<span data-ttu-id="d4def-163">使用 PowerShell 時 `Grant-CsTeamsUpgradePolicy` ，Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中的對應設定設定，以判斷這些設定是否由 TeamsUpgradePolicy 取代，若是如此，PowerShell 中會提供資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="d4def-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="d4def-164">如上所述，不再需要設定這些其他策略設定。</span><span class="sxs-lookup"><span data-stu-id="d4def-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="d4def-165">以下是 PowerShell 警告外觀的範例：</span><span class="sxs-lookup"><span data-stu-id="d4def-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="d4def-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4def-166">Related topics</span></span>

[<span data-ttu-id="d4def-167">適用于與應用程式一起使用Teams的移商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="d4def-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)