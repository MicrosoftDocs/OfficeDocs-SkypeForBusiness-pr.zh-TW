---
title: 在商務用 Skype Online 中設定邀請中包含的電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '取得建立預設電話號碼的步驟，讓來電者加入商務用 Skype Online 會議。 '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113219"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>在商務用 Skype Online 中設定邀請中包含的電話號碼

> [!Note]
> 有關 Microsoft Teams 中會議邀請電話號碼的資訊，請參閱在 [Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)中設定邀請中包含的電話號碼。

Microsoft 365 或 Office 365 的音訊會議可讓貴組織的使用者建立商務用 Skype 會議，然後允許使用者使用電話撥入這些會議。 在 Microsoft 365 和 Office 365 中，您可以選擇使用由核准的音訊會議提供者 (ACP) 託管的 Microsoft 音訊會議橋接器或協力廠商音訊會議橋接器。
  
> [!NOTE]
> 沒有任何資源會包含音訊會議的所有撥入號碼清單。 如果您想要查看您的地區或國家/地區是否有可用的撥入電話號碼，請使用商務用 **Skype** 系統管理中心語音電話號碼，按一下 [  >    >  ******新增** 服務 **號碼**> 。 使用國家/地區、省 **/** 市 **/** 區及縣/市的清單來篩選您的搜尋。>此外，如果您要尋找免付費服務號碼，請從州 **/** 地區清單中選取免付費。
  
會議橋接器會提供您組織的一組撥入電話號碼。 所有會議都可以用來加入會議召集人所建立的會議，但您可以選取哪些會議邀請會包含在會議邀請中。
  
> [!NOTE]
> 會議邀請的會議召集人最多可以有一個付費電話和一個免付費電話號碼，但每個會議邀請底部也有一個連結，可開啟可用來加入會議之所有撥入電話號碼的完整清單。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>設定會議召集人的預設撥入電話號碼

1. 使用公司或學校帳戶來登錄。
    
2. 選擇 **系統管理中心**  >  **商務用 Skype**。
    
3. 選擇 **使用者**。
    
    ![顯示在商務用 Skype 系統管理中心選取使用者](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 選擇您想要編輯的使用者：
    
   - 若要選取單一使用者，請選取使用者的名稱。
    
   - 若要選取頁面上的所有使用者，請選取清單頂端的顯示名稱旁的方塊。
    
   - 若要選取多個使用者，請選取每個使用者名稱旁的方塊。
    
5. 在右面板中 **，選擇編輯**。
    
    ![選擇編輯圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 選擇 **音訊會議**。
    
7. 在屬性 **頁面上** 的提供者 **名稱** 清單中，選擇使用者的提供者。 根據提供者，完成下列框。
    
   - **Microsoft 是提供者**：使用 **預設** 付費號碼和預設免付費 **號碼** 清單來選取使用者的預設號碼。
    
     > [!NOTE]
     > 至少必須指派一個免付費號碼給會議橋接器，才能將其設定為使用者的預設免付費號碼。 若要取得免付費號碼，請參閱 [取得商務用 Skype 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)。 
  
   - **協力廠商是** 提供者：使用付費號碼和免付費 **號碼欄位** 來輸入使用者的數位。


## <a name="reset-audio-conferencing-phone-numbers"></a>重設音訊會議電話號碼

1. 在商務 **用 Skype 系統管理中心**，選擇 **音訊會議**。
    
2. 在頁面頂端， **選擇使用者**。
    
3. 選擇您想要重設的使用者，然後在 [動作窗格> 中，按一下 [ **清除**。
    
根據預設，當您變更使用者的會議設定時，電子郵件會發送給使用者。 若要變更此設定，請參閱在音訊會議設定變更時啟用或 [停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 當您變更使用者的音訊會議設定時，週期性和未來商務用 Skype 會議必須更新並寄給出席者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或自動化這項功能，您可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) Cmdlet 變更特定使用者的預設付費或免付費號碼。
    
    若要變更使用者的預設免付費號碼，請執行：
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** Cmdlet，根據使用者的原始預設號碼或位置來變更預設的付費或免付費使用者數目。
    
    > [!NOTE]
    > 若要尋找 BridgeID，請使用 **Get-CsOnlineDialInConferencingBridge** Cmdlet。
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要將所有使用者的預設免付費號碼設為 +18005551234，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要將具有 +18005551234 作為預設免付費號碼的所有使用者的預設免付費號碼變更為 +18005551239，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將位於美國的所有使用者的預設免付費號碼設為 +18005551234，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？
- 當涉及 Windows PowerShell 時，所有內容都是關於管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題

[在 Microsoft 365 或 Office 365 中試用或購買音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)