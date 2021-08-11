---
title: 重設線上音訊會議 PIN 商務用 Skype PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: '瞭解您應該瞭解哪些 PIN，以及如何在 商務用 Skype 中重設。 '
ms.openlocfilehash: 79568b3b050f456d64ba4dfc9f1c86b46401536274caf88a4cbc51f20cbd14cc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310242"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>重設線上音訊會議 PIN 商務用 Skype PIN

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關在 Microsoft Teams 重設音訊會議 PIN 的資訊，請參閱重設 Microsoft Teams 中的音訊會議[PIN。](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

PIN 是由每個已啟用音訊會議商務用 Skype使用者所建立的數位所建立的代碼。 會議召集人會使用音訊會議 PIN 來識別他們是會議召集人，並允許他們以電話開始會議。 如果他們使用 商務用 Skype應用程式來開始會議，則不需要 PIN。 如果使用者忘記 PIN，卻在啟用音訊會議時，無法于電子郵件中找到 PIN，系統管理員可以重設其 PIN，或重設自己的 PIN。
  
當經過驗證的使用者使用 商務用 Skype App 加入時，或當召集人使用其 PIN 在電話上加入時，就可以開始會議。 當會議需要 PIN 才能啟動時，電話加入的使用者會放在大廳，並聆聽等候音樂，直到會議開始。 如果會議召集人不需要 PIN，以電話開始會議，則來電者加入會議時不會要求他們提供 PIN。
  
## <a name="reset-a-users-pin"></a>重設使用者的 PIN

1. 使用公司或學校帳戶來登錄。
    
2. 請前往系統管理中心>商務用 Skype，然後按一下左側流覽中的 [**音訊會議**> 。
    
3. 按一下 **[使用者**」，選取要重設 PIN 的使用者。
    
4. 在 [動作窗格的 **PIN** 中，按一下 [ **重設**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>讓使用者重設自己的 PIN

使用者可以使用電話撥入式會議頁面上的重設 **PIN** **選項來重設 PIN。** 您可以用三種方式之一存取此頁面：

* 在瀏覽器中，前往 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) 。
* 在 商務用 Skype 中，按一下 [選項旁的顯示功能表箭號，然後按一下[工具  >  **電話撥入式會議設定。**
* 在 商務用 Skype中，按一下[選項>，按一下左側功能表中的 [**呼叫轉設定，** 然後按一下 [線上編輯 **設定**> 。  

## <a name="what-else-should-you-know-about-pins"></a>關於 PIN，您還需要知道什麼？

- 基於安全性目的，PIN 只會在 PIN 重設時一次顯示給系統管理員。 在系統管理員重設 PIN 之後，PIN 會列在 商務用 Skype 系統管理中心，以及當 PIN 在 Windows PowerShell 中使用Get-CsCsOnlineDialInConfencingUser時Windows PowerShell。
    
- 系統預設會啟用自動傳送電子郵件給使用者，當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件，PIN 重設電子郵件將不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。
    
- 會議開始時，大廳中的所有使用者都會自動加入會議。 例如，如果兩位參與者在會議開始之前嘗試加入會議，則他們會放在大廳，並保留聆聽音樂，而當會議召集人透過電話使用 PIN 加入時，會議就會開始，而大廳中的參與者會加入會議。
    
- 預設設定是不允許匿名來電者啟動會議。
    
- 當您啟用音訊會議的使用者時，根據預設，使用者會收到包含會議資訊及其 PIN 的電子郵件。 使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為當 PIN 重設時，會以電子郵件將新的 PIN 寄到使用者為使用者設定的主要 SMTP 位址 (別名) 。
    
- 當您設定音訊會議時，您可以設定組織中 PIN 所需的位數。 PIN 可以是 4 到 12 位數 -預設值為 5。 如果您變更 PIN 長度設定，則設定只會在新產生的 PIN 上，不會適用于已啟用音訊會議的現有使用者的 PIN 設定。 請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 根據預設，電子郵件會設定為使用者Microsoft 365或Office 365 SMTP 位址。 您可以將電子郵件傳送至非Microsoft 365非Office 365位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用預設電子郵件地址來取代Windows PowerShell。 如果使用者在郵件或信箱中Exchange信箱，Microsoft 365 Office 365。
    
- 若要取代傳送電子郵件的預設使用者位址，租使用者系統管理員可以使用下列 Cmdlet：Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com"。 要取代使用者的電子郵件地址，需要 SendEmail 參數。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
- 您可以進行以下操作來設定 Amos Marble 的 PIN：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如一次對許多使用者進行設定變更。 請從下列主題瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user.md)
