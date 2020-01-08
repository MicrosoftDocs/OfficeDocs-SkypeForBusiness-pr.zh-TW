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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '取得建立呼叫者加入商務用 Skype Online 會議的預設電話號碼的步驟。 '
ms.openlocfilehash: 33c2f69cbd05efedf5af1bb35c7ea5d560930da4
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962511"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>在商務用 Skype Online 中設定邀請中包含的電話號碼

> [!Note]
> 如需 Microsoft 團隊中會議邀請電話號碼的相關資訊，請參閱[在 Microsoft 團隊中設定邀請中所包含的電話號碼](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。

Office 365 中的音訊會議可讓貴組織中的使用者建立商務用 Skype 會議，然後允許使用者使用電話撥入這些會議。 在 Office 365 中，您可以選擇使用 Microsoft 音訊會議橋接器或由已核准的音訊會議提供者（ACP）託管的協力廠商音訊會議橋。
  
> [!NOTE]
> 沒有一個資源包含所有撥入號碼的音訊會議清單。 如果您要查看您的地區或國家/地區是否有可用的撥入電話號碼，請使用**商務用 Skype 系統管理中心** > **語音** > **電話號碼** **，按一下 [** 新增]，然後輸入新的**服務號碼**。 使用 [**國家/地區**]、[**州/地區**] 和 [**城市**] 的清單來篩選您的搜尋。 > 此外，如果您正在尋找免費的服務號碼，請從 [**省/市/自治區**] 清單中選取 [**免付費電話**]。
  
「會議橋接」會為您的組織提供一組撥入電話號碼。 所有這些專案都可以用來加入會議召集人所建立的會議，但您可以選取哪些專案會包含在他們的會議邀請中。
  
> [!NOTE]
> 在會議召集人的會議邀請中，最多隻能有一個付費電話號碼，還有一個免付費電話號碼，在每個會議邀請的底部，都會開啟完整的清單，其中包含可用於加入會議的所有電話撥入電話號碼。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>設定會議召集人的預設撥入電話號碼

1. 使用您的公司或學校帳戶登入 Office 365。
    
2. 選擇系統**管理中心** > **的商務用 Skype**。
    
3. 選擇 [**使用者**]。
    
    ![顯示在商務用 Skype 系統管理中心中選取使用者](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 選擇您要編輯的使用者：
    
   - 若要選取單一使用者，請選取該使用者的名稱。
    
   - 若要選取頁面上的所有使用者，請選取清單頂端 [**顯示名稱**] 旁的方塊。
    
   - 若要選取多個使用者，請選取每個使用者名稱旁的方塊。
    
5. 在右面板中，選擇 [Edit] （**編輯**）。
    
    ![選擇 [編輯] 圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 選擇 [**音訊會議**]。
    
7. 在 [**屬性**] 頁面的 [**提供者名稱**] 清單中，選擇使用者的提供者。 視提供者而定，請完成下列方塊。
    
   - **Microsoft 是提供者**：使用**預設的付費電話號碼**和**預設的免付費電話號碼**清單來選取使用者的預設號碼。
    
     > [!NOTE]
     > 您必須先將至少一個免付費電話號碼指派給您的會議橋接器，才能將其設為使用者的預設免付費電話號碼。 若要取得免付費電話號碼，請參閱[取得商務用 Skype 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)。 
  
   - **協力廠商是提供者**：使用 [**付費電話號碼**] 和 [**免付費電話號碼**] 欄位輸入使用者的號碼。


## <a name="reset-audio-conferencing-phone-numbers"></a>重設音訊會議電話號碼

1. 在**商務用 Skype 系統管理中心**中，選擇 [**音訊會議**]。
    
2. 在頁面頂端，選擇 [**使用者**]。
    
3. 選擇您要重設的使用者，然後在 [動作] 窗格中，按一下 [**清除**]。
    
根據預設，當您變更使用者的會議設定時，系統會傳送電子郵件給使用者。 若要變更此設定，請參閱[在音訊會議設定變更時啟用或停用傳送電子郵件](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 當您變更使用者的音訊會議設定時，必須更新週期性及未來的商務用 Skype 會議，並傳送給出席者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

- 若要節省時間或將這項作業自動化，您可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet。
    
- 使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) Cmdlet 來變更特定使用者的預設付費或免付費電話號碼。
    
    若要變更使用者的預設免付費電話號碼，請執行：
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用**CsOnlineDialInConferencingUserDefaultNumber** Cmdlet 根據原始預設號碼或其位置來變更預設的付費或免付費使用者數目。
    
    > [!NOTE]
    > 若要尋找 BridgeID，請使用**CsOnlineDialInConferencingBridge** Cmdlet。
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要為所有不含1到 + 18005551234 的使用者設定預設免付費電話號碼，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要將擁有 + 18005551234 的所有使用者的預設免付費電話號碼改為預設的免付費電話號碼至 + 18005551239，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要將美國所有使用者的預設免付費電話號碼設定為 + 18005551234，請執行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？
- 若要使用 Windows PowerShell，請參閱管理使用者和允許或不允許的使用者。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題

[試用或購買 Office 365 的音訊會議](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
