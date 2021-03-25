---
title: 在商務用 Skype Online 中設定音訊會議自動語音服務語言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: 瞭解如何在商務用 Skype Online 中為音訊會議號碼選取音訊會議自動語音服務語言。
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109995"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在商務用 Skype Online 中設定音訊會議自動語音服務語言

> [!Note]
> 有關在 Microsoft Teams 中設定自動語音翻譯語言的資訊，請參閱在 Microsoft Teams 中設定音訊會議 [自動語音語音處理語言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

商務用 Skype 的音訊會議自動語音機可在語音來電者加入會議時，以多種語言向來電者致意。
  
選擇一種主要語言，最多四種次要語言。 您設定的主要語言會先使用，而次要語言會由自動翻譯使用，以便您選取。 
  
> [!NOTE]
>  您只可以變更專屬類別之音訊會議號碼的語言。 無法變更共用音訊會議號碼的語言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>設定會議自動語音服務語言

您必須是全域[系統管理員或](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)[商務用 Skype 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能執行此步驟。
    
1. 在商務 **用 Skype 系統管理中心** 左側的流覽中，前往 **舊版入口網站**。 進入舊版入口網站後，選取 **[音訊會議**，然後按一下 **Microsoft 橋接器**。
    
2. 從清單中選取音訊會議電話號碼，然後按一下 [動作窗格設定 **語言**> 。 只能變更專用音訊會議號碼的語言。  
    
3. 在 [ **設定語言>** 頁面上，按一下 **[主要** 語言清單> 以查看可用語言的完整清單。 如果需要，請按一下每個次要 **語言清單以** 選取次要語言。
    
    > [!NOTE]
    > 系統列出支援的主要和次要語言。 在清單中選取它們的順序，就是呈現給來電者的語言順序。 
  
4. 按一下 [儲存]。
    
## <a name="want-else-should-i-know"></a>想要我應該知道嗎？

- 若要查看音訊會議支援的語言清單，請參閱 [音訊會議支援的語言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 語言可以設定為專用，但不能設定為共用電話號碼。
    
- 若要查看在 Microsoft 365 或 Office 365 中提供使用 Microsoft 作為提供者的音訊會議可用的國家/地區清單，請參閱音訊會議 [的電話號碼](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell 嗎？

若要自動化此步驟，您可以使用 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) Cmdlets。
  
若要深入瞭解，請參閱 [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)