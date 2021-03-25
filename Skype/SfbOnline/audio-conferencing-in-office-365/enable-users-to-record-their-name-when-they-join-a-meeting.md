---
title: 允許使用者在商務用 Skype Online 中加入會議時記錄其名稱
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 瞭解如何啟用或停用使用者加入商務用 Skype Online 會議時是否可以錄製其名稱。
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114239"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>允許使用者在商務用 Skype Online 中加入會議時記錄其名稱

> [!Note]
> 如果您想要允許使用者在 Teams 中記錄其名稱，請參閱允許使用者在 Microsoft Teams 中加入會議時記錄 [其名稱](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)。

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到電話號碼和所謂的音訊會議橋接器。 會議橋接器可以包含一或多個電話號碼，可以是專用或共用的電話號碼。
  
會議橋接器會針對使用電話撥入會議的使用者接聽電話。 會議橋接器會以自動語音應答的語音提示來接聽來電者，然後視他們的設定播放通知、要求來電者錄製其名稱，以及設定會議召集人的 PIN 安全性。 PIN 會提供給會議召集人，讓他們可以開始會議。 不過，您可以進行設定，讓會議不需要 PIN。

## <a name="set-whether-callers-should-record-their-name"></a>設定來電者是否應該錄製其名稱
    
1. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **音訊會議**  >  **Microsoft 橋接器設定**。
    
2. 在 **會議加入體驗下**，請參閱標示為啟用會議 **進入和離開通知的核取方塊**。
    
   - **已選取** 來電者在進入會議之前，會要求他們先記錄他們的名稱。 這是預設選取的。
    
   - **已清除** 來電者在進入會議之前，不會被要求記錄他們的名稱。
    
3. 進行變更之後，請按一下 [**儲存。**
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet。
    
- Windows PowerShell 就是管理使用者，以及允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從 Windows PowerShell Online 版 Skype 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)