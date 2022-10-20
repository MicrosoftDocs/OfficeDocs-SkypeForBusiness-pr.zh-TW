---
title: 通話共用和群組來電接聽
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Microsoft Teams 中的通話共用和群組通話接聽功能可讓使用者與同事共用來電，以便在使用者無法使用時擷取來電。
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613845"
---
# <a name="call-sharing-and-group-call-pickup"></a>通話共用和群組來電接聽

Microsoft Teams 的通話共用和群組通話接聽功能可讓使用者與同事共用來電，讓同事可以接聽使用者無法接聽的電話。

與其他形式的通話共用相比，接聽群組通話對收件者干擾較少，因為使用者可以設定接收共用來電通知的方式，並決定是否要接聽。 通話群組成員收到來電通知的順序可以指定為同時或順序，以 (5 位或少於 5 個成員) 。

> [!IMPORTANT]
> 使用者、通話群組擁有者及通話群組的成員必須處於 Teams 的部署模式。 如需 Teams 部署模式的詳細資料，請參閱[瞭解 Microsoft Teams 和商務用 Skype共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="license-required"></a>需要授權

使用者必須獲指派Microsoft Teams 電話系統授權，才能設定並使用通話共用和群組通話接聽。 如需授權模型的其他詳細資料，請參閱 [電話系統提供以下](/MicrosoftTeams/here-s-what-you-get-with-phone-system)專案。

## <a name="limitations"></a>限制

使用者只能是一個通話群組的擁有者。 每個設定的通話群組最多可以有 25 個使用者或 32，768 個字元。 使用者可以是最多 25 個通話群組的成員。

請注意，行動裝置只有在設定為橫幅和鈴聲時才會收到通知。

## <a name="enable-the-use-of-group-call-pickup"></a>啟用使用群組通話取貨

您可以為使用者設定 **TeamsCallingPolicy AllowCallGroups** 設定，以啟用通話群組。 您可以使用 Teams 系統管理中心或 PowerShell。 啟用時，使用者可以在 Teams 用戶端中設定他們的通話群組。 

重要：當您關閉使用者的通話群組時，您必須在 Teams 系統管理中心為使用者清理通話群組關係，以避免錯誤的來電路由。 

## <a name="use-teams-admin-center"></a>使用 Teams 系統管理中心

若要使用 Teams 系統管理中心為使用者設定群組通話接聽，請參閱 [為您的使用者設定通話設定](/MicrosoftTeams/user-call-settings)。

## <a name="use-powershell"></a>使用 PowerShell

若要為使用者設定通話群組，請使用下列 Teams PowerShell 模組 Cmdlet：

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>範例

下列範例會為 user1@contoso.com 成員建立 user2@contoso.com 和 user3@contoso.com 的通話群組，並將立即來電轉接設定為 user1@contoso.com：

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

下一個範例示範如何更新 user1@contoso.com 的通話群組以新增 user5@contoso.com，以及移除 user6@contoso.com：

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>詳細資訊

[Teams 中的來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Teams 通話原則](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
