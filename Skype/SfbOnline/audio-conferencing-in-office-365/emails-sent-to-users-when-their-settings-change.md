---
title: 在商務用 Skype Online 的設定變更時傳送給使用者的電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '瞭解在商務用 Skype Online 的電話撥入式會議設定變更時，電子郵件會自動傳送哪些資訊給使用者。 '
ms.openlocfilehash: 12904c6485a422c7df314767b58ac485c38816ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986548"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>在商務用 Skype Online 的設定變更時傳送給使用者的電子郵件

> [!Note]
> 如果您正在尋找 Microsoft 團隊中的自動電子郵件資訊，請參閱在[Microsoft 團隊中的設定變更時傳送給使用者的電子郵件](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)。

電子郵件會自動傳送給已使用 Microsoft 做為音訊會議提供者[的音訊會議的](set-up-audio-conferencing.md)使用者。
  
根據預設，會傳送四種類型的電子郵件給已啟用音訊會議的使用者。 不過，如果您想要限制傳送給使用者的電子郵件數目，您可以將它關閉。 Office 365 中的音訊會議會在下列情況傳送電子郵件給使用者的電子郵件：
  
- **系統會將音訊會議授權指派給他們，或者當您將音訊會議提供者變更為 Microsoft 時。**
    
     此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN，以及使用用來更新現有會議的 [商務用 Skype Online 會議更新] 工具的指示與連結。使用者名. 請參閱[指派商務用 Skype 授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)，或[將 Microsoft 指派為音訊會議提供者](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > 如果您的組織已啟用動態會議 Id，他們排程的所有使用者會議都會有唯一的會議 Id。 您可以[在組織中設定音訊會議動態 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    以下是這封電子郵件的範例：
    
     ![商務用 Skype 驗證授權](../images/audio-conferencing-user-enabled.png)
  
    您可以查看[商務用 skype 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)，進一步瞭解商務用 skype 的授權。
    
- **使用者的會議 ID 或預設會議電話號碼會變更。**
    
    此電子郵件包含會議 ID、預設會議電話號碼，以及使用商務用 Skype Online 會議更新工具來更新使用者現有會議的指示與連結。 但此電子郵件不會包含使用者的音訊會議 PIN。 請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user.md)。
    
    > [!NOTE]
    > 如果您的組織已啟用動態會議 Id，他們排程的所有使用者會議都會有唯一的會議 Id。 您可以[在組織中設定音訊會議動態 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    以下是這封電子郵件的範例：
    
     ![電話撥入式會議資訊已變更。](../images/audio-conferencing-info-change.png)
  
- **使用者的音訊會議 PIN 將會重設。**
    
    此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID，以及使用者的預設會議電話號碼。 請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin.md)。
    
    > [!NOTE]
    > 如果您的組織已啟用動態會議 Id，他們排程的所有使用者會議都會有唯一的會議 Id。 您可以[在組織中設定音訊會議動態 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。 
  
    以下是這封電子郵件的範例：
    
     ![電話撥入式會議 PIN 已變更。](../images/audio-conferencing-pin-has-changed.png)
  
- **使用者的授權已移除，或音訊會議提供者從 Microsoft 變更為其他提供者或 [無]。**
    
    當您在使用者中移除**音訊會議**授權，或是將使用者的音訊會議提供者從 Microsoft 改為協力廠商音訊會議提供者或將提供者設定為 [**無**] 時，就會發生這種情況。 此電子郵件包含使用者使用商務用 Skype Online 會議更新工具來移除語音會議特定資訊（例如預設會議電話號碼或會議 ID）的指示與資訊。
    
    請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
    以下是這封電子郵件的範例：
    
     ![電話撥入式會議已關閉。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>對傳送給他們的電子郵件訊息進行變更

您可以對自動傳送給使用者的電子郵件進行變更，包括 [寄件者] 和 [*發件*人] 資訊中所包含的電子郵件地址和顯示名稱。 根據預設，電子郵件的寄件者會來自 Office 365，但您可以使用 Windows PowerShell 和[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) Cmdlet 來變更電子郵件地址和顯示名稱。 若要對傳送電子郵件給使用者的電子郵件地址進行變更，您必須：
  
- 在_SendEmailFromAddress_參數中輸入電子郵件地址。
    
- 在_SendEmailFromDisplayName_參數中輸入電子郵件的顯示名稱。
    
- 將_SendEmailOverride_參數設定為_True_。
    
您可以執行下列動作，對傳送給使用者的電子郵件進行變更，例如電子郵件的寄件者電子郵件地址，以及電子郵件的顯示名稱。
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  如果您想要變更電子郵件地址資訊，您必須確認您的環境的輸入電子郵件原則允許來自自訂指定寄件者位址的電子郵件。 如果您決定要覆蓋 [*寄件者*] 連絡人資訊，您應該確認電子郵件是否已正確傳送給使用者。 您可以在組織中的一位使用者進行測試，以執行此動作。
  
您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) Cmdlet 來管理貴組織的其他設定，包括電子郵件。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果您不想傳送電子郵件給他們，該怎麼辦？

當您停用傳送電子郵件給使用者時，即使使用者獲指派授權，也不會傳送電子郵件。 在此情況下，會議 ID、預設會議電話號碼和其他重要的是，其音訊會議 PIN 不會傳送給使用者。 發生這種情況時，您必須透過傳送一封電子郵件或呼叫他們來通知使用者。
  
根據預設，電子郵件會傳送給您的使用者，但如果您想要防止他們接收電子郵件以進行音訊會議，您可以使用商務用 Skype 系統管理中心或 Windows PowerShell。 
 
![](../images/sfb-logo-30x30.png)**使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示  
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
2. 在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。 
    
3. 按一下 [**儲存**]。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**使用 Windows PowerShell**
  
1. 執行下列動作以停用傳送所有使用者電子郵件：
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) Cmdlet 來管理貴組織的其他設定，包括電子郵件。
  
## <a name="what-else-should-you-know-about-this-email"></a>關於此電子郵件，您還需要知道什麼？

- 如需啟用和停用自動傳送電子郵件給使用者的詳細資訊，請參閱[啟用或停用語音會議設定變更時](enable-or-disable-sending-emails-when-their-settings-change.md)傳送電子郵件。
    
- 有時候，使用者會遺失其音訊資訊，您必須能夠將他們的所有音訊資訊傳送給他們。 您可以使用商務用 Skype 系統管理中心，然後按一下使用者音訊會議屬性底下的 [以**電子郵件傳送會議資訊**] 來執行此動作。 請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。 不過，此資訊並不包含音訊會議 PIN。
    
    以下是將會傳送給他們的電子郵件範例：
    
     ![電話撥入式會議電子郵件](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 根據預設，電子郵件的寄件者會來自 Office 365，但您可以使用 Windows PowerShell 和[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) Cmdlet 來變更電子郵件地址和顯示名稱。
    
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[啟用或停用音訊會議設定變更時傳送電子郵件的設定](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)
