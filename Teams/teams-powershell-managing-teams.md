---
title: 使用 powerShell Teams管理Microsoft Teams
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何使用 PowerShell Microsoft Teams管理Teams程式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238969"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 powerShell Teams管理Microsoft Teams

本文將說明如何使用 PowerShell Microsoft Teams管理Teams商務用 Skype。 

請結合[Cmdlet Microsoft Teams和 Cmdlet 參照](/powershell/teams/?view=teams-ps)商務用 Skype[本指南](/powershell/skype/intro?view=skype-ps)。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 建立及管理團隊

建立及管理團隊的 Cmdlet 會Microsoft Teams [PowerShell 模組中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。

Teams群組Office 365，因此當您建立團隊時，即會建立群組。 有一組 Cmdlet 提供在核心小組及其設定 (、) 、管理小組使用者 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` (、) ，以及管理團隊 (、) 頻道的 ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` Cmdlet。 所有這些 Cmdlet 都可以以使用者方式執行，但只能在您擁有或成員的團隊中執行。 如果您是全域系統管理員或Teams系統管理員，就可以對貴組織的所有團隊採取行動。

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> **PowerShell** 模組 Cmdlet Microsoft Teams中使用的 GroupId 與 PowerShell 模組中所Exchange的 ``Get-UnifiedGroup`` Identity 屬性相同。

## <a name="manage-policies-via-powershell"></a>透過 PowerShell 管理政策

> [!NOTE]
> - 商務用 Skype線上連接器正在合併到 powerShell Teams中。 目前可在公開預覽中使用。 一段時間之後，商務用 Skype PowerShell 模組中Teams內提供適用于 Teams Cmdlet。 安裝步驟可在[PowerShell](teams-powershell-install.md) Teams中提供。
>
> - 一旦連線到線上，Cmdlet 就會在 PowerShell 會話中商務用 Skype使用。 如需詳細資訊，請參閱使用[PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)商務用 Skype管理 Office 365 Online 。

在 Cmdlet 模組中尋找管理商務用 Skype[的 Cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

原則是一組可精細地適用于個別使用者的設定。 每個策略類型都有一組自己的 Cmdlet，用於建立、檢視、刪除和更新策略本身，然後將那些策略指派給使用者。 一般結構為：

- **GET** 命令 (例如) ：會返回可供您指派在貴組織中使用的政策檔，包括 Microsoft 建立供您使用的政策，以及您建立之自訂策略。 ``Get-CsTeamsMeetingPolicy``
   - 若要只尋找您于組織中建立自訂策略，請使用 ``-Filter "tag:*"`` 。

- **新的** (例如) ：為貴組織建立新策略，以指派 ``New-CsTeamsMeetingPolicy`` 給貴組織的使用者。 並非所有策略都支援建立自訂策略。 這通常是為了確保貴組織使用的政策具有支援的設定組合。

- **SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy`` ，) ：設定特定策略上的特定值。 有些策略沒有 SET 命令可用，或包含無法自訂于該策略的參數。 PowerShell 描述會告訴您哪些參數無法自訂。 
   - 若要編輯預設會指派給組織中未指派自訂策略的使用者的策略，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **移除** (命令，例如) ：刪除已在租使用者中建立 ``Remove-CsTeamsMeetingPolicy`` 自訂策略。 如果您刪除已指派給貴組織中至少一位使用者的自訂策略，該使用者會回到全域原則。
   - 您實際上無法移除貴組織的全域原則，但如果您想要將貴組織的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- **例如** ， (GRANT 命令 ``Grant-CsTeamsMeetingPolicy``) ：指派一個策略給特定使用者。
   - 若要移除自訂策略指派，讓使用者回到貴組織的預設策略，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 並非所有策略都允許建立自訂策略，而有些策略有無法自訂 (因此您可以查看設定，但無法設定自訂值 ``set-`` ``new-``) 。 每個 Cmdlet 的檔會指出客戶是否可以使用參數。

常用參數：

- **身分** 識別： ``Get-`` 針對 ``Set-`` 、 ``New-`` 和 ``Remove-`` **，Identity** 參數一定會參照特定的策略實例。 針對 ``Grant`` **，Identity** 參數會參照要採用原則的特定使用者物件。

## <a name="manage-configurations-via-powershell"></a>透過 PowerShell 管理配置

在 Cmdlet 模組中尋找管理您商務用 Skype [Cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

設定是服務中維護的設定容器，無法以使用者層級指定。 設定一直適用于整個組織。 您的通用群組組是貴組織中唯一有效的組組。 每個組式類型都隨附兩個主要 Cmdlet：

- ``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：

- SET 命令 (例如 ``Set-CsTeamsClientConfiguration`` ，) ：設定該類型設定中的屬性。 指定要修改的參數。
   > 您可以用以下兩種方式之一來參照要修改的組式：指定 -**身分識別全域**，或按 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="what-can-each-admin-role-do"></a>每個系統管理員角色可以做什麼？

請參閱[使用Microsoft Teams系統管理員角色來管理](using-admin-roles.md)Teams瞭解哪些系統管理員角色可以執行每個 PowerShell Cmdlet。

## <a name="related-topics"></a>相關主題

[安裝 powerShell Teams PowerShell](teams-powershell-install.md)

[TeamsPowerShell 版本資訊](teams-powershell-release-notes.md)

[Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)

[使用 Teams 系統管理員角色來管理 Teams](using-admin-roles.md)