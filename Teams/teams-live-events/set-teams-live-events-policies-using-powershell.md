---
title: 使用 PowerShell 設定即時活動政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 如何使用 PowerShell 在 Teams 中設定策略以控制誰可以在貴組織中舉辦即時活動，以及活動可用的功能範例。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119142"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="1eb1b-103">使用 PowerShell 在 Microsoft Teams 中設定即時活動政策</span><span class="sxs-lookup"><span data-stu-id="1eb1b-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="1eb1b-104">您可以使用下列 Windows PowerShell Cmdlet 在 Teams 中設定和指派即時活動的政策設定：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="1eb1b-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1eb1b-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1eb1b-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1eb1b-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1eb1b-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1eb1b-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1eb1b-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="1eb1b-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="1eb1b-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="1eb1b-109">New-CsGroupPolicyAssignment</span></span>](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="1eb1b-110">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb1b-111">您必須先連線到商務用 Skype Online PowerShell，才能執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="1eb1b-112">詳細資訊，請參閱使用 [Microsoft 365 或 Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)管理商務用 Skype Online 。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="1eb1b-113">允許使用者排程即時活動</span><span class="sxs-lookup"><span data-stu-id="1eb1b-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="1eb1b-114">這些範例適用于 Teams 中產生的事件。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="1eb1b-115">對於使用外部 App 或裝置產生的事件，您必須執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="1eb1b-116">若要取得詳細資訊，請參閱讓使用者排程使用外部 App 或裝置產生的 [事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="1eb1b-117">**允許使用者排程即時活動**</span><span class="sxs-lookup"><span data-stu-id="1eb1b-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="1eb1b-118">如果使用者已指派全域原則，請執行並驗證 *AllowBroadcast 排程* 參數設為 *True：*</span><span class="sxs-lookup"><span data-stu-id="1eb1b-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="1eb1b-119">然後將使用者指派給全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="1eb1b-120">使用者案例</span><span class="sxs-lookup"><span data-stu-id="1eb1b-120">User scenarios</span></span>
<span data-ttu-id="1eb1b-121">**您希望貴組織中所有使用者都能排程即時活動**</span><span class="sxs-lookup"><span data-stu-id="1eb1b-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="1eb1b-122">如果使用者已指派全域原則，請執行並驗證 *AllowBroadcastScheduling* \*已設為 *True：*</span><span class="sxs-lookup"><span data-stu-id="1eb1b-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="1eb1b-123">如果使用者被指派全域原則外的其他策略，請執行並驗證 *-AllowBroadcast 排程* 設定為 *True：*</span><span class="sxs-lookup"><span data-stu-id="1eb1b-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="1eb1b-124">**您希望整個組織停用即時活動排程**</span><span class="sxs-lookup"><span data-stu-id="1eb1b-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="1eb1b-125">停用即時活動排程，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="1eb1b-126">將貴組織中所有使用者指派給全域原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="1eb1b-127">**您希望大量使用者能夠排程即時事件，並防止一組使用者排程活動**</span><span class="sxs-lookup"><span data-stu-id="1eb1b-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="1eb1b-128">執行並驗證 *AllowBroadcast 排程* 設定為 *True：*</span><span class="sxs-lookup"><span data-stu-id="1eb1b-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="1eb1b-129">然後指派使用者或使用者至全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="1eb1b-130">建立不允許排程即時事件的新策略，請執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="1eb1b-131">停用即時活動排程，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="1eb1b-132">然後指派使用者至此策略，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="1eb1b-133">**您想要針對大量使用者停用即時事件排程，並允許一組使用者排程**</span><span class="sxs-lookup"><span data-stu-id="1eb1b-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="1eb1b-134">停用即時活動排程，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="1eb1b-135">然後將這些使用者指派給全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="1eb1b-136">建立允許即時事件排程的策略，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="1eb1b-137">啟用即時活動排程，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="1eb1b-138">然後指派使用者至此策略，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="1eb1b-139">設定誰可以加入即時活動</span><span class="sxs-lookup"><span data-stu-id="1eb1b-139">Set who can join live events</span></span>
 
<span data-ttu-id="1eb1b-140">設定全域原則以允許使用者建立每個人都可以參加的活動，包括匿名使用者，執行：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="1eb1b-141">設定即時事件的錄製選項</span><span class="sxs-lookup"><span data-stu-id="1eb1b-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="1eb1b-142">此設定僅適用于 Teams 中產生的事件。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="1eb1b-143">設定全域原則以停用即時活動的錄製：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="1eb1b-144">在即時活動中設定即時字幕和字幕</span><span class="sxs-lookup"><span data-stu-id="1eb1b-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="1eb1b-145">此設定僅適用于 Teams 中產生的事件。</span><span class="sxs-lookup"><span data-stu-id="1eb1b-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="1eb1b-146">設定全域原則，為活動出席者開啟即時 (字幕) 字幕：</span><span class="sxs-lookup"><span data-stu-id="1eb1b-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="1eb1b-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="1eb1b-147">Related topics</span></span>
- [<span data-ttu-id="1eb1b-148">設定 Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="1eb1b-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="1eb1b-149">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="1eb1b-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)