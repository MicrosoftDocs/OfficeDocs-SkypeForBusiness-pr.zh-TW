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
description: 在商務用 Skype Online 中，以其音訊會議資訊傳送電子郵件給您的使用者。
ms.openlocfilehash: f2137d05ebe588a316704fabf4c8878910a40bc0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163895"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>在商務用 Skype Online 中，透過其音訊會議資訊傳送電子郵件給使用者

> [!Note]
> 如需在 microsoft 團隊中傳送音訊會議資訊給使用者的相關資訊，請參閱[在 Microsoft Teasms 中傳送電子郵件給使用者的音訊會議資訊](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)。

有時商務用 Skype 使用者可能需要您傳送其音訊會議資訊。 您可以使用商務用 Skype 系統**管理中心**，然後按一下使用者屬性底下的 [透過**電子郵件傳送會議資訊**] 來執行此動作。 傳送此電子郵件時，它會包含所有音訊會議資訊，包括：
  
- 使用者的會議電話或撥入電話號碼。
    
- 使用者的會議 ID。
    
   
以下是傳送的電子郵件範例：
  
![電話撥入式會議電子郵件](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>使用音訊會議資訊傳送電子郵件給使用者

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [**編輯**]。

3. 在 [**音訊會議**] 底下，按一下 [**以電子郵件傳送會議資訊**]。

1. 使用您的公司或學校帳戶登入。
    
2. 移至 [系統管理中心] >**商務用 Skype**，然後在左側導覽中，按一下 [**音訊會議**]。
    
3. 按一下 [**使用者**]，然後選取使用者。
    
4. 在 [動作] 窗格中，按一下 [透過**電子郵件傳送會議資訊**]。
    
> [!TIP]
> 您也可以編輯使用者的屬性，然後按一下 [**音訊會議** > 透過**電子郵件傳送會議資訊**]，透過音訊會議設定傳送電子郵件給使用者。 

## <a name="what-else-should-you-know-about-this-email"></a>關於此電子郵件，您還需要知道什麼？

- 在啟用音訊會議之後，會有幾封電子郵件會傳送給貴組織中的使用者：
    
  - 將**音訊會議**授權指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 手動重設使用者的會議 ID。
    
  - 從他們移除**音訊會議**授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一提供者或 [**無**] 時。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。
    
- 根據預設，電子郵件的寄件者是來自 Microsoft 365 或 Office 365，但是您可以使用 Windows PowerShell 和[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) Cmdlet 來變更電子郵件地址和顯示名稱。 若要對傳送電子郵件給使用者的電子郵件地址進行變更，您必須：
    
  - 在 SendEmailFromAddress 參數中輸入電子郵件地址。
    
  - 將 SendEmailOverride 參數設定為 True。
    
  - 在 SendEmailFromDisplayName 參數中輸入電子郵件的顯示名稱。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 如果您想要變更電子郵件地址資訊，您必須確認貴組織的輸入電子郵件原則允許來自自訂電子郵件地址的電子郵件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) Cmdlet。
    
    若要使用音訊會議資訊傳送電子郵件給使用者，請執行下列動作：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者以及允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
