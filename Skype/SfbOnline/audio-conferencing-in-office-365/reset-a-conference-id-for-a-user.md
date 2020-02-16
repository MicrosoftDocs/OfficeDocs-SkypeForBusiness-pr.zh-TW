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
description: '瞭解在商務用 Skype Online 中重設使用者的會議 ID，以及取得會議更新與遷移工具的連結的步驟。 '
ms.openlocfilehash: 9a1c2766da021d30feb14954d6e69b6978b64bc9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986488"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>在商務用 Skype Online 中重設使用者的會議 ID

> [!NOTE]
> 如需在 Microsoft 團隊中重設會議 ID 的相關資訊，請參閱[在 Microsoft 團隊中重設使用者的會議 id](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。

[動態會議 ID] 包含在會議邀請的底部，以及撥入電話號碼，可供呼叫者用來撥入會議。 當使用者撥打電話號碼時，會議的自動回應會要求來電者輸入此會議 ID，才能出席會議。
  
> [!NOTE]
> 如果您的會議提供者是 Microsoft，您的使用者的會議 Id 會設定為 [僅限動態]。 此為無法變更。 只有啟用音訊會議的商務用 Skype 使用者才會自動設定會議 Id。 

## <a name="resetting-the-conference-id-for-a-user"></a>重設使用者的會議 ID
   
1. 在**商務用 Skype 系統管理中心**中，按一下 [**音訊會議** > **使用者**]，選取使用者，然後在 [**會議 ID** ] 底下的 [動作] 窗格中，按一下 [**重設**]。
    
2. 在 [**重設會議 ID？** ] 視窗中，按一下 **[是]**。 系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。 根據預設，電子郵件會傳送給使用者，但您可以關閉此功能。
    
> [!NOTE]
> 在您重設會議 ID 之後，具有新會議 ID 的電子郵件將會傳送給使用者。 此電子郵件將會傳送至主要電子郵件地址，在許多情況下，也會傳送到他們的 Office 365 信箱。 電子郵件包含新的會議 ID、預設的撥入電話號碼，以及使用商務用 Skype 會議更新工具來更新現有會議的指示。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 您可以在 [動作] 窗格中按一下 [透過**電子郵件傳送會議資訊**]，將所有會議資訊以包含會議 ID 和撥入電話號碼的電子郵件傳送給使用者。 它不會傳送 PIN。
    
- 會議 ID 會包含7位數，而且您無法在商務用 Skype 系統管理中心或使用 Windows PowerShell 來變更它的長度。
    
- 重設之後，您可以在 [**會議 id**] 底下看到新的會議 ID。
    
- 當您在 [**使用者**] 頁面上選取使用者時，可以在 [**音訊會議**] 底下的 [動作] 窗格底部，查看 [音訊會議] 使用者的會議 ID。
    
- 在建立新的會議 ID 之後，不能讓呼叫者使用舊的會議 id。 您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。 使用者可以使用商務用 Skype 會議工具來更新現有的會議。 若要瞭解如何下載、安裝及執行商務用 Skype 會議更新工具，請參閱：
    
  - [商務用 Skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [商務用 Skype Online，會議遷移工具（64位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [商務用 Skype Online，會議遷移工具（32位）](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要使用 Windows PowerShell，請參閱管理使用者和允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin.md)
