---
title: Microsoft TeamsPowerShell 概觀
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
description: 瞭解如何使用 PowerShell 控制項來管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768352"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft TeamsPowerShell 概觀

Microsoft TeamsPowerShell 是一組 Cmdlet，Teams直接從 PowerShell 命令列管理資料。 PowerShell 以 .NET Standard 撰寫Teams PowerShell 5.1 適用于 Windows、PowerShell 6.x 及更高版本的所有平臺，包括 Azure Cloud Shell。

開始使用 PowerShell 之前，您必須 [安裝它](teams-powershell-install.md)。 

> [!WARNING]
> PowerShell 7 和 PowerShell Teams已知問題。 我們建議您使用 PowerShell 5.1，直到問題解決為止。

## <a name="releases"></a>釋放


TeamsPowerShell 可在[PowerShell 圖庫中提供](https://www.powershellgallery.com/packages/MicrosoftTeams)兩種發行類型。

- **一般 (GA)**： 生產就緒的 Cmdlet，每月更新一次。

- **公用預覽**：提早存取功能。 更新頻率可能會高於 GA。

有關兩個發行版本功能新增[及改良功能的詳細資訊](teams-powershell-release-notes.md)，請參閱 powerShell Teams說明。


## <a name="manage-teams-with-powershell"></a>使用 powerShell Teams管理

您將使用 PowerShell 模組Teams完全管理Teams：

- [Microsoft Teams PowerShell 模組：PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)模組Teams包含用於管理團隊、聊天和頻道的 Cmdlet。

> [!NOTE]
> PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本 2.0 或更新版本包含所有 商務用 Skype Online Connector Cmdlet，提供單一模組Teams PowerShell 管理。

- [商務用 Skype PowerShell 連接器](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)：商務用 Skype PowerShell 連接器現在是 PowerShell 模組Teams的一部分。

如需使用這些模組管理Teams的完整指南，請參閱使用[PowerShell](teams-powershell-managing-teams.md)Teams管理Teams程式。


## <a name="related-topics"></a>相關主題

[安裝 powerShell Teams PowerShell](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[TeamsPowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet 參照](/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參照](/powershell/skype/intro?view=skype-ps)

[使用Microsoft Teams系統管理員角色來管理Teams](using-admin-roles.md)
