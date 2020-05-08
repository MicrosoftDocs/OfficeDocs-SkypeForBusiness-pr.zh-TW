---
title: 在商務用 Skype Online 中的音訊會議設定變更時啟用或停用傳送電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解如何在設定例如 pin 變更或預設會議號碼變更時，啟用或停用 Skype 將電子郵件傳送給使用者。 '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164262"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>在商務用 Skype Online 中的音訊會議設定變更時啟用或停用傳送電子郵件

> [!Note]
> 如果您想要啟用或停用 Microsoft 團隊傳送電子郵件，請參閱[在 Microsoft 團隊中的音訊會議設定變更時啟用或停用傳送電子郵件](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)。

當使用者啟用音訊會議時，系統會自動透過電子郵件收到通知。 不過，您可能會想要減少傳送到商務用 Skype 使用者的電子郵件數目。 在這種情況下，您可以停用傳送電子郵件。
  
如果您停用傳送電子郵件，語音會議電子郵件不會傳送給您的使用者，包括使用者在音訊會議中啟用或停用的電子郵件、其 PIN 重設時，以及會議 ID 和預設會議電話號碼的變更。
  
以下是在啟用音訊會議時傳送給使用者的電子郵件範例：
  
![音訊會議電子郵件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>何時要傳送電子郵件給使用者？

- 在啟用音訊會議之後，會有幾封電子郵件會傳送給貴組織中的使用者：
    
  - 將**音訊會議**授權指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 手動重設使用者的會議 ID。
    
  - 從他們移除**音訊會議**授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或 [**無**] 時。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>啟用或停用傳送電子郵件給使用者的電子郵件

您可以使用商務用 Skype 系統管理中心或 Windows PowerShell 來啟用或停用傳送給使用者的電子郵件。

 
![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，按一下 [**音訊會議**]。
    
2. 在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。
    
3. 按一下 [儲存]****。
    
    > [!TIP]
    > 您也可以移至 [**音訊會議** > ]**使用者**、選取使用者，然後按一下 [透過**電子郵件傳送會議資訊**]，將電子郵件傳送給具有音訊會議設定的使用者。  如果您這樣做，就會傳送一封電子郵件，只包含會議 ID 與會議電話號碼，但不包含 PIN。  如需詳細資訊，請參閱[傳送電子郵件給使用者的音訊會議資訊](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**
  
- 執行下列動作以停用傳送電子郵件： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    如需此 Cmdlet 的說明，請參閱[設定 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)。
    
## <a name="what-else-should-you-know"></a>您還應該知道什麼？

- 當自動電子郵件停用時，您仍然可以使用商務用 Skype 系統管理中心，手動觸發傳送含有會議 ID 和電話號碼的電子郵件。 不過，如果您這麼做，就不會包含 PIN。 如果您想要重設音訊會議 PIN，且已停用 [傳送電子郵件]，您必須以另一種方式將其傳送給使用者。
    
- 您可以使用商務用 Skype 系統管理中心或 Windows PowerShell 來停用您的使用者傳送電子郵件給您的使用者。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 您可以使用這些 Cmdlet 來節省時間或將這項作業自動化。
    
  - [CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [移除-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[在使用者的音訊會議設定變更時傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)


