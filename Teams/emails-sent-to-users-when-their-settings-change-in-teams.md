---
title: 在 Microsoft 團隊中其設定變更時傳送給使用者的電子郵件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '瞭解在 Microsoft 團隊中，當使用者的電話撥入式會議設定變更時，電子郵件會自動傳送哪些資訊給使用者。 '
ms.openlocfilehash: a619a8a096e8ea25b89be1f71390de6b7f6c50a7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696178"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>在 Microsoft 團隊中其設定變更時傳送給使用者的電子郵件

電子郵件會自動傳送給已使用 Microsoft 做為音訊會議提供者[的音訊會議的](set-up-audio-conferencing-in-teams.md)使用者。

根據預設，會傳送四種類型的電子郵件給已啟用音訊會議的使用者。 不過，如果您想要限制傳送給使用者的電子郵件數目，您可以將它關閉。 Office 365 中的音訊會議會在下列情況傳送電子郵件給使用者的電子郵件：

- **系統會將音訊會議授權指派給他們，或者當您將音訊會議提供者變更為 Microsoft 時。**

     此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN，以及使用用來更新現有會議的 [商務用 Skype Online 會議更新] 工具的指示與連結。使用者名. 請參閱[指派 Microsoft 團隊授權](assign-teams-licenses.md)或[將 microsoft 指派為音訊會議提供者](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 如果您的組織已啟用動態會議 Id，他們排程的所有使用者會議都會有唯一的會議 Id。 您可以[在組織中設定音訊會議動態 id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 

    以下是這封電子郵件的範例：

     ![商務用 Skype 驗證授權](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    若要深入瞭解授權，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **使用者的會議 ID 或預設會議電話號碼會變更。**

    此電子郵件包含會議 ID、預設會議電話號碼，以及使用商務用 Skype Online 會議更新工具來更新使用者現有會議的指示與連結。 但此電子郵件不會包含使用者的音訊會議 PIN。 請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。

    以下是這封電子郵件的範例：

     ![電話撥入式會議資訊已變更。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **使用者的音訊會議 PIN 將會重設。**

    此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID，以及使用者的預設會議電話號碼。 請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)。
    
     以下是這封電子郵件的範例：
    
     ![電話撥入式會議 PIN 已變更。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **使用者的授權已移除，或音訊會議提供者從 Microsoft 變更為其他提供者或 [無]。**

    當您在使用者中移除**音訊會議**授權，或是將使用者的音訊會議提供者從 Microsoft 改為協力廠商音訊會議提供者或將提供者設定為 [**無**] 時，就會發生這種情況。 此電子郵件包含使用者使用商務用 Skype Online 會議更新工具來移除語音會議特定資訊（例如預設會議電話號碼或會議 ID）的指示與資訊。

    請參閱[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    以下是這封電子郵件的範例：

     ![電話撥入式會議已關閉。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>對傳送給他們的電子郵件訊息進行變更

您可以對自動傳送給使用者的電子郵件進行變更。 根據預設，電子郵件的寄件者將是來自 Office 365，但是您可以使用 Windows PowerShell 變更顯示名稱。 如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果您不想傳送電子郵件給他們，該怎麼辦？

當您停用傳送電子郵件給使用者時，即使使用者獲指派授權，也不會傳送電子郵件。 在此情況下，會議 ID、預設會議電話號碼和其他重要的是，其音訊會議 PIN 不會傳送給使用者。 發生這種情況時，您必須透過傳送一封電子郵件或呼叫他們來通知使用者。

根據預設，電子郵件會傳送給您的使用者，但如果您想要防止他們接收電子郵件以進行音訊會議，您可以使用 Microsoft 團隊或 Windows PowerShell。 

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示

1. 在左側導覽中，前往 [**會議** > **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在 [**橋設定**] 窗格中，如果使用者的撥入設定變更，請啟用或停用**自動傳送電子郵件給使用者**。

4. 按一下 [**儲存**]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**

如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

根據預設，電子郵件的寄件者會是來自 Office 365，但您可以使用 Windows PowerShell 變更電子郵件地址和顯示名稱。 

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。


## <a name="related-topics"></a>相關主題

[啟用或停用音訊會議設定變更時傳送電子郵件的設定](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
