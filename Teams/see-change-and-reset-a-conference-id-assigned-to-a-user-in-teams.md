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
description: 瞭解如何指派會議 ID 給使用者Microsoft Teams會議識別碼參數應該是什麼。
ms.openlocfilehash: 3086ff06d2a59028fd8b7c41aea8819cea733179e4596b036dc54d5eba927c91
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323955"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在會議名稱中，查看並重設指派給使用者Microsoft Teams

在 Microsoft 365 或 Office 365 中設定音訊會議並使用 Microsoft 做為音訊會議提供者時，系統會自動將會議 ID 指派給Microsoft Teams使用者。 會議排程時，指派的會議 ID 會以會議邀請中送出。 使用者排程的每個會議都會獲得唯一的會議 ID。 
  
雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。 您可以使用系統管理Microsoft Teams或Windows PowerShell來查看、變更及重設其會議 ID。
  
電子郵件會以會議 ID 和預設的音訊會議電話號碼發送給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。 請參閱[在 Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md)中重設使用者的會議 ID，以瞭解如何重設會議召集人的 PIN。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重設會議 ID

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **音訊會議下**，查看會議 **ID** 下的 。

    > [!TIP]
    > 您可以按一下電子郵件中傳送會議資訊的連結，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議資訊 **給使用者** 。
  
**使用Windows PowerShell**

請參閱[powerShell Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)參考資料以瞭解更多資訊。
    
  
### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

例如，如果使用者忘記會議 ID，您可以重設會議 ID。
  
![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯>**。

3. 在 **[音訊會議」** 下，按一下 **[重設會議 ID。**

4. 在 [ **重設會議 ID>** 視窗中，按一下 [ **重設**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。
  
**使用Windows PowerShell**

請參閱[powerShell Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)參考資料以瞭解更多資訊。


## <a name="what-else-should-you-know"></a>您還需要知道什麼？

   > [!IMPORTANT]
   >  建立新會議 ID 或重設會議 ID 之後，來電者即無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 
  
    
- 會議 ID 必須符合音訊會議橋接器上設定的數位長度。 會議 ID 中無法使用字母或特殊字元;只能使用數位。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。
    
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)