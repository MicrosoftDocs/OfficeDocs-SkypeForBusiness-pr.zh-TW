---
title: 在商務用 Skype Online 中查看已啟用音訊會議的使用者清單
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
description: '瞭解如何在商務用 Skype 系統管理中心中，查看您組織中已啟用電話撥入式會議的使用者清單。 '
ms.openlocfilehash: 206bd52d1b2e0cfc1a72bb557c5d5dc4c0162534
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163922"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>在商務用 Skype Online 中查看已啟用音訊會議的使用者清單

> [!NOTE]
> 如需在 Microsoft 團隊中啟用使用者的相關資訊，請參閱[在 Microsoft 團隊中查看已啟用音訊會議的使用者清單](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)。

在貴組織中啟用商務用 Skype 使用者以進行音訊會議之後，您就可以查看已啟用的使用者清單。 當您查看清單時，系統會針對清單中的每位使用者，查看其所使用的音訊會議提供者類型、使用者的預設撥入電話號碼，以及貴組織是否未啟用動態會議 Id，以及他們所組織的音訊會議會議的靜態會議 Id。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>查看使用者清單

   
- 在左側導覽中，移至 [**音訊會議** > **使用者**]。

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 當您查看已啟用的使用者清單時，您可以從清單中選取使用者，然後使用 [動作] 窗格來編輯該使用者的音訊會議設定。
    
- 當您選取一個被設定為使用 Microsoft 作為音訊會議提供者的使用者時，您可以查看預設的電話號碼，以及您的組織是否已啟用動態會議 Id，而且您可以重設使用者所組織之會議的會議 ID。
    
- 當您選取一個被設定為使用協力廠商音訊會議提供者的使用者時，您可以查看音訊會議提供者的名稱、付費電話號碼，以及免付費電話號碼（如果已設定）。
    
- 您可以使用篩選選項來顯示具有下列專案的使用者：
    
  - **音訊會議開啟**
    
  - **音訊會議關閉**
    
  - **會議提供者-Microsoft**
    
  - **會議提供者-其他**
    
- 您可以使用 [搜尋] 按鈕來搜尋清單中的個別使用者。
    
- 您可以選取一個以上的使用者，然後執行下列動作：
    
  - 為這些使用者選取不同的預設號碼。
    
  - 將提供者變更為 [**無**]，即可關閉使用者的音訊會議。
    
  - 如果使用者已獲指派**音訊會議**授權，請切換至 Microsoft 作為音訊會議提供者。
    
  - 允許/不允許匿名使用者啟動所選使用者的電話會議。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
