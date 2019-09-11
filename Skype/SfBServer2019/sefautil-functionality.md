---
title: 支援在商務用 Skype Server 2019 的 PowerShell 中使用 SEFAUtil 功能
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解如何在安裝累積更新1之後，在商務用 Skype Server 2019 中使用 PowerShell 來取得 SEFAUtil 功能。
ms.openlocfilehash: 6652e3b76a31ac4b315c70498ac2b01d4467b70e
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838096"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="b0229-103">在商務用 Skype Server 2019 中使用 SEFAUtil 功能經由 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0229-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="b0229-104">SEFAUtil （次要延伸功能啟用）可讓商務用 Skype Server 系統管理員和支援人員代理程式代表商務用 Skype Server 使用者設定代理人響鈴、來電轉接及群組呼叫的裝貨設定。</span><span class="sxs-lookup"><span data-stu-id="b0229-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="b0229-105">此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="b0229-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="b0229-106">安裝商務用 Skype Server 2019 7 月累計更新之後，目前只能透過 SEFAUtil 管理的下列功能也會透過 PowerShell 進行管理：</span><span class="sxs-lookup"><span data-stu-id="b0229-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="b0229-107">來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="b0229-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="b0229-108">委派設定</span><span class="sxs-lookup"><span data-stu-id="b0229-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="b0229-109">小組成員和相關設定</span><span class="sxs-lookup"><span data-stu-id="b0229-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="b0229-110">來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="b0229-110">Call forwarding settings</span></span>

<span data-ttu-id="b0229-111">系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更來電轉接設定：</span><span class="sxs-lookup"><span data-stu-id="b0229-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="b0229-112">這個 Cmdlet 會將指定使用者的來電轉接設定作為物件傳回，並在螢幕上顯示相同的值。</span><span class="sxs-lookup"><span data-stu-id="b0229-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="b0229-113">這個 Cmdlet 會修改指定使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="b0229-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="b0229-114">這個 Cmdlet 會將指定使用者的來電轉接設定作為物件傳回，並在畫面上顯示相同的畫面（如果成功的話）。</span><span class="sxs-lookup"><span data-stu-id="b0229-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="b0229-115">如果發生失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b0229-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="b0229-116">這個 Cmdlet 會停用使用者的來電轉接設定（我們會在這裡顯示兩個不同的參數範例）。</span><span class="sxs-lookup"><span data-stu-id="b0229-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="b0229-117">這個 Cmdlet 會修改使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="b0229-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="b0229-118">這個 Cmdlet 會修改 SimulRing 設定（同樣地，有兩個參數範例，一個用於無人回復給語音信箱，而第二個則是未回復的）。</span><span class="sxs-lookup"><span data-stu-id="b0229-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="b0229-119">委派設定</span><span class="sxs-lookup"><span data-stu-id="b0229-119">Delegation settings</span></span>

<span data-ttu-id="b0229-120">系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更委派設定：</span><span class="sxs-lookup"><span data-stu-id="b0229-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="b0229-121">這個 Cmdlet 會傳回代理人清單的物件，並顯示指定使用者的委派清單（如果成功的話）。</span><span class="sxs-lookup"><span data-stu-id="b0229-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="b0229-122">如果發生失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b0229-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="b0229-123">這個 Cmdlet 會修改指定使用者的委派設定、傳回代理人清單的物件，以及顯示代理人的清單（如果成功的話）。</span><span class="sxs-lookup"><span data-stu-id="b0229-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="b0229-124">如果發生失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b0229-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="b0229-125">這個 Cmdlet 會新增或移除代理人。</span><span class="sxs-lookup"><span data-stu-id="b0229-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="b0229-126">這個 Cmdlet 會將委派清單設定為特定的代理人。</span><span class="sxs-lookup"><span data-stu-id="b0229-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="b0229-127">小組成員和相關設定</span><span class="sxs-lookup"><span data-stu-id="b0229-127">Team members and related settings</span></span>

<span data-ttu-id="b0229-128">系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更小組成員和相關設定：</span><span class="sxs-lookup"><span data-stu-id="b0229-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="b0229-129">這個 Cmdlet 會傳回包含小組成員清單的物件，並在畫面上顯示物件（如果成功的話）。</span><span class="sxs-lookup"><span data-stu-id="b0229-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="b0229-130">如果發生失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b0229-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="b0229-131">這個 Cmdlet 會修改指定使用者的小組成員清單，傳回包含小組成員清單的物件，並在畫面上顯示該物件（如果成功的話）。</span><span class="sxs-lookup"><span data-stu-id="b0229-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="b0229-132">如果發生失敗，就會顯示適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b0229-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="b0229-133">這個 Cmdlet 會新增或移除小組成員。</span><span class="sxs-lookup"><span data-stu-id="b0229-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="b0229-134">這個 Cmdlet 會將小組清單設定為特定的成員。</span><span class="sxs-lookup"><span data-stu-id="b0229-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="b0229-135">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b0229-135">More information</span></span>

<span data-ttu-id="b0229-136">針對內部部署的部署，此功能中引入的 Cmdlet 只能由下列群組的成員執行，依據以下指定的存取層級：</span><span class="sxs-lookup"><span data-stu-id="b0229-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="b0229-137">CsAdministrator –取得並設定所有 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0229-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="b0229-138">CsVoiceAdministrator-取得與設定所有 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0229-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="b0229-139">CsHelpDesk-取得所有 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0229-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="b0229-140">如需這些系統管理員角色的詳細資訊，請參閱[建立商務用 Skype Server 控制台系統管理員](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。</span><span class="sxs-lookup"><span data-stu-id="b0229-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="b0229-141">系統管理員可以直接或遠端登入伺服器電腦來存取這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0229-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="b0229-142">針對混合式部署，商務用 Skype 系統管理員應該可以呼叫取得和設定所有 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0229-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="b0229-143">如需有關完整角色清單的詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="b0229-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="b0229-144">必須啟用伺服器自動探索。</span><span class="sxs-lookup"><span data-stu-id="b0229-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="b0229-145">不會推出其他授權需求來使用 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0229-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
