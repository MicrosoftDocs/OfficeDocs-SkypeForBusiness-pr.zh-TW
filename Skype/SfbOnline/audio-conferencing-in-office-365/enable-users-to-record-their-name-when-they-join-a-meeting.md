---
title: 讓使用者在商務用 Skype Online 中加入會議時，記錄他們的名稱
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
description: 瞭解如何啟用或停用您的使用者在商務用 Skype Online 中加入會議時，是否可以記錄他們的名稱。
ms.openlocfilehash: 88c1a24acc6d623410ec8048a7e41d5c9f17d637
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707208"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>讓使用者在商務用 Skype Online 中加入會議時，記錄他們的名稱

> [!Note]
> 如果您想要允許使用者在小組中記錄他們的名稱，請參閱在[Microsoft 團隊中加入會議時，讓使用者記錄其名稱](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)。

當您在 Office 365 中設定音訊會議時，您將會收到電話號碼，也就是「音訊會議橋」。 [會議橋] 可以包含一或多個可以是專用或共用電話號碼的電話號碼。
  
[會議橋接] 會使用電話撥入會議的使用者，接聽來電。 「會議橋接」會從自動語音應答中向來電者提供語音提示，然後根據其設定，可以播放通知、要求呼叫者記錄其名稱，以及設定會議召集人的 PIN 安全性。 提供給會議召集人的 Pin，讓他們可以開始會議。 不過，您可以設定它，讓您不需要 PIN 就能開始會議。

## <a name="set-whether-callers-should-record-their-name"></a>設定呼叫者是否應記錄其名稱
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
2. 在 [**會議加入體驗**] 底下，請參閱標示為 [**啟用會議專案] 和**[結束通知] 的核取方塊。
    
   - **選取**來電者進入會議前，系統會要求呼叫者先記錄他們的名稱。 預設會選取此選項。
    
   - 已**清除**在進入會議前，不會要求來電者記下其名稱。
    
3. 進行變更之後，按一下 [**儲存**]。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) Cmdlet。
    
- Windows PowerShell 全部說明如何管理使用者，以及使用者可以執行哪些動作。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
