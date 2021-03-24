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
description: 變更音訊會議橋接器設定，包括進入和離開通知、播放名稱或電話號碼、鈴聲，以及提示來電者錄製其名稱。
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102639"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>變更音訊會議橋接器的設定

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到來自所謂的音訊會議橋接器的使用者電話號碼。 一個會議橋接器可以包含一或多個電話號碼。 當來電者撥入會議時，會使用這些電話號碼。 電話號碼會包含在商務用 Skype 或 Microsoft Teams 會議邀請的底部。
  
會議橋接器會接聽來電，然後使用會議自動語音應答提示來電者，然後視您的設定播放通知、要求來電者錄製名稱，以及控制 PIN 設定。 PIN 會提供給會議召集人，讓他們在未使用商務用 Skype 或 Microsoft Teams App 時開始會議。

  > [!IMPORTANT]
  > 只有當商務用 Skype 或 Microsoft Teams 應用程式使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器」 **頁面頂端** ，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** ，選取： 
   - **會議進入和離開通知** 如果您關閉此功能，當某人進入或離開會議時，已加入會議的使用者不會收到通知。
    
     當您開啟會議 **專案並離開通知** 時，您可以選取這些選項：
    
   - **名稱或電話號碼** 當使用者撥入會議時，當他們加入會議時，就會播放其電話號碼。
    
   - **色調** 當使用者撥入會議時，當他們加入會議時，會播放音訊鈴聲。
      
   - **要求來電者在加入會議前先錄製他們的名稱** 如果您關閉此功能，不會要求來電者在加入會議之前先記錄他們的名稱。

4. 若要設定會議的 PIN 長度，請在 PIN 長度清單中選取 PIN **的位數** 。

5. 若要指定是否要傳送電子郵件給使用者，請啟用或停用如果使用者的音訊會議組組變更時自動 **傳送電子郵件給使用者**。
    請參閱 [在 Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) 中的音訊會議設定變更時自動將電子郵件發送給使用者，或當使用者的商務用 [Skype Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 設定變更時，將電子郵件發送給使用者以瞭解更多資訊。
 
6. 按一下 [儲存]。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化此程式，您可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) Cmdlet。
    
- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從商務用 Skype Online 版 Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

[設定商務用 Skype Online 的音訊會議](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)