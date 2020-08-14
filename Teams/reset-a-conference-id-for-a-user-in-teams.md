---
title: 在 Microsoft 團隊中重設使用者的會議 ID
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解在 Microsoft 團隊中重設使用者的會議 ID，以及取得會議更新與遷移工具的連結的步驟。
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662123"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>在 Microsoft 團隊中重設使用者的會議 ID

[動態會議 ID] 包含在會議邀請的底部，以及撥入電話號碼，可供呼叫者用來撥入會議。 當使用者撥打電話號碼時，會議的自動回應會要求來電者輸入此會議 ID，才能出席會議。
  
> [!NOTE]
> 會議 Id 會自動產生，在7-9 位數之間，且在您啟用使用者的音訊會議時進行設定。 **不支援靜態的會議 Id。** 

## <a name="resetting-the-conference-id-for-a-user"></a>重設使用者的會議 ID

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下 [ **編輯**]。

3. 在 [ **音訊會議** ] 底下，按一下 [ **重設會議 ID**]。

2. 在 [ **重設會議 ID** ] 視窗中，按一下 [ **重設**]。 系統會自動建立會議 ID，並以新的會議 ID 傳送給使用者的電子郵件。 根據預設，電子郵件會傳送給使用者，但您可以關閉此功能。   

    
> [!NOTE]
> 在您重設會議 ID 之後，具有新會議 ID 的電子郵件將會傳送給使用者。 此電子郵件將會傳送至主要電子郵件地址，在許多情況下，也會傳送到他們的 Microsoft 365 或 Office 365 信箱。 電子郵件包含新的會議 ID、預設的撥入電話號碼 (s) ，以及更新現有會議的指示。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我還需要知道什麼？

- 您可以在包含會議 ID 和撥入電話號碼的電子郵件中，將所有會議資訊傳送給使用者，方法是在 [**音訊會議**] 區段中，按一下 [**以電子郵件傳送會議資訊**]。 它不會傳送 PIN。
    
- [團隊服務] 會建立 7-9 位數的會議 ID。 您無法變更它的長度。
    
- 重設之後，您可以在 [ **會議 id**] 底下看到新的會議 ID。
    
- 在建立新的會議 ID 之後，不能讓呼叫者使用舊的會議 id。 您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。 

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱 [Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) ，以取得詳細資訊。
    
## <a name="related-topics"></a>相關主題

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)
