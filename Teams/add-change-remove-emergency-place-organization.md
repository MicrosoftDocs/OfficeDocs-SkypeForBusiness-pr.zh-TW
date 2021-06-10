---
title: 新增、變更、移除緊急位置的位置
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: 瞭解如何在系統管理中心為貴組織新增、變更或移除緊急Microsoft Teams位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121501"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a>新增、變更或移除貴組織緊急位置的地方

根據貴組織實體位置的數量，您可以新增建築物、樓層和辦公室的位置，以建立更具體的緊急位置。 請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md) 以瞭解更多資訊。
  
若要瞭解如何取得通話方案及其費用，請參閱Teams[授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

您可以在系統管理中心或使用 PowerShell Microsoft Teams組織的緊急位置。
  
## <a name="add-a-place-to-an-emergency-location"></a>新增位置至緊急位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 在清單中，按一下要新增位置的位置名稱。
3. 在 [ **位置」** 選項卡上，按一下 [ **新增**。
4. 輸入地點名稱，然後按一下 **[Apply.**

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation)。
    
## <a name="change-a-place-for-an-emergency-location"></a>變更緊急位置的位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 在清單中，按一下要變更位置的位置名稱。
3. 在 [ **位置」** 選項卡上，選取您想要變更的位置，然後按一下 [ **編輯**。
4. 更新位置資訊，然後按一下 **[Apply.**

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="remove-a-place-from-an-emergency-location"></a>從緊急位置移除位置

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[位置**  >  **緊急位址**> 。
2. 在清單中，按一下要移除位置的位置名稱。
3. 在 [ **位置」** 選項卡上，選取您想要移除的位置，然後按一下 [ **刪除**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)