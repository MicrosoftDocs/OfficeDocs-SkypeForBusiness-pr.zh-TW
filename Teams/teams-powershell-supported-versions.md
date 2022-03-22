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
ms.openlocfilehash: 9254afde824f072f6015531b90f4cacfb38acafe
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2022
ms.locfileid: "63689083"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 模組 - 支援的版本

Microsoft Teams PowerShell 模組 (4.x.x) 系列中的 TPM 模組版本將是唯一支援的版本。 所有較舊版本都位於停用路徑上。



## <a name="new-organizations"></a>新組織

從 2022 年 4 月 1 Teams起，新上Teams的組織只能使用 Teams PowerShell 模組 4.0.0 或以上。



## <a name="current-organizations-non-tpm-active"></a>目前組織 (TPM 作用中) 

過去三個月沒有使用 TPM 的組織 (年 1 月 22 日 -) 年 3 月 22 日，從 2022 年 4 月 1 日起，只能使用 TPM 4.0.0 或更新版。



## <a name="current-organizations-tpm-active"></a>目前使用 TPM (的組織) 

過去三個月使用 TPM 的組織 (年 1 月 22 日 - 3 月 22 日) 將有更多的時間更新至 TPM 4.x.x。 近期要追蹤的更多詳細資料。



## <a name="important-notes"></a>重要記事

- 您可以在 PowerShell 版本資訊Teams [PowerShell](teams-powershell-release-notes.md)模組版本的所有版本Teams說明。

- 若要更新任何 PowerShell 模組，您應該使用與安裝模組相同的方法。 例如，如果您原本是使用 Install-Module，您應該使用 [Update-Module](/powershell/module/powershellget/update-module) 取得最新版本。  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   如果從 PowerShell 模組Teams版本 1.1.6 更新，請更新腳本以使用 `Connect-MicrosoftTeams` ，而不是 `New-CsOnlineSession` 。

-   在更新期間，建議您不要將 TPM 4.x.x/3.x.x.x 與 3.0.0 版本一起使用。 例如，不建議將版本 4.0.0 & 2.6.0 一起用於同一組織的不同系統管理員作業。 

- 相關變更
  * TPM 3.0.0 及更新中的 Get-CsOnlineUser & Get-CsOnlineVoiceUser 更新 – [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) [](/powershell/module/skype/get-csonlineuser)  &  (訊息中心文章 – MC340774) 。

  * 電話 號碼指派即將變更 - [Set-CsUser](/powershell/module/skype/set-csuser)、[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)、[Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance)  &  (訊息中心文章 – MC316139 文章的更多詳細資料) [ ](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>相關主題

[Teams PowerShell 版本資訊](teams-powershell-release-notes.md)

[在 PowerShell Microsoft Teams安裝](teams-powershell-install.md)

[使用 powerShell Teams管理Teams](teams-powershell-managing-teams.md)

[Microsoft Teams Cmdlet 參照](/powershell/module/teams) 

[商務用 Skype Cmdlet 參照](/powershell/module/skype) 
