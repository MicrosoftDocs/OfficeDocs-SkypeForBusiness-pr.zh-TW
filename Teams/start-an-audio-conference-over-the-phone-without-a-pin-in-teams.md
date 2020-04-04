---
title: 在沒有小組中的 PIN 的情況下，在手機上啟動音訊會議
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
description: '瞭解如何啟用或停用匿名呼叫者從 [小組] 管理中心加入會議。 '
ms.openlocfilehash: e6e3244a3b2135023d80b9b0df925cc5293244f6
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140826"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在沒有 Microsoft 團隊中的 PIN 的情況下，透過電話啟動音訊會議

因為 Microsoft 團隊會議召集人還沒有啟動會議，所以撥入會議的使用者可能會不想要在會議的大廳聆聽音樂中舉行。 
  
如果會議召集人撥入會議，預設會需要 PIN 才能開始會議。 您可以設定它，讓任何人都能撥入會議，而不會提示您輸入 PIN 以啟動會議。 您可以使用系統管理中心來針對單一使用者啟用或停用此設定。
  
如果某人從 Microsoft 團隊 app 開始會議，則會議召集人不需要 PIN。 只有在會議召集人在手機上加入會議時，才需要 PIN。 當使用者指派**音訊會議**授權，且已啟用音訊會議時，會議的 PIN 會傳送給音訊使用者。 請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)，以及[在其音訊會議設定變更時自動傳送給使用者的電子](emails-sent-to-users-when-their-settings-change-in-teams.md)郵件。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名呼叫者加入會議

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [**使用者**]。 

2. 在清單中選取使用者，然後按一下頁面頂端的 [**編輯**]。 

3. 按一下 [**音訊會議**] 旁的 [**編輯**]。

4. 在 [**音訊會議**] 窗格中，啟用或停**用撥入呼叫者可以是會議中的第一個人員**。
    
4. 按一下 **[** 套用]。 

**使用 Windows PowerShell**
  
如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

## <a name="what-else-should-you-know"></a>您還應該知道什麼？

- 如果您想要重設 PIN，請參閱[重設音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 如果您使用匿名存取，或不需要 PIN 即可開始會議，則會停用：
    
  - 如果會議尚未開始（在會議中還沒有任何人）：如果您是召集人，系統會提示來電者;如果他說是，系統會提示您輸入 PIN，然後在輸入 PIN 之後，會議就會開始，且使用者會加入會議。
    
  - 如果會議已開始（其他人已在會議中）：如果他是召集人，則不會提示來電者，且系統不會提示您輸入 PIN;會議已啟動，且呼叫者會加入該會議。
    
- 如果啟用匿名存取，或不需要 PIN 即可開始會議，則會啟用：
    
  - 如果會議尚未開始（在會議中還沒有任何人）：如果她是召集人，系統不會提示來電者，而且系統不會提示您輸入 PIN。 因為召集人的設定設為 [關閉]，所以會議會啟動，而匿名呼叫者將會加入會議。
    
  - 如果會議已開始（其他人已在會議中）：如果她是召集人，系統不會提示來電者，而她將不會收到 PIN 提示; 會議已開始，且呼叫者會加入該會議。
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。
  
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
