---
title: 在 Microsoft 團隊中重設音訊會議 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解您應該瞭解的 Pin，以及如何在 Microsoft 團隊中重設它們。 '
ms.openlocfilehash: 6d0d986789fb987494ded16bb8d6f6d7c3bf58a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693828"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft 團隊中重設音訊會議 PIN

PIN 是由為每個啟用音訊會議的 Microsoft 團隊使用者所建立的數位組成的程式碼。 會議召集人會使用音訊會議 Pin 來找出他們是會議召集人，並允許他們透過電話啟動會議。 如果他們使用 Microsoft 團隊 app 來啟動會議，則不需要 PIN。 如果使用者忘記自己的 PIN，而且他們無法在啟用音訊會議時傳送給他們的電子郵件中找到它，系統管理員可以重設其 PIN，或者可以重設自己的 PIN。
  
當經過驗證的使用者使用 Microsoft 團隊應用程式加入會議，或當召集人透過電話與對方的 PIN 連線時，就可以開始會議。 當會議需要 PIN 才能開始時，以手機加入的使用者將會放在大廳，並會在會議開始前聆聽音樂保留狀態。 如果會議召集人不需要 PIN 即可在手機上啟動會議，則不會要求呼叫者在加入會議時提供 PIN。

## <a name="reset-a-users-pin"></a>重設使用者的 PIN

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下 [**編輯**]。

3. 在 [**音訊會議**] 底下，按一下 [**重設 PIN**]。

4. 按一下 [**重設**]。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>讓使用者重設自己的 PIN

1. 讓使用者移至[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。
2. 按一下 [**重設 PIN**]。 


## <a name="what-else-should-you-know-about-pins"></a>關於 Pin，您還需要知道什麼？

- 為安全起見，pin 只會在 PIN 重設時向系統管理員顯示一次。 由管理員重設 PIN 之後，PIN 將會列為 * * * * * * * * * * * *。
    
- 預設會啟用自動將電子郵件傳送給使用者，當使用者啟用音訊會議或 PIN 重設時，就會收到一封電子郵件及其 PIN。 但如果您已停用自動傳送電子郵件，則 PIN 重設電子郵件不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。
    
- 當會議開始時，大廳中的所有使用者都會自動加入該會議。 例如，如果有兩個參與者嘗試在會議開始前加入會議，則會將它們放在大廳，並在會議召集人透過電話使用其 PIN 進行加入時，會議將會啟動，且會議廳中的參與者將會加入 [會議]。
    
- 預設設定為 [不允許匿名呼叫者啟動會議]。
    
- 當您為使用者啟用音訊會議時，預設會傳送包含會議資訊及其 PIN 的電子郵件。 使用者必須擁有 Office 365 信箱，因為當 PIN 重設時，新的 PIN 碼會以電子郵件傳送給使用者，以傳送給使用者設定的主要 SMTP 位址（別名）。
    
- 當您設定音訊會議時，您會設定貴組織中的 Pin 所需的數位。 Pin 可能是4到12位數，預設值是5。 如果您變更 [PIN 長度] 設定，此設定只會套用到新產生的針腳上，且不適用於已啟用音訊會議的現有使用者的 PIN 設定。 請參閱[設定音訊會議的 PIN 長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 預設的電子郵件將會設定為使用者的 Office 365 主要 SMTP 位址。 您可以傳送電子郵件至非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用 Windows PowerShell 來覆寫預設電子郵件地址。 如果使用者在 Office 365 沒有 Exchange 信箱，這會很有用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user-in-teams.md)
