---
title: 以電子郵件將使用者的音訊會議資訊電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中傳送包含其音訊會議資訊的電子郵件給使用者。
ms.openlocfilehash: 8cc0e549d502a2c7a8d8052ebe496a82e36b6648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117201"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>在 Microsoft Teams 中傳送包含音訊會議資訊的電子郵件給使用者

有時候 Microsoft Teams 使用者可能需要您傳送音訊會議資訊給他們。 您可以按一下使用者屬性下的透過 **電子郵件** 傳送會議資訊，以執行此操作。 當您傳送此電子郵件時，它會包含所有音訊會議資訊，包括：
  
- 使用者的會議電話或撥入電話號碼。
    
- 使用者的會議 ID。
    
   
以下是所寄電子郵件的範例：
  
![電話撥入式會議電子郵件訊息範例](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>傳送包含音訊會議資訊的電子郵件給使用者

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **[音訊會議」** 下，按一下 **[以電子郵件傳送會議資訊。**


## <a name="what-else-should-you-know-about-this-email"></a>關於此電子郵件，您還需要知道什麼？

- 啟用音訊會議後，會將數封電子郵件寄給貴組織的使用者：
    
  - 當 **音訊會議授權** 指派給他們時。
    
  - 當您手動重設使用者的音訊會議 PIN 時。
    
  - 當您手動重設使用者的會議 ID 時。
    
  - 移除 **音訊會議** 授權時。
    
  - 當使用者的音訊會議提供者從 Microsoft 變更為另一個提供者或無 **時**。
    
  - 當使用者的音訊會議提供者變更為 Microsoft 時。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。
    
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)