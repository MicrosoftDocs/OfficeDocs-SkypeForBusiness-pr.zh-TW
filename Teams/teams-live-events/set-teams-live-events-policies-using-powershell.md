---
title: 使用 PowerShell 設定即時事件原則
author: lanachin
ms.author: v-lanac
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
description: 如何使用 PowerShell 來設定小組中的原則，以控制哪些人可以在組織中擁有即時事件，以及事件中的可用功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c1131790e36fe451444a8c8a3fb25259d5741da
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691569"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="eb02f-103">使用 PowerShell 在 Microsoft 團隊中設定即時事件原則</span><span class="sxs-lookup"><span data-stu-id="eb02f-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="eb02f-104">您可以在團隊中使用下列 Windows PowerShell Cmdlet 來設定及指派即時事件的原則設定：</span><span class="sxs-lookup"><span data-stu-id="eb02f-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="eb02f-105">CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="eb02f-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="eb02f-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="eb02f-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="eb02f-107">新-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="eb02f-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="eb02f-108">授與 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="eb02f-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="eb02f-109">以下是一些範例。</span><span class="sxs-lookup"><span data-stu-id="eb02f-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="eb02f-110">您必須先連線到商務用 Skype Online PowerShell，才能執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eb02f-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="eb02f-111">如需詳細資訊，請參閱[使用 Microsoft 365 或 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="eb02f-111">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="eb02f-112">允許使用者排程即時事件</span><span class="sxs-lookup"><span data-stu-id="eb02f-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="eb02f-113">這些範例適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="eb02f-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="eb02f-114">對於使用外部 app 或裝置所產生的事件，您必須執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="eb02f-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="eb02f-115">如需詳細資訊，請參閱[讓使用者排程由外部 app 或裝置產生的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。</span><span class="sxs-lookup"><span data-stu-id="eb02f-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="eb02f-116">**允許使用者排程即時事件**</span><span class="sxs-lookup"><span data-stu-id="eb02f-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="eb02f-117">如果使用者指派了全域原則，請執行並確認*AllowBroadcastScheduling*參數設定為*True*：</span><span class="sxs-lookup"><span data-stu-id="eb02f-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="eb02f-118">然後，將使用者指派給全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="eb02f-119">使用者案例</span><span class="sxs-lookup"><span data-stu-id="eb02f-119">User scenarios</span></span>
<span data-ttu-id="eb02f-120">**您希望貴組織中的所有使用者都能夠排程即時事件**</span><span class="sxs-lookup"><span data-stu-id="eb02f-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="eb02f-121">如果使用者指派了全域原則，請執行並確認*AllowBroadcastScheduling* \* 設定為*True*：</span><span class="sxs-lookup"><span data-stu-id="eb02f-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="eb02f-122">如果使用者指派了全域原則以外的原則，請執行並確認 *-AllowBroadcastScheduling*已設定為*True*：</span><span class="sxs-lookup"><span data-stu-id="eb02f-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="eb02f-123">**您想要在整個組織中停用即時事件排程**</span><span class="sxs-lookup"><span data-stu-id="eb02f-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="eb02f-124">停用即時事件排程，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="eb02f-125">將貴組織中的所有使用者指派給全域原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="eb02f-126">**您想要有大量的使用者能夠排程即時事件，並防止一組使用者進行排程**</span><span class="sxs-lookup"><span data-stu-id="eb02f-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="eb02f-127">執行並確認*AllowBroadcastScheduling*已設定為*True*：</span><span class="sxs-lookup"><span data-stu-id="eb02f-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="eb02f-128">然後，將使用者或使用者指派給全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="eb02f-129">建立不允許排程即時事件的新原則，請執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="eb02f-130">停用即時事件排程，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="eb02f-131">然後將使用者指派給此原則，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="eb02f-132">**您想要針對大量的使用者停用即時事件排程，並允許一組使用者進行排程**</span><span class="sxs-lookup"><span data-stu-id="eb02f-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="eb02f-133">停用即時事件排程，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="eb02f-134">然後將這些使用者指派給全域原則，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="eb02f-135">建立原則以允許即時事件排程，請執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="eb02f-136">啟用即時事件排程，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="eb02f-137">然後將使用者指派給此原則，執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="eb02f-138">設定誰可以加入即時事件</span><span class="sxs-lookup"><span data-stu-id="eb02f-138">Set who can join live events</span></span>
 
<span data-ttu-id="eb02f-139">將全域原則設定為允許使用者建立每個人（包括匿名使用者）都可以出席的事件，請執行：</span><span class="sxs-lookup"><span data-stu-id="eb02f-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="eb02f-140">設定即時事件的錄製選項</span><span class="sxs-lookup"><span data-stu-id="eb02f-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="eb02f-141">此設定僅適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="eb02f-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="eb02f-142">設定全域原則，停用錄製即時事件：</span><span class="sxs-lookup"><span data-stu-id="eb02f-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="eb02f-143">在即時事件中設定即時標題和字幕</span><span class="sxs-lookup"><span data-stu-id="eb02f-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="eb02f-144">此設定僅適用于小組中產生的活動。</span><span class="sxs-lookup"><span data-stu-id="eb02f-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="eb02f-145">設定 [全域原則]，為活動出席者開啟即時輔助字幕和字幕（會議）：</span><span class="sxs-lookup"><span data-stu-id="eb02f-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="eb02f-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="eb02f-146">Related topics</span></span>
- [<span data-ttu-id="eb02f-147">設定 Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="eb02f-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="eb02f-148">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="eb02f-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

