---
title: 指派、變更使用者緊急位置的位置
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
description: 在本文中，您將瞭解如何為貴組織中的使用者指派或變更緊急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 385855c456d3a4e5c2de53fb2605e4d5d30d84a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809523"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>為使用者指派或變更緊急位置的位置

當您將電話號碼指派給使用者時，每個活躍的電話號碼都必須有相關聯的緊急位置。  (當您在 Office 365 中取得電話號碼或傳送電話號碼時，就會建立關聯的位址。 ) 當您將數位與緊急位置建立關聯時，您也可以新增位置，以便在物理位置中提供更精確的位置。 位置可以是地面、建築物翼或使用者所在的辦公室號碼。 您可以在指定的緊急位置有不限數量的位置，而且如果使用者移至不同的 office 或組建，就可以變更位置。 例如，如果使用者從 floor 34 移至地面35。
  
若要瞭解如何取得通話方案和成本，請參閱 [小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
您可以在 Microsoft 團隊系統管理中心或使用 PowerShell 中為使用者指派或變更緊急位置的位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**語音**  >  **電話號碼**]。

2. 在 [ **電話號碼** ] 頁面上，按一下 [ **數位** ] 索引標籤，選取清單中的使用者編號，然後按一下 [ **編輯**]。

3. 在 [ **編輯** ] 窗格的 [ **緊急位置**] 底下，執行下列其中一項操作：

    - 若要指派位置，請搜尋位置或位置，然後選取搜尋結果中的位置。

    - 若要變更已指派給使用者的位置，請按一下 [ **X** ] 以移除現有的位置和位置，然後按一下 [搜尋]，然後選取您要指派的位置。

4. 視您是否想要傳送電子郵件給使用者的電話號碼資訊而定，請關閉或開啟 **含有電話號碼資訊的電子郵件使用者**。 根據預設，這是開啟的。

5. 按一下 **[** 套用]。

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [設定 CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](/microsoftteams/emergency-calling-terms-and-conditions)
