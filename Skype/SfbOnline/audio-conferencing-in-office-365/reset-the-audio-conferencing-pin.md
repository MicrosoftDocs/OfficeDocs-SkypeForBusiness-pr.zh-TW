---
title: 在商務用 Skype Online 中重設音訊會議 PIN
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解關於 Pin 的資訊，以及如何在商務用 Skype Online 中重設。 '
ms.openlocfilehash: ca2bbef02b0c6ecdefef700ca316188f5c544070
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642879"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>在商務用 Skype Online 中重設音訊會議 PIN

> [!Note]
> 如需在 Microsoft 團隊中重設音訊會議 pin 的相關資訊，請參閱[重設 Microsoft 團隊中的音訊會議 PIN 碼](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。

PIN 是由為已啟用音訊會議的每個商務用 Skype 使用者所建立的數位組成的程式碼。 會議召集人會使用音訊會議 Pin 來找出他們是會議召集人，並允許他們透過電話啟動會議。 如果他們使用商務用 Skype 應用程式來啟動會議，則不需要 PIN。 如果使用者忘記自己的 PIN，而且他們無法在啟用音訊會議時傳送給他們的電子郵件中找到它，系統管理員可以重設其 PIN，或者可以重設自己的 PIN。
  
當經過驗證的使用者使用商務用 Skype app 加入，或當召集人透過電話與對方的 PIN 連線時，就可以開始會議。 當會議需要 PIN 才能開始時，以手機加入的使用者將會放在大廳，並會在會議開始前聆聽音樂保留狀態。 如果會議召集人不需要 PIN 即可在手機上啟動會議，則不會要求呼叫者在加入會議時提供 PIN。
  
## <a name="reset-a-users-pin"></a>重設使用者的 PIN

1. 使用您的公司或學校帳戶登入 Office 365。
    
2. 移至 [系統管理中心] >**商務用 Skype**，然後在左側導覽中，按一下 [**音訊會議**]。
    
3. 按一下 [**使用者**]，選取您要重設 PIN 的使用者。
    
4. 在 [動作] 窗格的 [**釘**選] 底下，按一下 [**重設**]。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>讓使用者重設自己的 PIN

使用者可以使用 [**電話撥入式會議**] 頁面上的 [**重設 pin** ] 選項來重設 pin。 您可以透過下列三種方式之一來存取此頁面：

* 在瀏覽器中，移[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)至。
* 在商務用 Skype 中，按一下 [**選項**] 旁的 [**顯示功能表**] 箭號，然後按一下 [**工具** > **電話撥入式會議設定**]。
* 在商務用 Skype 中，按一下 [**選項**]，按一下左側功能表中的 [**來電轉接**]，然後在 [**其他通話設定**] 區段中，按一下 [**線上編輯設定**]。 

## <a name="what-else-should-you-know-about-pins"></a>關於 Pin，您還需要知道什麼？

- 為安全起見，pin 只會在 PIN 重設時向系統管理員顯示一次。 由管理員重設 PIN 之後，當**商務用 Skype 系統管理中心**以及在 Windows PowerShell 中使用 CsCsOnlineDialInConfencingUser 時，pin 將會列為 * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * *。
    
- 預設會啟用自動將電子郵件傳送給使用者，當使用者啟用音訊會議或 PIN 重設時，就會收到一封電子郵件及其 PIN。 但如果您已停用自動傳送電子郵件，則 PIN 重設電子郵件不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。
    
- 當會議開始時，大廳中的所有使用者都會自動加入該會議。 例如，如果有兩個參與者嘗試在會議開始前加入會議，則會將它們放在大廳，並在會議召集人透過電話使用其 PIN 進行加入時，會議將會啟動，且會議廳中的參與者將會加入 [會議]。
    
- 預設設定為 [不允許匿名呼叫者啟動會議]。
    
- 當您為使用者啟用音訊會議時，預設會傳送包含會議資訊及其 PIN 的電子郵件。 使用者必須擁有 Office 365 信箱，因為當 PIN 重設時，新的 PIN 碼會以電子郵件傳送給使用者，以傳送給使用者設定的主要 SMTP 位址（別名）。
    
- 當您設定音訊會議時，您會設定貴組織中的 Pin 所需的數位。 Pin 可能是4到12位數，預設值是5。 如果您變更 [PIN 長度] 設定，此設定只會套用到新產生的針腳上，且不適用於已啟用音訊會議的現有使用者的 PIN 設定。 請參閱[設定音訊會議的 PIN 長度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 預設的電子郵件將會設定為使用者的 Office 365 主要 SMTP 位址。 您可以傳送電子郵件至非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用 Windows PowerShell 來覆寫預設電子郵件地址。 如果使用者在 Office 365 沒有 Exchange 信箱，這會很有用。
    
- 若要覆寫傳送電子郵件的預設使用者位址，租使用者系統管理員可以使用下列 Cmdlet： Get-csonlinedialinconferencinguser-amos。大理石-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com"。 SendEmail 參數是覆寫使用者的電子郵件地址所必需的。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) Cmdlet。
    
- 您可以執行下列動作，為 Amos 大理石設定 PIN：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議 ID](reset-a-conference-id-for-a-user.md)
