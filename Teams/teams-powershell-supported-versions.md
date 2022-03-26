---
title: Teams PowerShell 模組 - 支援的版本
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解 PowerShell 模組支援Teams，用於管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fc980420b53d850c48e680d25bdbf6ec437e8f8
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783963"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模組 - 支援的版本

Microsoft Teams 4.x.x (系列或更新版本中) 的 PowerShell 模組是未來支援的唯一版本。 所有較舊版本都位於停用路徑上。 建議您將 PowerShell 模組Teams更新至最新版本。



## <a name="new-organizations"></a>新組織

從 2022 年 4 月 1 Teams起，新上Teams的組織只能使用 4.x.x 系列或以上的 Teams PowerShell 模組。



## <a name="current-organizations-non-tpm-active"></a>目前組織 (TPM 作用中) 

自 2022 年 4 月 1 日起，過去三個月 (年 1 月 22 日 -3 月 22 日) 尚未使用 Teams PowerShell 模組的組織，只能使用 4.x.x.x 系列或以上的 Teams PowerShell 模組。



## <a name="current-organizations-tpm-active"></a>目前使用 TPM (的組織) 

過去三個月使用 Teams PowerShell 模組的組織 (年 1 月 22 日 -) 年 3 月 22 日，從 2022 年 6 月 15 日起，將只能使用 4.x.x 系列或以上的 Teams PowerShell 模組。 



## <a name="important-notes"></a>重要記事

- 您可以在 PowerShell 版本資訊Teams [PowerShell](teams-powershell-release-notes.md)模組版本的所有版本Teams說明。

- 若要更新任何 PowerShell 模組，您應該使用與安裝模組相同的方法。 例如，如果您原本是使用 Install-Module，您應該使用 [Update-Module](/powershell/module/powershellget/update-module) 取得最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果從 PowerShell 模組Teams版本 1.1.6 更新，請更新腳本以使用 `Connect-MicrosoftTeams` ，而不是 `New-CsOnlineSession` 。

-   在更新期間，建議您不要將 TPM 4.x.x/3.x.x.x 與 3.0.0 版本一起使用。 例如，不建議將版本 4.x.x & 2.6.0 一起用於同一組織的不同系統管理員作業。 

- 相關變更
  * TPM 3.x.x Get-CsOnlineUser & Get-CsOnlineVoiceUser 更新更新 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser)  &  (訊息中心文章 - MC340774) 。[ ](/powershell/module/skype/get-csonlinevoiceuser)

  * 電話 號碼指派即將變更 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance)  &  (訊息中心文章 – MC316139 文章的更多詳細資料) [ ](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>相關主題

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[在 PowerShell Microsoft Teams安裝](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/module/teams) 

[商務用 Skype Cmdlet 參照](/powershell/module/skype) 
