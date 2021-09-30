---
title: 讓使用者在加入線上會議時商務用 Skype名稱
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 瞭解如何啟用或停用使用者加入線上會議時，是否可以商務用 Skype名稱。
ms.openlocfilehash: 6f1c6c5d582665f411eaa17b76e7c1922ee9e468
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012947"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>讓使用者在加入線上會議時商務用 Skype名稱

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 如果您想要允許使用者在 Teams 中記錄其名稱，請參閱允許使用者在 Microsoft Teams 中加入會議時記錄[Microsoft Teams。](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到電話號碼和所謂的音訊會議橋接器。 會議橋接器可以包含一或多個電話號碼，可以是專用或共用的電話號碼。
  
會議橋接器會針對使用電話撥入會議的使用者接聽電話。 會議橋接器會以自動語音應答的語音提示來接聽來電者，然後視他們的設定播放通知、要求來電者錄製其名稱，以及設定會議召集人的 PIN 安全性。 PIN 會提供給會議召集人，讓他們可以開始會議。 不過，您可以進行設定，讓會議不需要 PIN。

## <a name="set-whether-callers-should-record-their-name"></a>設定來電者是否應該錄製其名稱
    
1. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。
    
2. 在 **會議加入體驗** 下，請參閱標示為啟用會議 **進入和離開通知的核取方塊**。
    
   - **已選取** 來電者在進入會議之前，會要求他們先記錄他們的名稱。 這是預設選取的。
    
   - **已清除** 來電者在進入會議之前，不會要求他們記錄其名稱。
    
3. 進行變更之後，請按一下 [**儲存。**
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Cmdlet。
    
- Windows PowerShell管理使用者，以及允許使用者做什麼。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 powerShell Microsoft 365或Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援 64 位電腦，可從 Microsoft 下載中心下載並安裝[PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)模組Teams模組。
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
