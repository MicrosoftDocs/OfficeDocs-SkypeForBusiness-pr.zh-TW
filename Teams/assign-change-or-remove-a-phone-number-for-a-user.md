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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 瞭解如何指派、變更或移除您的公司電話號碼Teams讓外部企業和客戶可以來電。
ms.openlocfilehash: 44254c8d8c8886e72b699c3890017a2b817cd135
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727502"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>指派、變更或移除使用者的電話號碼 (方案) 

當您設定通話方案時，會指派電話號碼給使用者。 在 Microsoft Teams中，當使用者按一下通話時，會列出您指派 **的電話號碼**。 有關在直接路由情況下指派、變更或移除使用者電話號碼的指示，請參閱啟用使用者進行直接路由、語音和 [語音信箱](./direct-routing-enable-users.md)。

![使用者的電話號碼會顯示在 Teams。](media/teams-phone-number.png)

當您設定使用者以便他們撥打和接聽電話時，您必須先使用 Microsoft Teams系統管理中心並指派電話號碼。 如果需要，您可以變更或移除電話號碼。
  
若要瞭解如何取得通話方案Teams方案的成本，請參閱Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
> [!NOTE]
> 查看使用者是否已指派授權的方法之一，是Microsoft Teams系統管理中心>**使用者**。 如果已指派授權，就會在頁面上顯示授權。  您也可以使用Microsoft 365 系統管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>指派電話號碼給使用者
 
![顯示標誌圖示Microsoft Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**
    
1. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
2. 在 [**數位電話** 頁面上，選取清單中的未指定號碼，然後按一下 [**編輯**。  
3. 在 [ **編輯窗格** 的 **[** 指派給中， the user by， search by the user by display name or user name， then click **Assign**.
4. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。
5. 根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。 
6. 按一下 [儲存]。

有關 PowerShell 範例，請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。

> [!NOTE]
> 由於使用者與Microsoft 365之間的Office 365 Teams，使用者最多可能需要 24 小時才能啟用。 如果 24 小時後電話號碼未正確指派，請聯絡商務產品 [支援人員 - 系統管理協助](/microsoft-365/admin/contact-support-for-business-products)。 我們在此提供協助！

  
## <a name="change-a-phone-number-for-a-user"></a>變更使用者的電話號碼
 
![顯示標誌圖示Microsoft Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**
    
1. 在左側導航中，按一下 [使用者」，找出並按兩下您想要的使用者，按一下[帳戶」，然後在 [一般資訊> 下，記下指派給使用者的電話號碼。 
2. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
3. 在 [數位 **電話** 頁面上，選取您于步驟 1 中識別的數位，然後按一下 [**編輯**。  
4. 在 [ **編輯窗格** 的 **[指派給** 的> 下，按一下 **[X** 以移除使用者。
5. 按一下 [儲存]。
6. 在 [**數位電話** 頁面上，選取清單中的未指定號碼，然後按一下 [**編輯**。  
7. 在 [ **編輯窗格** 的 **[** 指派給中， the user by， search by the user by display name or user name， then click **Assign**.
8. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。
9. 按一下 [儲存]。

如需 PowerShell 範例，請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="remove-a-phone-number-from-a-user"></a>移除使用者的電話號碼
 
![顯示標誌圖示Microsoft Teams圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導航中，按一下 [使用者」，找出並按兩下您想要的使用者，按一下[帳戶」，然後在 [一般資訊> 下，記下指派給使用者的電話號碼。 
2. 在左側流覽中，按一下 **[語音**  >  **電話號碼**。
3. 在 [數位 **電話** 頁面上，選取您于步驟 2 中識別的數位，然後按一下 [**編輯**。  
4. 在 [ **編輯窗格** 的 **[指派給** 的> 下，按一下 **[X** 以移除使用者。
5. 按一下 [儲存]。

如需 PowerShell 範例，請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="related-topics"></a>相關主題

[什麼是位址驗證？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

[通話方案Microsoft 365](./calling-plans-for-office-365.md)
