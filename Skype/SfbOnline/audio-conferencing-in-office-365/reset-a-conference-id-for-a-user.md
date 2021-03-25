---
title: 在商務用 Skype Online 中重設使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: '瞭解在商務用 Skype Online 中重設使用者會議 ID 的步驟，並取得會議更新和移移工具的連結。 '
ms.openlocfilehash: 424b0dfb24d6034af20c18a0172221a09bef5ecd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114209"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>在商務用 Skype Online 中重設使用者的會議 ID

> [!NOTE]
> 有關在 Microsoft Teams 中重設會議 ID 的資訊，請參閱為 Microsoft Teams 中的使用者重設會議[ID。](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

動態會議 ID 會包含在會議邀請的底部，以及來電者可用來撥入會議的電話撥入電話號碼。 當使用者撥打電話號碼時，會議的自動語音機會要求來電者輸入此會議 ID，以便他們參加會議。
  
> [!NOTE]
> 如果您的會議提供者是 Microsoft，使用者的會議 ID 會設定為 Dynamic Only。 這無法變更。 系統只會針對已啟用音訊會議功能的商務用 Skype 使用者自動設定會議 ID。 

## <a name="resetting-the-conference-id-for-a-user"></a>為使用者重設會議 ID
   
1. 在商務 **用 Skype 系統管理中心** 中，按一下 [音訊會議使用者」，選取使用者，然後在 [動作窗格的 [會議  >  **** **ID>** 下，按一下 [**重設**。
    
2. 在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。 根據預設，電子郵件會寄給使用者，但可以關閉此功能。
    
> [!NOTE]
> 重設會議 ID 之後，系統就會將一封包含新會議 ID 的電子郵件寄給使用者。 在許多情況下，此電子郵件會寄到主要電子郵件地址，包括其 Microsoft 365 或 Office 365 信箱。 電子郵件包含新的會議 ID、預設撥入 (電話號碼) 以及使用商務用 Skype 會議更新工具更新現有會議的指示。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 您可以在包含會議 ID 和撥入電話號碼的電子郵件中，按一下動作窗格中的使用者以電子郵件傳送會議資訊，以傳送所有會議資訊給使用者。 它不會傳送 PIN。
    
- 會議 ID 會包含 7 位數，而且您無法變更商務用 Skype 系統管理中心或 Windows PowerShell 的長度。
    
- 重設之後，您可以在會議 ID 下看到新的會議 **ID。**
    
- 當您選取使用者頁面上的使用者時，可在音訊會議下的動作窗格底部查看音訊會議使用者的會議 **ID。** 
    
- 建立新會議 ID 之後，來電者無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 使用者可以使用商務用 Skype 會議工具更新現有的會議。 若要瞭解如何下載、安裝及執行商務用 Skype 會議更新工具，請參閱：
    
  - [商務用 Skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [商務用 Skype Online、會議移 (64 位) ](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [商務用 Skype Online、會議移 (32 位) ](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 當涉及 Windows PowerShell 時，所有內容都是關於管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin.md)