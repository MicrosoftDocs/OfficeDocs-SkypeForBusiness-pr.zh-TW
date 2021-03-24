---
title: 管理音訊會議設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '請參閱 Microsoft Teams 將電話撥入式會議授權和會議 ID 指派給使用者的步驟，以及許多其他電話撥入式會議設定。 '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101089"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 管理貴組織的音訊會議設定

您可以更輕鬆地在單一位置查看 Microsoft Teams 的所有音訊會議設定。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>指派音訊會議授權

> [!NOTE]
> 您無法使用 Teams 指派授權。 您必須使用 Microsoft 365 系統管理中心。 請參閱 [指派 Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。 
  
 **為使用者指派授權**
  
1. 使用公司或學校帳戶來登錄 Microsoft 365。
    
2. 在 **Microsoft 365** 系統管理中心的左側導覽中，前往使用者活動使用者，然後從可用使用者清單中選取  >  使用者。
    
    > [!NOTE]
    > 如果您同時將授權指派給最多 20 個使用者，您可以使用選取視圖下拉式清單，然後選擇其中一個選項，或建立您自己的視圖。 然後按一下 [**編輯，****下** 一步兩次，然後選取授權並 **按一下 [提交**> 。  
  
3. 在 [產品授權」 下的 [動作 **窗格**> 中，按一下 **[編輯。** 
    
4. 在 [ **產品授權>** 頁面上，開啟 **音訊會議** ，然後按一下 [ **儲存**。 有關授權的更多資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
   > [!NOTE]
   > 指派授權之後，Microsoft 一開始可能不會在清單中顯示為音訊會議提供者。 如果發生這種情況，請登出系統管理中心，或按 CTRL+F5 重新啟用瀏覽器視窗。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>啟用或停用發送給音訊會議使用者的電子郵件

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** ，啟用或停用當使用者的撥入設定變更時自動 **傳送電子郵件給使用者**。

4. 按一下 [儲存]。

    
**使用 Windows PowerShell**
  
請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。
  
## <a name="reset-the-meeting-conference-id"></a>重設會議 ID

![顯示 Teams 標誌 ](media/teams-logo-30x30.png) **的圖示使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議」** 下，按一下 **[重設會議 ID。**  

3. 在 [ **重設會議 ID？ 視窗中** ，按一下 [ **重設**。 如果已啟用傳送電子郵件給使用者，系統會自動建立會議 ID，並傳送一封具有新會議 ID 的電子郵件給使用者。 預設會啟用此功能。

請參閱[為使用者重設會議 ID。](reset-a-conference-id-for-a-user-in-teams.md)
  
## <a name="reset-a-conference-organizers-pin"></a>重設會議召集人的 PIN

使用者排程的每個會議都會獲得一個唯一的會議識別碼。 雖然會議 ID 會自動建立並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。 

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議」** 下，按一下 **[重** 設 PIN 碼，然後按一下 [ **重設**。 
  
當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。 但如果您已停用自動傳送電子郵件，將不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。 PIN 在重設後只會顯示一次。 在重設後顯示 PIN 之後，PIN 不會再顯示在使用者屬性上;而是會顯示 **** 。 
  
請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>傳送包含音訊會議資訊的電子郵件給使用者

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 在 **[音訊會議」** 下，按一下 **[以電子郵件傳送會議資訊。** 

    > [!NOTE]
    > 當您這麼做時，音訊會議 PIN 不會發送給使用者。 

請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>設定邀請中包含的電話號碼

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。

2. 在 [ **音訊會議」 旁**，按一下 [ **編輯>**。
 
3. 在音訊 **會議窗格中** ，您可以設定付費 **號碼** ，如果允許，也可以設定 **免付費號碼**。

4. 按一下 [儲存]。
    
請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>選擇音訊會議橋接器設定

**設定來電者加入會議時的會議體驗**

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** ，啟用或停用 **會議專案及離開通知**。

    此功能預設為啟用。 如果您停用此選項，根據預設，已加入會議的使用者不會在有人進入或離開會議時收到通知。

4. 在 **進入/離開公告類型下**，選擇 **色調或****名稱或電話號碼**。 

    如果您選擇名稱 **或電話號碼**，您也可以選擇啟用或停用要求來電者在加入會議前錄製 **其名稱**。 
    > [!NOTE]
    > 根據預設，外部參與者看不到撥入參與者的電話號碼。 如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。


5. 按一下 [儲存]。

    
請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **設定會議的 PIN 長度**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在 [**橋接器設定>** 窗格中，在 PIN 長度清單中輸入 PIN的位數，然後按一下 [**儲存**。

    PIN 必須介於 4 到 12 位數之間。 預設值為 5。

    
請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **啟用或停用電子郵件，禁止將電子郵件發送給音訊使用者**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 在 [會議橋接器 **」** 頁面頂端，按一下 [ **橋接器設定>**。 

3. 在橋接器 **設定窗格中** ，啟用或停用如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。

4. 按一下 [儲存]。 
 
    您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以電子郵件傳送會議 **資訊**。
    
    如果您這麼做，將會送出只包含會議 ID 和會議電話號碼的電子郵件，但不包含 PIN。

請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音訊會議橋接器 (查看) 次要 (次要) 語言

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 從清單中選取電話號碼，然後按一下 [ **編輯**。

3. 在預設語言和替代語言下選擇您想要的語言 **， (選擇) 。**

4. 按一下 [儲存]。


請參閱 [設定音訊會議的自動語音語音處理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>查看音訊會議電話撥入號碼

![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，前往 **會議**  >  **會議橋接器**。 

2. 從清單中選取電話號碼，然後按一下 [ **編輯**。 您可以在這裡：
    
   - 查看要用於音訊會議的電話號碼。 
    
   - 查看音訊會議自動語音機會使用的位置和主要語言。

  
請參閱 [查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。
  

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。
  
    
## <a name="related-topics"></a>相關主題

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)