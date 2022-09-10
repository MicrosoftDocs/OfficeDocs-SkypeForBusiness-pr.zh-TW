---
title: 設定音訊會議的 PIN 碼長度
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
- seo-marvel-mar2020
description: 瞭解 PIN 的長度和需求參數，並瞭解如何在 Microsoft Teams 中設定會議長度。
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641954"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中設定音訊會議的 PIN 長度

當您為 Microsoft Teams 設定音訊會議時，您會獲得音訊會議橋接器。 一個會議橋接器可以包含一或多個電話號碼。 您設定的電話號碼會包含在 Microsoft Teams 應用程式的會議邀請中。
  
音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。 它會使用自動語音應答的語音提示接聽來電者，然後根據您的設定播放通知，並要求來電者錄下他們的名稱。 **Microsoft 橋接器設定** 可讓您變更會議通知和會議加入體驗的設定，並設定會議召集人所使用的 PIN 長度。 如果會議召集人無法使用 Microsoft Teams 應用程式加入會議，請使用 PIN 來開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>設定 PIN 長度

使用 Microsoft Teams 系統管理中心：

1. 在左側導覽中，移至 **[會議**  >  **橋樑]**。

2. 在 [ **會議橋** ] 頁面頂端，按一下 [ **橋接器設定]**。

3. 在 [ **橋接器設定** ] 窗格的 **[PIN 長度**] 底下，選取 PIN 碼所需的位數。

4. 按一下 [儲存]。

> [!NOTE]
> PIN 與會議 ID 不同。 來電者加入會議時，會使用會議 ID。 它們會用來識別會議。 PIN 可用來驗證來電者是會議召集人。

## <a name="want-to-know-more-about-pin-settings"></a>想要深入瞭解 PIN 設定嗎？

- PIN 可以是 4 到 12 位數;預設值為 5。 數位只會在建立 PIN 時使用。 字母和特殊字元不會使用。

- 只有當 Microsoft Teams 使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都要撥入會議，則會議召集人必須使用 PIN 才能開始會議。

- PIN 安全性設定會套用到與 Microsoft 橋接器相關聯的所有電話號碼。 這些專案將會套用至所有使用與指定橋接器相關聯之電話號碼的會議。

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解Windows PowerShell嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：

- [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

如需Windows PowerShell的詳細資訊，請參[閱 Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps)資訊以取得詳細資訊。

## <a name="related-topics"></a>相關主題

[在 Microsoft Teams 版 Microsoft 365 中試用或購買音訊會議](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
