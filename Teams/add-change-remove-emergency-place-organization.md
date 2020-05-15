---
title: 新增、變更、移除緊急位置的位置
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: 瞭解如何在 Microsoft 團隊系統管理中心新增、變更或移除您組織緊急位置的位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232494"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>新增、變更或移除貴組織緊急位置的地方

視貴組織中的物理位置數量而定，您可以新增建築物、地面和辦事處的位置，以建立更明確的緊急位置。 如需詳細資訊，請參閱[管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。
  
若要瞭解如何取得通話方案和成本，請參閱[小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 管理您組織的緊急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>在緊急位置加入地點

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。
2. 在清單中，按一下您要新增位置的位置名稱。
3. 按一下 [**位置**] 索引標籤上的 [**新增位置**]。
4. 輸入地點名稱，**然後按一下 [** 套用]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[新-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>變更緊急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。
2. 在清單中，按一下您要變更位置的位置名稱。
3. 在 [**位置**] 索引標籤上，選取您要變更的位置，然後按一下 [**編輯**]。
4. 更新 [位置資訊]，**然後按一下 [** 套用]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[設定 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>從緊急位置移除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**地點**  >  **緊急位址**]。
2. 在清單中，按一下您要移除位置的位置名稱。
3. 在 [**位置**] 索引標籤上，選取您要移除的位置，然後按一下 [**刪除**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[移除-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)
