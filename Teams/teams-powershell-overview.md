---
title: Microsoft Teams PowerShell 概觀
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
description: 瞭解如何使用 PowerShell 控制項來管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569019"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams PowerShell 概觀

Microsoft Teams PowerShell 是一組 Cmdlet，可直接從 PowerShell 命令列管理 Teams。 Teams PowerShell 以 .NET Standard 撰寫，可于 Windows 上的 PowerShell 5.1、PowerShell 6.x 及更新版本在所有平臺上運作，包括 Azure Cloud Shell。

您開始使用 PowerShell 之前，必須[安裝 PowerShell。](teams-powershell-install.md) 

> [!WARNING]
> PowerShell 7 和 Teams PowerShell 有已知問題。 建議您使用 PowerShell 5.1，直到問題解決為止。

## <a name="releases"></a>釋放


Teams PowerShell 在 [PowerShell 圖庫中提供](https://www.powershellgallery.com/packages/MicrosoftTeams) 兩種發行類型。

- **GA (可用性) ：** 生產就緒的 Cmdlet，每月更新。

- **公開預覽**：提早存取功能。 更新頻率可能會高於 GA。

有關兩個版本功能新增及改良功能的詳細資訊，請參閱 [Teams PowerShell 版本資訊](teams-powershell-release-notes.md)。


## <a name="manage-teams-with-powershell"></a>使用 PowerShell 管理 Teams

您將使用 Teams PowerShell 模組來完整管理 Teams：

- [Microsoft Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams/)：Teams PowerShell 模組包含管理團隊、聊天和頻道的 Cmdlet。

> [!NOTE]
> [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行版本 1.1.6 或更新版本已與商務用 Skype Online Connector 整合，提供 Teams PowerShell 管理的單一模組。

- [商務用 Skype PowerShell 連接器](https://www.microsoft.com/download/details.aspx?id=39366)：商務用 Skype PowerShell 連接器現在是 Teams PowerShell 模組的一部分。

如需使用這些模組管理 Teams 的完整指南，請參閱使用[Teams PowerShell 管理 Teams。](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>相關主題

[安裝 Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[使用 Microsoft Teams 系統管理員角色來管理 Teams](using-admin-roles.md)
