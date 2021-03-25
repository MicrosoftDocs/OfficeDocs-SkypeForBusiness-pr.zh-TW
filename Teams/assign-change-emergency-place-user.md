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
description: 在本文中，您將瞭解如何為貴組織的使用者指派或變更緊急位置的位置。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120825"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>指派或變更使用者緊急位置的位置

當您將電話號碼指派給使用者時，每個使用中電話號碼都必須有相關聯的緊急位置。  (當您在 Office 365 中取得電話號碼或轉接電話號碼時，即會建立位址關聯。) 當您將號碼與緊急位置建立關聯時，您也可以新增位置，在實體位置中提供更精確的位置。 位置可以是使用者所在的樓面、大樓樓面或辦公室號碼。 您可以為指定緊急位置提供無限個位置，如果使用者移至不同的辦公室或建築物，您可以變更位置。 例如，如果使用者從第 34 層移至第 35 層。
  
若要瞭解如何取得通話方案及其費用，請參閱 [Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
您可以在 Microsoft Teams 系統管理中心，或使用 PowerShell，為使用者指派或變更緊急位置的位置。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側流覽中，按一下 **[語音**  >  **電話號碼>**。

2. 在 [**電話號碼>** 頁面上，按一下 [數位 **>** 選項卡，選取清單中的使用者號碼，然後按一下 [**編輯。**

3. 在編輯 **窗格** 的緊急 **位置下**，執行下列其中一項操作：

    - 若要指派位置，請搜尋位置或位置，然後選取搜尋結果中的位置。

    - 若要變更已指派給使用者的位置，請按一下 **[X** 以移除現有的位置和位置，然後搜尋並選取您想要指派的位置。

4. 根據您是否要傳送包含其電話號碼資訊的電子郵件給使用者，請關閉或開啟包含電話號碼 **資訊的電子郵件使用者**。 根據預設，這會是啟用狀態。

5. 按一下 **[Apply.**

## <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation)。
    
## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [新增、變更或移除貴組織緊急位置的地方](add-change-remove-emergency-place-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)
- [緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)