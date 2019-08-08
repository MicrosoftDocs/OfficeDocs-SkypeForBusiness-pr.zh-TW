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
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243902"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="d4340-103">團隊用戶端體驗與共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="d4340-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="d4340-104">此頁面說明團隊用戶端在任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 行為中的重要、最近發佈的變更。</span><span class="sxs-lookup"><span data-stu-id="d4340-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="d4340-105">共存模式的用途是提供一種簡單且可預測的方式, 讓使用者在公司從商務用 Skype 轉換為小組時, 提供一種簡單且可預知的體驗。</span><span class="sxs-lookup"><span data-stu-id="d4340-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="d4340-106">針對組織移至 [團隊], TeamsOnly 模式是每個使用者的最終目的地, 但並非所有使用者都需要同時指派 TeamsOnly (或任何其他模式)。</span><span class="sxs-lookup"><span data-stu-id="d4340-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="d4340-107">在使用者進入 TeamsOnly 模式之前, 組織可以使用任何商務用 Skype 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings), 以確保 TeamsOnly 的使用者和尚不在他們的使用者可以預期地進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d4340-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="d4340-108">當使用者處於任何商務用 Skype 模式時, 所有傳入聊天和通話會傳送到使用者的商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d4340-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="d4340-109">若要避免使用者混淆並確保正確地進行路由, 小組用戶端中的呼叫及聊天功能會在使用者處於任何商務用 Skype 模式時停用。</span><span class="sxs-lookup"><span data-stu-id="d4340-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="d4340-110">同樣地, 在使用者處於 SfBOnly 或 SfBWithTeamsCollab 模式時, 小組中的會議排程會明確停用, 且在使用者處於 SfBWithTeamsCollabAndMeetings 模式時明確啟用。</span><span class="sxs-lookup"><span data-stu-id="d4340-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="d4340-111">團隊用戶端中的可用功能如何根據模式變更</span><span class="sxs-lookup"><span data-stu-id="d4340-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="d4340-112">團隊中的可用功能, 取決於使用者的共存模式 (由 TeamsUpgradePolicy 設定)。</span><span class="sxs-lookup"><span data-stu-id="d4340-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="d4340-113">下表摘要說明行為:</span><span class="sxs-lookup"><span data-stu-id="d4340-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="d4340-114">使用者的有效模式</span><span class="sxs-lookup"><span data-stu-id="d4340-114">User's effective mode</span></span>|<span data-ttu-id="d4340-115">團隊用戶端中的體驗</span><span class="sxs-lookup"><span data-stu-id="d4340-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="d4340-116">任何商務用 Skype 模式</span><span class="sxs-lookup"><span data-stu-id="d4340-116">Any Skype for Business mode</span></span>|<span data-ttu-id="d4340-117">通話和聊天功能已停用。</span><span class="sxs-lookup"><span data-stu-id="d4340-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="d4340-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="d4340-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="d4340-119">提供會議排程</span><span class="sxs-lookup"><span data-stu-id="d4340-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="d4340-120">SfBWithTeamsCollab 或 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d4340-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="d4340-121">無法使用會議排程</span><span class="sxs-lookup"><span data-stu-id="d4340-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="d4340-122">下列螢幕擷取畫面說明 TeamsOnly 或孤島模式與所有其他模式之間的差異。</span><span class="sxs-lookup"><span data-stu-id="d4340-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="d4340-123">請注意, [聊天] 和 [呼叫] 圖示可使用 TeamsOnly 或孤島模式 (左螢幕擷取畫面), 但不適用於其他模式 (右側螢幕擷取畫面):</span><span class="sxs-lookup"><span data-stu-id="d4340-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![團隊模式的並排比較](media/teams-mode-comparison.png)


 
<span data-ttu-id="d4340-125">**注意:**
<sup></sup>現在, SfBwithTeamsCollab 和 SfBOnly 的行為相同, 但在 SfBOnly 模式中也會停用團隊中的頻道與檔案功能;不過, 目前沒有任何設定可讓團隊中的此項功能停用。</span><span class="sxs-lookup"><span data-stu-id="d4340-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="d4340-126">模式對其他原則設定的影響</span><span class="sxs-lookup"><span data-stu-id="d4340-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="d4340-127">如上所述, 使用者的共存模式會影響使用者的團隊用戶端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="d4340-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="d4340-128">這表示 mode 的值可能會優先于其他原則設定的值, 視模式而定。</span><span class="sxs-lookup"><span data-stu-id="d4340-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="d4340-129">具體說來, 共存模式會影響是否會遵守下列原則設定:</span><span class="sxs-lookup"><span data-stu-id="d4340-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="d4340-130">**模態 (應用程式)**</span><span class="sxs-lookup"><span data-stu-id="d4340-130">**Modality (App)**</span></span>|<span data-ttu-id="d4340-131">**原則。設定**</span><span class="sxs-lookup"><span data-stu-id="d4340-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="d4340-132">交流</span><span class="sxs-lookup"><span data-stu-id="d4340-132">Chat</span></span>|<span data-ttu-id="d4340-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="d4340-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="d4340-134">通話</span><span class="sxs-lookup"><span data-stu-id="d4340-134">Calling</span></span>|<span data-ttu-id="d4340-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d4340-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="d4340-136">會議排程</span><span class="sxs-lookup"><span data-stu-id="d4340-136">Meeting scheduling</span></span>|<span data-ttu-id="d4340-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4340-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="d4340-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4340-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="d4340-139">當您使用 [共存] 模式時, 系統管理員*不*需要明確設定這些原則設定, 但請務必瞭解這些設定在特定模式下的行為方式如下。</span><span class="sxs-lookup"><span data-stu-id="d4340-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="d4340-140">下</span><span class="sxs-lookup"><span data-stu-id="d4340-140">Mode</span></span>|<span data-ttu-id="d4340-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="d4340-141">AllowUserChat</span></span>|<span data-ttu-id="d4340-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d4340-142">AllowPrivateCalling</span></span>|<span data-ttu-id="d4340-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4340-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="d4340-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d4340-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="d4340-145">TeamsOnly 或孤島</span><span class="sxs-lookup"><span data-stu-id="d4340-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="d4340-146">後</span><span class="sxs-lookup"><span data-stu-id="d4340-146">Enabled</span></span>|<span data-ttu-id="d4340-147">後</span><span class="sxs-lookup"><span data-stu-id="d4340-147">Enabled</span></span>|<span data-ttu-id="d4340-148">後</span><span class="sxs-lookup"><span data-stu-id="d4340-148">Enabled</span></span>|<span data-ttu-id="d4340-149">後</span><span class="sxs-lookup"><span data-stu-id="d4340-149">Enabled</span></span>|
|<span data-ttu-id="d4340-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="d4340-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="d4340-151">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-151">Disabled</span></span>|<span data-ttu-id="d4340-152">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-152">Disabled</span></span>|<span data-ttu-id="d4340-153">後</span><span class="sxs-lookup"><span data-stu-id="d4340-153">Enabled</span></span>|<span data-ttu-id="d4340-154">後</span><span class="sxs-lookup"><span data-stu-id="d4340-154">Enabled</span></span>|
|<span data-ttu-id="d4340-155">SfBWithTeamsCollab 或 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="d4340-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="d4340-156">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-156">Disabled</span></span>|<span data-ttu-id="d4340-157">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-157">Disabled</span></span>|<span data-ttu-id="d4340-158">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-158">Disabled</span></span>|<span data-ttu-id="d4340-159">禁止</span><span class="sxs-lookup"><span data-stu-id="d4340-159">Disabled</span></span>|
||||||

<span data-ttu-id="d4340-160">使用 PowerShell 時, 此`Grant-CsTeamsUpgradePolicy` Cmdlet 會檢查 TeamsMessagingPolicy、TeamsCallingPolicy 和 TeamsMeetingPolicy 中對應設定的設定, 以判斷是否會將這些設定取代 TeamsUpgradePolicy, 如果是,PowerShell 中提供了資訊性訊息。</span><span class="sxs-lookup"><span data-stu-id="d4340-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="d4340-161">如上所述, 不需要再設定其他原則設定。</span><span class="sxs-lookup"><span data-stu-id="d4340-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="d4340-162">以下是 PowerShell 警告外觀的範例:</span><span class="sxs-lookup"><span data-stu-id="d4340-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="d4340-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4340-163">Related topics</span></span>

[<span data-ttu-id="d4340-164">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="d4340-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




