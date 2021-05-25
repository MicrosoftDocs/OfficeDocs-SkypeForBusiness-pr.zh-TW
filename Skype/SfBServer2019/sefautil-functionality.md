---
title: 支援在商務用 Skype Server 2019 PowerShell 中使用 SEFAUtil 功能
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解在安裝累積更新1之後，如何使用 PowerShell 以取得商務用 Skype Server 2019 的 SEFAUtil 功能。
ms.openlocfilehash: fa7bccaa30b559bf694274471b1f8883e8482861
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52629002"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="7efbb-103">在商務用 Skype Server 2019 中使用 SEFAUtil 功能 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7efbb-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="7efbb-104">SEFAUtil (次要擴充功能啟動) 可讓商務用 Skype Server 系統管理員和支援人員代理程式代表商務用 Skype Server 使用者設定代理人震鈴、來電轉接和群組呼叫收取設定。</span><span class="sxs-lookup"><span data-stu-id="7efbb-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="7efbb-105">這個工具也可讓系統管理員查詢針對特定使用者所發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="7efbb-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="7efbb-106">在您商務用 Skype Server 安裝2019年7月累積更新後，目前只能透過 SEFAUtil 進行管理的下列功能將可透過 PowerShell: 進行管理。</span><span class="sxs-lookup"><span data-stu-id="7efbb-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="7efbb-107">來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="7efbb-108">委派設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="7efbb-109">小組成員和相關設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="7efbb-110">來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-110">Call forwarding settings</span></span>

<span data-ttu-id="7efbb-111">管理員可以在 PowerShell: 中使用下列 Cmdlet 變更來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="7efbb-112">這個 Cmdlet 會將指定使用者的「來電轉接」設定視為物件，並在螢幕上顯示相同。</span><span class="sxs-lookup"><span data-stu-id="7efbb-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="7efbb-113">此 Cmdlet 會修改指定使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="7efbb-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="7efbb-114">此 Cmdlet 會以物件的形式傳回指定使用者的「來電轉接」設定，並在畫面上顯示相同的畫面，以防成功。</span><span class="sxs-lookup"><span data-stu-id="7efbb-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="7efbb-115">如果失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7efbb-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="7efbb-116">此 Cmdlet 會停用使用者的來電轉接設定 (會在這裡顯示兩個不同的參數範例) 。</span><span class="sxs-lookup"><span data-stu-id="7efbb-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="7efbb-117">此 Cmdlet 會修改使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="7efbb-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="7efbb-118">此 Cmdlet 會同時修改同時振鈴設定 (，其中有兩個參數範例，一個用於無人接聽語音信箱，第二個則是不應答其他) 。</span><span class="sxs-lookup"><span data-stu-id="7efbb-118">This cmdlet modifies the simultaneous ring settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="7efbb-119">委派設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-119">Delegation settings</span></span>

<span data-ttu-id="7efbb-120">管理員可以在 PowerShell: 中使用下列 Cmdlet 變更委派設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="7efbb-121">此 Cmdlet 會傳回代理人清單的物件，並顯示指定使用者的代理人清單（如果成功）。</span><span class="sxs-lookup"><span data-stu-id="7efbb-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="7efbb-122">如果失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7efbb-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="7efbb-123">此 Cmdlet 會修改指定使用者的委派設定、傳回代理人清單的物件，以及顯示代理人的清單，以防成功。</span><span class="sxs-lookup"><span data-stu-id="7efbb-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list, and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="7efbb-124">如果失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7efbb-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="7efbb-125">此 Cmdlet 會新增或移除代理人。</span><span class="sxs-lookup"><span data-stu-id="7efbb-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="7efbb-126">此 Cmdlet 會將委派清單設定為特定代理人。</span><span class="sxs-lookup"><span data-stu-id="7efbb-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="7efbb-127">小組成員和相關設定</span><span class="sxs-lookup"><span data-stu-id="7efbb-127">Team members and related settings</span></span>

<span data-ttu-id="7efbb-128">管理員可以在 PowerShell: 中使用下列 Cmdlet 變更小組成員和相關設定。</span><span class="sxs-lookup"><span data-stu-id="7efbb-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="7efbb-129">此 Cmdlet 會傳回包含小組成員清單的物件，並在畫面上顯示物件，以防成功。</span><span class="sxs-lookup"><span data-stu-id="7efbb-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="7efbb-130">如果失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7efbb-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="7efbb-131">此 Cmdlet 會修改指定使用者的小組成員清單，傳回包含小組成員清單的物件，並在畫面上顯示物件，以防成功。</span><span class="sxs-lookup"><span data-stu-id="7efbb-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="7efbb-132">如果失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="7efbb-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="7efbb-133">此 Cmdlet 會新增或移除小組成員。</span><span class="sxs-lookup"><span data-stu-id="7efbb-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="7efbb-134">此 Cmdlet 會將小組清單設為特定成員。</span><span class="sxs-lookup"><span data-stu-id="7efbb-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="7efbb-135">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="7efbb-135">More information</span></span>

<span data-ttu-id="7efbb-136">在內部部署中，此功能中引入的指令程式只能由下列群組的成員執行，依下列所指定的訪問層級：</span><span class="sxs-lookup"><span data-stu-id="7efbb-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="7efbb-137">CsAdministrator –取得及設定所有 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7efbb-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="7efbb-138">CsVoiceAdministrator-取得及設定所有 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7efbb-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="7efbb-139">所有 Cmdlet 的 CsHelpDesk-取得</span><span class="sxs-lookup"><span data-stu-id="7efbb-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="7efbb-140">如需這些系統管理員角色的詳細資訊，請參閱[Create 商務用 Skype Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。</span><span class="sxs-lookup"><span data-stu-id="7efbb-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="7efbb-141">管理員可以直接或遠端登入伺服器電腦，存取這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7efbb-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="7efbb-142">在混合式部署中，商務用 Skype 管理員應該能夠為所有 Cmdlet 呼叫 Get 及 Set。</span><span class="sxs-lookup"><span data-stu-id="7efbb-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="7efbb-143">如需完整角色清單的詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="7efbb-143">For more information about the full list of roles, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="7efbb-144">必須啟用伺服器自動探索。</span><span class="sxs-lookup"><span data-stu-id="7efbb-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="7efbb-145">不會引入其他授權需求，以供使用 Cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="7efbb-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
