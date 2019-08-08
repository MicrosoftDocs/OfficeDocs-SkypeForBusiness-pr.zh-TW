---
title: 使用 PowerShell 在 Microsoft 團隊中設定即時事件原則
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 如何使用 PowerShell 來設定小組中的原則, 以控制哪些人可以在組織中擁有即時事件, 以及他們所建立的事件中提供的功能
appliesto:
- Microsoft Teams
ms.openlocfilehash: b92d52178f7b57b453eaaec010ded4731d166caf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243645"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="01cb5-103">使用 PowerShell 在 Microsoft 團隊中設定即時事件原則</span><span class="sxs-lookup"><span data-stu-id="01cb5-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="01cb5-104">您可以在團隊中使用下列 Windows PowerShell Cmdlet 來設定及指派即時事件的原則設定:</span><span class="sxs-lookup"><span data-stu-id="01cb5-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="01cb5-105">CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="01cb5-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="01cb5-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="01cb5-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="01cb5-107">新-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="01cb5-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="01cb5-108">授與 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="01cb5-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="01cb5-109">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="01cb5-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="01cb5-110">允許使用者排程即時事件</span><span class="sxs-lookup"><span data-stu-id="01cb5-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="01cb5-111">這些範例適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="01cb5-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="01cb5-112">對於使用外部 app 或裝置所產生的事件, 您必須執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="01cb5-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="01cb5-113">如需詳細資訊, 請參閱[讓使用者排程由外部 app 或裝置產生的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。</span><span class="sxs-lookup"><span data-stu-id="01cb5-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="01cb5-114">**允許使用者排程即時事件**</span><span class="sxs-lookup"><span data-stu-id="01cb5-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="01cb5-115">如果使用者指派了全域原則, 請執行並確認*AllowBroadcastScheduling*參數設定為*True*:</span><span class="sxs-lookup"><span data-stu-id="01cb5-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="01cb5-116">然後, 將使用者指派給全域原則, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="01cb5-117">使用者案例</span><span class="sxs-lookup"><span data-stu-id="01cb5-117">User scenarios</span></span>
<span data-ttu-id="01cb5-118">**您希望貴組織中的所有使用者都能夠排程即時事件**</span><span class="sxs-lookup"><span data-stu-id="01cb5-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="01cb5-119">如果使用者指派了全域原則, 請執行並確認*AllowBroadcastScheduling* \* 設定為*True*:</span><span class="sxs-lookup"><span data-stu-id="01cb5-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="01cb5-120">如果使用者指派了全域原則以外的原則, 請執行並確認 *-AllowBroadcastScheduling*已設定為*True*:</span><span class="sxs-lookup"><span data-stu-id="01cb5-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="01cb5-121">**您想要在整個組織中停用即時事件排程**</span><span class="sxs-lookup"><span data-stu-id="01cb5-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="01cb5-122">停用即時事件排程, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="01cb5-123">將貴組織中的所有使用者指派給全域原則, 請執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="01cb5-124">**您想要有大量的使用者能夠排程即時事件, 並防止一組使用者進行排程**</span><span class="sxs-lookup"><span data-stu-id="01cb5-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="01cb5-125">執行並確認*AllowBroadcastScheduling*已設定為*True*:</span><span class="sxs-lookup"><span data-stu-id="01cb5-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="01cb5-126">然後, 將使用者或使用者指派給全域原則, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="01cb5-127">建立不允許排程即時事件的新原則, 請執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="01cb5-128">停用即時事件排程, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="01cb5-129">然後將使用者指派給此原則, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="01cb5-130">**您想要針對大量的使用者停用即時事件排程, 並允許一組使用者進行排程**</span><span class="sxs-lookup"><span data-stu-id="01cb5-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="01cb5-131">停用即時事件排程, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="01cb5-132">然後將這些使用者指派給全域原則, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="01cb5-133">建立原則以允許即時事件排程, 請執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="01cb5-134">啟用即時事件排程, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="01cb5-135">然後將使用者指派給此原則, 執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="01cb5-136">設定誰可以加入即時事件</span><span class="sxs-lookup"><span data-stu-id="01cb5-136">Set who can join live events</span></span>
 
<span data-ttu-id="01cb5-137">將全域原則設定為允許使用者建立每個人 (包括匿名使用者) 都可以出席的事件, 請執行:</span><span class="sxs-lookup"><span data-stu-id="01cb5-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="01cb5-138">設定即時事件的錄製選項</span><span class="sxs-lookup"><span data-stu-id="01cb5-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="01cb5-139">此設定僅適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="01cb5-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="01cb5-140">設定全域原則, 停用錄製即時事件:</span><span class="sxs-lookup"><span data-stu-id="01cb5-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="01cb5-141">在即時事件中設定即時標題和字幕</span><span class="sxs-lookup"><span data-stu-id="01cb5-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="01cb5-142">此設定僅適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="01cb5-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="01cb5-143">設定 [全域原則], 為活動出席者開啟即時輔助字幕和字幕 (會議):</span><span class="sxs-lookup"><span data-stu-id="01cb5-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="01cb5-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="01cb5-144">Related topics</span></span>
- [<span data-ttu-id="01cb5-145">設定小組即時事件</span><span class="sxs-lookup"><span data-stu-id="01cb5-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


