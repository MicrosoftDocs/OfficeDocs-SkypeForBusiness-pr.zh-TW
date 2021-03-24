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
description: 瞭解 PIN 長度和需求的參數，並瞭解如何在商務用 Skype 中設定會議長度。
ms.openlocfilehash: a2acaad15712621c33b275e914263f6781178d9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100789"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>在商務用 Skype Online 中設定音訊會議會議的 PIN 長度


> [!NOTE]
> 有關在 Microsoft Teams 中設定 PIN 長度的資訊，請參閱在 Microsoft Teams 中設定音訊會議會議的 [PIN 長度](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)。

當您為商務用 Skype 設定音訊會議時，您將獲得音訊會議橋接器。 一個會議橋接器可以包含一或多個電話號碼。 您設定的電話號碼會包含在商務用 Skype 應用程式的會議邀請中。
  
音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。 它會使用自動語音應答的語音提示來接聽來電者，然後視您的設定播放通知，並要求來電者錄製其名稱。 **Microsoft 橋接器** 設定允許您變更會議通知和會議加入體驗的設定，並設定會議召集人所使用的 PIN 長度。 如果會議召集人無法使用商務用 Skype 應用程式加入會議，請使用 PIN 開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>設定 PIN 長度
 
1. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。
    
2. 在 **[安全性** PIN 長度圖》 下，選取要用於 PIN 的位數，  >  然後按一下 [**儲存**。
    
> [!NOTE]
> PIN 與會議 ID 不同。 當來電者加入會議時，會使用會議 ID。 它們是用來識別會議。 PIN 是用來驗證來電者為會議召集人。 

## <a name="want-to-know-more-about-pin-settings"></a>想要進一瞭解 PIN 設定嗎？

- PIN 可以是 4 到 12 位數;預設值為 5。 數位只有在建立 PIN 時才能使用。 不會使用字母和特殊字元。
    
- 只有當商務用 Skype 使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。
    
- PIN 安全性設定會適用于與 Microsoft 橋接器相關聯的所有電話號碼。 這些將會適用于使用與特定橋接器相關聯的電話號碼的所有會議。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet。
    
- 若要將 PIN 中的位數設為 8：  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如一次變更許多使用者的設定。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>另請參閱

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)