---
title: 在 Teams 中在沒有 PIN 的情況下，在電話上啟動音訊會議
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '瞭解如何從 Teams 系統管理中心啟用或停用匿名來電者加入會議。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116961"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在 Microsoft Teams 中，在沒有 PIN 的情況下，在手機上啟動音訊會議

因為 Microsoft Teams 會議召集人尚未開始會議，因此撥入會議的使用者在會議大廳聆聽音樂可能會感到沮喪。 
  
如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。 您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。 您可以使用系統管理中心為單一使用者啟用或停用此設定。
  
如果有人從 Microsoft Teams 應用程式開始會議，會議召集人不需要 PIN。 只有當會議召集人以電話加入其會議時，才需要 PIN。 當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。 請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名來電者加入會議

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，按一下 [ **使用者>**。 

2. 選取清單中的使用者，然後按一下頁面頂端的 [編輯。 

3. 在 [ **音訊會議」 旁**，按一下 [ **編輯>**。

4. 在音訊 **會議窗格中** ，啟用或停用電話撥入 **來電者可以是會議的第一個人**。
    
4. 按一下 **[Apply.** 

**使用 Windows PowerShell**
  
請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。

## <a name="what-else-should-you-know"></a>您還需要知道什麼？

- 如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 如果匿名存取或不需要 PIN 來啟動會議，則停用：
    
  - 如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。
    
  - 如果會議已開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。
    
- 如果已啟用匿名存取，或不需要 PIN 來啟動會議：
    
  - 如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。 由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。
    
  - 如果會議已經開始 (其他人已經在會議) ：來電者不會提示她，如果對方是召集人，而且永遠不會提示她輸入 PIN;會議已經啟動，來電者會加入。
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)