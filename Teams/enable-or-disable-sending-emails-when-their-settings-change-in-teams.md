---
title: 音訊會議設定變更時的電子郵件選項
ms.author: tonysmit
author: tonysmit
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
description: '瞭解如何啟用或停用Skype針變更或預設會議號碼變更等設定時，將電子郵件傳送給使用者Microsoft Teams。 '
ms.openlocfilehash: fa52306afbee534b52e9bfdbd304a22cda395704
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537224"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>啟用或停用在音訊會議設定變更時傳送Microsoft Teams

使用者啟用音訊會議時，會自動收到電子郵件通知。 不過，有時候您可能會想要減少寄給使用者的電子郵件Microsoft Teams數量。 在這種情況下，您可以停用傳送電子郵件。
  
如果您停用傳送電子郵件，音訊會議電子郵件將不會傳送給使用者，包括使用者啟用或停用音訊會議時、其 PIN 重設時間，以及會議 ID 和預設會議電話號碼變更時的電子郵件。
  
以下是啟用音訊會議時，會寄給使用者的電子郵件範例：
  
![音訊會議電子郵件訊息範例。](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>何時會將電子郵件寄給您的使用者？

- 啟用音訊會議後，會將數封電子郵件寄給貴組織的使用者：
    
  - 當 **音訊會議授權** 指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 當您手動重設使用者的會議 ID 時。
    
  - 從 **這些會議中移除音訊會議** 授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>啟用或停用電子郵件，禁止將電子郵件寄給使用者

您可以使用電子郵件Microsoft Teams或Windows PowerShell來啟用或停用已寄給使用者的電子郵件。

 **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** ，啟用或停用當使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。

4. 按一下 [儲存]。

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用Windows PowerShell**
  
您也可以使用 PowerShell 模組Microsoft Teams並執行：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 來管理貴組織的其他設定，包括電子郵件。

詳細資訊[Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)。

    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。
    
  
## <a name="related-topics"></a>相關主題

[當使用者的音訊會議設定變更時，寄來的電子郵件](emails-sent-to-users-when-their-settings-change-in-teams.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
