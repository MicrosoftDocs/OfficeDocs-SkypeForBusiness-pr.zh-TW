---
title: 指派或變更使用者的緊急位置
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
description: 本文將瞭解如何為貴組織的使用者指派或變更緊急位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004635be112bb8d38b88277e89c24d263b21ec37
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180896"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>指派或變更使用者的緊急位置

無論您選擇 Microsoft 通話方案、連線或直接路由的[PSTN](pstn-connectivity.md)連接選項，都需要將緊急位置指派給每個電話號碼 &mdash; &mdash; 或使用者。

不過，根據您的 PSTN 連接選項，您管理及指派使用者緊急位置方式可能會有所不同。 詳細資訊，請參閱管理 [緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)。

本文將說明如何指派或變更使用者的緊急位置。 

本文適用于通話方案及接線連線。
  
您可以在系統管理中心指派或變更使用者的緊急Microsoft Teams，或使用 PowerShell。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，按一下 **[語音電話**  >  **號碼**。

2. 在 [數位 **電話** 頁面上，按一下 [數位> 選項卡，選取清單中的使用者號碼，然後按一下 [**編輯**。

3. 在編輯 **窗格** 的緊急 **位置下**，執行下列其中一項操作：

   - 若要指派緊急位置，請搜尋並選取緊急位置。

   - 若要變更已指派給使用者的緊急位置，請按一下 **[X** 以移除現有位置，然後搜尋並選取您想要指派的位置。

4. 根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。

5. 按一下 **[Apply.**

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)。 

    
## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者緊急位置的地方](assign-change-emergency-place-user.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)
