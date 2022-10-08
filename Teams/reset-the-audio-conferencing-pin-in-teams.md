---
title: 重設 Microsoft Teams 中的音訊會議 PIN
ms.author: heidip
author: MicrosoftHeidi
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
description: 瞭解如何在 Microsoft Teams 中重設使用者的音訊會議 PIN，以及瞭解 PIN 的重要事項。
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329027"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>重設 Microsoft Teams 中的音訊會議 PIN

PIN 是由數位組成的代碼，是針對每個啟用音訊會議的 Microsoft Teams 使用者所建立。 音訊會議 PIN 可讓會議召集人識別其為會議召集人，並允許他們透過電話召開會議。 如果他們使用 Microsoft Teams 應用程式來開始會議，則不需要 PIN。 如果使用者忘記 PIN 碼，且無法在啟用音訊會議時傳送給使用者的電子郵件中找到 PIN，系統管理員可以重設 PIN，也可以重設自己的 PIN。
  
當經過驗證的使用者使用 Microsoft Teams 應用程式加入，或當召集人透過電話以 PIN 加入時，就可以開始會議。 當會議需要 PIN 召開時，透過電話加入的使用者會被置於大廳，並保留聆聽音樂，直到召集人允許為止。 如果會議召集人不需要 PIN 即可透過電話召開會議，那麼當來電者加入會議時，系統不會要求他們提供 PIN。

## <a name="reset-a-users-pin"></a>重設使用者的 PIN

使用 Microsoft Teams 系統管理中心：

1. 在左側導覽中，按一下 [ **使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下 **[編輯]**。

3. 在 **[音訊會議] 底** 下，按一下 [ **重設 PIN]**。

4. 按一下 [ **重設]**。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>讓使用者重設自己的 PIN 碼

1. 請讓使用者移至 [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp) 。
2. 按一下 **[重設 PIN]**。

> [!NOTE]
> 對於 GCCH，請移至： [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp) .
> 若是 DoD，請移至： [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp) 。

> [!NOTE]
> 使用此方法時，PIN 重設電子郵件將不會傳送給使用者。

## <a name="what-else-should-you-know-about-pins"></a>關於 PIN，您還應知道什麼？

- 為了安全起見，PIN 只會在 PIN 重設時向系統管理員顯示一次。 系統管理員重設 PIN 之後，PIN 會列為 **}}}。。

- 系統預設會自動傳送電子郵件給使用者，當使用者可以使用音訊會議或重設 PIN 時，就會收到含有 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件的功能，PIN 重設電子郵件將不會傳送給使用者，您必須手動傳送 PIN 資訊給使用者。

- 會議開始時，召集人必須在大廳允許所有 PSTN 使用者加入會議。 例如，如果有兩個 PSTN 參與者嘗試在會議開始前加入會議，他們會被放在大廳等候並聆聽保留的音樂，而當會議召集人透過電話使用 PIN 加入時，會議將會開始，而召集人可以使用會議內命令 (按 *21) ，以准許所有 PSTN 使用者進入大廳。

- 預設設定是不允許匿名來電者召開會議。

- 當您為使用者啟用音訊會議時，系統預設會傳送包含會議資訊及其 PIN 的電子郵件。 使用者必須擁有 Microsoft 365 或Office 365信箱，因為重設 PIN 時，新的 PIN 會以電子郵件傳送給使用者， (為使用者設定的別名) 傳送給使用者。

- 設定音訊會議時，您會設定組織中 PIN 所需的數位。 PIN 可以是 4 到 12 位數 - 預設值為 5。 如果您變更 PIN 長度設定，此設定只會套用在新產生的 PIN 上，且不會套用到已啟用音訊會議之現有使用者的 PIN 設定。 請參閱 [設定音訊會議 PIN 的長度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。

- 根據預設，電子郵件會設定為使用者的 Microsoft 365 或Office 365主要 SMTP 位址。 您可以將電子郵件傳送到非 Microsoft 365 或非Office 365位址，例如 Hotmail 或 MSN 電子郵件地址。 您可以使用Windows PowerShell覆寫預設的電子郵件地址。 如果使用者在 Microsoft 365 或 Office 365 中沒有 Exchange 信箱，這項功能就很實用。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。
  
## <a name="related-topics"></a>相關主題

[重設使用者的會議識別碼](reset-a-conference-id-for-a-user-in-teams.md)
