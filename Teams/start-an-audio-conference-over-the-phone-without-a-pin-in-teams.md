---
title: 在沒有 PIN 的情況下，在手機上啟動音訊Teams
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '瞭解如何從系統管理中心啟用或停用匿名來電Teams會議。 '
ms.openlocfilehash: da31c734275113eab3e96b67230a578d0609c1bb
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537304"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在沒有 PIN 的情況下，在手機上啟動音訊Microsoft Teams

撥入會議的使用者在會議大廳中聆聽音樂可能會令人感到沮喪，因為會議Microsoft Teams尚未開始會議。 
  
如果會議召集人預設會來電到會議，則啟動會議時必須輸入 PIN。 您可以設定，讓任何人都可以撥入會議，而且不會提示 PIN 開始會議。 您可以使用系統管理中心為單一使用者啟用或停用此設定。
  
如果有人從應用程式啟動會議，會議召集人Microsoft Teams PIN。 只有當會議召集人以電話加入其會議時，才需要 PIN。 當音訊使用者獲得音訊會議授權並啟用音訊會議時，會議 PIN會發送給音訊使用者。 請參閱 [傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) ，其音訊會議資訊和電子郵件會在使用者的音訊會議設定變更時 [自動傳送給使用者](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名來電者加入會議

 **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，按一下 [**使用者。** 

2. 選取清單中的使用者，然後按一下頁面頂端的 [編輯。 

3. 在 [ **音訊會議」 旁**，按一下 [ **編輯>**。

4. 在音訊 **會議窗格中** ，啟用或停用電話撥入 **來電者可以是會議的第一個人**。
    
4. 按一下 **[Apply.** 

**使用Windows PowerShell**
  
詳細資訊[Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)。

## <a name="what-else-should-you-know"></a>您還需要知道什麼？

- 如果您想要重設 PIN，請參閱重設 [音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 如果匿名存取或不需要 PIN 來啟動會議，則停用：
    
  - 如果會議尚未開始 (會議中還沒有人員) ：如果來電者是召集人，系統就會提示來電者;如果表示是，系統會提示他輸入 PIN，而輸入 PIN 之後，會議就會開始，而使用者將加入會議。
    
  - 如果會議已經開始 (其他人已經在會議) ：如果來電者是召集人，系統將不會提示來電者輸入 PIN;會議已開始，來電者會加入會議。
    
- 如果已啟用匿名存取，或不需要 PIN 來啟動會議：
    
  - 如果會議尚未開始 (會議中還沒有人) ：來電者若是召集人，系統將不會提示她，而且永遠不會提示她輸入 PIN。 由於召集人的設定設為關閉，會議將會開始，匿名來電者會加入會議。
    
  - 如果會議已經開始 (其他人已在會議) ：來電者若是會議召集人，系統將不會提示對方輸入 PIN;會議已開始，來電者會加入會議。
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個任務時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)