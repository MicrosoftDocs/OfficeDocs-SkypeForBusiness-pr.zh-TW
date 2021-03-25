---
title: 在商務用 Skype Online 中，在沒有 PIN 的情況下，在電話上啟動音訊會議
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
description: '瞭解如何啟用或停用匿名來電者從商務用 Skype 系統管理中心加入會議，或是使用 PowerShell 腳本。 '
ms.openlocfilehash: 6eb62e2a2a295644185b3f0e6fd424749dc5bf56
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111939"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>在商務用 Skype Online 中，在沒有 PIN 的情況下，在電話上啟動音訊會議

> [!Note]
> 有關在 Microsoft Teams 中啟動沒有 PIN 的音訊會議的資訊，請參閱在 Microsoft Teams 中在沒有 PIN 的情況下，在手機上啟動 [音訊會議](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)。

因為商務用 Skype 會議召集人尚未開始會議，因此撥入會議的使用者在會議大廳聆聽音樂可能會感到沮喪。 
  
如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。 您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。 您可以使用商務用 Skype 系統管理中心為單一使用者啟用或停用此設定。
  
如果有人從商務用 Skype 應用程式開始會議，會議召集人不需要 PIN。 只有當會議召集人以電話加入其會議時，才需要 PIN。 當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。 請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名來電者加入會議
    
1. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **使用者**。 
    
2. 在清單中，選取使用者，然後按一下 [動作窗格 **編輯>**。 
    
3. 在使用者的屬性頁面上，選取或 **清除會議選項** 下的允許未經驗證的來電 **者成為會議的第一個人。如果沒有，他們會在大廳等候，直到經過驗證的使用者加入**。
    
4. 按一下 [儲存]。 


    
 **使用 Windows Powershell**
  
- 執行下列操作： 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>您還需要知道什麼？

- 如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin.md)。
    
- 如果匿名存取或不需要 PIN 來啟動會議，則停用：
    
  - 如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。
    
  - 如果會議已開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。
    
- 如果已啟用匿名存取，或不需要 PIN 來啟動會議：
    
  - 如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。 由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。
    
  - 如果會議已經開始 (其他人已經在會議) ：來電者不會提示她，如果對方是召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要為多個使用者節省時間或將其自動化，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次變更許多使用者的設定時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)