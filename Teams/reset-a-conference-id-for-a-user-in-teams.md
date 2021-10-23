---
title: 重設使用者的會議 ID Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 瞭解在 Microsoft Teams 中重設使用者會議 ID 的步驟，並取得會議更新和移移工具的連結。
ms.openlocfilehash: 3a308be01f84509ea93793d7c2b1bdfd6e084268
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536484"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>重設使用者的會議 ID Microsoft Teams

動態會議 ID 會包含在會議邀請的底部，以及來電者可用來撥入會議的撥入電話號碼。 當使用者撥打電話號碼時，會議的自動語音機會要求來電者輸入此會議 ID，以便他們參加會議。
  
> [!NOTE]
> 會議 ID 會自動產生，介於 7 到 9 位數之間，且會在您為使用者啟用音訊會議時設定。 **不支援靜態會議 ID。** 

## <a name="resetting-the-conference-id-for-a-user"></a>為使用者重設會議 ID

 **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 按一下 **[編輯**> 。

3. 在 **[音訊會議>** 下，按一下 **[重設會議 ID>**。

2. 在 [ **重設會議 ID>** 視窗中，按一下 [ **重設**。 系統會自動建立會議 ID，並且會以新的會議 ID 將電子郵件寄給使用者。 根據預設，電子郵件會寄給使用者，但可以關閉。   
    
> [!NOTE]
> 重設會議 ID 之後，系統就會將一封包含新會議 ID 的電子郵件寄給使用者。 在許多情況下，此電子郵件會寄到主要電子郵件地址，Microsoft 365或Office 365信箱。 電子郵件包含新的會議 ID、預設撥入 (電話號碼) 更新現有會議的指示。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 您可以在包含會議 ID 和撥入電話號碼的電子郵件中，為使用者傳送所有會議資訊，方法是在音訊會議區段按一下以電子郵件傳送 **會議資訊。** 它不會傳送 PIN。
    
- 7- 9 位數的會議 ID 是由 Teams建立。 您無法變更其長度。
    
- 重設之後，您可以在會議 ID 下看到新的會議 **ID。**
    
- 建立新會議 ID 之後，來電者無法使用舊的會議 ID。 您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。 

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 有了Windows PowerShell，您可以使用單一Microsoft 365管理Office 365管理，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps&preserve-view=true) Microsoft Teams以瞭解更多資訊。
    
## <a name="related-topics"></a>相關主題

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)