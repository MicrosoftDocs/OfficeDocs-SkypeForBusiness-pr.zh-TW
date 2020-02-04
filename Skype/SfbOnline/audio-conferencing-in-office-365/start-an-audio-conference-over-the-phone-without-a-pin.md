---
title: 在商務用 Skype Online 中不使用 PIN 在手機上啟動音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '瞭解如何從商務用 Skype 系統管理中心或使用 PowerShell 腳本，來啟用或停用匿名呼叫者加入會議。 '
ms.openlocfilehash: e2cb4fc543f92bd4dc5c2a16a1fb7e10f65e0660
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680340"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>在商務用 Skype Online 中不使用 PIN 在手機上啟動音訊會議

> [!Note]
> 如需在 Microsoft 團隊中不使用 PIN 來啟動音訊會議的相關資訊，請參閱透過[沒有 pin 的 Microsoft 團隊在手機上啟動音訊會議](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。

因為商務用 Skype 會議召集人尚未開始會議，所以撥入會議的使用者可能會不想要在會議的大廳聆聽音樂中舉行。 
  
如果會議召集人撥入會議，預設會需要 PIN 才能開始會議。 您可以設定它，讓任何人都能撥入會議，而不會提示您輸入 PIN 以啟動會議。 您可以使用商務用 Skype 系統管理中心來針對單一使用者啟用或停用此設定。
  
如果某人從商務用 Skype app 開始會議，則會議召集人不需要 PIN。 只有在會議召集人在手機上加入會議時，才需要 PIN。 當使用者指派**音訊會議**授權，且已啟用音訊會議時，會議的 PIN 會傳送給音訊使用者。 請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)，以及[在其音訊會議設定變更時自動傳送給使用者的電子](emails-sent-to-users-when-their-settings-change.md)郵件。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名呼叫者加入會議
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議** > **使用者**]。 
    
2. 在清單中，選取使用者，然後在 [動作] 窗格中，按一下 [**編輯**]。 
    
3. 在使用者的 [屬性] 頁面的 [**會議選項**] 底下，選取或清除 [**允許未驗證的呼叫者成為會議中的第一位人員]。如果不是，則會在大廳等候，直到經過驗證的使用者加入為止**。
    
4. 按一下 [**儲存**]。 


    
 **使用 Windows Powershell**
  
- 執行下列動作： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>您還應該知道什麼？

- 如果您想要重設 PIN，請參閱[重設音訊會議 PIN](reset-the-audio-conferencing-pin.md)。
    
- 如果您使用匿名存取，或不需要 PIN 即可開始會議，則會停用：
    
  - 如果會議尚未開始（在會議中還沒有任何人）：如果您是召集人，系統會提示來電者;如果他說是，系統會提示您輸入 PIN，然後在輸入 PIN 之後，會議就會開始，且使用者會加入會議。
    
  - 如果會議已開始（其他人已在會議中）：如果他是召集人，則不會提示來電者，且系統不會提示您輸入 PIN;會議已啟動，且呼叫者會加入該會議。
    
- 如果啟用匿名存取，或不需要 PIN 即可開始會議，則會啟用：
    
  - 如果會議尚未開始（在會議中還沒有任何人）：如果她是召集人，系統不會提示來電者，而且系統不會提示您輸入 PIN。 因為召集人的設定設為 [關閉]，所以會議會啟動，而匿名呼叫者將會加入會議。
    
  - 如果會議已開始（其他人已在會議中）：如果她是召集人，系統不會提示來電者，而她將不會收到 PIN 提示; 會議已開始，且呼叫者會加入該會議。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化給一個以上的使用者，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) Cmdlet。
    
- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者以及允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
