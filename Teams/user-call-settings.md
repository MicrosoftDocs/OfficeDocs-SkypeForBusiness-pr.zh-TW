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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: 瞭解如何設定呼叫轉轉和委派的使用者設定。
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689079"
---
# <a name="configure-call-settings-for-your-users"></a>為使用者設定通話設定

本文將說明系統管理員如何變更使用者的呼叫轉呼叫和委派設定。 您可能會想要變更這些設定，例如：：

- 使用者休假休假，您必須確保將來電轉給同事。

- 您需要檢查部門中所有使用者的呼叫前轉設定，並視需要加以修正。

- 已雇用新的助理，您必須將助理新增為一組員工的代理人。

您可以使用系統管理Teams或 powerShell Teams，來查看及變更使用者的通話設定。

若要設定使用者的通話設定，使用者必須擁有系統授權Microsoft 電話授權。

## <a name="use-the-teams-admin-center"></a>使用 Teams系統管理中心

您可以使用系統管理Teams，為使用者設定群組呼叫代答和通話委派。 

> [!NOTE]
> 系統管理中心目前無法提供設定呼叫轉Teams選項。

若要設定群組呼叫代答：

1. 在 Teams系統管理中心，前往 **UserManage**   >  使用者，然後選取使用者。

2. 在使用者詳細資料頁面上，前往語音 **標籤** 。

3. 在 **群組呼叫代答** 下，選取新增 **人員**。 

4. 指定通話延遲 **和訂單的設定**。

若要設定委派，請在同一頁上前往呼叫 **委派** ，然後選取新增 **人員**。

## <a name="use-powershell"></a>使用 PowerShell

您可以讓 PowerShell 為使用者設定呼叫前轉和委派設定。  您將使用下列 Cmdlet，Teams PowerShell 模組版本 4.0 或更新版本提供：

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - 顯示使用者的呼叫轉派設定、代理人和委派程式資訊。

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - 設定使用者的呼叫轉轉設定。

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - 新增具有使用者許可權的新代理人。

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - 變更現有代理人的許可權。

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - 從使用者移除代理人。


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>顯示使用者的呼叫前轉和委派設定

若要顯示使用者的目前呼叫轉寄和委派設定，請使用 Get-CsUserCallingSettings Cmdlet，如下列範例所示：

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
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

輸出顯示使用者 1 已同時響鈴給已配置的代理人。 未接聽的通話在 20 秒後會送到語音信箱。 User2 定義為具有所有代理人許可權的代理人。


### <a name="set-call-forward-settings-for-a-user"></a>設定使用者的呼叫前轉設定

若要將使用者 1 的所有通話轉寄到 user2，請使用 Set-CsUserCallingSettings Cmdlet，如下列範例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

若要同時響鈴使用者 3 的所有代理人，請使用 Set-CsUserCallingSettings Cmdlet，如下列範例所示： 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

下列範例使用 Set-CsUserCallingSettings Cmdlet 來設定使用者 4 的通話群組，使用者5 和 user6 為成員。 所有對群組成員的通話會按照定義的順序轉出： 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

有關更多範例，請參閱 [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps)。

### <a name="add-a-calling-delegate-for-a-user"></a>新增使用者的通話代理人

若要將 user2 新增為使用者 1 的代理人，並擁有擁有權限，請使用 New-CsUserCallingDelegate Cmdlet，如下列範例所示： 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>變更通話代理人許可權

若要變更代理人許可權 ，例如不允許使用者 2 撥打使用者電話1，請使用 Set-CsUserCallingDelegate Cmdlet，如下列範例所示： 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>移除使用者的通話代理人

若要將 user2 移除為使用者 1 的代理人，請使用 Remove-CsUserCallingDelegate Cmdlet，如下列範例所示： 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>相關主題

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
