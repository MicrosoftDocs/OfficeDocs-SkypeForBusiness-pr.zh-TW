---
title: 在 Teams 中透過電話啟動音訊會議，但不使用 PIN
ms.author: heidip
author: MicrosoftHeidi
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
description: '瞭解如何從 Teams 系統管理中心啟用或停用匿名來電者加入會議。 '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641944"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在 Microsoft Teams 中透過電話召開沒有 PIN 碼的音訊會議

因為 Microsoft Teams 會議召集人尚未開始會議，因此撥入會議的使用者在會議的大廳聆聽音樂可能令人感到沮喪。
  
如果會議召集人撥入會議，根據預設，啟動會議需要 PIN。 您可以將它設定為讓任何人都可以撥入會議，而不會提示您輸入 PIN 以開始會議。 您可以使用系統管理中心為單一使用者啟用或停用此設定。
  
如果有人從 Microsoft Teams 應用程式開始會議，會議召集人就不需要 PIN。 只有當會議召集人透過電話加入會議時，才需要 PIN。 會議的 PIN 會在獲派 **音訊會議** 授權時傳送給音訊使用者，並啟用音訊會議。 請參閱傳 [送含有音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) ，以及在 [音訊會議設定變更時自動傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>啟用或停用匿名來電者加入會議

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，按一下 [ **使用者]**。

2. 選取清單中的使用者，然後按一下頁面頂端的 **[編輯** ]。

3. 在 **[音訊會議**] 旁邊，按一下 [ **編輯]**。

4. 在 **[音訊會議** ] 窗格中，啟用或停用 **撥入式來電者可以是會議中的第一個人**。

5. 按一下 [ **套用]**。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-else-should-you-know"></a>您還應知道什麼？

- 如果您想要重設 PIN，請參閱[重設音訊會議 PIN。](reset-the-audio-conferencing-pin-in-teams.md)

- 如果已停用匿名存取，或不需要 PIN 來開始會議：

  - 如果會議尚未開始 (會議中還沒有任何人) ：如果來電者是召集人，系統會提示來電者;如果對方說是，系統會提示他輸入 PIN 碼，而輸入 PIN 之後，會議便會開始，且使用者會加入會議。

  - 如果會議已開始 (其他人已在會議中) ：如果來電者是召集人，則不會提示他輸入 PIN;會議已開始，來電者會加入會議。

- 如果已啟用匿名存取，或不需要 PIN 來開始會議：

  - 如果會議尚未開始 (會議中還沒有人) ：如果來電者是召集人，系統就不會提示她輸入 PIN 碼。 由於召集人的設定設為關閉，因此會議將會開始，匿名來電者會加入會議。

  - 如果會議已開始 (其他人已在會議中) ：如果來電者是召集人，則不會出現提示，也不會提示她輸入 PIN;會議已開始，來電者會加入會議。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。
  
## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 版 Microsoft 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
