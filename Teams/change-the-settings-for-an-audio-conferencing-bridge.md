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
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '您可以在不使用商務用 Skype 或 Microsoft 團隊 app 的情況下，取得您變更會議橋的設定所需的步驟，用來提示來電者並收集會議召集人的名稱和釘選。 '
ms.openlocfilehash: b7ac85729bafe9d27f9e33cfa22597811b8d3d0b
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "37516949"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>變更音訊會議橋接器的設定

當您在 Office 365 中設定音訊會議時，您將會收到「音訊會議橋」的電話號碼供使用者使用。 [會議橋] 可以包含一或多個電話號碼。 當來電者撥入會議時，會用到這些電話號碼。 電話號碼包含在商務用 Skype 或 Microsoft 團隊會議邀請的底部。
  
[會議橋接] 會使用會議自動語音應答接聽來電，並使用語音提示提示來電者，然後根據您的設定，您可以播放通知、要求呼叫者記錄其名稱，以及控制 PIN 設定。 當使用者不是使用商務用 Skype 或 Microsoft 團隊 app 時，會為會議召集人提供 Pin，讓他們可以開始會議。

  > [!IMPORTANT]
  > 只有在商務用 Skype 或 Microsoft 團隊 app 使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都要撥入會議，會議召集人需要 PIN 才能啟動會議。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft [小組標誌] 的圖示](media/teams-logo-30x30.png) 使用 Microsoft 團隊系統管理中心

1. 在左側導覽中，前往 [**會議** > **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在 [**橋接器設定**] 窗格中，選取： 
   - **會議進入與結束通知**如果您關閉此功能，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。
    
     當您開啟**會議進入和結束通知**時，您可以選取下列選項：
    
   - **姓名或電話號碼**當使用者撥入會議時，系統會在他們加入會議時播放他們的電話號碼。
    
   - **聲音**當使用者撥入會議時，會在他們加入會議時播放音訊音調。
      
   - **要求呼叫者在加入會議前記錄他們的名稱**如果您關閉此功能，不會要求來電者在加入會議前記錄他們的名稱。

4. 若要設定會議的 PIN 長度，請在 [ **pin 長度**] 清單中，選取您想要的 pin 數位位數。

5. 若要指定是否要傳送電子郵件給使用者，請啟用或停用 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定變更**）。
    當[電子郵件的音訊會議設定在](emails-sent-to-users-when-their-settings-change-in-teams.md)[商務用 Skype Online 中的設定變更時](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，請參閱自動傳送給使用者的電子郵件，以取得詳細資訊。
 
6. 按一下 [**儲存**]。 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![顯示商務用 Skype 標誌的圖示](media/sfb-logo-30x30.png)  使用商務用 Skype 系統管理中心

 **設定呼叫者加入會議時的會議體驗**
    
1. 在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議** > **Microsoft 橋接器設定**]。
    
2. 在 [ **Microsoft 橋接器設定**] 頁面的 [**會議加入體驗**] 底下，選取：
    
   - [**啟用會議專案] 和 [結束通知] 以開啟**預設會選取此選項。 如果您清除該核取方塊，當有人進入或離開會議時，已加入會議的使用者就不會收到通知。
    
   - 當您選取 [**啟用會議進入] 和**[結束通知] 時，您可以從 [**進入/** 結束通知類型] 清單中選取這些選項：
    
   - **姓名或電話號碼**當使用者撥入會議時，系統會在他們加入會議時播放他們的電話號碼。
    
   - **聲音**當使用者撥入會議時，會在他們加入會議時播放音訊音調。
  
   - **要求呼叫者在加入會議前記錄他們的名稱**預設會選取此選項。 如果您清除該核取方塊，則不會要求呼叫者在加入會議前記錄他們的名稱。
    
3. 進行變更之後，按一下 [**儲存**]。
    
**設定會議的 PIN 長度**
  
1. 使用您的公司或學校帳戶登入 Office 365。
    
2. 移至**Microsoft 365 管理中心** > **商務用 Skype**。
    
3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
4. 在 [ **Microsoft 橋接器設定**] 頁面的 [**安全性**] 底下，于 [ **pin 長度**] 清單中輸入您想要的 pin 數位位數，然後按一下 [**儲存**]。
    
    > [!IMPORTANT]
    > PIN 必須在4到12位數之間。 
  
**選取是否要傳送電子郵件給您的使用者**
  
1. 使用您的公司或學校帳戶登入 Office 365。
    
2. 移至**Microsoft 365 管理中心** > **商務用 Skype**。
    
3. 在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。
    
4. 在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**如果使用者的撥入資訊變更，則自動傳送電子郵件給使用者**]，然後按一下 [**儲存**]。
    
    當[電子郵件的音訊會議設定在](emails-sent-to-users-when-their-settings-change-in-teams.md)[商務用 Skype Online 中的設定變更時](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)，請參閱自動傳送給使用者的電子郵件，以取得詳細資訊。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動執行此程式，您可以使用[CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) Cmdlet。
    
- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點： 
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  
## <a name="related-topics"></a>相關主題

[為 Microsoft 團隊設定音訊會議](set-up-audio-conferencing-in-teams.md)

[在商務用 Skype Online 中設定音訊會議](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
