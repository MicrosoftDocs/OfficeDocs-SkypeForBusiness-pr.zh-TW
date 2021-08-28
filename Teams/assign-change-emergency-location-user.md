---
title: 指派或變更使用者的緊急位置
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
description: 在本文中，您將瞭解如何為貴組織的使用者指派或變更緊急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36be65ef14cfe0fc97ce49dfa9227fe50daa18f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588375"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>指派或變更使用者的緊急位置

當您設定通話方案時，您必須為每個電話號碼或使用者指派緊急位置。 在歐盟國家/地區，當您從 Microsoft 365 或 Office 365 取得電話號碼，或將電話號碼轉接到 Microsoft 365 或 Office 365 時，緊急位置會與電話號碼相關聯。 在美國，緊急位置會與指派給使用者的電話號碼相關聯。 如果指派給緊急位址的使用者移至新位置，可以變更緊急位址。 有關緊急位址和位置的更多資訊，請參閱什麼是緊急位置、地點 [和通話路由？](./what-are-emergency-locations-addresses-and-call-routing.md)。
  
若要瞭解如何取得通話方案及其費用，請參閱Teams[附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
您可以在系統管理中心指派或變更使用者的緊急Microsoft Teams，或使用 PowerShell。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[語音** 電話  >  **號碼**。

2. 在 [數位 **電話** 頁面上，按一下 [數位> 選項卡，選取清單中的使用者號碼，然後按一下 [**編輯**。

3. 在編輯 **窗格** 的緊急 **位置下**，執行下列其中一項操作：

   - 若要指派緊急位置，請搜尋並選取緊急位置。

   - 若要變更已指派給使用者的緊急位置，請按一下 **[X** 以移除現有位置，然後搜尋並選取您想要指派的位置。

4. 根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。

5. 按一下 **[Apply.**

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [指派或變更使用者緊急位置的地方](assign-change-emergency-place-user.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)