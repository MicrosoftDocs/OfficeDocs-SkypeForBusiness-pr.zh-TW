---
title: 變更音訊會議橋接器的設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 變更音訊會議橋接器設定，包括進入與離開通知、播放名稱或電話號碼、鈴聲，以及提示來電者錄下他們的名稱。
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918699"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>變更音訊會議橋接器的設定

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，會從所謂的音訊會議橋接器收到使用者的電話號碼。 一個會議橋接器可以包含一或多個電話號碼。 這些電話號碼在來電者撥入會議時會使用。 電話號碼會包含在商務用 Skype 或 Microsoft Teams 會議邀請的底部。
  
會議橋接器會以會議自動語音應答的語音提示接聽來電並提示來電者，然後視您的設定來播放通知、要求來電者錄下他們的名稱，以及控制 PIN 設定。 當 PIN 不在使用商務用 Skype 或 Microsoft Teams 應用程式時，會提供給會議召集人，讓他們開始會議。

  > [!IMPORTANT]
  > 只有當商務用 Skype 或 Microsoft Teams 應用程式使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都撥入會議，會議召集人需要 PIN 才能開始會議。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側流覽區中，前往 **會議**  >  **橋接器**。 

2. 在會議橋接器頁面 **頂端** ，按一下 [ **橋接器設定**。 

3. 在橋接器 **設定窗格中** ，選取： 
   - **會議進入與離開通知** 如果您關閉此功能，已加入會議的使用者就不會在有人進入或離開會議時收到通知。
    
     當您開啟會議進入 **與離開通知時**，您可以選取這些選項：
    
   - **名稱或電話號碼** 當使用者撥入會議時，就會在加入會議時播放其電話號碼。
    
   - **鈴聲** 當使用者撥入會議時，當他們加入會議時，會播放音訊鈴聲。
      
   - **要求來電者在加入會議前記錄他們的名稱** 如果您關閉此功能，系統就不會要求來電者在加入會議前記錄他們的名稱。

4. 若要設定會議的 PIN 長度，請在 PIN 長度清單中選取 PIN 的 **位數** 。

5. 若要指定是否要傳送電子郵件給使用者，請啟用或停用當使用者的音訊會議組式變更時自動 **傳送電子郵件給使用者**。
    請參閱 [當使用者在 Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) 中的音訊會議設定變更時自動將電子郵件發送給使用者，或當使用者在商務用 [Skype Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 中的設定變更時，將電子郵件發送給使用者，以瞭解更多資訊。
 
6. 按一下 **[儲存]**。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項程式自動化，您可以使用 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) Cmdlet。
    
- Windows PowerShell 的用場就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 在速度、簡化及生產力方面有許多優點，是僅用 Microsoft 365 系統管理中心所沒有的，例如當您要一次為許多使用者變更設定時。 在下列主題中瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位的電腦，可從商務用 Skype Online 的 Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

[設定商務用 Skype Online 的音訊會議](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
