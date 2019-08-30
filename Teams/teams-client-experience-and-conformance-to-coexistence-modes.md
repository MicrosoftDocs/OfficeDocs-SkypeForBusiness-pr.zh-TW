---
title: 團隊用戶端體驗與共存模式的一致性
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 團隊用戶端經驗及 comformance 共存模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5e637fc8be92f136d05a3e7f41628d61afce70
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2019
ms.locfileid: "36675384"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="5d137-103">團隊用戶端體驗與共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="5d137-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="5d137-104">此頁面說明團隊用戶端在任何商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 行為中的重要、最近發佈的變更。</span><span class="sxs-lookup"><span data-stu-id="5d137-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="5d137-105">商務用 Skype 共存模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的用途, 是提供使用者的簡單且可預測的體驗, 就像是組織從商務用 Skype 轉換到團隊。</span><span class="sxs-lookup"><span data-stu-id="5d137-105">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="5d137-106">如果組織要移至團隊, 則 [**團隊專用**] 模式是每個使用者的最終目的地, 但並非所有使用者都需要同時指派**團隊**(或任何其他模式)。</span><span class="sxs-lookup"><span data-stu-id="5d137-106">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="5d137-107">在使用者進入 TeamsOnly 模式之前, 組織可以使用任何商務用 Skype 共存模式, 以確保**僅供團隊**使用的使用者和尚不在小組中的使用者進行預期通訊。</span><span class="sxs-lookup"><span data-stu-id="5d137-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="5d137-108">當使用者處於任何商務用 Skype 模式時, 所有傳入聊天和通話會傳送到使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="5d137-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="5d137-109">若要避免使用者混淆並確保正確地進行路由, 小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時停用。</span><span class="sxs-lookup"><span data-stu-id="5d137-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="5d137-110">同樣地, 在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時, 小組中的會議排程會明確停用, 且在使用者處於 SfBWithTeamsCollabAndMeetings 模式時明確啟用。</span><span class="sxs-lookup"><span data-stu-id="5d137-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="5d137-111">因為目前狀態是透過聊天和通話提供可存取性的指示, 所以當聊天和通話停用時, 會在團隊中自行存在 (也就是, 在使用者圖片的團隊用戶端中顯示自己的目前狀態) 也會隱藏。</span><span class="sxs-lookup"><span data-stu-id="5d137-111">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="5d137-112">團隊用戶端中的可用功能如何根據模式變更</span><span class="sxs-lookup"><span data-stu-id="5d137-112">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="5d137-113">團隊中的可用功能, 取決於使用者的共存模式 (由 TeamsUpgradePolicy 設定)。</span><span class="sxs-lookup"><span data-stu-id="5d137-113">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="5d137-114">下表摘要說明行為:</span><span class="sxs-lookup"><span data-stu-id="5d137-114">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="5d137-115">使用者的有效模式</span><span class="sxs-lookup"><span data-stu-id="5d137-115">User's effective mode</span></span>|<span data-ttu-id="5d137-116">團隊用戶端中的體驗</span><span class="sxs-lookup"><span data-stu-id="5d137-116">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="5d137-117">任何商務用 Skype 模式</span><span class="sxs-lookup"><span data-stu-id="5d137-117">Any Skype for Business mode</span></span>|<span data-ttu-id="5d137-118">[通話]、[交談] 和 [自我顯示] 是停用的。</span><span class="sxs-lookup"><span data-stu-id="5d137-118">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="5d137-119">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="5d137-119">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="5d137-120">提供會議排程</span><span class="sxs-lookup"><span data-stu-id="5d137-120">Meeting scheduling is available</span></span>|
|<span data-ttu-id="5d137-121">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="5d137-121">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="5d137-122">無法使用會議排程</span><span class="sxs-lookup"><span data-stu-id="5d137-122">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="5d137-123">下列螢幕擷取畫面說明**僅限團隊**或**孤島**模式與所有其他模式之間的差異。</span><span class="sxs-lookup"><span data-stu-id="5d137-123">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="5d137-124">請注意, 「聊天」和「通話」圖示預設會提供給**小組**或**孤島**模式 (左螢幕擷取畫面), 但不適用於其他模式 (右側螢幕擷取畫面):</span><span class="sxs-lookup"><span data-stu-id="5d137-124">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![團隊模式的並排比較](media/teams-mode-comparison.png)

<span data-ttu-id="5d137-126">此外, 在其他模式中不提供自我目前狀態, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="5d137-126">In addition, self presence is not available in the other modes, as shown here.</span></span>

![在會議中先顯示自我狀態的螢幕擷取畫面](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="5d137-128">**注意:**
<sup>1</sup>此時, SfBwithTeamsCollab 和 SfBOnly 的行為相同, 但在 SfBOnly 模式中, 也可以停用團隊中的頻道與檔案功能。</span><span class="sxs-lookup"><span data-stu-id="5d137-128">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="5d137-129">在間歇中, 您可以使用應用程式許可權原則隱藏頻道。</span><span class="sxs-lookup"><span data-stu-id="5d137-129">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="5d137-130">模式對其他原則設定的影響</span><span class="sxs-lookup"><span data-stu-id="5d137-130">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="5d137-131">如上所述, 使用者的共存模式會影響使用者的團隊用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="5d137-131">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="5d137-132">這表示 mode 的值可能會優先于其他原則設定的值, 視模式而定。</span><span class="sxs-lookup"><span data-stu-id="5d137-132">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="5d137-133">具體說來, 共存模式會影響是否會遵守下列原則設定:</span><span class="sxs-lookup"><span data-stu-id="5d137-133">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="5d137-134">**模態 (應用程式)**</span><span class="sxs-lookup"><span data-stu-id="5d137-134">**Modality (App)**</span></span>|<span data-ttu-id="5d137-135">**原則。設定**</span><span class="sxs-lookup"><span data-stu-id="5d137-135">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="5d137-136">交流</span><span class="sxs-lookup"><span data-stu-id="5d137-136">Chat</span></span>|<span data-ttu-id="5d137-137">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="5d137-137">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="5d137-138">通話</span><span class="sxs-lookup"><span data-stu-id="5d137-138">Calling</span></span>|<span data-ttu-id="5d137-139">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="5d137-139">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="5d137-140">會議排程</span><span class="sxs-lookup"><span data-stu-id="5d137-140">Meeting scheduling</span></span>|<span data-ttu-id="5d137-141">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5d137-141">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="5d137-142">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5d137-142">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="5d137-143">當您使用 [共存] 模式時, 系統管理員*不*需要明確設定這些原則設定, 但請務必瞭解這些設定在特定模式下的行為方式如下。</span><span class="sxs-lookup"><span data-stu-id="5d137-143">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="5d137-144">下</span><span class="sxs-lookup"><span data-stu-id="5d137-144">Mode</span></span>|<span data-ttu-id="5d137-145">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="5d137-145">AllowUserChat</span></span>|<span data-ttu-id="5d137-146">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="5d137-146">AllowPrivateCalling</span></span>|<span data-ttu-id="5d137-147">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5d137-147">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="5d137-148">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="5d137-148">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="5d137-149">TeamsOnly 或孤島</span><span class="sxs-lookup"><span data-stu-id="5d137-149">TeamsOnly or Islands</span></span>|<span data-ttu-id="5d137-150">後</span><span class="sxs-lookup"><span data-stu-id="5d137-150">Enabled</span></span>|<span data-ttu-id="5d137-151">後</span><span class="sxs-lookup"><span data-stu-id="5d137-151">Enabled</span></span>|<span data-ttu-id="5d137-152">後</span><span class="sxs-lookup"><span data-stu-id="5d137-152">Enabled</span></span>|<span data-ttu-id="5d137-153">後</span><span class="sxs-lookup"><span data-stu-id="5d137-153">Enabled</span></span>|
|<span data-ttu-id="5d137-154">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="5d137-154">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="5d137-155">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-155">Disabled</span></span>|<span data-ttu-id="5d137-156">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-156">Disabled</span></span>|<span data-ttu-id="5d137-157">後</span><span class="sxs-lookup"><span data-stu-id="5d137-157">Enabled</span></span>|<span data-ttu-id="5d137-158">後</span><span class="sxs-lookup"><span data-stu-id="5d137-158">Enabled</span></span>|
|<span data-ttu-id="5d137-159">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="5d137-159">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="5d137-160">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-160">Disabled</span></span>|<span data-ttu-id="5d137-161">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-161">Disabled</span></span>|<span data-ttu-id="5d137-162">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-162">Disabled</span></span>|<span data-ttu-id="5d137-163">禁止</span><span class="sxs-lookup"><span data-stu-id="5d137-163">Disabled</span></span>|
||||||

<span data-ttu-id="5d137-164">使用 PowerShell 時, 此`Grant-CsTeamsUpgradePolicy` Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中對應設定的設定, 以判斷是否會將這些設定取代 TeamsUpgradePolicy, 如果是,PowerShell 中提供了資訊性訊息。</span><span class="sxs-lookup"><span data-stu-id="5d137-164">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="5d137-165">如上所述, 不需要再設定其他原則設定。</span><span class="sxs-lookup"><span data-stu-id="5d137-165">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="5d137-166">以下是 PowerShell 警告外觀的範例:</span><span class="sxs-lookup"><span data-stu-id="5d137-166">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="5d137-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="5d137-167">Related topics</span></span>

[<span data-ttu-id="5d137-168">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="5d137-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




