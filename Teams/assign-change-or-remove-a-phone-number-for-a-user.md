---
title: 指派、變更或移除使用者的電話號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何為 Teams 使用者指派、變更或移除公司電話號碼，以便外部企業和客戶可以來電。
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589617"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>指派、變更或移除使用者的電話號碼， (通話方案) 

當您設定通話方案時，會指派電話號碼給使用者。 在 Microsoft Teams 中，當使用者按一下通話時，會列出您指派 **的電話號碼**。 有關在直接路由情況下指派、變更或移除使用者電話號碼的指示，請參閱啟用使用者進行直接路由、語音和 [語音信箱](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)。

![Teams 中顯示的使用者電話號碼。](media/teams-phone-number.png)

當您設定使用者以便他們撥打和接聽電話時，您必須先使用 Microsoft Teams 系統管理中心並指派電話號碼。 如果需要，您可以變更或移除電話號碼。
  
若要瞭解如何在 Teams 中取得通話方案及其費用，請參閱 [Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
  
> [!NOTE]
> 若要查看使用者是否已指派授權，其中一個方法就是請至 Microsoft Teams 系統管理中心> **使用者**。 如果指派授權，就會在頁面上顯示授權。  您也可以使用 Microsoft 365 系統管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>指派電話號碼給使用者
 
![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**
    
1. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
2. 在 [ **電話號碼> 頁面上** ，選取清單中的未分配的號碼，然後按一下 [ **編輯**。  
3. 在 [**編輯窗格**， under **assigned to，** search by the user by display name or user name， and then click **Assign.**
4. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。
5. 視您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。 
6. 按一下 [儲存 **]**。

有關 PowerShell 範例，請參閱[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>變更使用者的電話號碼
 
![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**
    
1. 在左側流覽中，按一下 [使用者，找出並按兩下您想要的使用者;按一下帳戶;然後在一般資訊下，記下已指派給使用者的電話號碼。 
2. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
3. 在 [ **電話號碼> 頁面上** ，選取您于步驟 1 中識別的號碼，然後按一下 [ **編輯**。  
4. 在 [ **編輯窗格** ， under **assigned to，** click **the X** to remove the user.
5. 按一下 [儲存 **]**。
6. 在 [ **電話號碼> 頁面上** ，選取清單中的未分配的號碼，然後按一下 [ **編輯**。  
7. 在 [**編輯窗格**， under **assigned to，** search by the user by display name or user name， and then click **Assign.**
8. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。
9. 按一下 [儲存 **]**。

如需 PowerShell 範例，請參閱[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="remove-a-phone-number-from-a-user"></a>移除使用者的電話號碼
 
![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側流覽中，按一下 [使用者，找出並按兩下您想要的使用者;按一下帳戶;然後在一般資訊下，記下已指派給使用者的電話號碼。 
2. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
3. 在 [ **電話號碼> 頁面上** ，選取您于步驟 2 中識別的號碼，然後按一下 [ **編輯**。  
4. 在 [ **編輯窗格** ， under **assigned to，** click **the X** to remove the user.
5. 按一下 [儲存 **]**。

如需 PowerShell 範例，請參閱[Set-CsOnlineVoiceUser。](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

## <a name="related-topics"></a>相關主題

[什麼是位址驗證？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Microsoft 365 通話方案](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
