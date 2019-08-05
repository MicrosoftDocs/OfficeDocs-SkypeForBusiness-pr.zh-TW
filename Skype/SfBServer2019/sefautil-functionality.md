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
description: '摘要: 瞭解如何在安裝累積更新1之後, 在商務用 Skype Server 2019 中使用 PowerShell 來取得 SEFAUtil 功能。'
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2019
ms.locfileid: "36194118"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在商務用 Skype Server 2019 中使用 SEFAUtil 功能經由 PowerShell

SEFAUtil (次要延伸功能啟用) 可讓商務用 Skype Server 系統管理員和支援人員代理程式代表商務用 Skype Server 使用者設定代理人響鈴、來電轉接及群組呼叫的裝貨設定。 此工具也可讓系統管理員查詢針對特定使用者發佈的呼叫路由設定。 安裝此更新後, 目前只能透過 SEFAUtil 管理的下列功能也會透過 PowerShell 進行管理:

- [來電轉接設定](#call-forwarding-settings)
- [委派設定](#delegation-settings)
- [小組成員和相關設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>來電轉接設定

系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更來電轉接設定:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

這個 Cmdlet 會將指定使用者的來電轉接設定作為物件傳回, 並在螢幕上顯示相同的值。

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

這個 Cmdlet 會修改指定使用者的來電轉接設定。 這個 Cmdlet 會將指定使用者的來電轉接設定作為物件傳回, 並在畫面上顯示相同的畫面 (如果成功的話)。 如果發生失敗, 就會顯示適當的錯誤訊息。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

這個 Cmdlet 會停用使用者的來電轉接設定 (我們會在這裡顯示兩個不同的參數範例)。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

這個 Cmdlet 會修改使用者的來電轉接設定。

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

這個 Cmdlet 會修改 SimulRing 設定 (同樣地, 有兩個參數範例, 一個用於無人回復給語音信箱, 而第二個則是未回復的)。

## <a name="delegation-settings"></a>委派設定

系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更委派設定:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

這個 Cmdlet 會傳回代理人清單的物件, 並顯示指定使用者的委派清單 (如果成功的話)。 如果發生失敗, 就會顯示適當的錯誤訊息。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

這個 Cmdlet 會修改指定使用者的委派設定、傳回代理人清單的物件, 以及顯示代理人的清單 (如果成功的話)。 如果發生失敗, 就會顯示適當的錯誤訊息。 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

這個 Cmdlet 會新增或移除代理人。

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

這個 Cmdlet 會將委派清單設定為特定的代理人。

## <a name="team-members-and-related-settings"></a>小組成員和相關設定

系統管理員可以在 PowerShell 中使用下列 Cmdlet 來變更小組成員和相關設定:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

這個 Cmdlet 會傳回包含小組成員清單的物件, 並在畫面上顯示物件 (如果成功的話)。 如果發生失敗, 就會顯示適當的錯誤訊息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

這個 Cmdlet 會修改指定使用者的小組成員清單, 傳回包含小組成員清單的物件, 並在畫面上顯示該物件 (如果成功的話)。 如果發生失敗, 就會顯示適當的錯誤訊息。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

這個 Cmdlet 會新增或移除小組成員。

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

這個 Cmdlet 會將小組清單設定為特定的成員。

## <a name="more-information"></a>其他資訊

針對內部部署的部署, 此功能中引入的 Cmdlet 只能由下列群組的成員執行, 依據以下指定的存取層級:

- CsAdministrator –取得並設定所有 Cmdlet
- CsVoiceAdministrator-取得與設定所有 Cmdlet
- CsHelpDesk-取得所有 Cmdlet

如需這些系統管理員角色的詳細資訊, 請參閱[建立商務用 Skype Server 控制台系統管理員](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。 系統管理員可以直接或遠端登入伺服器電腦來存取這些 Cmdlet。
針對混合式部署, 商務用 Skype 系統管理員應該可以呼叫取得和設定所有 Cmdlet。 如需有關完整角色清單的詳細資訊, 請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> 必須啟用伺服器自動探索。 不會推出其他授權需求來使用 Cmdlet。
