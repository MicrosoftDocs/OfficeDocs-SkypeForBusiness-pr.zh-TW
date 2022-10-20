---
title: Microsoft Teams 中的共用線條外觀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
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
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: 瞭解 Microsoft Teams 中的 [共用線條外觀] 功能。
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614095"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Microsoft Teams 中的共用線條外觀

共用線條外觀可讓使用者選擇代理人代表其接聽或處理通話。 如果使用者有定期處理使用者通話的系統管理助理，這項功能就很有説明。 在共用行外觀的情境中，主管是指授權代理人代表其撥打或接聽電話的人。 代理人可以代表委派者撥打或接聽電話。

> [!IMPORTANT]
> 此功能僅適用于 Teams 部署模式。 如需 Teams 部署模式的詳細資料，請參閱[瞭解 Microsoft Teams 和商務用 Skype共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要授權

主管和代理人都必須擁有具有 PSTN 連線 (通話方案、運算子連線或直接路由) 的電話系統授權。 共用行體驗是委派的一部分，並包含在 [電話系統] 中。 如需授權的詳細資訊，請參閱 [Microsoft Teams 服務說明](/office365/servicedescriptions/teams-service-description)。

## <a name="shared-line-appearance-feature-availability"></a>共用線條外觀功能可用性

下列應用程式和裝置目前支援共用線條外觀。

| 功能 | Teams 電腦版 | Teams Mac App | Teams Web App (Edge)  |Teams 行動裝置版 iOS/Android App | Teams IP 手機 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| 設定委派 | 是 | 是 | 是 | 否 | 是 |
| 代表另一個接聽來電 | 是 | 是 | 是 | 是 | 是 |
| 代表另一個電話號碼撥打 | 是 | 是 | 是 | 是 | 是 |
| 代表另一位 Teams 使用者撥打電話 | 是 | 是 | 是 | 是 | 是 |
| 查看共用行的代理人檢視 | 是 | 是 | 是 | 否 | 是 |
| 查看主管通話活動的代理人檢視 | 是 | 是 | 是 | 否 | 是 |
| 查看代理人的管理員檢視 | 是 | 是 | 是 | 否 | 是 |
| 代理人或主管可以按住或繼續 | 是 | 是 | 是 | 否 | 是 |

## <a name="limitations"></a>限制

主管最多可以新增 25 位代理人，而代理人最多可以有 25 位主管。 您可以在租使用者中建立的委派關聯數目沒有限制。 
 
如果委派者和代理人不在同一個地理位置，PSTN 提供者必須允許來電者識別碼從不同的地理位置顯示，才能進行委派的通話。 

不允許迴圈委派設定。 如果委派的使用者之間也有代理人，他們就只能查看其委派，而無法看到初始委派。

## <a name="enable-delegation-and-shared-line-appearance"></a>啟用委派和共用行的外觀

您可以使用 **TeamsCallingPolicy AllowDelegation** 設定來啟用委派。 您可以使用 Teams 系統管理中心或 Teamsms PowerShell。 

啟用時，使用者可以直接在 Teams 中設定其委派關係。 

> [!IMPORTANT]
> 當您關閉使用者的委派時，您也需要在 Teams 系統管理中心為該使用者清理委派關係，以避免錯誤的通話路由。

## <a name="use-teams-admin-center"></a>使用 Teams 系統管理中心

若要使用 Teams 系統管理中心設定委派和共用行外觀，請參閱 [為您的使用者設定通話設定](/MicrosoftTeams/user-call-settings)。

## <a name="use-powershell"></a>使用 PowerShell

若要使用 Teams PowerShell 設定委派和共用線條外觀，請使用下列 Cmdlet：

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>範例

在下列範例中，user2@contoso.com 新增為 user1@contoso.com 代理人，並有權代表 user1 撥打和接聽電話，以及變更其他代理人的設定：

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

在下一個範例中，不允許代理 user2@contoso.com 代表 user 撥打電話1：

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

在下一個範例中，會以 user1@contoso.com 代理人的身分移除 user2@contoso.com：

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>詳細資訊

[與代理人共用電話線](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Teams 通話原則](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
