---
title: 設定使用者的通話設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解如何設定來電轉接和委派的使用者設定。
ms.openlocfilehash: 64907043448f44ff861ede026d0a4343899ad98b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272228"
---
# <a name="configure-call-settings-for-your-users"></a>為您的使用者設定通話設定

本文說明系統管理員如何變更使用者的來電轉接和委派設定。 您可能會想要變更這些設定，例如：：

- 使用者已休假，您必須確保轉接給使用者的來電給同事。
- 您需要檢查部門中所有使用者的來電轉接設定，並視需要加以修正。
- 已雇用新的助理，您必須將助理新增為一組員工的代理人。

您可以使用 Teams 系統管理中心或 Teams PowerShell Cmdlet 來檢視及變更使用者的通話設定。

若要設定使用者的通話設定，使用者必須擁有指派的 Microsoft 電話系統授權。

## <a name="use-the-teams-admin-center"></a>使用 Teams 系統管理中心

您可以使用 Teams 系統管理中心為您的使用者設定來電轉接和未接聽的設定、群組通話接聽，以及通話委派。

若要設定立即來電轉接設定：

1. 在 Teams 系統管理中心，移至 [**使用者**  >  **管理使用者**] 並選取使用者。

2. 在 [使用者詳細資料] 頁面上，移至 [ **語音] 索引** 標籤。

3. 在 **[撥號接聽規則]** 底下，選取 [ **立即傳輸**]，然後選取適當的來電轉接類型和目的地。

若要設定同時響鈴，請在同一頁面上選 **取 [讓使用者的裝置響鈴]**。 在 [ **也允許** ] 下拉式清單中，選取適當的同時響鈴設定。

若要設定未回答的設定，請在同一頁的 **[如果未** 回答] 下拉式清單中選取適當的設定。 在 [ **響鈴] 中，在重新導向下拉式清單前多秒** ，指定要等待的秒數。

通話委派和群組通話接聽的設定會整合到來電轉接和未接聽的設定中，方法是選取適當的類型。 例如，若要設定通話也應撥打給使用者的代理人，請在同一頁面上選取 [也允許] 下的 [**通話委****派]**。 然後選取 [ **新增人員** ]，然後按一下 [儲存 **]**，以新增適當的代理人。

## <a name="use-powershell"></a>使用 PowerShell

您可以使用 PowerShell 為使用者設定來電轉接和委派設定。  您將使用下列 Cmdlet，可在 Teams PowerShell 模組 4.0 或更新版本中使用：

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) - 顯示使用者的來電轉接設定、代理人和委派資訊。
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) - 設定使用者的來電轉接設定。
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - 新增具有使用者許可權的新代理人。
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) - 變更現有代理人的許可權。
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) - 會從使用者中移除代理人。

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>顯示使用者的來電轉接和委派設定

若要顯示使用者目前的來電轉接和委派設定，請使用Get-CsUserCallingSettings Cmdlet，如下列範例所示：

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

輸出顯示使用者1 同時響鈴給已設定的代理人。 未接聽的通話會在 20 秒後傳送至語音信箱。 User2 定義為具有所有代理人許可權的代理人。

### <a name="set-call-forward-settings-for-a-user"></a>設定使用者的來電轉接設定

若要將 user1 的所有來電轉接至 user2，請使用 Set-CsUserCallingSettings Cmdlet，如下列範例所示：

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

若要同時為 user3 的所有代理人響鈴，請使用Set-CsUserCallingSettings Cmdlet，如下列範例所示：

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

下列範例使用Set-CsUserCallingSettings Cmdlet 來設定 user4 的通話群組，並以 user5 和 user6 為成員。 所有呼叫群組成員的呼叫都會以其定義順序轉接：

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

如需更多範例，請參閱 [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)。

### <a name="add-a-calling-delegate-for-a-user"></a>新增使用者的通話代理人

若要將 user2 新增為允許擁有權限的 user1 代理人，請使用New-CsUserCallingDelegate Cmdlet，如下列範例所示：

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>變更通話代理人許可權

若要變更代理人許可權，例如不允許 user2 撥打使用者電話1，請使用Set-CsUserCallingDelegate Cmdlet，如下列範例所示：

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>移除使用者的通話代理人

若要移除 user2 做為 user1 的代理人，請使用Remove-CsUserCallingDelegate Cmdlet，如下列範例所示：

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>相關主題

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
