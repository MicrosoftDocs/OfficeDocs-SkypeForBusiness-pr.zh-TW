---
title: 新增、變更、移除緊急位置
author: cichur
ms.author: v-cichur
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
description: '瞭解如何在系統管理中心新增、變更或移除組織的緊急Microsoft Teams位置。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6523a3a3f19b2c3145bb6e89f47029c4d982ab1
ms.sourcegitcommit: 5a28d052379aef67531d3023cbe4dff30dba1136
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2021
ms.locfileid: "60465789"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a>新增、變更或移除貴組織的緊急位置

**無論您選擇 [何種 PSTN](pstn-connectivity.md)連接選項 ，例如 Microsoft 通話方案、連線或直接路由，緊急位置都可以與電話號碼相關聯。不過，根據您的 PSTN 連接選項，位置需求可能會有所不同。**

**針對通話方案，** 緊急位置必須與電話號碼相關聯，但發生這種情況時，可能會因國家/地區而異。 例如，在美國，當您將電話號碼指派給使用者時，您必須建立緊急位置的關聯。 在英國，當您從目前服務提供者取得電話號碼或Microsoft 365電話號碼時，您必須將緊急位置與電話號碼建立關聯。

**針對運算子連線， ...**

**針對直接路由...**

**這是否適用于所有 3 個？**
無論您位於哪個國家/地區，都可以在緊急位置新增地點或地點，並移除緊急位置。 根據貴組織中實際位置的數量，您可以建立建築物、樓層和辦公室的位置。 請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)。

您可以在系統管理中心或使用 PowerShell 管理Microsoft Teams組織的緊急位置。

**若要指派緊急位置，使用者、電話號碼和緊急位置必須位於同一個國家/地區。**  詳細資訊，請參閱指派 [或變更使用者的緊急位置](assign-change-emergency-location-user.md)。
  
## <a name="add-an-emergency-location"></a>新增緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 按一下 [新增 **]**。
3. 輸入位置的名稱和描述。
4. 選取國家/地區，然後輸入位址。

   > [!NOTE]
   > 在比利時、法國、德國、愛爾蘭、荷蘭和西班牙，您必須瞭解，若要在 Microsoft 365 中成功啟用電話號碼，緊急位置中用來取得號碼的位址必須與電話號碼的區碼相符。

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