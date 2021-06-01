---
title: 查看在 商務用 Skype Online 中啟用音訊會議商務用 Skype清單
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
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
description: '瞭解如何在系統管理中心內，查看組織中已啟用電話撥入式會議商務用 Skype清單。 '
ms.openlocfilehash: 070b11c047ec90413128995196b99872a0884663
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236999"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>查看在 商務用 Skype Online 中啟用音訊會議商務用 Skype清單

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 請參閱在 Microsoft Teams 中查看已啟用音訊會議的使用者[Microsoft Teams。](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

在貴組織中商務用 Skype使用者進行音訊會議之後，您可以查看已啟用的使用者清單。 當您查看清單時，您也會在清單中為每個使用者看到他們使用的音訊會議提供者類型、使用者的預設撥入電話號碼，以及如果您的組織未啟用動態會議 ID，即他們組織之音訊會議會議的靜態會議 ID。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>檢視使用者清單

   
- 在左側流覽中，前往 **音訊會議**  >  **使用者**。

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 當您查看已啟用的使用者清單時，可以從清單中選取使用者，並使用動作窗格編輯該使用者的音訊會議設定。
    
- 當您選取已設定為使用 Microsoft 做為音訊會議提供者的單一使用者時，您可以查看預設電話號碼，以及貴組織是否已啟用動態會議 ID，也可以重設使用者組織的會議 ID。
    
- 當您選取已設定為使用協力廠商音訊會議提供者的單一使用者時，您可以查看音訊會議提供者的名稱、付費電話號碼，以及免付費電話號碼 (如果他們已設定) 。
    
- 您可以使用篩選選項來顯示具有：
    
  - **音訊會議在**
    
  - **音訊會議關閉**
    
  - **會議提供者 - Microsoft**
    
  - **會議提供者 - 其他**
    
- 您可以使用搜尋按鈕搜尋清單中的個別使用者。
    
- 您可以選取多個使用者，然後執行下列操作：
    
  - 為這些使用者選取不同的預設號碼。
    
  - 將提供者變更為 None 以關閉使用者的音訊 **會議**。
    
  - 如果使用者已指派音訊會議授權，請切換到 Microsoft 做為音訊 **會議提供者。**
    
  - 允許/不允許匿名使用者啟用選取的使用者電話會議。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
