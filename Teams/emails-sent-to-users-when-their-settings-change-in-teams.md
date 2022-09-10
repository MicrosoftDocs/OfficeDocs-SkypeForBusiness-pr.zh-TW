---
title: 在設定變更時傳送給使用者的電子郵件
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '瞭解當使用者的電話撥入式會議設定在 Microsoft Teams 中變更時，會透過電子郵件自動傳送哪些資訊給使用者。 '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642134"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>當使用者在 Microsoft Teams 中的設定變更時傳送給使用者的電子郵件

電子郵件會自動傳送給 [已啟用音訊會議](set-up-audio-conferencing-in-teams.md) 的使用者，並使用 Microsoft 做為音訊會議提供者。

根據預設，會傳送四種類型的電子郵件給啟用音訊會議的使用者。 不過，如果您想要限制傳送給使用者的電子郵件數量，可以將它關閉。 Microsoft 365 或 Office 365 中的音訊會議會在下列情況下傳送電子郵件到使用者的電子郵件：

- **音訊會議授權已指派給他們，或者當您將音訊會議提供者變更為 Microsoft 時。**

     此電子郵件包含會議 ID、會議的預設會議電話號碼、使用者的音訊會議 PIN，以及使用 Teams 會議更新工具來更新使用者現有會議的指示和連結。 請參閱 [指派 Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    > [!NOTE]
    > 如果您的組織已啟用動態會議 ID，則他們排程的所有使用者會議都會有唯一的會議 ID。 如需詳細資訊，請參 [閱檢視及重設指派給使用者的會議 ID](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) 一文。

    以下是此電子郵件的範例：

     ![Teams 驗證授權。](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    若要深入瞭解授權，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **使用者的會議 ID 或預設會議電話號碼會變更。**

    此電子郵件包含會議 ID、預設會議電話號碼，以及使用 Teams 會議更新工具來更新使用者現有會議的指示和連結。 但此電子郵件不包含使用者的音訊會議 PIN。 請參閱 [重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。

    以下是此電子郵件的範例：

     ![電話撥入式會議資訊已變更。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **系統會重設使用者的音訊會議 PIN。**

    此電子郵件包含召集人的音訊會議 PIN、現有的會議 ID，以及使用者的預設會議電話號碼。 請參閱[重設音訊會議 PIN。](reset-the-audio-conferencing-pin-in-teams.md)

     以下是此電子郵件的範例：

     ![電話撥入式會議 PIN 已變更。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **使用者的授權會移除，或當音訊會議提供者從 Microsoft 變更為其他提供者或無時。**

    當 **音訊會議** 授權從使用者移除，或將音訊會議提供者設定為 **[無**] 時，就會發生這種情況。

    請參閱 [指派或移除商務用 Microsoft 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    以下是此電子郵件的範例：

     ![電話撥入式會議已關閉。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>變更傳送給他們的電子郵件訊息

您可以變更自動傳送給使用者的電子郵件。 根據預設，電子郵件的寄件者是來自 Microsoft 365 或 Office 365，但您可以使用Windows PowerShell變更顯示名稱。 如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果您不希望電子郵件傳送給他們，該怎麼辦？

當您停用傳送電子郵件給使用者時，即使使用者獲派授權，電子郵件也不會傳送。 在此情況下，會議 ID、預設會議電話號碼，以及更重要的是，他們的音訊會議 PIN 不會傳送給使用者。 發生這種情況時，您必須傳送另一封電子郵件或致電通知使用者。

根據預設，電子郵件會傳送給您的使用者，但如果您要防止他們收到音訊會議的電子郵件，您可以使用 Microsoft Teams 或Windows PowerShell。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 **[會議**  >  **橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格中，啟用或停用 **在使用者的電話撥入設定變更時自動傳送電子郵件給使用者**。

4. 按一下 [儲存]。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

您也可以使用 Microsoft Teams PowerShell 模組並執行：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 來管理貴組織的其他設定，包括電子郵件。

如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

根據預設，電子郵件的寄件者是來自 Microsoft 365 或 Office 365，但您可以使用Windows PowerShell變更電子郵件地址和顯示名稱。

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。

## <a name="related-topics"></a>相關主題

[啟用或停用音訊會議設定變更時傳送電子郵件的設定](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[傳送內含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
