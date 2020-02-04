---
title: 在商務用 Skype Online 中設定音訊會議的自動助理語言
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
description: 瞭解如何在商務用 Skype Online 中為音訊會議編號選取音訊會議自動語音應答語言。
ms.openlocfilehash: 22c3ad1d2386dec07060548cd055a5d289db4364
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680380"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>在商務用 Skype Online 中設定音訊會議的自動助理語言

> [!Note]
> 如需在 Microsoft 團隊中設定自動助理語言的相關資訊，請參閱[在 Microsoft 團隊中設定音訊會議的自動助理語言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。

商務用 Skype 的音訊會議自動語音應答，在加入會議時，可以向音訊撥號者使用多種不同的語言。
  
選擇一種主要語言，以及最多四個次要語言。 您首先會使用您所設定的主要語言，並依您選取的順序，自動助理會使用次要語言。 
  
> [!NOTE]
>  您只能變更專用類別之音訊會議號碼的語言。 無法變更共用音訊會議號碼的語言。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>設定會議自動語音應答語言

您必須是[Office 365 全域系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或[商務用 Skype 系統管理員](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能執行這個步驟。
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**舊版入口網站**]。 在舊版入口網站中，選取 [**音訊會議**]，然後按一下 [ **Microsoft 橋接器**]。
    
2. 從清單中選取音訊會議電話號碼，然後在 [動作] 窗格中，按一下 [**設定語言**]。 只可以變更專用音訊會議號碼的語言。  
    
3. 在 [**設定語言**] 頁面上，按一下 [**主要語言**] 清單，以查看可用語言的完整清單。 如有需要，請按一下每個**次要語言**清單，選取 [次要語言]。
    
    > [!NOTE]
    > 列出支援的主要和次要語言。 您在清單中選取它們的順序就會是提供給呼叫者的語言順序。 
  
4. 按一下 [**儲存**]。
    
## <a name="want-else-should-i-know"></a>還需要知道嗎？

- 若要查看音訊會議支援的語言清單，請參閱[音訊會議支援的語言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 您可以將 [語言] 設定為 [專用]，而不是用於共用的電話號碼。
    
- 若要查看 Office 365 中可使用 Microsoft 作為提供者的音訊會議的國家/地區清單，請參閱[音訊會議的電話號碼](phone-numbers-for-audio-conferencing.md)。
    
## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell 嗎？

若要自動化此步驟，您可以使用[CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684) Cmdlet。
  
若要深入瞭解，請參閱[使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
