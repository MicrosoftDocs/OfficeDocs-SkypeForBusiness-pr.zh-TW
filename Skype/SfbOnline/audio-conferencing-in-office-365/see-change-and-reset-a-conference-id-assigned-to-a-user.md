---
title: 查看、變更及重設在商務用 Skype Online 中指派給使用者的會議 ID
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
description: '瞭解如何在商務用 Skype Online 中指派會議 ID 給使用者，以及會議 ID 參數應該是什麼。 '
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110009"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>在商務用 Skype Online 中，查看並重設指派給使用者的會議 ID

> [!Note]
> 若要瞭解 Microsoft Teams 中的使用者會議 ID，請參閱在 Microsoft Teams 中查看並重設指派給使用者[的會議 ID。](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

當商務用 Skype 使用者在 Microsoft 365 或 Office 365 中設定音訊會議並使用 Microsoft 做為音訊會議提供者時，系統會自動指派會議 ID 給該使用者。 會議排程時，指派的會議 ID 會以會議邀請進行。 使用者排程的每個會議都會獲得一個唯一的會議識別碼。

雖然會議 ID 會自動建立並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。 您可以使用商務用 **Skype 系統** 管理中心和 Windows PowerShell 來查看、變更及重設其會議 ID。

電子郵件會以會議 ID 和預設的音訊會議電話號碼寄給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。 有關重設會議召集人 PIN 的資訊， [請前往這裡](reset-a-conference-id-for-a-user.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>查看和重設會議 ID

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

您可以查看他們的會議 ID，並將它傳送給使用者。

1. 使用公司或學校帳戶來登錄。

2. 前往商務用 Skype > **系統管理中心**。

3. 在商務 **用 Skype 系統管理中心** >  **音訊會議**  >  **使用者** 中，選取需要會議 ID 的使用者。

4. 在動作頁面中，查看會議 **ID 下的**。

    > [!TIP]
    > 您可以在選取使用者頁面上的使用者之後，按一下透過電子郵件傳送會議資訊，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議 **資訊給使用者**。

**使用 Windows PowerShell**

您可以使用 Windows PowerShell 來查看使用者的會議 ID。 若要這麼做，請執行：

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

請參閱 [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。


### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

例如，如果使用者忘記會議 ID，您可以重設會議 ID。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 使用公司或學校帳戶來登錄。

2. 前往商務用 Skype > **系統管理中心**。

3. 在商務 **用 Skype 系統管理中心** 音訊會議使用者中，按一下 [會議識別碼》 下的 [動作窗格> >    >  中的 [**重設**。 

4. 在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。

**使用 Windows PowerShell**

您可以使用 Windows PowerShell 來重設使用者的會議 ID。 若要這麼做，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>您還需要知道什麼？

   > [!IMPORTANT]
   >  建立新會議 ID 或重設會議 ID 之後，來電者即無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 使用者可以使用商務用 Skype 會議移移工具更新現有的會議。 若要瞭解如何下載、安裝及執行工具，請參閱：商務用 Skype 和 [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的會議更新工具、商務用 Skype Online、會議移移工具 [ (64 ](https://go.microsoft.com/fwlink/?LinkID=626047)位) ，以及商務用 Skype Online、會議移移工具  [ (32 ](https://www.microsoft.com/download/details.aspx?id=54079)位) 。

- 請參閱 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。

- 會議 ID 必須符合音訊會議橋接器上設定的數位長度。 會議 ID 中無法使用字母或特殊字元;只能使用數位。

- 根據預設，所有音訊會議使用者的會議 ID 為 9 位數，而且無法變更位數。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 當涉及 Windows PowerShell 時，所有內容都是關於管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)