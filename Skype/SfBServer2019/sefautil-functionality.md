---
title: 支援在 商務用 Skype Server 2019 Skype PowerShell 中使用 SEFAUtil 功能
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 摘要：瞭解如何在安裝累積更新 1 之後，使用 PowerShell 在 商務用 Skype Server 2019 中取得 SEFAUtil 功能。
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676535"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>在 商務用 Skype Server 2019 中透過 PowerShell 使用 SEFAUtil 功能

SEFAUtil (次要擴充功能啟用) 可讓商務用 Skype Server系統管理員和技術支援中心代理程式代表商務用 Skype Server使用者設定委派通道、通話轉接和群組通話接聽設定。 SEFAUtil 也可讓系統管理員查詢特定使用者的呼叫路由設定。

安裝 商務用 Skype Server 2019 年 7 月累積更新之後，只有透過 SEFAUtil 才能使用的下列功能也可在 Skype PowerShell 中使用：

- [呼叫轉送設定](#call-forwarding-settings)
- [委派設定](#delegation-settings)
- [小組成員和相關設定](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>呼叫轉送設定

系統管理員可以在 PowerShell 中使用下列命令來變更呼叫轉送設定：

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

此命令會以 物件傳回指定使用者的呼叫轉送設定，並在畫面上顯示相同的設定。

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

此命令會修改指定使用者的呼叫轉送設定。 此命令會傳回指定使用者的呼叫轉送設定做為 物件，並在畫面上顯示相同的 。 如果命令不成功，將會顯示適當的錯誤訊息。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

此命令會停用使用者的呼叫轉送設定 (我們會在此處顯示兩個不同的參數範例) 。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

此命令會修改使用者的呼叫轉送設定。

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

此命令會使用兩個參數範例，再次修改同步通道設定 (，一個用於未回應語音信箱，另一個則未回應至其他) 。

## <a name="delegation-settings"></a>委派設定

系統管理員可以在 PowerShell 中使用下列命令來變更委派設定：

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

此命令會傳回委派清單的物件，並顯示指定的使用者委派清單。 如果命令不成功，將會顯示適當的錯誤訊息。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

此命令會修改指定使用者的委派設定、傳回委派清單的物件，並顯示委派清單。 如果命令不成功，將會顯示適當的錯誤訊息。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

此命令會新增或移除委派。

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

此命令會將委派清單設定為特定委派。

## <a name="team-members-and-related-settings"></a>小組成員和相關設定

系統管理員可以在 PowerShell 中使用下列命令來變更小組成員和相關設定：

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

此命令會傳回包含小組成員清單的物件，並在螢幕上顯示物件。 如果命令不成功，將會顯示適當的錯誤訊息。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

此命令會修改指定使用者的小組成員清單、傳回包含小組成員清單的物件，並在螢幕上顯示物件。 如果命令不成功，將會顯示適當的錯誤訊息。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

此命令會新增或移除小組成員。

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

此命令會將小組清單設定為特定成員。

## <a name="more-information"></a>其他相關資訊

針對內部部署，此功能中引進的 Cmdlet 只能由下列群組的成員根據下列指定的存取層級來執行：

- CsAdministrator – 取得和設定所有 Cmdlet
- CsVoiceAdministrator - 取得和設定所有 Cmdlet
- CsHelpDesk - 取得所有 Cmdlet

如需這些系統管理員角色的詳細資訊，請參[閱建立商務用 Skype Server 主控台系統管理員。](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md) 系統管理員可以直接或從遠端登入伺服器電腦來存取這些 Cmdlet。
針對混合式部署，商務用 Skype系統管理員應該能夠針對所有 Cmdlet 呼叫 Get 和 Set。 如需有關角色完整清單的詳細資訊，請參閱 [關於系統管理員角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> 必須啟用伺服器自動探索。 不會針對 Cmdlet 的使用引入其他授權需求。
