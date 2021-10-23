---
title: 指派、變更或移除使用者的電話號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.openlocfilehash: 92c19912e566f7dbea09b4849d9970619551b4a4
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536504"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>指派、變更或移除使用者的電話號碼

當您設定通話方案或接線連線時，會指派電話號碼給使用者。 在 Microsoft Teams中，當使用者按一下通話時，會列出您指派 **的電話號碼**。 

本文適用于通話方案及接線連線。 若要在直接路由情況下指派、變更或移除使用者的電話號碼，請參閱啟用使用者進行直接路由、語音和 [語音信箱](./direct-routing-enable-users.md)。

在您為通話方案或接線連線使用者指派號碼之前，您必須為使用者取得號碼。 詳細資訊，請參閱取得[通話](getting-phone-numbers-for-your-users.md)方案使用者的號碼，或為使用者設定[運算子連線號碼](operator-connect-configure.md#set-up-phone-numbers)。

  
> [!NOTE]
> 查看使用者是否已指派授權的方法之一，是Microsoft Teams系統管理中心>**使用者**。 如果已指派授權，就會在頁面上顯示授權。  您也可以使用Microsoft 365 系統管理中心。
  
## <a name="assign-a-phone-number-to-a-user"></a>指派電話號碼給使用者

將電話號碼指派給使用者時，請確認使用者的電話號碼和使用位置都在同一個國家/地區。

若要使用系統管理中心指派Teams號碼：
    
1. 在左側流覽中，按一下 **[語音**  >  **電話數位**。

2. 在 [數位 **電話** 頁面上，選取清單中的未指定號碼，然後按一下 [**編輯**。  

3. 在 [ **編輯窗格** 的 **[** 指派給中， the user by， search by the user by display name or user name， then click **Assign**.

4. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。

   > [!NOTE]
   > 如果您要將號碼指派給運算子連線使用者，您可能無法指派或變更相關聯的緊急位置。 此功能取決於您的運算子。 如需詳細資訊，請與您的接線員聯繫。

5. 根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。 

6. 按一下 [儲存]。

若要使用 PowerShell 指派數位，請使用 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) Cmdlet，如下所示：


''PowerShell Set-CsOnlineVoiceUser -identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> 由於使用者與Microsoft 365之間的Teams，使用者最多可能需要 24 小時才能啟用。 如果電話號碼在 24 小時後未正確指派，請參閱電話[服務中心](https://pstnsd.powerappsportals.com/)。 

  
## <a name="change-a-phone-number-for-a-user"></a>變更使用者的電話號碼

若要使用系統管理中心變更使用者Teams電話號碼：
    
1. 在左側導圖中，按一下 [使用者」，找出並按兩下您想要的使用者，按一下[帳戶」，然後在 [一般資訊」 下記下指派給使用者的電話號碼。 

2. 在左側流覽中，按一下 **[語音**  >  **電話數位**。

3. 在 [數位 **電話** 頁面上，選取您于步驟 1 中識別的數位，然後按一下 [**編輯**。  

4. 在 [ **編輯窗格** 的 **[指派給** 的> 下，按一下 **[X** 以移除使用者。

5. 按一下 [儲存]。

6. 在 [數位 **電話** 頁面上，選取清單中的未指定號碼，然後按一下 [**編輯**。  

7. 在 [ **編輯窗格** 的 **[** 指派給中， the user by， search by the user by display name or user name， then click **Assign**.

8. 若要指派或變更相關聯的緊急位置，請在緊急位置下搜尋，然後選取該位置。

      > [!NOTE]
      > 如果您要變更運算子使用者連線號碼，您可能無法指派或變更相關聯的緊急位置。 此功能取決於您的運算子。 如需詳細資訊，請與您的接線員聯繫。

9. 按一下 [儲存]。

有關 PowerShell 範例，請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="remove-a-phone-number-from-a-user"></a>移除使用者的電話號碼

若要使用系統管理中心移除Teams電話號碼：

1. 在左側導圖中，按一下 [使用者」，找出並按兩下您想要的使用者，按一下[帳戶」，然後在 [一般資訊」 下記下指派給使用者的電話號碼。 

2. 在左側流覽中，按一下 **[語音**  >  **電話數位**。

3. 在 [數位 **電話** 頁面上，選取您于步驟 2 中識別的數位，然後按一下 [**編輯**。  

4. 在 [ **編輯窗格** 的 **[指派給** 的> 下，按一下 **[X** 以移除使用者。

5. 按一下 [儲存]。

有關 PowerShell 範例，請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。

## <a name="related-topics"></a>相關主題

[什麼是位址驗證？](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

