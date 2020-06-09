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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '請參閱 Microsoft 團隊步驟，將電話撥入式會議授權及會議 ID 指派給使用者和許多其他電話撥入式會議設定。 '
ms.openlocfilehash: 704bcd5777fd0327ed944cc903959ef019f794a5
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638462"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft 團隊中管理貴組織的音訊會議設定

在單一位置查看 Microsoft 團隊的所有音訊會議設定可能會更容易。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>指派音訊會議授權

> [!NOTE]
> 您無法使用團隊指派授權。 您必須使用 Microsoft 365 系統管理中心。 請參閱[指派 Microsoft 團隊附加元件授權](teams-add-on-licensing/assign-teams-add-on-licenses.md)。 
  
 **指派使用者的授權**
  
1. 使用您的公司或學校帳戶登入 Microsoft 365。
    
2. 在**Microsoft 365 系統管理中心**的左導覽中，前往 [**使用者**作用中的  >  **使用者**]，然後從可用使用者清單中選取使用者。
    
    > [!NOTE]
    > 如果您要同時指派授權給20個以上的使用者，您可以使用 [**選取視圖**] 下拉式清單，然後選擇其中一個選項，或建立您自己的 [視圖]。 然後按一下**Edit**[編輯 **]，接著**兩次，選取授權，然後按一下 [**提交**]。  
  
3. 在 [**產品授權**] 底下的 [動作] 窗格中，按一下 [**編輯**]。 
    
4. 在 [**產品授權**] 頁面上，開啟 [**音訊會議**]，然後按一下 [**儲存**]。 如需授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
> [!NOTE]
> 指派授權之後，Microsoft 可能不會在清單中以音訊會議提供者的形式開始。 如果發生這種情況，請登出系統管理中心，或按 CTRL + F5 重新整理瀏覽器視窗。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>啟用或停用傳送給音訊會議使用者的電子郵件

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在 [**橋設定**] 窗格中，如果使用者的撥入設定變更，請啟用或停用**自動傳送電子郵件給使用者**。

4. 按一下 [儲存]****。

    
**使用 Windows PowerShell**
  
如需詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
  
## <a name="reset-the-meeting-conference-id"></a>重設會議 ID

![](media/teams-logo-30x30.png)**使用 Microsoft [團隊管理中心**] 顯示小組標誌的圖示

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 在 [**音訊會議**] 底下，按一下 [**重設會議 ID**]。  

3. 在 [**重設會議 ID？** ] 視窗中，按一下 [**重設**]。 如果已啟用傳送電子郵件給您的使用者，系統會自動建立會議 ID，並以新的會議 ID 傳送電子郵件給使用者。 預設為啟用。

請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重設會議召集人的 PIN

使用者排程的每個會議都會指派唯一的會議 ID。 雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或者您的使用者無法記住或遺失其會議 ID。 

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 在 [**音訊會議**] 底下，按一下 [**重設 PIN**]，然後按一下 [**重設**]。 
  
當使用者啟用音訊會議或 PIN 重設時，會收到一封電子郵件及其 PIN。 但如果您已停用自動傳送電子郵件，就不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。 PIN 只會在重定後顯示一次。 在重設之後，PIN 就不會再顯示在使用者屬性上;相反，* * * * * 將會顯示。 
  
請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>使用音訊會議資訊傳送電子郵件給使用者

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 在 [**音訊會議**] 底下，按一下 [**以電子郵件傳送會議資訊**]。 

    > [!NOTE]
    > 當您這麼做時，音訊會議 PIN 不會傳送給使用者。 

請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>設定邀請中包含的電話號碼

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。

2. 按一下 [**音訊會議**] 旁的 [**編輯**]。
 
3. 在 [**音訊會議**] 窗格中，您可以設定**付費電話號碼**，並在允許的情況下**撥打免費電話號碼**。

4. 按一下 [儲存]****。
    
請參閱[設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>選擇 [音訊會議橋] 設定

**設定呼叫者加入會議時的會議體驗**

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在 [**橋設定**] 窗格中，啟用或停用**會議進入和結束通知**。

    預設會啟用此功能。 如果您停用此選項，當有人進入或離開會議時，預設已加入會議的使用者將不會收到通知。

4. 在 [**進入/結束宣告類型**] 底下，選擇 [**聲調**] 或 [姓名]**或 [電話號碼**]。 

    如果您選擇 [**名稱] 或 [電話號碼**]，您也可以在加入會議前，選擇要啟用或停用**要求呼叫者記錄其名稱**。 
    > [!NOTE]
> 根據預設，外部參與者看不到撥入參與者的電話號碼。 如果您想要維持這些電話號碼的隱私權，請選取 [**輸入/結束宣告類型**的**音調**] （這可防止小組中的號碼）。

    > [!NOTE]
    > 根據預設，外部參與者看不到撥入參與者的電話號碼。 如果您想要維持這些電話號碼的隱私權，請選取 [**輸入/結束宣告類型**的**音調**] （這可防止小組中的號碼）。

5. 按一下 [儲存]****。

    
請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **設定會議的 PIN 長度**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在 [**橋接器設定**] 窗格中，于 [ **pin 長度**] 清單中輸入您想要的 pin 位數，然後按一下 [**儲存**]。

    PIN 必須在4到12位數之間。 預設值為5。

    
請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **啟用或停用傳送電子郵件給音訊使用者的電子郵件**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 在 [**會議橋接**] 頁面頂端，按一下 [**橋設定**]。 

3. 在橋接器的 [**設定**] 窗格中，啟用或停用 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定變更**）。

4. 按一下 [儲存]****。 
 
    您也可以移至使用者的音訊會議屬性，然後按一下 [**以電子郵件傳送會議資訊**]，透過音訊會議設定傳送電子郵件給使用者。
    
    如果您這樣做，就會傳送一封電子郵件，其中只包含會議 ID 和會議電話號碼，但不會包含該 PIN。

請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音訊會議橋中查看及設定主要（預設）和次要（替代）語言

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 從清單中選取電話號碼，然後按一下 [**編輯**]。

3. 在 [**預設語言**] 和 [**備用語言] （選用）** 底下，選擇您想要的語言。

4. 按一下 [儲存]****。


請參閱[設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>請參閱音訊會議撥入號碼

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，前往 [**會議**  >  **會議橋**]。 

2. 從清單中選取電話號碼，然後按一下 [**編輯**]。 您可以在這裡進行下列動作：
    
   - 查看要用於音訊會議的電話號碼。 
    
   - 查看音訊會議自動語音應答將使用的位置和主要語言。

  
請參閱[音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。
  

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Microsoft 365 或 Office 365，以便在您有多個工作執行時，簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
如需有關 Windows PowerShell 的詳細資訊，請參閱[Microsoft 團隊 PowerShell 參考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)，以取得詳細資訊。
  
    
## <a name="related-topics"></a>相關主題

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


