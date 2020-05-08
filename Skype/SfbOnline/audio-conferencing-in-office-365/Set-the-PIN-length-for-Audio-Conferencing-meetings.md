---
title: 在商務用 Skype Online 中設定音訊會議會議的 PIN 長度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: 瞭解 PIN 長度與需求的參數，並瞭解如何在商務用 Skype 中設定會議的長度。
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164532"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>在商務用 Skype Online 中設定音訊會議會議的 PIN 長度


> [!NOTE]
> 如需在 Microsoft 團隊中設定 PIN 長度的相關資訊，請參閱[在 Microsoft 團隊中設定音訊會議會議的 PIN 長度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。

當您設定商務用 Skype 的音訊會議時，您會收到音訊會議橋。 一個會議橋接器可以包含一或多個電話號碼。 您所設定的電話號碼將會包含在商務用 Skype app 的會議邀請中。
  
音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。 它會從自動語音應答中向來電者提供語音提示，然後視您的設定而定，您可以播放通知並要求呼叫者記錄他們的名稱。 **Microsoft bridge 設定**可讓您變更會議通知與會議加入體驗的設定，以及設定會議召集人所使用的 pin 長度。 如果您無法使用商務用 Skype app 加入會議，會議召集人就可以使用 Pin 來啟動會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>設定 PIN 長度
 
1. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
2. 在 [**安全性** > **PIN 長度**] 底下，選取您想要的 PIN 數位位數，然後按一下 [**儲存**]。
    
> [!NOTE]
> PIN 與會議 ID 不同。 呼叫者加入會議時，會使用會議 Id。 它們可用來識別會議。 PIN 是用來將來電者驗證為會議召集人。 

## <a name="want-to-know-more-about-pin-settings"></a>想要進一步瞭解 PIN 設定嗎？

- Pin 可能是4到12位數;預設值為5。 只有在建立 Pin 時才會使用數位。 不會使用字母和特殊字元。
    
- 只有在商務用 Skype 使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都要撥入會議，會議召集人需要 PIN 才能開始會議。
    
- PIN 安全設定會套用到與 Microsoft 橋接器相關聯的所有電話號碼。 它們會套用至所有使用與指定的橋接器相關聯之電話號碼的會議。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) Cmdlet。
    
- 若要將 PIN 中的位數設定為8：`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="see-also"></a>另請參閱

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
