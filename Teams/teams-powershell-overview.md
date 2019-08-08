---
title: 團隊 PowerShell 概覽
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20e85b2f45977a0a78d0d358c2e8aaa01b9257e4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235128"
---
# <a name="teams-powershell-overview"></a>團隊 PowerShell 概覽

Microsoft 團隊有一套豐富的工具, 可讓 IT 管理員透過 Microsoft 團隊系統管理中心、PowerShell 控制項及圖形 Api 來管理產品。 本指南說明我們如何組織我們的 PowerShell Cmdlet 供 IT 管理員使用, 並提供進一步說明文件的指標。 請注意, 不同的團隊管理員角色可以存取不同的 Cmdlet。 如需詳細資訊, 請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。

## <a name="which-modules-do-you-need-to-use"></a>您需要使用哪些模組？

管理團隊的 PowerShell 控制項位於兩個不同的 PowerShell 模組中: 
- [Microsoft 團隊 powershell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/): [團隊 powershell] 模組包含您建立及管理團隊所需的所有 Cmdlet。  
- [商務用 Skype powershell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366): 商務用 skype powershell 模組包含管理原則、設定及其他團隊工具的 Cmdlet。 

PowerShell 控制項的參考檔將會告知您要調查的 Cmdlet 所在的模組。 (最終會結合兩個模組)。

## <a name="what-can-each-admin-role-do"></a>每個管理員角色可以做什麼？

已閱讀 [[使用 Microsoft 團隊管理員角色] 管理團隊](using-admin-roles.md), 瞭解不同管理員角色可以利用哪些 PowerShell Cmdlet。

## <a name="creating-and-managing-teams-via-powershell"></a>透過 PowerShell 建立及管理團隊

建立及管理團隊的 Cmdlet 位於[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。 

受 O365 群組支援小組, 所以當您建立小組時, 就會建立群組。 提供一組 Cmdlet 來在核心團隊及其設定 (``new-team``、 ``get-team``、 ``set-team``)、管理團隊使用者 (``add-teamuser``、 ``remove-teamuser``), 以及管理團隊通道 (``new-teamchannel``、 ``remove-teamchannel``) 的 Cmdlet 中進行操作。 所有這些 Cmdlet 都可以以使用者身分執行, 但它們只能在您擁有或隸屬于您擁有的小組中運作。 如果您是全域系統管理員或團隊服務系統管理員, 您就可以在組織中的所有團隊進行動作。

> Microsoft 團隊 PowerShell 模組 Cmdlet 中使用的**GroupId**與 Exchange PowerShell 模組``Get-UnifiedGroup``中傳回的身分**識別**屬性相同。

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>預覽與一般可用的 Microsoft 團隊 PowerShell 模組間的差異

當我們發佈我們的通用版本的 PowerShell 模組時, 只有在 Beta 版模組中留下了幾個 Cmdlet, 如下表所述。

| Cmdlet | 可在預覽中使用 | 在1.0 中提供 |
|------- | -------------------- | ------------------------------ |
| 附加 TeamUser | 是的 | 是的 |
| 連接-MicrosoftTeams | 是的 | 是的 |
| 中斷連線-MicrosoftTeams | 是的 | 是的 |
| 取得團隊 | 是的 | 是的 |
| TeamChannel | 是的 | 是的 |
| TeamFunSettings | 僅限1.0 發行之前 | 不 |
| TeamGuestSettings | 僅限1.0 發行之前 | 不 |
| TeamHelp | 是的 | 是的 |
| TeamMemberSettings | 僅限1.0 發行之前 | 不 |
| TeamMessagingSettings | 僅限1.0 發行之前 | 不 |
| TeamUser | 是的 | 是的 |
| 新團隊 | 是的 | 是的 |
| 新-TeamChannel | 是的 | 是的 |
| 移除團隊 | 是的 | 是的 |
| 移除-TeamChannel | 是的 | 是的 |
| 移除-TeamUser | 是的 | 是的 |
| 集-小組 | 是的 | 是的 |
| Set-TeamChannel | 是的 | 是的 |
| Set-TeamFunSettings | 僅限1.0 發行之前 | 不 |
| Set-TeamGuestSettings | 僅限1.0 發行之前 | 不 |
| Set-TeamMemberSettings | 僅限1.0 發行之前 | 不 |
| Set-TeamMessagingSettings | 僅限1.0 發行之前 | 不 |
| Set-TeamPicture | 是的 | 否, 規劃 |


## <a name="managing-policies-via-powershell"></a>透過 PowerShell 管理原則

管理原則的 Cmdlet 位於[商務用 Skype Cmdlet 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。

原則是一組設定, 可將它們精確套用至個別使用者。 每個原則類型都有自己的一組 Cmdlet, 可用於建立、查看、刪除及更新原則, 然後將這些原則指派給使用者。 一般結構如下:

- 取得命令 (例如, ``Get-CsTeamsMeetingPolicy``): 傳回您在組織中可指派的原則檔、由 Microsoft 所建立的原則, 以及您建立的自訂原則。
   > 如果您只想尋找您在組織中建立的自訂原則, 您可以使用``-Filter "tag:*"``。

- 新命令 (例如``New-CsTeamsMeetingPolicy``): 讓您為貴組織建立新的原則, 然後將其指派給您組織中的使用者。 並非所有原則都支援建立自訂原則。 通常, 這是為了確保您在組織中使用的原則具有受支援的設定組合。

- SET 命令 (例如``Set-CsTeamsMeetingPolicy``): 可讓您在指定原則上設定特定值。 有些原則沒有 set 命令可用, 或包含無法在原則中自訂的參數。 每個 PowerShell 描述將會找出哪些參數無法自訂。 
   > 若要編輯預設將指派給貴組織中未指派自訂策略之使用者的原則, 請執行``Set-Cs<PolicyName> -Identity Global``。

- 移除命令 (例如``Remove-CsTeamsMeetingPolicy``): 您可以使用此 Cmdlet 來刪除已在您的租使用者中建立的自訂原則。 如果您刪除已指派給貴組織中至少一個使用者的自訂原則, 該使用者會回到全域原則。
   > 您不能實際移除貴組織中的全域原則, 但如果您想要將貴組織中的全域原則重設為 Microsoft 提供的預設設定, 您``Remove-Cs<PolicyName> -Identity Global``可以執行。

- GRANT 命令 (例如``Grant-CsTeamsMeetingPolicy``): 可讓您將原則指派給特定的使用者。
   > 若要移除自訂原則指派, 並讓使用者回到貴組織中的預設原則, 請執行``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。

> [!TIP]
> 並非所有原則都允許建立自訂原則, 而且有些原則擁有您無法自訂的設定 (所以您可以在與``set-`` ``new-``期間中查看設定, 但不能設定自訂值)。 如果客戶不能使用參數, 則特定 Cmdlet 的檔將會撥出。

一般參數:

- **身分識別**: ``Get-``對於``Set-``、 ``New-``、和``Remove-``, 身分**識別**參數會永遠參照特定原則實例。 針對``Grant``, 身分**識別**參數會參照要套用原則的特定使用者物件。

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>透過 PowerShell 管理設定

管理您的設定的 Cmdlet 位於商務用[Skype Cmdlet 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。

[配置] 是服務中維護的 [設定] 桶, 不能在使用者層級指定。 設定總是在整個組織內套用。 您的全域設定是貴組織中的唯一有效配置。 每個配置類型都有兩個主要的 Cmdlet:

- ``Get-Cs<ConfigurationName>``(例如, ``Get-CsTeamsClientConfiguration``): 

- SET 命令 (例如``Set-CsTeamsClientConfiguration``): 設定該類型的配置中的屬性。 指定您要修改的參數。
   > 您可以透過兩種方式的其中一種來參考您要修改的設定:**指定全域身分識別**, 或``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``執行。

## <a name="other-powershell-tools"></a>其他 PowerShell 工具

您可以在[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和 Skype 中找到如何使用所有 PowerShell 控制項來管理 Microsoft 團隊和商務用 skype 的詳細指示, 包括每個原則中設定的詳細描述。 [商務 Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="learn-more"></a>瞭解更多資訊

- [Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)
