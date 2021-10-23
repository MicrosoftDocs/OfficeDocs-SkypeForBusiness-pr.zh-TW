---
title: 重設音訊會議 PIN Microsoft Teams
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 重設使用者的音訊會議 PIN，並瞭解 PIN 的重要事實。
ms.openlocfilehash: 8c7525605f0dedaed05ba9b98db689715e468865
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537294"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>重設音訊會議 PIN Microsoft Teams

PIN 是由每個已啟用音訊會議Microsoft Teams使用者所建立的數位所建立的代碼。 會議召集人會使用音訊會議 PIN 來識別他們是會議召集人，並允許他們以電話開始會議。 如果他們使用 Microsoft Teams應用程式來開始會議，則不需要 PIN。 如果使用者忘記 PIN，卻在啟用音訊會議時，無法于電子郵件中找到 PIN，系統管理員可以重設其 PIN，或重設自己的 PIN。
  
當經過驗證的使用者使用 Microsoft Teams App 加入時，或當召集人使用他們的 PIN 在電話上加入時，就可以開始會議。 當會議需要 PIN 才能啟動時，使用電話加入的使用者會放在大廳，並聆聽等候音樂，直到召集人准許他們加入。 如果會議召集人不需要 PIN，以在電話上開始會議，則來電者加入會議時不會要求他們提供 PIN。

## <a name="reset-a-users-pin"></a>重設使用者的 PIN

 **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**」，然後從可用使用者清單中選取使用者。

2. 按一下 **[編輯**> 。

3. 在 **[音訊會議」** 下，按一下 [ **重設 PIN** 碼。

4. 按一下 **[重設**。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>讓使用者重設自己的 PIN

1. 讓使用者前往 [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp) 。
2. 按一下 **[重設 PIN** 碼。 

> [!NOTE]
> 針對 GCCH，請前往： https://dialin.cpc.gov.teams.microsoft.us/usp 。
> 針對 DoD，請前往： https://dialin.cpc.dod.teams.microsoft.us/usp 。

## <a name="what-else-should-you-know-about-pins"></a>關於 PIN，您還需要知道什麼？

- 為了安全，PIN 只會在 PIN 重設時顯示給系統管理員一次。 系統管理員重設 PIN 之後，PIN 會列為 ********。。
    
- 系統預設會啟用自動傳送電子郵件給使用者，當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件，PIN 重設電子郵件將不會傳送給使用者，您必須手動將 PIN 資訊傳送給使用者。
    
- 會議開始時，召集人必須允許大廳的所有 PSTN 使用者加入會議。 例如，如果兩個 PSTN 參與者在會議開始之前嘗試加入會議，則他們會放在大廳中，並保留聆聽音樂，當會議召集人透過電話使用 PIN 加入時，會議就會開始，而召集人可以使用會議內命令 (按 *21) 以允許大廳的所有 PSTN 使用者。
    
- 預設設定是不允許匿名來電者啟動會議。
    
- 當您啟用音訊會議的使用者時，根據預設，系統會送出包含會議資訊及其 PIN 的電子郵件。 使用者必須擁有 Microsoft 365 或 Office 365 信箱，因為當 PIN 重設時，會以電子郵件將新的 PIN 寄到使用者為使用者設定的主要 SMTP 位址 (別名) 。
    
- 當您設定音訊會議時，您可以設定組織中 PIN 所需的位數。 PIN 可以是 4 到 12 位數 -預設值為 5。 如果您變更 PIN 長度設定，則設定只會在新產生的 PIN 上，而且不會適用于已啟用音訊會議的現有使用者的 PIN 設定。 請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 電子郵件預設會設定為使用者Microsoft 365或Office 365 SMTP 位址。 您可以將電子郵件傳送至非Microsoft 365非Office 365位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用預設電子郵件地址來取代Windows PowerShell。 如果使用者沒有位於或Exchange信箱Microsoft 365此功能Office 365。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
如要進一Windows PowerShell，請參閱[powerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams以瞭解更多資訊。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user-in-teams.md)
