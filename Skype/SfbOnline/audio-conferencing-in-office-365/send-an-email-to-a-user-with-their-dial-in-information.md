---
title: 在線上傳送電子郵件給使用者的音訊商務用 Skype會議
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
description: 在線上傳送包含其音訊會議資訊的電子郵件商務用 Skype使用者。
ms.openlocfilehash: 4f4590fcfb9233d7ad2d58358de08db58d014ecc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237029"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>在線上傳送包含音訊會議資訊的電子郵件商務用 Skype使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關將音訊會議資訊傳送給使用者Microsoft Teams，請參閱在[Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)中傳送包含音訊會議資訊的電子郵件給使用者。

有時候商務用 Skype使用者可能需要您傳送音訊會議資訊給他們。 您可以使用系統管理中心商務用 Skype，然後按一下使用者屬性下的透過 **電子郵件** 傳送會議資訊，即可執行這項操作。 當您傳送此電子郵件時，它會包含所有音訊會議資訊，包括：
  
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
    
2. 請前往系統管理中心>商務用 Skype，然後按一下左側流覽中的 [**音訊會議**> 。
    
3. 按一下 **[使用者**，然後選取使用者。
    
4. 在 [動作」 窗格中，按一下 **[透過電子郵件傳送會議資訊。**
    
> [!TIP]
> 您也可以使用音訊會議設定傳送電子郵件給使用者，方法是編輯使用者的屬性，然後按一下音訊會議以  >  **電子郵件傳送會議資訊**。 

## <a name="what-else-should-you-know-about-this-email"></a>關於此電子郵件，您還需要知道什麼？

- 啟用音訊會議後，會向貴組織的使用者數封電子郵件：
    
  - 當 **音訊會議授權** 指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 當您手動重設使用者的會議 ID 時。
    
  - 移除 **音訊會議** 授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。
    
- 根據預設，電子郵件的寄件者會來自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet 來變更電子郵件地址和顯示名稱。 若要變更傳送電子郵件給使用者的電子郵件地址，您必須：
    
  - 在 SendEmailFromAddress 參數中輸入電子郵件地址。
    
  - 將 SendEmailOverride 參數設為 True。
    
  - 在 SendEmailFromDisplayName 參數中輸入電子郵件顯示名稱。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 如果您想要變更電子郵件地址資訊，您必須確定貴組織的輸入電子郵件政策允許來自已設定之自訂電子郵件地址的電子郵件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
    若要傳送包含音訊會議資訊的電子郵件給使用者，請執行下列操作：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 當涉及Windows PowerShell商務用 Skype，商務用 Skype是管理使用者，以及使用者允許或不允許執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比使用 Microsoft 365 系統管理中心時，在速度、簡易性及生產力方面有許多優點，例如一次對許多使用者進行設定變更。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
