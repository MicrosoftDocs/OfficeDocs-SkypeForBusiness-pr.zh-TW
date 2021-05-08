---
title: 在 商務用 Skype 中設定音訊會議商務用 Skype語言
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
description: 瞭解如何在 商務用 Skype Online 中選取音訊會議自動語音商務用 Skype語言。
ms.openlocfilehash: 714312989bc3898fea2ed0d335fed8f5f2eebbb3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237019"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在 商務用 Skype 中設定音訊會議商務用 Skype語言

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關在 Microsoft Teams 中設定自動語音語音Microsoft Teams，請參閱在 Microsoft Teams 中設定音訊會議[自動語音Microsoft Teams。](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)

音訊會議自動語音商務用 Skype語音通話者加入會議時，可以使用多種語言向來電者打招呼。
  
選擇一種主要語言，最多四種次要語言。 您設定的主要語言會先使用，而次要語言會由自動翻譯使用，以便您選取。 
  
> [!NOTE]
>  您只可以變更專屬類別之音訊會議號碼的語言。 無法變更共用音訊會議號碼的語言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>設定會議自動語音服務語言

您必須是全域[系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[商務用 Skype才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)執行此步驟。
    
1. 在 商務用 Skype **系統管理中心**，在左側流覽中，前往舊版 **入口網站**。 進入舊版入口網站後，選取 **[音訊會議**，然後按一下 **Microsoft 橋接器**。
    
2. 從清單中選取音訊會議電話號碼，然後按一下 [動作窗格設定 **語言**> 。 只能變更專用音訊會議號碼的語言。  
    
3. 在 [ **設定語言>** 頁面上，按一下 **[主要** 語言清單> 以查看可用語言的完整清單。 如果需要，請按一下每個次要 **語言清單以** 選取次要語言。
    
    > [!NOTE]
    > 系統列出支援的主要和次要語言。 在清單中選取它們的順序，就是呈現給來電者的語言順序。 
  
4. 按一下 [儲存]。
    
## <a name="want-else-should-i-know"></a>想要我應該知道嗎？

- 若要查看音訊會議支援的語言清單，請參閱 [音訊會議支援的語言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 語言可以設定為專用，但不能設定為共用電話號碼。
    
- 若要查看使用 Microsoft 作為提供者的 Microsoft 365 或 Office 365 音訊會議可用的國家/地區清單，請參閱音訊會議電話[號碼。](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>想要使用Windows PowerShell？

若要自動化此步驟，您可以使用 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) Cmdlets。
  
若要深入瞭解，請參閱[使用 Windows PowerShell 執行商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
