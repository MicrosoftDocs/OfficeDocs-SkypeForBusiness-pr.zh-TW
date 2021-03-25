---
title: 設定音訊會議的 PIN 碼長度
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解 PIN 長度和需求的參數，並瞭解如何在 Microsoft Teams 中設定會議長度。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117161"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中設定音訊會議會議的 PIN 長度

當您為 Microsoft Teams 設定音訊會議時，將會取得音訊會議橋接器。 一個會議橋接器可以包含一或多個電話號碼。 您設定的電話號碼會包含在 Microsoft Teams 應用程式的會議邀請中。
  
音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。 它以自動語音應答的語音提示回答來電者，然後視您的設定播放通知，並要求來電者錄製其名稱。 **Microsoft 橋接器** 設定允許您變更會議通知和會議加入體驗的設定，並設定會議召集人所使用的 PIN 長度。 如果會議召集人無法使用 Microsoft Teams 應用程式加入會議，請使用 PIN 開始會議。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>設定 PIN 長度

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** 的 **PIN 長度** 下，選取 PIN 的位數。

4. 按一下 [儲存]。

> [!NOTE]
> PIN 與會議 ID 不同。 當來電者加入會議時，會使用會議 ID。 它們是用來識別會議。 PIN 是用來驗證來電者為會議召集人。 

## <a name="want-to-know-more-about-pin-settings"></a>想要進一瞭解 PIN 設定嗎？

- PIN 可以是 4 到 12 位數;預設值為 5。 數位只有在建立 PIN 時才能使用。 不會使用字母和特殊字元。
    
- 只有當 Microsoft Teams 使用者尚未開始會議時，會議召集人才需要 PIN。 如果每個人都撥入會議，會議召集人必須輸入 PIN 才能開始會議。
    
- PIN 安全性設定會適用于與 Microsoft 橋接器相關聯的所有電話號碼。 這些將會適用于使用與特定橋接器相關聯的電話號碼的所有會議。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。
    
  
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)