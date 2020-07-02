---
title: 使用 Microsoft 團隊 PowerShell 管理團隊
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
description: 瞭解如何使用團隊 PowerShell 管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944100"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>使用 Microsoft 團隊 PowerShell 管理團隊

本文說明如何使用 Microsoft 團隊 PowerShell 來管理團隊及商務用 Skype。 

請將本指南與[Microsoft 團隊 Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)及商務用[Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)搭配使用。

## <a name="create-and-manage-teams-using-powershell"></a>使用 PowerShell 建立及管理團隊

建立及管理團隊的 Cmdlet 位於[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。

團隊是由 Office 365 群組支援，因此當您建立小組時，就會建立群組。 提供一組 Cmdlet 來在核心團隊及其設定（ ``new-team`` 、 ``get-team`` 、 ``set-team`` ）、管理團隊使用者（、），以及 ``add-teamuser`` ``remove-teamuser`` 管理團隊通道（ ``new-teamchannel`` 、）的 Cmdlet ``remove-teamchannel`` 中進行操作。 所有這些 Cmdlet 都可以以使用者身分執行，但它們只能在您擁有或隸屬于您擁有的小組中運作。 如果您是全域系統管理員或團隊服務系統管理員，您就可以在組織中的所有團隊進行動作。

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Microsoft 團隊 PowerShell 模組 Cmdlet 中使用的**GroupId**與 Exchange PowerShell 模組中傳回的身分**識別**屬性相同 ``Get-UnifiedGroup`` 。

## <a name="manage-policies-via-powershell"></a>透過 PowerShell 管理原則

> [!NOTE]
> - 商務用 Skype Online 連接器會整合成團隊 PowerShell。 它目前可在公用預覽中取得。 在時間裡，適用于團隊的商務用 Skype Online Cmdlet 會在團隊 PowerShell 模組中自行提供。 您可以在[安裝團隊 PowerShell](teams-powershell-install.md)文章中取得安裝步驟。
>
> - 在您連線到商務用 Skype Online 之後，您的 PowerShell 會話中就會提供 Cmdlet。 如需詳細資訊，請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

在[商務用 Skype Cmdlet 模組](https://www.microsoft.com/download/details.aspx?id=39366)中尋找管理原則的 Cmdlet。

原則是一組設定，可將它們精確套用至個別使用者。 每個原則類型都有自己的一組 Cmdlet，可用於建立、查看、刪除及更新原則，然後將這些原則指派給使用者。 一般結構如下：

- **取得**命令（例如， ``Get-CsTeamsMeetingPolicy`` ）：傳回您在組織中可指派的原則檔，包括由 Microsoft 建立的原則，以及您所建立的自訂原則。
   - 若只要尋找您在組織中建立的自訂原則，請使用 ``-Filter "tag:*"`` 。

- **新**命令（例如 ``New-CsTeamsMeetingPolicy`` ）：為貴組織建立新的原則，以指派給貴組織中的使用者。 並非所有原則都支援建立自訂原則。 通常，這是為了確保您在組織中使用的原則具有受支援的設定組合。

- **SET**命令（例如 ``Set-CsTeamsMeetingPolicy`` ）：設定指定原則上的特定值。 有些原則沒有可用的 SET 命令，或它們包含無法在原則中自訂的參數。 PowerShell 描述告訴您無法自訂哪些參數。 
   - 若要編輯預設將指派給貴組織中未指派自訂策略之使用者的原則，請執行 ``Set-Cs<PolicyName> -Identity Global`` 。

- **移除**命令（例如 ``Remove-CsTeamsMeetingPolicy`` ）：刪除已在您的租使用者中建立的自訂原則。 如果您刪除已指派給貴組織中至少一個使用者的自訂原則，該使用者會回到全域原則。
   - 您不能實際移除貴組織中的全域原則，但如果您想要將貴組織中的全域原則重設為 Microsoft 提供的預設設定，請執行 ``Remove-Cs<PolicyName> -Identity Global`` 。

- **GRANT**命令（例如 ``Grant-CsTeamsMeetingPolicy`` ）：指派原則給特定的使用者。
   - 若要移除自訂原則指派，並讓使用者回到貴組織中的預設原則，請執行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。

> [!TIP]
> 並非所有原則都允許建立自訂原則，而且有些原則擁有您無法自訂的設定（所以您可以在與期間中查看設定，但不能設定自訂值 ``set-`` ``new-`` ）。 每個 Cmdlet 的檔都要指出是否可供客戶使用參數。

一般參數：

- 身分**識別**：對於 ``Get-`` 、、 ``Set-`` ``New-`` 和 ``Remove-`` ，身分**識別**參數會永遠參照特定原則實例。 針對 ``Grant`` ，身分**識別**參數會參照要套用原則的特定使用者物件。

## <a name="manage-configurations-via-powershell"></a>透過 PowerShell 管理設定

在[商務用 Skype Cmdlet 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中尋找管理您的設定的 Cmdlet。

[配置] 是服務中維護的 [設定] 桶，不能在使用者層級指定。 設定總是在整個組織內套用。 您的全域設定是貴組織中的唯一有效配置。 每個配置類型都有兩個主要的 Cmdlet：

- ``Get-Cs<ConfigurationName>``（例如， ``Get-CsTeamsClientConfiguration`` ）：

- SET 命令（例如 ``Set-CsTeamsClientConfiguration`` ）：設定該類型的配置中的屬性。 指定您要修改的參數。
   > 您可以透過兩種方式的其中一種來參考您要修改的設定：指定**全域身分識別**，或執行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。

## <a name="what-can-each-admin-role-do"></a>每個管理員角色可以做什麼？

[閱讀][使用 Microsoft 團隊管理員角色來管理團隊](using-admin-roles.md)，以瞭解哪些管理員角色可以執行每個 PowerShell Cmdlet。

## <a name="related-topics"></a>相關主題

[安裝團隊 PowerShell](teams-powershell-install.md)

[團隊 PowerShell 版本資訊](teams-powershell-release-notes.md)

[團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Teams 系統管理員角色來管理 Teams](using-admin-roles.md)