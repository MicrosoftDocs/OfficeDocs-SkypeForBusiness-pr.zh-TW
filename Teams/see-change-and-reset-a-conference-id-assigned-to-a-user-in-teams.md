---
title: 在 Microsoft 團隊中查看、變更及重設指派給使用者的會議 ID
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
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解如何將會議 ID 指派給 Microsoft 團隊中的使用者，以及會議 ID 的參數應該是什麼。 '
ms.openlocfilehash: fe166dc7b70c30e995bbbd6412a6baa6769c1bb6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694118"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft 團隊中查看及重設指派給使用者的會議 ID

當您在 Office 365 中設定音訊會議，且使用 Microsoft 作為音訊會議提供者時，會議 ID 會自動指派給 Microsoft 團隊使用者。 在會議排程時，指派的會議 ID 會在會議邀請中傳送。 使用者排程的每個會議都會指派唯一的會議 ID。 
  
雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或是您的使用者無法記住或遺失其會議 ID。 您可以使用 Microsoft 團隊系統管理中心或 Windows PowerShell 來查看、變更及重設其會議 ID。
  
系統會傳送電子郵件給使用者，並提供會議 ID 和預設的音訊會議電話號碼; 或者，如果您重設會議 ID，就會傳送不同的電子郵件，並包含會議 ID，但不包含 PIN。 如需重設會議召集人 PIN 的詳細資訊，請[移至這裡](reset-a-conference-id-for-a-user-in-teams.md)。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看及重設會議 Id

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [**編輯**]。

3. 在 [**音訊會議**] 下，查看 [**會議 ID**] 底下。

    > [!TIP]
    > 您可以按一下 [透過**電子郵件傳送會議資訊**] 連結，在包含會議 ID 和音訊電話號碼的電子郵件中傳送所有會議資訊給使用者。
  
**使用 Windows PowerShell**

如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
    
  
### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

您可以重設使用者的會議 ID （例如忘記它）。
  
![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [**編輯**]。

3. 在 [**音訊會議**] 底下，按一下 [**重設會議 ID**]。

4. 在 [**重設會議 ID** ] 視窗中，按一下 [**重設**]。 系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。
  
**使用 Windows PowerShell**

如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="what-else-should-you-know"></a>您還應該知道什麼？

   > [!IMPORTANT]
   >  在建立新的會議 ID 或重新設定之後，舊的會議 ID 無法由呼叫者使用。 您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。 
  
    
- 會議 ID 必須符合在音訊會議橋設定的位數長度。 您不能在會議 Id 中使用字母或特殊字元;只有數位可以使用。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。
    
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

