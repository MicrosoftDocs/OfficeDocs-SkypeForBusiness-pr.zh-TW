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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: '瞭解如何為貴組織新增、變更或移除緊急位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4d9c7c56b4e2b2fd14f703d51b4c07cfc173dfa3
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634852"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>新增、變更或移除貴組織的緊急位置

無論您選擇[哪個 PSTN 連接](pstn-connectivity.md)選項，選擇 Microsoft 通話方案、連線或直接路由緊急位置都可以與電話號碼 &mdash; &mdash; 相關聯。

不過，視 PSTN 連接選項不同，您管理緊急位置和位置需求方式可能會有所不同。 詳細資訊，請參閱管理 [緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)。

本文將說明如何新增、變更或移除貴組織的緊急位置。 

本文適用于 Microsoft 通話方案、連線和直接路由。

您可以在系統管理中心或使用 PowerShell 管理Microsoft Teams組織的緊急位置。

若要指派緊急位置，使用者、電話號碼和緊急位置必須位於同一個國家/地區。 詳細資訊，請參閱指派 [或變更使用者的緊急位置](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>新增緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 按一下 [新增 **]**。
3. 輸入位置的名稱和描述。
4. 選取國家/地區，然後輸入位址。

   > [!NOTE]
   > 在比利時、法國、德國、愛爾蘭、荷蘭和西班牙，必須瞭解，若要在 Microsoft 365 中成功啟用電話號碼，緊急位置中用來取得號碼的位址必須與電話號碼的區碼相符。

5. 如果找不到位址，而您想要手動編輯位址，請開啟手動 **編輯位址**。
6. 按一下 [儲存]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsOnlineLisCivicAddress](/powershell/module/skype/new-csonlineliscivicaddress)。
    
## <a name="change-an-emergency-location"></a>變更緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 在清單中，選取您想要變更的位置，然後按一下 [ **編輯**。
3. 進行您想要的變更。
4. 按一下 [儲存]。

> [!NOTE]
> 只有在位址未驗證時，您才能變更位置的位址資訊。 如果位址已經過驗證，而您需要變更位址、刪除位置，然後使用正確的位址建立新位置。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisCivicAddress](/powershell/module/skype/set-csonlineliscivicaddress)。
    
## <a name="remove-an-emergency-location"></a>移除緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 在清單中，選取您想要移除的位置，然後按一下 [ **刪除**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Remove-CsOnlineLisCivicAddress](/powershell/module/skype/remove-csonlineliscivicaddress)。

## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)