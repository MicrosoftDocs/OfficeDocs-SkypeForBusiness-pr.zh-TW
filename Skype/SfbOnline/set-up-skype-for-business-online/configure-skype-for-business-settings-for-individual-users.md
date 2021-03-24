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
description: '瞭解如何變更個別使用者的商務用 Skype 設定，例如：音訊和視訊會議、錄製通話和會議。 '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093387"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>系統管理員：為個別使用者設定商務用 Skype 設定

> [!IMPORTANT]
> Microsoft Teams 系統管理中心已取代商務用 Skype 系統管理中心 (舊版) 。 管理商務用 Skype 的所有設定現在都位於 Teams 系統管理中心。 您必須被指派全域系統管理員或商務用 Skype 系統管理員的 Azure [AD](/azure/active-directory/roles/permissions-reference) 系統管理員角色，才能在 Teams 系統管理中心管理商務用 Skype 功能。 若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。

本文將說明系統管理員如何為少數使用者設定商務用 Skype。 若要大量執行這些步驟，我們已提供您可以使用的 Windows PowerShell Cmdlet 連結。
  
若要允許 (或封鎖) 企業中的每個人與外部人員通訊，請參閱：
  
- 允許使用者與外部商務用[Skype](allow-users-to-contact-external-skype-for-business-users.md)使用者聯繫：您可以讓貴組織使用進一步商務用 Skype 功能 (共用桌面、尋找誰在線上等 ) 來與特定信任的 (聯盟) 企業的人員通訊。 本文也會說明如何封鎖與特定網域的通訊。
    
- [讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)。 您可以讓貴組織使用商務用 Skype 搜尋並使用免費應用程式 Skype 的人員並 IM。
    
## <a name="configure-general-settings-for-one-user"></a>設定一位使用者的一般設定
<a name="__toc325019204"> </a>

您必須擁有 [系統管理員許可權，才能](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 執行這些步驟。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**
  
1. 使用公司或學校帳戶來登錄。
    
2. 選擇 **系統管理中心**  >  **商務用 Skype**。
    
3. 選擇 **使用者**。
    
    ![在商務用 Skype 系統管理中心，選擇使用者。](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 選擇您想要編輯的使用者。
    
5. 在右面板中 **，選擇編輯**。
    
    ![選擇編輯圖示。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 在一 **般** 選項頁面上，選取或清除您想要變更的功能旁的核取方塊， **然後選擇儲存**。
    
|**選項**|**詳細資料**|
|:-----|:-----|
|音訊和 HD 影片  <br/> |允許此人錄製音訊會議、音訊和視訊會議，或不允許他們排程任何 (會議) 。  <br/> |
|錄製交談和會議  <br/> |選擇允許此人錄製哪些專案。  <br/> 此選項不適用於商務用 Skype Basic。  <br/> |
|針對合規性，請關閉未存檔的功能  <br/> | 如果您依法需要保留以電子方式儲存的資訊，請選擇這個選項。 <br/>  選取此選項會關閉 Exchange 系統管理中心設定就地保留時未[](/exchange/security-and-compliance/in-place-and-litigation-holds)捕獲的功能。 它會關閉下列功能： <br/>  使用立即訊息傳輸檔案 <br/>  共用 OneNote 頁面 <br/>  PowerPoint 注釋 <br/> |
   
若要大量設定這些設定，請使用 PowerShell。 請參閱 [為 Windows PowerShell 設定您的電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="block-external-communications"></a>封鎖外部通訊
<a name="__toc325019206"> </a>

當您讓 [商務用 Skype 使用者為公司](let-skype-for-business-users-add-skype-contacts.md) 中的每個人新增 Skype 連絡人之後，您可以使用這些步驟選擇性地封鎖特定人員的外部通訊。
  
1. 選擇 **使用者**，選取您想要停用其設定的使用者，然後選擇 **編輯編輯** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. 選擇 **外部通訊**，然後適當清除選項：
    
   - **外部商務** 用 Skype 使用者：如果您不希望使用者與在聯盟網域的商務用 Skype 使用者通訊，請清除此方塊。
    
   - **外部 Skype 使用者**：如果您不希望使用者能夠與使用 freeSkype 應用程式的人員通訊，請清除此方塊。
    
3. 按一下 [儲存]。
    
若要大量設定這些設定，請使用 PowerShell。 請參閱 [為 Windows PowerShell 設定您的電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>編輯一個使用者的音訊會議設定
<a name="__toc314837483"> </a>

1. 選擇 **使用者**，選取要編輯其音訊會議設定的使用者， **然後選擇編輯** ![ 編輯 ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) 。
    
2. 選擇 **[音訊會議」，** 選取您的音訊會議提供者，輸入或變更要求的資訊，然後按一下 [ **儲存**。
    
|**音訊會議設定**|**描述**|
|:-----|:-----|
|**提供者名稱** <br/> |從清單中選擇您的提供者。  <br/> |
|**必須撥打 (** 電話號碼)  <br/> |對於協力廠商 ACP，這些電話號碼就是您從音訊會議提供者收到的號碼。 如果使用者使用 Microsoft 做為音訊會議提供者，這些號碼會設定在音訊會議橋接器上。 在商務用 Skype 和 Microsoft Teams 會議要求中，將數位格式格式化為您想要的數位。  <br/> |
|**免付費號碼** <br/> |對於協力廠商 ACP，這些電話號碼就是您從音訊會議提供者收到的號碼。 如果使用者使用 Microsoft 做為音訊會議提供者，這些號碼會設定在音訊會議橋接器上。 在商務用 Skype 和 Microsoft Teams 會議要求中，格式化數位。  <br/> |
|**會議 ID 和 PIN** (必須)  <br/> |參與者 PIN 或會議代碼，用來加入此使用者排程的會議，且由協力廠商音訊會議提供者提供。 如果使用者使用 Microsoft 做為音訊會議提供者，則不需要這樣做。  <br/> |
   
若要大量設定這些設定，請使用 PowerShell。 請參閱[設定邀請中包含的電話號碼](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md)[設定電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>相關主題 

[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[商務用 Skype 和 Microsoft Teams 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
