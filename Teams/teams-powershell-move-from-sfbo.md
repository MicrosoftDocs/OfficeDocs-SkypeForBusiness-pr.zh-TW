---
title: 從商務用 Skype Online 連接器移至團隊 PowerShell 模組
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解如何從商務用 Skype Online 連接器移至團隊 PowerShell 模組以管理團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469662"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>從商務用 Skype Online 連接器移至團隊 PowerShell 模組

若要從使用商務用 Skype Online 連接器移至團隊 PowerShell 模組以管理團隊，您必須更新現有的 PowerShell 腳本。 本文說明如何執行此動作。

1. 安裝最新的團隊 PowerShell 模組。 如需步驟，請參閱 [安裝 Microsoft 團隊 Powershell](teams-powershell-install.md)。
2. 卸載商務用 Skype Online 連接器。 若要這樣做，請在 [控制台] 中，移至 [ **程式和功能**]，選取 [ **商務用 Skype Online]、[Windows PowerShell 模組**]，然後選取 [ **卸載**]。 
3. 在您的 PowerShell 腳本中，變更 [ ```Import-Module``` 寄件者] 或 [至] 中所參照的模組名稱 ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 。

    例如，[變更 ```Import-Module -Name SkypeOnlineConnector``` 為] ```Import-Module -Name MicrosoftTeams``` 。

> [!NOTE]
> 系統管理員應該在使用商務用 Skype Online Cmdlet 之前，繼續使用 [新的 CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) ，並匯入會話。 

## <a name="related-topics"></a>相關主題

[安裝 Microsoft 團隊 Powershell](teams-powershell-install.md)

[使用團隊 PowerShell 管理團隊](teams-powershell-managing-teams.md)

[團隊 PowerShell 版本資訊](teams-powershell-release-notes.md)

[Microsoft 團隊 Cmdlet 參考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[商務用 Skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
