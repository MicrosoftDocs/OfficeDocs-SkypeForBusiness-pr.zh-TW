---
title: 使用 Microsoft Teams PowerShell 管理 Teams
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
description: 瞭解如何使用 Teams PowerShell 管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4200c23f6320e67781353e62363d588c230fceb7
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756152"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 Microsoft Teams PowerShell 管理 Teams

本文將說明如何使用 Microsoft Teams PowerShell 來管理 Teams 和商務用 Skype。 

請結合 Microsoft Teams [Cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 參考和商務 [用 Skype Cmdlet 參考，使用本指引](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 建立及管理團隊

用於建立及管理團隊的 Cmdlet 在 [Microsoft Teams PowerShell 模組中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。

Teams 由 Office 365 群組支援，因此當您建立團隊時，會建立群組。 提供一組 Cmdlet 以在核心團隊及其設定 (、) 、管理小組使用者 ``new-team`` ``get-team``  ``set-team`` (、) ，以及管理團隊 ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` (、) ``remove-teamchannel`` 頻道的 Cmdlet。 所有這些 Cmdlet 都可以以使用者方式執行，但只能在您擁有或為成員的團隊中執行。 如果您是全域系統管理員或 Teams 服務系統管理員，您可以在貴組織的所有團隊上採取行動。

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Microsoft Teams PowerShell 模組 Cmdlet 中使用的 **GroupId** 與Exchange PowerShell 模組中所返回的 ``Get-UnifiedGroup`` 身分識別屬性相同。

## <a name="manage-policies-via-powershell"></a>透過 PowerShell 管理原則

> [!NOTE]
> - 商務用 Skype Online Connector 正在整合到 Teams PowerShell 中。 目前可在公開預覽版中使用。 一段時間之後，適用于 Teams 的商務用 Skype Online Cmdlet 將會原生地在 Teams PowerShell 模組中提供。 安裝步驟可在安裝 [Teams PowerShell](teams-powershell-install.md) 一文中提供。
>
> - 一旦連線到商務用 Skype Online，Cmdlet 就會在 PowerShell 會話中使用。 如需詳細資訊，請參閱使用 [Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)管理商務用 Skype Online。

在商務用 Skype Cmdlet 模組中尋找管理原則[的 Cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

原則是一組可細微地適用于個別使用者的設定。 每一個策略類型都有一組自己的 Cmdlet，用於建立、檢視、刪除和更新該政策本身，然後將那些策略指派給使用者。 一般結構為：

- **GET** 命令 (例如) ：會返回可供您指派在貴組織中使用之政策檔，包括 Microsoft 建立供您使用以及您建立之自訂政策。 ``Get-CsTeamsMeetingPolicy``
   - 若要只尋找您建立于貴組織的自訂策略，請使用 ``-Filter "tag:*"`` 。

- **新的** (例如) ：為貴組織建立新策略以指派 ``New-CsTeamsMeetingPolicy`` 給貴組織的使用者。 並非所有策略都支援建立自訂策略。 這通常是為了確保您組織使用的策略具有支援的設定組合。

- **SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy``) ：設定特定策略的特定值。 某些策略沒有可用的 SET 命令，或包含無法自訂于該策略的參數。 PowerShell 描述會告訴您哪些參數無法自訂。 
   - 若要編輯預設會指派給貴組織中未指派自訂策略的使用者之策略，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **REMOVE** 命令 (例如) ：刪除已在租使用者 ``Remove-CsTeamsMeetingPolicy`` 中建立自訂策略。 如果您刪除已指派給貴組織中至少一位使用者的自訂策略，該使用者會回到全域原則。
   - 您實際上無法移除貴組織的全域原則，但如果您想要將貴組織的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT** 命令 (例如 ``Grant-CsTeamsMeetingPolicy`` ，) ：指派一個策略給特定使用者。
   - 若要移除自訂策略指派，並讓使用者回到貴組織的預設策略，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 並非所有策略都允許建立自訂策略，而有些策略有無法自訂 (因此您可以在設定期間和期間設定自訂 ``set-`` ``new-`` 值) 。 每個 Cmdlet 的檔會說明客戶是否可以使用參數。

一般參數：

- **身分** 識別：對於 ``Get-`` ``Set-`` ``New-`` 、、和 ``Remove-`` **，Identity** 參數一定會參照特定的策略實例。 針對 ``Grant`` ， **身分識別** 參數是指要將原則所針對的特定使用者物件。

## <a name="manage-configurations-via-powershell"></a>透過 PowerShell 管理組式

在商務用 Skype Cmdlet 模組中尋找管理您配置的[Cmdlet。](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

設定是服務中維護的設定，無法以使用者層級指定。 設定一直適用于整個組織。 您的通用群組配置是貴組織中唯一有效的組配置。 每個組式類型都隨附兩個主要 Cmdlet：

- ``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：

- SET 命令 (例如 ``Set-CsTeamsClientConfiguration``) ：設定該類型的屬性。 指定要修改的參數。
   > 您可以用兩種方式之一來參照要修改的組式：指定 - 身分識別 **全域**，或是按程式。 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``

## <a name="what-can-each-admin-role-do"></a>每個系統管理員角色可以做什麼？

請閱讀 [使用 Microsoft Teams 系統管理員角色來管理 Teams，](using-admin-roles.md) 以瞭解哪些系統管理員角色可以執行每個 PowerShell Cmdlet。

## <a name="related-topics"></a>相關主題

[安裝 Teams PowerShell](teams-powershell-install.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Teams Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Teams 系統管理員角色來管理 Teams](using-admin-roles.md)
