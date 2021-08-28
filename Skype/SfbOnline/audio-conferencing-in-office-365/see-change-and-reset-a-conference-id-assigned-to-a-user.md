---
title: 查看、變更及重設在線上版中指派給使用者商務用 Skype ID
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解如何將會議 ID 指派給 商務用 Skype Online 中的使用者，以及會議識別碼參數應該是什麼。 '
ms.openlocfilehash: c8c3abcf515a0a60046cd2438833467b8be78231
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607670"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>在 Online 中查看並重設指派給使用者商務用 Skype ID

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有關使用者會議識別碼Microsoft Teams，請參閱在 Microsoft Teams 中查看[和重設指派給使用者的會議 id。](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

在 Microsoft 365 或 Office 365 中設定音訊會議，並使用 Microsoft 做為音訊會議提供者時，系統會自動將會議 ID 指派給 商務用 Skype 使用者。 會議排程時，指派的會議 ID 會以會議邀請中送出。 使用者排程的每個會議都會獲得唯一的會議 ID。

雖然會議 ID 會自動建立並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是使用者不記得或遺失其會議 ID。 您可以使用系統 **管理商務用 Skype和** Windows PowerShell來查看、變更和重設其會議 ID。

電子郵件會以會議 ID 和預設的音訊會議電話號碼發送給使用者，或者如果您重設會議 ID，將會送出包含會議 ID 但不包含 PIN 的不同電子郵件。 有關重設會議召集人 PIN 的資訊， [請前往這裡](reset-a-conference-id-for-a-user.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>查看和重設會議 ID

### <a name="to-view-the-conference-id"></a>若要查看會議 ID

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

您可以查看他們的會議 ID，並將它傳送給使用者。

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 商務用 Skype **系統管理中心** >  **音訊會議**  >  **使用者中**，選取需要會議 ID 的使用者。

4. 在動作頁面中，查看會議 **ID 下的**。

    > [!TIP]
    > 您可以在選取使用者頁面上的使用者之後，按一下透過電子郵件傳送會議資訊，以包含會議 ID 和音訊電話號碼的電子郵件傳送所有會議 **資訊給使用者**。

**使用Windows PowerShell**

您可以使用 Windows PowerShell來查看使用者的會議 ID。 若要這麼做，請執行：

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

請參閱 [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。


### <a name="to-reset-the-conference-id"></a>若要重設會議 ID

例如，如果使用者忘記會議 ID，您可以重設會議 ID。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 使用公司或學校帳戶來登錄。

2. 請前往系統管理中心 **>商務用 Skype。**

3. 在 **[商務用 Skype系統** 管理中心 >  **音訊會議使用者** 中，按一下 [會議識別碼》 下的 [動作窗格>  >  中的 [**重設**。 

4. 在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。

**使用Windows PowerShell**

您可以使用會議識別碼來重設使用者Windows PowerShell。 若要這麼做，請執行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>您還需要知道什麼？

   > [!IMPORTANT]
   >  建立新會議 ID 或重設會議 ID 之後，來電者即無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 使用者可以使用會議移商務用 Skype工具來更新現有的會議。 若要瞭解如何下載、安裝及執行工具，請參閱：商務用 Skype 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的會議更新工具、商務用 Skype Online、會議移移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 商務用 Skype Online、會議移移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。

- 請參閱 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 以深入瞭解 Cmdlet。

- 會議 ID 必須符合音訊會議橋接器上設定的數位長度。 會議 ID 中無法使用字母或特殊字元;只能使用數位。

- 根據預設，所有音訊會議使用者的會議 ID 為 9 位數，而且無法變更位數。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

- 當要Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理Microsoft 365或 Office 365 商務用 Skype管理線上，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [為什麼您需要使用 powerShell Microsoft 365或Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相關主題

[嘗試或購買音訊會議Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
