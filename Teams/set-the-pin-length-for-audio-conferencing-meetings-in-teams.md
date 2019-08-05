---
title: 在 Microsoft 團隊中設定音訊會議會議的 PIN 長度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 瞭解 PIN 長度與需求的參數, 並瞭解如何在 Microsoft 團隊中設定會議的長度。
ms.openlocfilehash: 938e8096cf39c482a2de9f143174e6c261c652d8
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183438"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft 團隊中設定音訊會議會議的 PIN 長度

當您為 Microsoft 團隊設定音訊會議時, 您將會收到音訊會議橋。 [會議橋] 可以包含一或多個電話號碼。 您所設定的電話號碼將會包含在 Microsoft 團隊 app 的會議邀請中。
  
[音訊會議橋接] 會針對使用電話撥入會議的人員接聽來電。 它會從自動語音應答中向來電者提供語音提示, 然後視您的設定而定, 您可以播放通知並要求呼叫者記錄他們的名稱。 **Microsoft bridge 設定**可讓您變更會議通知與會議加入體驗的設定, 以及設定會議召集人所使用的 pin 長度。 如果會議召集人無法使用 Microsoft 團隊 app 加入會議, 請使用 Pin 來啟動會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>設定 PIN 長度

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中, 前往 [**會議** > **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端, 按一下 [**橋設定**]。 

3. 在 [**橋接器設定**] 窗格的 [ **PIN 長度**] 底下, 選取您想要的 PIN 數位位數。

4. 按一下 [**儲存**]。

> [!NOTE]
> PIN 與會議 ID 不同。 呼叫者加入會議時, 會使用會議 Id。 它們可用來識別會議。 PIN 是用來將來電者驗證為會議召集人。 

## <a name="want-to-know-more-about-pin-settings"></a>想要進一步瞭解 PIN 設定嗎？

- Pin 可能是4到12位數;預設值為5。 只有在建立 Pin 時才會使用數位。 不會使用字母和特殊字元。
    
- 只有在 Microsoft 團隊使用者尚未開始會議時, 會議召集人才需要 PIN。 如果每個人都要撥入會議, 會議召集人需要 PIN 才能開始會議。
    
- PIN 安全設定會套用到與 Microsoft 橋接器相關聯的所有電話號碼。 它們會套用至所有使用與指定的橋接器相關聯之電話號碼的會議。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者, 以及允許或不允許的使用者執行。 在 Windows PowerShell 中, 您可以使用單一管理點來管理 Office 365, 以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell, 請參閱以下主題:
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊, 請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps), 以取得詳細資訊。
    
  
## <a name="related-topics"></a>相關主題

[在 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
