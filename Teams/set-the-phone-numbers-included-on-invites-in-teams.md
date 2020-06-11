---
title: 設定邀請中包含的電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 請依照下列步驟，為呼叫者加入 Microsoft 團隊會議所用的預設電話號碼。
ms.openlocfilehash: 81624090b1e82bf695f8e558cd55324a45d927e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691109"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>在 Microsoft 團隊中設定邀請中所包含的電話號碼

Microsoft 365 和 Office 365 中的音訊會議可讓貴組織中的使用者建立 Microsoft 團隊會議，然後允許使用者使用電話撥入這些會議。
  
「會議橋接」會為您的組織提供一組撥入電話號碼。 所有這些專案都可以用來加入會議召集人所建立的會議，但您可以選取哪些專案會包含在他們的會議邀請中。
  
> [!NOTE]
> 在會議召集人的會議邀請中，最多隻能有一個付費電話號碼，還有一個免付費電話號碼，在每個會議邀請的底部，都會開啟完整的清單，其中包含可用於加入會議的所有電話撥入電話號碼。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>新使用者的會議邀請中所包含的電話號碼初始指派

在啟用音訊會議之使用者的會議邀請中所包含的電話號碼，是由預設的會議付費電話號碼和預設的會議免付費電話號碼使用者設定所定義。 每個設定都會指定要在指定使用者的會議邀請中包含哪些免付費電話號碼和免付費電話號碼。 如上所述，每個會議邀請都包含一份收費電話號碼，一個可選的免付費電話號碼和一個連結，可開啟完整清單，供您用來加入特定會議的所有電話撥入電話號碼。

針對新使用者，系統會根據在使用者啟用音訊會議服務時，在使用者的 Microsoft 365 系統管理中心設定的使用位置來指派預設的會議付費電話號碼。 如果在會議橋中有一個與使用者的國家/地區相符的收費號碼，該號碼會自動指派為使用者的預設付費號碼。 如果沒有其中一個號碼，則會將定義為會議橋接器預設收費號碼的號碼指派為使用者的預設付費號碼。  

在使用者啟用音訊會議服務之後，租使用者可隨時從其初始值變更使用者的預設付費電話號碼和免付費電話號碼。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>設定或變更會議召集人或使用者的預設音訊會議電話號碼

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

您必須是系統管理員，才能進行這些變更。

1. 登入系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. 在左側導覽中，按一下 [**使用者**]。

    ![顯示在 Microsoft 團隊系統管理中心中選取使用者](media/Admin-users.png)

3. 按一下可用使用者清單中的使用者名稱。

4. 按一下 [**音訊會議**] 旁的 [**編輯**]。 
    
    ![按一下 [音訊會議] 旁的 [編輯]](media/teams-set-phone-numbers-on-invites-image3.png)

5. 使用 [**付費電話號碼**] 或 [**免付費電話號碼**] 欄位輸入使用者的號碼。


> [!IMPORTANT]
> 當您變更使用者的音訊會議設定時，必須更新定期及未來的 Microsoft 團隊會議，並傳送給出席者。 

## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。 
  
    
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
