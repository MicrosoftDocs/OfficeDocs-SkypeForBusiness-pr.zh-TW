---
title: 在商務用 Skype Online 中使用音訊會議傳送電子郵件給使用者
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: 在商務用 Skype Online 中傳送包含其音訊會議資訊的電子郵件給使用者。
ms.openlocfilehash: f070353069c937a62935e1cc570ebae6c0e981db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109990"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>在商務用 Skype Online 中傳送包含音訊會議資訊的電子郵件給使用者

> [!Note]
> 若要傳送音訊會議資訊給 Microsoft Teams 中的使用者，請參閱在 [Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)中傳送包含音訊會議資訊的電子郵件給使用者。

有時候商務用 Skype 使用者可能需要您傳送音訊會議資訊給他們。 您可以使用商務用 Skype 系統管理 **中心** ，然後按一下使用者屬性下的透過 **電子郵件** 傳送會議資訊，即可執行此操作。 當您傳送此電子郵件時，它會包含所有音訊會議資訊，包括：
  
- 使用者的會議電話或撥入電話號碼。
    
- 使用者的會議 ID。
    
   
以下是所寄電子郵件的範例：
  
![電話撥入式會議電子郵件](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>傳送包含音訊會議資訊的電子郵件給使用者

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **[音訊會議」** 下，按一下 **[以電子郵件傳送會議資訊。**

1. 使用公司或學校帳戶來登錄。
    
2. 前往商務用 Skype >系統管理 **中心**，然後按一下左側流覽中的 [ **音訊會議**> 。
    
3. 按一下 **[使用者**，然後選取使用者。
    
4. 在 [動作」 窗格中，按一下 **[透過電子郵件傳送會議資訊。**
    
> [!TIP]
> 您也可以使用音訊會議設定傳送電子郵件給使用者，方法是編輯使用者的屬性，然後按一下音訊會議以  >  **電子郵件傳送會議資訊**。 

## <a name="what-else-should-you-know-about-this-email"></a>關於此電子郵件，您還需要知道什麼？

- 啟用音訊會議後，會將數封電子郵件寄給貴組織的使用者：
    
  - 當 **音訊會議授權** 指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 當您手動重設使用者的會議 ID 時。
    
  - 移除 **音訊會議** 授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。
    
- 根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet 來變更電子郵件地址和顯示名稱。 若要變更傳送電子郵件給使用者的電子郵件地址，您必須：
    
  - 在 SendEmailFromAddress 參數中輸入電子郵件地址。
    
  - 將 SendEmailOverride 參數設為 True。
    
  - 在 SendEmailFromDisplayName 參數中輸入電子郵件顯示名稱。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 如果您想要變更電子郵件地址資訊，您必須確定貴組織的輸入電子郵件政策允許來自已設定之自訂電子郵件地址的電子郵件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
    若要傳送包含音訊會議資訊的電子郵件給使用者，請執行下列操作：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)