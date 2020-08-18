---
title: 指派或變更使用者的緊急位置
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
description: 在本文中，您將瞭解如何為貴組織中的使用者指派或變更緊急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f2e927e90a7ac6b79d6eb63c807e063ca7d78c7
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788657"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>指派或變更使用者的緊急位置

當您設定通話方案時，您必須將緊急位置指派給每個電話號碼或使用者。 在歐洲國家/地區，當您從 Microsoft 365 或 Office 365 取得電話號碼時，或當您將電話號碼轉接到 Microsoft 365 或 Office 365 時，緊急位置會與電話號碼產生關聯。 在美國，緊急位置會與指派給使用者的電話號碼相關聯。 如果您指派的使用者移至新的位置，就可以變更緊急位址。 如需有關緊急位址和位置的詳細資訊，請參閱 [什麼是緊急位置、地點及呼叫路由？](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。
  
若要瞭解如何取得通話方案和成本，請參閱 [小組附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。
  
您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 指派或變更使用者的緊急位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**語音**  >  **電話號碼**]。

2. 在 [ **電話號碼** ] 頁面上，按一下 [ **數位** ] 索引標籤，選取清單中的使用者編號，然後按一下 [ **編輯**]。

3. 在 [ **編輯** ] 窗格的 [ **緊急位置**] 底下，執行下列其中一項操作：

   - 若要指派緊急位置，請搜尋並選取緊急位置。

   - 若要變更已指派給使用者的緊急位置，請按一下 [ **X** ] 以移除現有的位置，然後搜尋並選取您要指派的位置。

4. 視您是否想要傳送電子郵件給使用者的電話號碼資訊而定，請關閉或開啟 **含有電話號碼資訊的電子郵件使用者**。 根據預設，這是開啟的。

5. 按一下 **[** 套用]。

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [設定 CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)。 

    
## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [指派或變更使用者緊急位置的地方](assign-change-emergency-place-user.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
