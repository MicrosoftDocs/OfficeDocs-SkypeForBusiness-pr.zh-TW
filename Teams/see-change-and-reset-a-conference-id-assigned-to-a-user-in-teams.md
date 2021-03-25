---
title: 查看、變更及重設使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中指派會議 ID 給使用者，以及會議 ID 參數應該是什麼。
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117206"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中查看並重設指派給使用者的會議 ID

在 Microsoft 365 或 Office 365 中設定音訊會議並使用 Microsoft 做為音訊會議提供者時，系統會自動將會議 ID 指派給 Microsoft Teams 使用者。 會議排程時，指派的會議 ID 會以會議邀請中送出。 使用者排程的每個會議都會獲得唯一的會議 ID。 
  
雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。 您可以使用 Microsoft Teams 系統管理中心或 Windows PowerShell 來查看、變更及重設其會議 ID。
  
電子郵件會以會議 ID 和預設的音訊會議電話號碼寄給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。 請參閱 [在 Microsoft Teams 中](reset-a-conference-id-for-a-user-in-teams.md) 重設使用者的會議 ID，以瞭解如何重設會議召集人的 PIN。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重設會議 ID

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **音訊會議下**，查看會議 **ID** 下的 。

    > [!TIP]
    > 您可以按一下電子郵件中傳送會議資訊的連結，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議 **資訊給使用者** 。
  
**使用 Windows PowerShell**

請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。
    
  
### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

例如，如果使用者忘記會議 ID，您可以重設會議 ID。
  
![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **[音訊會議」** 下，按一下 **[重設會議 ID。**

4. 在 [ **重設會議 ID>** 視窗中，按一下 [ **重設**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。
  
**使用 Windows PowerShell**

請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。


## <a name="what-else-should-you-know"></a>您還需要知道什麼？

   > [!IMPORTANT]
   >  建立新會議 ID 或重設會議 ID 後，來電者無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 
  
    
- 會議 ID 必須符合音訊會議橋接器上設定的數位長度。 會議 ID 中無法使用字母或特殊字元;只能使用數位。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。
    
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)