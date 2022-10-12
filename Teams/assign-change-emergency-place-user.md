---
title: 指派或變更使用者緊急位置的地點
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
description: 在本文中，您將瞭解如何為組織中的使用者指派或變更緊急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bd471e42eb6e8c2404eef47636da2c9894268c
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551637"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>指派或變更使用者緊急位置的位置

無論您選擇 &mdash; [Microsoft 通話方案]、[運算子連線]、[Teams Phone Mobile] 或 [直接路由 &mdash; ] 的[PSTN 連線選項](pstn-connectivity.md)，都必須指派給每個電話號碼或使用者。

不過，視您的 PSTN 連線選項而定，您管理和指派緊急位置給使用者的方式可能會有所不同。 如需詳細資訊，請參閱 [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)。

本文說明如何在 Microsoft Teams 系統管理中心或使用 PowerShell *為使用者* 指派或變更緊急位置的位置。

本文適用于通話方案、電信業者連線和 Teams Phone Mobile。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，按一下 **[語音**  >  **電話號碼]**。

2. 在 [ **電話號碼]** 頁面上，按一下 [ **號碼] 索引卷** 標，選取清單中的使用者號碼，然後按一下 [ **編輯]**。

3. 在 [ **編輯]** 窗格的 [ **緊急位置**] 底下，執行下列其中一項操作：

    - 若要指派位置，請搜尋位置或位置，然後在搜尋結果中選取位置。

    - 若要變更已指派給使用者的位置，請按一下 **[X** ] 移除現有的位置和位置，搜尋並選取您要指派的位置。

4. 根據您是否要傳送含有電話號碼資訊的電子郵件給使用者，請關閉或開啟 **Email有電話號碼資訊的使用者**。 預設會開啟此設定。

5. 按一下 [ **套用]**。

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)