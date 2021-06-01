---
title: 在線上啟動沒有 PIN 的商務用 Skype會議
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
description: '瞭解如何啟用或停用匿名來電者從系統管理中心商務用 Skype使用 PowerShell 腳本加入會議。 '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237589"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>在線上啟動沒有 PIN 的商務用 Skype會議

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關在沒有 PIN 的情況下Microsoft Teams音訊會議的資訊，請參閱在 Microsoft Teams 中在沒有 PIN 的情況下[，在手機上Microsoft Teams。](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

撥入會議的使用者在會議大廳聆聽音樂可能會令人感到沮喪，因為商務用 Skype會議召集人尚未開始會議。 
  
如果會議召集人會來電到會議，根據預設，啟動會議需要 PIN。 您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。 您可以使用系統管理商務用 Skype，為單一使用者啟用或停用此設定。
  
如果有人從應用程式開始會議，會議召集人不需要 PIN 商務用 Skype PIN。 只有當會議召集人以電話加入其會議時，才需要 PIN。 當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。 請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名來電者加入會議
    
1. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**  >  **使用者**。 
    
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
    
  - 如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，然後輸入 PIN 之後，會議就會開始，而使用者將加入會議。
    
  - 如果會議已開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。
    
- 如果已啟用匿名存取，或不需要 PIN 來啟動會議：
    
  - 如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。 由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。
    
  - 如果會議已經開始 (其他人已經在會議) ：來電者不會提示她，如果對方是召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要為多個使用者節省時間或將其自動化，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
- 當涉及Windows PowerShell商務用 Skype，商務用 Skype是管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
