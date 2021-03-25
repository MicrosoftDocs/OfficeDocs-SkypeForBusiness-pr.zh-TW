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
description: 本附錄包含更新 AAD 連線的詳細步驟，以包含多個樹系，作為小組和商務用 Skype 的雲端合併的一部分。
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120372"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD Connect 以包含多個樹系

Azure AD Connect 支援 [從多個樹系進行同步](/azure/active-directory/connect/active-directory-aadconnect-topologies)處理。 不過，它只支援 Azure AD Connect 的一個實例同步至 AAD。 因此，在 Azure AD 已安裝在一個樹系中的情況下，必須更新 AAD 連線的現有實例，以便從其他樹系進行同步處理。

 - 若所有的身分識別只會在兩個樹系中呈現一次 (也就是說，您未將任何擁有郵件功能的連絡人) 上，請選擇 [自訂同步處理選項]，然後在 [連線您的 **目錄** ] 頁面上，輸入其他樹系和身分識別的名稱。<br><br>
 ![[連線您的目錄] 頁面](../media/cloud-consolidation-connect-your-directories.png)
 - 不過，如果使用者可以存在於多個目錄中，且您將會合並資料 (例如，如果連絡人物件存在於與另一個樹系中的使用者相對應的樹系) 中，您將需要卸載 Azure AD Connect，然後重新安裝。  這是因為跨樹系的加入規則條件只會在第一次安裝期間進行設定。 這是在下列頁面上完成：<br><br>
 ![唯一識別使用者頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另請參閱

[小組和商務用 Skype 的雲端整合](cloud-consolidation.md)