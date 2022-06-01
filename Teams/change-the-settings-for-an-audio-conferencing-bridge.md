---
title: 變更音訊會議橋接器的設定
ms.author: heidip
author: MicrosoftHeidi
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
description: 變更音訊會議橋接器設定，包括進入和結束通知、播放名稱或電話號碼、音調，以及提示來電者錄製其名稱。
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823042"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>變更音訊會議橋接器的設定

在 Microsoft 365 或 Office 365 中設定音訊會議時，您會從所謂的音訊會議橋接器接收使用者的電話號碼。 一個會議橋接器可以包含一或多個電話號碼。 這些電話號碼會在來電者撥入會議時使用。 電話號碼會包含在商務用 Skype或Microsoft Teams會議邀請的底部。
  
會議橋接器會使用會議自動語音應答，以語音提示接聽來電並提示來電者，然後根據您的設定播放通知、要求來電者錄下他們的名稱，以及控制 PIN 設定。 系統會提供 PIN 給會議召集人，讓他們在不使用商務用 Skype或Microsoft Teams應用程式時召開會議。

  > [!IMPORTANT]
  > 只有當商務用 Skype或Microsoft Teams應用程式使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都要撥入會議，會議召集人必須使用 PIN 才能開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 **會議**  >  **橋接器**。

2. 在 [ **會議橋接器** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定]** 窗格中，選取：
   - **會議進入和結束通知** 如果您關閉此功能，當有人進入或離開會議時，已加入會議的使用者將不會收到通知。

     當您開啟 **會議進入和結束通知** 時，您可以選取下列選項：

   - **名稱或電話號碼** 當使用者撥入會議時，他們的電話號碼會在加入會議時播放。

   - **色調** 當使用者撥入會議時，會在加入會議時播放音訊鈴聲。

   - **在加入會議之前要求來電者記錄他們的名稱** 如果您關閉此功能，來電者加入會議前就不會被要求記錄他們的名稱。

4. 若要設定會議的 PIN 長度，請選取 PIN **長度** 清單中 PIN 所需的位數。

5. 若要指定是否要傳送電子郵件給使用者，請啟用或停用 **在使用者的音訊會議設定變更時自動傳送電子郵件給使用者**。
    如需詳細資訊，請參閱[當Microsoft Teams中的音訊會議設定變更時自動傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change-in-teams.md)，或[當使用者在 商務用 Skype Online 中設定變更時傳送給使用者的電子郵件](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)。

6. 按一下 [儲存]。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用Windows PowerShell管理嗎？

- 若要節省時間或將此程式自動化，您可以使用 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) Cmdlet。

- Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理Microsoft 365或Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [使用 Windows PowerShell 管理Microsoft 365或Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell在速度、簡易性和生產力方面有許多優點，比起只使用Microsoft 365 系統管理中心，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：

  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 執行一般商務用 Skype線上管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > 商務用 Skype Online 的Windows PowerShell模組可讓您建立連線到 商務用 Skype Online 的遠端Windows PowerShell會話。 只有 64 位電腦才支援此模組，可從 Microsoft 下載中心下載[，網Windows PowerShell Module for 商務用 Skype Online。](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)
  
## <a name="related-topics"></a>相關主題

[設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md)

[設定 商務用 Skype Online 的音訊會議](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
