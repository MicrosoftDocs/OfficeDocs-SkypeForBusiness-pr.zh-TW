---
title: Microsoft 團隊 PowerShell 概覽
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft 團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814362"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft 團隊 PowerShell 概覽

Microsoft 團隊 PowerShell 是一組用來從 PowerShell 命令列直接管理團隊的 Cmdlet。 在 .NET 標準版中，小組 PowerShell 在 Windows 上的 PowerShell 5.1 上運作，在所有平臺上（包括 Azure Shell）都可以使用。

您必須先 [安裝它](teams-powershell-install.md)，才能開始使用 PowerShell。 

> [!WARNING]
> PowerShell 7 和團隊 PowerShell 存在已知問題。 我們建議您使用 PowerShell 5.1，直到問題解決為止。

## <a name="releases"></a>鬆開


您可以在兩種版本類型中的 [PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams) 上使用團隊 PowerShell。

- **正式供貨 (GA) **：生產已就緒的 Cmdlet，每月更新。

- **公用預覽**：提前存取功能。 更新頻率可能比 GA 更新。

如需這兩個版本之功能新增和改良的詳細資訊，請閱讀 [團隊 PowerShell 版本](teams-powershell-release-notes.md)資訊。


## <a name="manage-teams-with-powershell"></a>使用 PowerShell 管理團隊

您將使用團隊 PowerShell 模組來全面管理團隊：

- [Microsoft 團隊 powershell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)：團隊 powershell 模組包含管理團隊、聊天和頻道的 Cmdlet。

> [!NOTE]
> 最新的 [團隊 powershell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/) 與商務用 Skype Online 連接器整合，提供單一模組供團隊 PowerShell 管理使用。

- [商務用 Skype Powershell 連接器](https://www.microsoft.com/download/details.aspx?id=39366)：商務用 skype powershell 連接器現已成為團隊 PowerShell 模組的一部分。

如需使用這些模組管理團隊的完整指南，請參閱使用 [團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)。


## <a name="related-topics"></a>相關主題

[安裝團隊 PowerShell](teams-powershell-install.md)

[使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)

[團隊 PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)
