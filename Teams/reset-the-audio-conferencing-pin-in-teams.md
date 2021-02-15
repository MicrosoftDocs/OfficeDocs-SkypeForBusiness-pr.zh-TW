---
title: 在 Microsoft Teams 中重設音訊會議 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中重設使用者的音訊會議 PIN，以及瞭解 PIN 的重要事實。
ms.openlocfilehash: 3f1055551edb45ac422052476196f01ee4d2765d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237463"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重設音訊會議 PIN

PIN 是由每個啟用音訊會議功能的 Microsoft Teams 使用者所建立的數位所建立的代碼。 會議召集人會使用音訊會議 PIN，以識別他們是會議召集人，並允許他們使用電話開始會議。 如果他們使用 Microsoft Teams 應用程式來啟動會議，則不需要 PIN。 如果使用者忘記 PIN，卻在啟用音訊會議時所寄給他們的電子郵件中找不到 PIN，系統管理員可以重設 PIN，也可以重設自己的 PIN。
  
當已驗證的使用者使用 Microsoft Teams App 加入，或當召集人使用他們的 PIN 在電話加入時，就可以開始會議。 當會議需要 PIN 才能開始時，使用電話加入的使用者會放在大廳，並聆聽等候音樂，直到會議開始。 如果會議召集人不需要 PIN，只要使用電話啟動會議，來電者加入會議時就不會要求他們提供 PIN。

## <a name="reset-a-users-pin"></a>重設使用者的 PIN

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 **[** 使用者，然後從可用使用者清單中選取使用者。

2. 按一下 **[編輯**。

3. 在 **音訊會議下，** 按一下 [重 **設 PIN** 碼。

4. 按一下 [ **重設**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>讓使用者重設自己的 PIN

1. 讓使用者前往 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。
2. 按一下 **[重設 PIN** 碼。 


## <a name="what-else-should-you-know-about-pins"></a>關於 PIN，您還需要知道什麼？

- 為了安全，PIN 重設時，系統只會向系統管理員顯示一次 PIN。 系統管理員重設 PIN 之後，PIN 會列為 ****。。
    
- 系統預設會啟用自動傳送電子郵件給使用者，使用者會在啟用音訊會議或 PIN 重設時收到一封包含 PIN 的電子郵件。 但是如果您已經停用自動傳送電子郵件，PIN 重設電子郵件就不會傳送給使用者，您必須手動傳送 PIN 資訊給使用者。
    
- 會議開始時，大廳的所有使用者都會自動加入會議。 例如，如果有兩位參與者在會議開始之前嘗試加入會議，他們會被放在大廳等候並聆聽保留的音樂，而當會議召集人透過電話使用 PIN 加入時，會議就會開始，而大廳的參與者也會加入會議。
    
- 預設設定是不允許匿名來電者啟動會議。
    
- 當您允許使用者使用音訊會議時，根據預設，使用者會收到包含會議資訊和 PIN 的電子郵件。 使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為當 PIN 重設時，會以電子郵件將新的 PIN (別名) 寄給使用者，
    
- 當您設定音訊會議時，您可以設定貴組織中 PIN 所需的位數。 PIN 可以是 4 到 12 位數 - 預設值為 5。 如果您變更 PIN 長度設定，該設定只會在新產生的 PIN 上，不會針對已啟用音訊會議的現有使用者的 PIN 設定。 請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 根據預設，電子郵件會設定為使用者的 Microsoft 365 或 Office 365 主要 SMTP 位址。 您可以傳送電子郵件至非 Microsoft 365 或非 Office 365 位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用 Windows PowerShell 來覆蓋預設電子郵件地址。 如果使用者在 Microsoft 365 或 Office 365 中沒有 Exchange 信箱，這項功能就很實用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 參考資料以瞭解更多資訊。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user-in-teams.md)
