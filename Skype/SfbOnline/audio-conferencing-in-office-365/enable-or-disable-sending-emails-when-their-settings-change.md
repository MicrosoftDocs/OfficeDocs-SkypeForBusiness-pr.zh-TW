---
title: 啟用或停用在線上音訊會議設定變更時傳送商務用 Skype電子郵件
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
description: '瞭解如何啟用或停用Skype釘號變更或預設會議號碼變更等設定時，傳送電子郵件給使用者。 '
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237319"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>啟用或停用在線上音訊會議設定變更時傳送商務用 Skype電子郵件

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 如果您想要啟用或停用在 Microsoft Teams 中傳送電子郵件，請參閱在 Microsoft Teams 中音訊會議設定變更時啟用或[停用Microsoft Teams。](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

使用者啟用音訊會議時，會自動收到電子郵件通知。 不過，有時候您可能會想要減少寄給使用者的電子郵件商務用 Skype數量。 在這種情況下，您可以停用傳送電子郵件。
  
如果您停用傳送電子郵件，音訊會議電子郵件將不會傳送給使用者，包括使用者啟用或停用音訊會議時、其 PIN 重設時間，以及會議 ID 和預設會議電話號碼變更時的電子郵件。
  
以下是啟用音訊會議時，會寄給使用者的電子郵件範例：
  
![音訊會議電子郵件](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>何時會將電子郵件寄給您的使用者？

- 啟用音訊會議後，會向貴組織的使用者數封電子郵件：
    
  - 當 **音訊會議授權** 指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 當您手動重設使用者的會議 ID 時。
    
  - 從 **音訊會議授權** 中移除時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>啟用或停用電子郵件，禁止將電子郵件寄給使用者

您可以使用系統管理中心商務用 Skype或Windows PowerShell以啟用或停用發送給使用者的電子郵件。

 
![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**
    
1. 在 商務用 Skype **系統管理中心**，按一下左側流覽中的 [**音訊會議**> 。
    
2. 在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。
    
3. 按一下 [儲存]。
    
    > [!TIP]
    > 您也可以使用音訊會議設定傳送電子郵件給使用者，方法是進入音訊會議使用者、選取使用者，然後按一下以  >  ******電子郵件傳送會議資訊**。  如果您這麼做，將會送出一封電子郵件，只包含會議 ID 和會議電話號碼，但不包括 PIN。  請參閱 [傳送電子郵件給使用者及其音訊會議資訊](send-an-email-to-a-user-with-their-dial-in-information.md) 以瞭解更多資訊。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用Windows PowerShell**
  
- 執行下列操作以停用傳送電子郵件： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    有關此 Cmdlet 的協助，請參閱 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。
    
## <a name="what-else-should-you-know"></a>您還需要知道什麼？

- 當自動電子郵件停用時，您仍可使用系統管理中心手動觸發使用會議 ID 和電話號碼商務用 Skype電子郵件。 不過，如果您這麼做，將不會包含 PIN。 如果您想要重設音訊會議 PIN 並停用傳送電子郵件，您必須以其他方式將 PIN 傳送給使用者。
    
- 您可以使用系統管理中心或商務用 Skype來停用傳送電子郵件給使用者Windows PowerShell。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 您可以使用這些 Cmdlet 來節省時間或將這項功能自動化。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[當使用者的音訊會議設定變更時，寄來的電子郵件](emails-sent-to-users-when-their-settings-change.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)
