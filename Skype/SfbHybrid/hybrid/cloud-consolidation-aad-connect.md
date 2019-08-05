---
title: 更新 AAD Connect 以包含一個以上的林
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附錄包含更新 AAD 連線的詳細步驟, 以包含多個林, 做為小組和商務用 Skype 的雲端整合的一部分。
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185488"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD Connect 以包含一個以上的林

Azure AD Connect 支援[從多個林進行同步](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)處理。 不過, 它只支援 Azure AD Connect 同步處理到 AAD 的一個實例。 因此, 如果 Azure AD 已安裝在一個目錄林中, 則 AAD Connect 的現有實例必須更新, 才能從額外的林進行同步處理。

 - 如果所有身分識別都只會在兩個目錄林之間呈現一次, 您就可以直接重新執行 AAD 連接嚮導, 選擇 [自訂同步處理選項], 然後在 [連線**您的目錄]** 頁面上, 輸入其他林及憑據的名稱。<br><br>
 ![[連線您的目錄] 頁面](../media/cloud-consolidation-connect-your-directories.png)
 - 不過, 如果使用者可以在多個目錄中存在, 而且您要合併資料 (例如, 如果連絡人物件存在於與另一個目錄林中的使用者對應的林中), 您將需要卸載 Azure AD Connect 並重新安裝。  這是因為跨目錄林連接規則條件只能在第一次安裝期間進行設定。 這會在下列頁面上完成:<br><br>
 ![唯一識別您的使用者頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另請參閱

[團隊與商務用 Skype 的雲端整合](cloud-consolidation.md)