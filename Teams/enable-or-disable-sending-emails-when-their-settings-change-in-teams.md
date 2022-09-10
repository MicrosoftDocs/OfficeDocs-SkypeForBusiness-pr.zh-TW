---
title: Email音訊會議設定變更時的選項
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '瞭解當 Teams 中的釘選變更或預設會議號碼變更等設定時，如何啟用或停用 Microsoft Teams 傳送電子郵件給使用者。 '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642104"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>當 Microsoft Teams 中的音訊會議設定變更時，啟用或停用傳送電子郵件

啟用音訊會議時，使用者會透過電子郵件自動收到通知。 不過，有時候您可能會想要減少傳送給 Microsoft Teams 使用者的電子郵件數量。 在這種情況下，您可以停用傳送電子郵件。
  
如果您停用傳送電子郵件的功能，音訊會議電子郵件將不會傳送給您的使用者，包括當使用者已啟用或停用音訊會議、重設 PIN 時，以及會議 ID 和預設會議電話號碼變更時的電子郵件。
  
以下是啟用音訊會議時傳送給使用者的電子郵件範例：
  
![音訊會議電子郵件訊息的範例。](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>何時會傳送電子郵件給您的使用者？

- 組織中的使用者啟用音訊會議後，會傳送數封電子郵件給使用者：

  - 指派 **音訊會議** 授權給他們時。

  - 當您手動重設使用者的音訊會議 PIN 時。

  - 當您手動重設使用者的會議 ID 時。

  - 移除 **音訊會議** 授權時。

  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者，或 **[無]**。

  - 當使用者的音訊會議提供者變更為 Microsoft 時。

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>啟用或停用傳送給使用者的電子郵件

您可以使用 Microsoft Teams 或 Windows PowerShell 啟用或停用傳送給使用者的電子郵件。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 **[會議**  >  **橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格中，啟用或停用 **在使用者的電話撥入設定變更時自動傳送電子郵件給使用者**。

4. 按一下 [儲存]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

您也可以使用 Microsoft Teams PowerShell 模組並執行：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 來管理貴組織的其他設定，包括電子郵件。

如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。

## <a name="related-topics"></a>相關主題

[當使用者的音訊會議設定變更時傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change-in-teams.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
