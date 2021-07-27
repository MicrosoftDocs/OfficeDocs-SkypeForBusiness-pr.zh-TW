---
title: 更新 AAD Connect 以包含多個樹系
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含更新 AAD 連線的詳細步驟，以包含多個樹系做為 Teams 和商務用 Skype 雲端合併的一部分。
ms.openlocfilehash: 5ca5789ca50f24266ce5fccf16bcf06118e42742
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510524"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD Connect 以包含多個樹系

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD 連線支援[從多個樹系進行同步](/azure/active-directory/connect/active-directory-aadconnect-topologies)處理。 不過，它只支援 Azure AD 連線的一個實例，可同步處理至 AAD。 因此，在 Azure AD 已安裝在一個樹系中的情況下，必須更新 AAD 連線的現有實例，才能從其他樹系進行同步處理。

 - 若所有的身分識別只會在兩個樹系中呈現一次 (也就是說，您未將任何擁有郵件功能的連絡人) 中，您只需重新執行 AAD 連線嚮導，然後選擇 [自訂同步處理選項]，然後在 [**連線目錄**] 頁面上，輸入額外樹系和身分識別的名稱。<br><br>
 ![您的目錄頁面連線](../media/cloud-consolidation-connect-your-directories.png)
 - 不過，如果使用者可以存在於多個目錄中，且您將會合並資料 (例如，如果連絡人物件存在於與另一個樹系) 中的使用者相對應的樹系，則您必須卸載 Azure AD 連線，然後重新安裝。  這是因為跨樹系的加入規則條件只會在第一次安裝期間進行設定。 這是在下列頁面上完成：<br><br>
 ![唯一識別使用者頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另請參閱

[Teams 與商務用 Skype 的雲整合](cloud-consolidation.md)