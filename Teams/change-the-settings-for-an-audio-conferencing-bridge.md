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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 變更音訊會議橋接器設定，包括進入和離開通知、播放名稱或電話號碼、鈴聲，以及提示來電者錄製其名稱。
ms.openlocfilehash: 434142eb0e7d8cd4759eec180e903eaecad47525
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607850"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>變更音訊會議橋接器的設定

當您在 Microsoft 365 或 Office 365 中設定音訊會議時，您會收到使用者從稱為音訊會議橋接器的電話號碼。 一個會議橋接器可以包含一或多個電話號碼。 當來電者撥入會議時，會使用這些電話號碼。 電話號碼會包含在會議邀請或商務用 Skype Microsoft Teams底端。
  
會議橋接器會接聽來電，然後使用會議自動語音應答提示來電者，然後視您的設定播放通知、要求來電者錄製名稱，以及控制 PIN 設定。 PIN 會提供給會議召集人，讓他們在未使用應用程式或商務用 Skype時Microsoft Teams會議。

  > [!IMPORTANT]
  > 只有當應用程式使用者尚未啟動會議商務用 Skype或Microsoft Teams，會議召集人才需要 PIN。 如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。 

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
      
   - **要求來電者在加入會議前先錄製其名稱** 如果您關閉此功能，不會要求來電者在加入會議之前先記錄他們的名稱。

4. 若要設定會議的 PIN 長度，請在 PIN 長度清單中選取 PIN **的位數** 。

5. 若要指定是否要傳送電子郵件給使用者，請啟用或停用如果使用者的音訊會議組組變更時自動 **傳送電子郵件給使用者**。
    請參閱[當使用者](emails-sent-to-users-when-their-settings-change-in-teams.md)的音訊會議設定在 Microsoft Teams 中變更時自動發送給使用者的電子郵件，或當使用者的設定在 商務用 Skype [Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)中變更時，將電子郵件發送給使用者。詳細資訊。
 
6. 按一下 [儲存]。 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 若要節省時間或自動化此程式，您可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) Cmdlet。
    
- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。 此模組僅支援 64 位電腦，可從 Microsoft 下載中心下載，Windows PowerShell Online 商務用 Skype[模組。](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

[設定適用于線上商務用 Skype會議](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)