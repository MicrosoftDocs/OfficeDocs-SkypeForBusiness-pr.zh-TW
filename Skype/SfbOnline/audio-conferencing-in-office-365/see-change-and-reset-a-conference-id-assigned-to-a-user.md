---
title: 在商務用 Skype Online 中，查看、變更及重設指派給使用者的會議 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: '瞭解如何在商務用 Skype Online 中將會議 ID 指派給使用者，以及會議 Id 參數的用途。 '
ms.openlocfilehash: caa94984b06ff73d8f14acf4727870a988298974
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163911"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>在商務用 Skype Online 中查看及重設指派給使用者的會議 ID

> [!Note]
> 如需 Microsoft 團隊中使用者會議 Id 的相關資訊，請參閱[在 Microsoft 團隊中查看及重設指派給使用者的會議 id](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。

當您在 Microsoft 365 或 Office 365 中設定音訊會議，且使用 Microsoft 作為音訊會議提供者時，會議 ID 會自動指派給商務用 Skype 使用者。 在會議排程時，指派的會議 ID 會在會議邀請中傳送。 使用者排程的每個會議都會指派唯一的會議 ID。

雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或是您的使用者無法記住或遺失其會議 ID。 您可以使用**商務用 Skype 系統管理中心**和 Windows PowerShell 來查看、變更及重設其會議 ID。

系統會傳送電子郵件給使用者，並提供會議 ID 和預設的音訊會議電話號碼; 或者，如果您重設會議 ID，就會傳送不同的電子郵件，並包含會議 ID，但不包含 PIN。 如需重設會議召集人 PIN 的詳細資訊，請[移至這裡](reset-a-conference-id-for-a-user.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>查看及重設會議 Id

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

您可以查看其會議 ID 並傳送給使用者。

1. 使用您的公司或學校帳戶登入。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**> **音訊會議** > **使用者**中，選取需要會議 ID 的使用者。

4. 在 [動作] 頁面中，查看 [**會議 ID**] 底下。

    > [!TIP]
    > 您可以在 [**使用者**] 頁面上選取使用者之後，按一下 [透過**電子郵件傳送會議資訊**] 連結，在包含會議 ID 和音訊電話號碼的電子郵件中，傳送所有會議資訊給使用者。

**使用 Windows PowerShell**

您可以使用 Windows PowerShell 來查看使用者的會議 ID。 若要這樣做，請執行：

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

若要深入瞭解 Cmdlet，請參閱[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 ) 。


### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

您可以重設使用者的會議 ID （例如忘記它）。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 使用您的公司或學校帳戶登入。

2. 移至 [系統管理中心] > [**商務用 Skype**]。

3. 在**商務用 Skype 系統管理中心**> **音訊會議** > **使用者**的 [動作] 窗格中，按一下 [**會議 ID**] 底下的 [**重設**]。

4. 在 [**重設會議 ID？** ] 視窗中，按一下 **[是]**。 系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。

**使用 Windows PowerShell**

您可以使用 Windows PowerShell 來重設使用者的會議 ID。 若要這樣做，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>您還應該知道什麼？

   > [!IMPORTANT]
   >  在建立新的會議 ID 或重新設定之後，舊的會議 ID 無法由呼叫者使用。 您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。 使用者可以使用商務用 Skype 會議遷移工具來更新現有的會議。 若要瞭解如何下載、安裝及執行此工具，請參閱：[適用于商務用 skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[商務用 Skype Online、會議遷移工具（64位）](https://go.microsoft.com/fwlink/?LinkID=626047)，以及[商務用 Skype online、會議遷移工具（32位）](https://www.microsoft.com/download/details.aspx?id=54079)。

- 若要深入瞭解 Cmdlet，請參閱[設定 get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 。

- 會議 ID 必須符合在音訊會議橋設定的位數長度。 您不能在會議 Id 中使用字母或特殊字元;只有數位可以使用。

- 每個音訊會議使用者的會議 ID 預設會是7位數，且位數無法變更。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要使用 Windows PowerShell，請參閱管理使用者和允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點管理 Microsoft 365 或 Office 365 及商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：

  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

