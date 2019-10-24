---
title: 開啟或關閉商務用 Skype Online 中的進入與結束會議宣告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '瞭解如何使用商務用 Skype 系統管理中心來開啟或關閉商務用 Skype Online 會議中的進入與結束公告。 '
ms.openlocfilehash: 62b3437b75e36b57bebd167f6d2e155deb31a41b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642916"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>開啟或關閉商務用 Skype Online 中的進入與結束會議宣告

> [!Note]
> 如需在 Microsoft 團隊中進入與結束宣告的相關資訊，請參閱[開啟或關閉 Microsoft 團隊會議的進入與結束公告](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)。

當您在 Office 365 中設定音訊會議時，您會收到音訊會議橋。 [會議橋] 可以包含一或多個電話號碼，供人們撥入商務用 Skype 會議時使用。 
  
[會議橋接] 會使用電話撥入會議的使用者，接聽來電。 「會議橋接」會使用會議自動語音應答中的語音提示來應答來電者，然後根據您的設定，可以播放通知、要求呼叫者記錄其名稱，以及設定 PIN 安全性。 您可以將 PIN 提供給商務用 Skype 會議召集人，如果他們無法使用商務用 Skype app 來啟動會議，就能讓他們開始會議。 不過，您可以將它設定為不需要 PIN 就能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>設定會議加入選項
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
2. 在 [**會議加入體驗**] 底下，選取或清除 [**啟用會議專案] 和 [結束通知] 以開啟**。 預設會選取此選項。 如果您清除此選項，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。
    
3. 在 [**進入/結束宣告類型**] 底下，選取 [**名稱或電話號碼**] 或 [**聲音**]。
    
4. **在加入會議前，** 請核取或取消核取 [要求來電者] 來記錄其名稱。
    
5. 進行變更之後，按一下 [**儲存**]。
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet。
    
- 在 Windows PowerShell 中，商務用 Skype Online 就是管理使用者以及允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心（例如當您在一次為多位使用者進行設定變更時）。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[音訊會議常見問題](/MicrosoftTeams/audio-conferencing-common-questions)
