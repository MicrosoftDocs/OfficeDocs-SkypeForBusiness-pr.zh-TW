---
title: 新增、變更、移除緊急位置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 瞭解如何新增、變更或移除組織的緊急位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 23eb549592c8ead6983253d1a228020f3851e1a7
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551487"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>新增、變更或移除貴組織的緊急位置

無論您選擇 &mdash; 的[PSTN 連線選項](pstn-connectivity.md)為何，Microsoft 通話方案、運算子連線、Teams Phone Mobile 或直接路由 &mdash; 緊急位置都可以與電話號碼相關聯。

不過，視您的 PSTN 連線選項而定，您管理緊急位置和位置需求的方式可能會有所不同。 如需詳細資訊，請參閱 [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。

本文說明如何新增、變更或移除組織的緊急位置。 

本文適用于 Microsoft 通話方案、電信業者連線、Teams Phone Mobile 和直接路由。

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 來管理組織的緊急位置。

若要指派緊急位置，使用者、電話號碼和緊急位置都必須在同一個國家/地區。 如需詳細資訊，請參閱 [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>新增緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 按一下 [新增 **]**。
3. 輸入位置的名稱和描述。
4. 選取國家或地區，然後輸入位址。

   > [!NOTE]
   > 在比利時、法國、德國、愛爾蘭、荷蘭和西班牙，請務必瞭解，若要在 Microsoft 365 中成功啟用電話號碼，在緊急位置中設定的位址必須符合電話號碼的區碼。

5. 如果找不到位址，而且您想要手動編輯位址，請開啟 **[手動編輯位址]**。
6. 按一下 [儲存]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>變更緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 在清單中，選取您要變更的位置，然後按一下 [ **編輯]**。
3. 進行您想要的變更。
4. 按一下 [儲存]。

> [!NOTE]
> 只有未驗證位址時，您才能變更位置的位址資訊。 如果位址已經過驗證，而您需要變更位址，請刪除位置，然後建立具有正確位址的新位置。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>移除緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 在清單中，選取您要移除的位置，然後按一下 [ **刪除]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)