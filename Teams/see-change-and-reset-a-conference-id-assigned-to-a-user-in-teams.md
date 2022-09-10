---
title: 查看、變更及重設使用者的會議 ID
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中將會議 ID 指派給使用者，以及會議 ID 參數應該是什麼。
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642114"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中檢視及重設指派給使用者的會議 ID

當 Microsoft Teams 使用者在 Microsoft 365 中設定音訊會議或Office 365並使用 Microsoft 做為音訊會議提供者時，會議 ID 會自動指派給他們。 會議排程時，指派的會議 ID 會在會議邀請中傳送。 使用者排程的每個會議都會獲指派一個唯一的會議 ID。
  
雖然會議 ID 會自動建立並指派給使用者，但有時候使用者可能不想使用此會議 ID，而您想要將它設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。 您可以使用 Microsoft Teams 系統管理中心或Windows PowerShell來檢視、變更及重設其會議 ID。
  
系統會傳送一封含有會議 ID 和預設音訊會議電話號碼的電子郵件給使用者，或者如果您重設會議 ID，則會傳送另一封包含會議 ID 但不包含 PIN 的電子郵件。 如需如何重設會議召集人的 PIN 的詳細資訊，請參閱 [在 Microsoft Teams 中重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md) 。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>檢視及重設會議 ID

### <a name="to-view-the-conference-id"></a>檢視會議 ID

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心檢視會議 ID

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯]**。

3. 在 **[音訊會議] 底** 下，查看 **[會議 ID]** 下方。

    > [!TIP]
    > 您可以按一下 [在電子郵件中傳送會議資訊] 連結，以包含會議 ID 和音訊電話號碼的電子郵件，將所有會議資訊傳 **送給使用者** 。
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>使用 Windows PowerShell 檢視會議 ID

如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

### <a name="to-reset-the-conference-id"></a>重設會議 ID

例如，如果使用者忘記會議 ID，您可以重設會議 ID。
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心重設會議 ID

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下頁面頂端的 [ **編輯]**。

3. 在 **[音訊會議] 底** 下，按一下 **[重設會議 ID]**。

4. 在 [ **重設會議 ID]** 視窗中，按一下 [ **重設]**。 系統會自動建立會議 ID，並傳送一封含有新會議 ID 的電子郵件給使用者。
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>使用 Windows PowerShell 重設會議 ID

如需詳細資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-else-should-you-know"></a>您還應知道什麼？

> [!IMPORTANT]
> 建立新的會議 ID 或重設會議 ID 之後，來電者就無法使用舊的會議 ID。 您應該通知使用者重新排程現有的會議邀請，以確保新會議 ID 已新增至邀請。

- 會議 ID 必須符合音訊會議橋接器上設定的數位長度。 您無法在會議 ID 中使用字母或特殊字元;只能使用數位。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。

## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 版 Microsoft 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
