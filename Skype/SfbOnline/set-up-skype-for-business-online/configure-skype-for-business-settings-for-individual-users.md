---
title: 系統管理員為個別使用者設定商務用 Skype 設定
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '瞭解如何變更個別使用者的商務用 Skype 設定，例如音訊與視訊會議、通話和會議的錄製。 '
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739171"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>系統管理員：針對個別使用者設定商務用 Skype 設定

> [!IMPORTANT]
> Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。 管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。 若要深入瞭解，請參閱在 [Microsoft 團隊系統管理中心管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。

本文說明管理員如何為少數使用者設定商務用 Skype。 若要大量執行這些步驟，我們提供了您可以使用的 Windows PowerShell Cmdlet 連結。
  
若要允許 (或封鎖) 貴公司中的所有人都能與外部人員通訊，請參閱：
  
- [允許使用者與外部商務用 skype 使用者進行聯絡](allow-users-to-contact-external-skype-for-business-users.md)：您可以讓您的組織使用高級商務用 skype 功能 (共用桌面]、尋找線上的人員等等。 ) 與特定受信任 (同盟) 商務中的人員進行通訊。 本文也說明如何封鎖與特定網域的通訊。
    
- [讓商務用 Skype 使用者新增 skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。 您可以讓您的組織使用商務用 Skype 來搜尋與使用 Skype 的 IM 人員（免費應用程式）。
    
## <a name="configure-general-settings-for-one-user"></a>設定一位使用者的一般設定
<a name="__toc325019204"> </a>

您必須具備系統 [管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 才能執行這些步驟。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**
  
1. 使用您的公司或學校帳戶登入。
    
2. 選擇系統**管理中心**  >  **的商務用 Skype**。
    
3. 選擇 [ **使用者**]。
    
    ![在商務用 Skype 系統管理中心中，選擇 [使用者]。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 選擇您要編輯的使用者。
    
5. 在右面板中，選擇 [Edit] （ **編輯**）。
    
    ![選擇 [編輯] 圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在 [ **一般** ] 選項頁面上，選取或清除您想要變更之功能旁的核取方塊，然後選擇 [ **儲存**]。
    
|**件**|**詳細資料**|
|:-----|:-----|
|音訊及 HD 影片  <br/> |允許此人錄製音訊會議、音訊及視訊會議，或不允許他們排程任何會議 (無) 。  <br/> |
|記錄交談和會議  <br/> |選擇 [允許此人錄製的內容]。  <br/> [商務用 Skype 基本版] 無法使用此選項。  <br/> |
|針對合規性，請關閉未存檔的功能  <br/> | 如果您在法律上需要保留電子儲存資訊，請選擇此選項。 <br/>  選取此選項會關閉您在 Exchange 系統管理中心設定 [就地保留](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) 時不會捕獲的功能。 它會關閉下列功能： <br/>  使用立即訊息傳輸檔案 <br/>  共用的 OneNote 頁面 <br/>  PowerPoint 注釋 <br/> |
   
若要大量設定這些設定，請使用 PowerShell。 請參閱 [設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="block-external-communications"></a>封鎖外部通訊
<a name="__toc325019206"> </a>

在您 [讓商務用 skype 使用者](let-skype-for-business-users-add-skype-contacts.md) 為公司中的每個人新增 Skype 連絡人之後，您就可以使用這些步驟選擇性地封鎖特定人員的外部通訊。
  
1. 選擇 [ **使用者**]，選取您要停用其設定的使用者，然後選擇 [ **編輯** ![ 編輯] ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. 選擇 [ **外部通訊**]，然後視需要清除這些選項：
    
   - **外部商務用 Skype 使用者**：如果您不想讓使用者能夠與聯盟網域中的商務用 skype 使用者通訊，請清除此方塊。
    
   - **外部 Skype 使用者**：如果您不希望使用者能夠與使用 freeSkype 應用程式的人員進行通訊，請清除此方塊。
    
3. 按一下 [儲存]****。
    
若要大量設定這些設定，請使用 PowerShell。 請參閱 [設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>編輯一位使用者的音訊會議設定
<a name="__toc314837483"> </a>

1. 選擇 [ **使用者**]，選取您要進行 wan 編輯之音訊會議設定的使用者，然後選擇 [ **編輯** ![ 編輯] ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. 選擇 [ **音訊會議**]，選取您的音訊會議提供者，輸入或變更要求的資訊，然後按一下 [ **儲存**]。
    
|**音訊會議設定**|**描述**|
|:-----|:-----|
|**提供者名稱** <br/> |從清單中選擇您的提供者。  <br/> |
|需要**付費電話號碼** ()  <br/> |針對協力廠商 ACP，這些電話號碼是您從音訊會議提供者接收到的電話號碼。 如果使用者使用 Microsoft 做為音訊會議提供者，則會是在音訊會議橋接器上設定的號碼。 將數位格式化為想要在商務用 Skype 和 Microsoft 團隊會議邀請中顯示的數位。  <br/> |
|**免付費電話號碼** <br/> |針對協力廠商 ACP，這些電話號碼是您從音訊會議提供者接收到的電話號碼。 如果使用者使用 Microsoft 做為音訊會議提供者，則會是在音訊會議橋接器上設定的號碼。 將數位格式化為想要在商務用 Skype 和 Microsoft 團隊會議邀請中顯示的數位。  <br/> |
|需要**會議 ID 和 PIN** ()  <br/> |參與者 PIN （或會議程式碼），用來加入由這個使用者排程的會議，以及由協力廠商音訊會議提供者提供的會議。 如果使用者使用 Microsoft 作為音訊會議提供者，就不需要這麼做。  <br/> |
   
若要大量設定這些設定，請使用 PowerShell。 請參閱[設定邀請中包含的電話號碼](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[設定您的 Windows PowerShell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>相關主題 

[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[商務用 Skype 和 Microsoft 團隊附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
