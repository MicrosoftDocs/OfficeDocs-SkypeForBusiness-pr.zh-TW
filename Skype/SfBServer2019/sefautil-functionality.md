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
ms.openlocfilehash: afb0c34afedde91bac40ee90b155809ed3c2b557d88608028b77e0835eb9661d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277618"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在商務用 Skype Server 2019 中使用 SEFAUtil 功能 PowerShell

SEFAUtil (次要擴充功能啟動) 可讓商務用 Skype Server 系統管理員和支援人員代理程式代表商務用 Skype Server 使用者設定代理人震鈴、來電轉接和群組呼叫收取設定。 這個工具也可讓系統管理員查詢針對特定使用者所發佈的呼叫路由設定。 在您商務用 Skype Server 安裝2019年7月累積更新後，目前只能透過 SEFAUtil 進行管理的下列功能將可透過 PowerShell: 進行管理。

- [來電轉接設定](#call-forwarding-settings)
- [委派設定](#delegation-settings)
- [小組成員和相關設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>來電轉接設定

管理員可以在 PowerShell: 中使用下列 Cmdlet 變更來電轉接設定

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

這個 Cmdlet 會將指定使用者的「來電轉接」設定視為物件，並在螢幕上顯示相同。

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

此 Cmdlet 會修改指定使用者的「來電轉接」設定。 此 Cmdlet 會以物件的形式傳回指定使用者的「來電轉接」設定，並在畫面上顯示相同的畫面，以防成功。 如果失敗，就會顯示適當的錯誤訊息。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 Cmdlet 會停用使用者的來電轉接設定 (會在這裡顯示兩個不同的參數範例) 。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

此 Cmdlet 會修改使用者的「來電轉接」設定。

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

此 Cmdlet 會同時修改同時振鈴設定 (，其中有兩個參數範例，一個用於無人接聽語音信箱，第二個則是不應答其他) 。

## <a name="delegation-settings"></a>委派設定

管理員可以在 PowerShell: 中使用下列 Cmdlet 變更委派設定

- `Get-CsuserDelegates -Identity <UserIdParameter>`

此 Cmdlet 會傳回代理人清單的物件，並顯示指定使用者的代理人清單（如果成功）。 如果失敗，就會顯示適當的錯誤訊息。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

此 Cmdlet 會修改指定使用者的委派設定、傳回代理人清單的物件，以及顯示代理人的清單，以防成功。 如果失敗，就會顯示適當的錯誤訊息。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

此 Cmdlet 會新增或移除代理人。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

此 Cmdlet 會將委派清單設定為特定代理人。

## <a name="team-members-and-related-settings"></a>小組成員和相關設定

管理員可以在 PowerShell: 中使用下列 Cmdlet 變更小組成員和相關設定。

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

此 Cmdlet 會傳回包含小組成員清單的物件，並在畫面上顯示物件，以防成功。 如果失敗，就會顯示適當的錯誤訊息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

此 Cmdlet 會修改指定使用者的小組成員清單，傳回包含小組成員清單的物件，並在畫面上顯示物件，以防成功。 如果失敗，就會顯示適當的錯誤訊息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

此 Cmdlet 會新增或移除小組成員。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

此 Cmdlet 會將小組清單設為特定成員。

## <a name="more-information"></a>其他相關資訊

在內部部署中，此功能中引入的指令程式只能由下列群組的成員執行，依下列所指定的訪問層級：

- CsAdministrator –取得及設定所有 Cmdlet
- CsVoiceAdministrator-取得及設定所有 Cmdlet
- 所有 Cmdlet 的 CsHelpDesk-取得

如需這些系統管理員角色的詳細資訊，請參閱[Create 商務用 Skype Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 管理員可以直接或遠端登入伺服器電腦，存取這些 Cmdlet。
在混合式部署中，商務用 Skype 管理員應該能夠為所有 Cmdlet 呼叫 Get 及 Set。 如需完整角色清單的詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> 必須啟用伺服器自動探索。 不會引入其他授權需求，以供使用 Cmdlet 使用。
