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
description: 瞭解如何在 Microsoft Teams 中重設使用者的音訊會議 PIN，以及瞭解 PIN 的重要資訊。
ms.openlocfilehash: cf660331bebfe32fe1809067570e316449c12a22
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918979"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重設音訊會議 PIN

PIN 是由數位所建立的代碼，會針對每個啟用音訊會議功能的 Microsoft Teams 使用者建立。 會議召集人會使用音訊會議 PIN，識別他們為會議召集人，並允許他們使用電話開始會議。 如果他們使用 Microsoft Teams 應用程式來開始會議，則不需要 PIN。 如果使用者忘記 PIN，而且在可以使用音訊會議時所寄給他們的電子郵件中找不到 PIN，系統管理員可以重設他們的 PIN，或重設自己的 PIN。
  
當已驗證的使用者使用 Microsoft Teams 應用程式加入，或當會議召集人使用 PIN 使用電話加入時，就可以召開會議。 當會議需要 PIN 才能開始時，以電話加入的使用者將會被安置在大廳等候，並且保留通話時聆聽音樂，直到會議召開。 如果會議召集人不需要 PIN，只要使用電話啟動會議，那麼當來電者加入會議時，系統就不會要求他們提供 PIN。

## <a name="reset-a-users-pin"></a>重設使用者的 PIN

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 **[使用者**，然後從可用使用者清單中選取使用者。

2. 按一下 **[編輯**。

3. 在 **[音訊會議> 下**，按一下 [**重設 PIN。**

4. 按一下 [ **重設**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>讓使用者重設自己的 PIN

1. 讓使用者前往 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。
2. 按一下 [ **重設 PIN** 碼。 


## <a name="what-else-should-you-know-about-pins"></a>您應該知道有關 PIN 還有哪些資訊？

- 基於安全性的參考資料，重設 PIN 時，PIN 只會向管理員顯示一次。 系統管理員重設 PIN 之後，PIN 就會列為 ******。。
    
- 系統預設會啟用自動傳送電子郵件給使用者，而且使用者可以使用音訊會議或 PIN 重設時，也會收到一封包含 PIN 的電子郵件。 但是如果您停用了自動傳送電子郵件的設定，PIN 重設電子郵件將不會傳送給使用者，您必須手動傳送 PIN 資訊給使用者。
    
- 會議開始時，大廳的所有使用者都會自動加入會議。 例如，如果有兩位參與者嘗試在會議開始之前加入會議，他們會被放在大廳等候，並且保留通話時聆聽音樂，當會議召集人透過電話使用 PIN 加入時，會議就會開始，而大廳等候的參與者也會加入會議。
    
- 預設設定是不允許匿名來電者啟動會議。
    
- 當您允許使用者使用音訊會議時，根據預設，使用者會收到包含會議資訊和 PIN 的電子郵件。 使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為 PIN 重設之後，新的 PIN 會以電子郵件，寄給使用者為使用者設定的主要 SMTP 位址 (別名) 。
    
- 當您設定音訊會議時，會設定貴組織中 PIN 所需的位數。 PIN 可以是 4 到 12 位數 - 預設值為 5。 如果您變更了 PIN 長度設定，此設定只會新產生的 PIN 上，不會針對啟用音訊會議的現有使用者，將之用於 PIN 設定。 請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 根據預設，電子郵件會設定為使用者的 Microsoft 365 或 Office 365 主要 SMTP 位址。 您可以傳送電子郵件至非 Microsoft 365 或非 Office 365 位址 ，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用 Windows PowerShell 來取代預設的電子郵件地址。 如果使用者在 Microsoft 365 或 Office 365 中沒有 Exchange 信箱，這項功能就很實用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

Windows PowerShell 的用場就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有關 Windows PowerShell 詳細資訊，請參閱 [Microsoft Teams PowerShell 參照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 以進一詳細資訊。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user-in-teams.md)
