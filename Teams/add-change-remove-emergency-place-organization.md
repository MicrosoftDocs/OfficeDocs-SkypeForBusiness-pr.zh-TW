---
title: 新增、變更、移除緊急位置的地點
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 瞭解如何新增、變更或移除組織的緊急位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5421ff4e73d93c12244b3419342110b419f1b500
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614186"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>新增、變更或移除貴組織緊急位置的地方

根據組織中的實體位置數目，您可以新增建築物、樓層和辦公室的 *地點* ，以建立更特定的緊急位置。

不過，視您的 PSTN 連線選項而定，您管理緊急位置和位置需求的方式可能會有所不同。 如需詳細資訊，請參閱 [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。

本文說明如何為貴組織新增、變更或移除緊急位置。

本文適用于 Microsoft 通話方案、電信業者連線、Teams Phone Mobile 和直接路由。

您可以在 Microsoft Teams 系統管理中心或使用 PowerShell 來管理組織的緊急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>新增位置至緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 在清單中，按一下您要新增位置的位置名稱。
3. 在 [ **位置] 索引** 標籤上，按一下 [ **新增]**。
4. 輸入地名，然後按一下 [ **套用]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>變更緊急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 在清單中，按一下您要變更位置的位置名稱。
3. 在 [位置 **] 索** 引標籤上，選取您要變更的位置，然後按一下 [ **編輯]**。
4. 更新位置資訊，然後按一下 [ **套用]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>從緊急位置移除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 [**位置**  >  **緊急位址]**。
2. 在清單中，按一下您要移除位置的位置名稱。
3. 在 [位置 **] 索** 引標籤上，選取您要移除的位置，然後按一下 [ **刪除]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)