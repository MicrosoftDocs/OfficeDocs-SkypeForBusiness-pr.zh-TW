---
title: 更新 AAD 連線至包含多個樹系
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
description: 本附錄包含更新 AAD 連線至包含在多個樹系的 microsoft Teams 和商務用 Skype 雲端彙總的詳細的步驟。
ms.openlocfilehash: 3d3d72c14957f0ed8932d95fcd2dbe9ec9c1e37e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696058"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>更新 AAD 連線至包含多個樹系

Azure AD Connect 支援[多個樹系同步處理](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)。 不過，它支援 Azure AD Connect 同步處理至 AAD 只能有一個執行的個體。 因此，在 Azure AD 已安裝在一個樹系的情況下，AAD 連線的現有執行個體必須更新以從其他樹系的同步處理。

 - 如果這兩個樹系間只有一次表示所有的身分識別 （亦即，您還未做任何擁有郵件功能的連絡人），然後您可以只重新執行 [AAD 連線精靈]，選擇 [「 自訂同步處理選項 」，然後在 [**連線您的目錄**] 頁面中，輸入認證與其他樹系的名稱。<br><br>
 ![[連線目錄頁面](../media/cloud-consolidation-connect-your-directories.png)
 - 不過，如果使用者可以在於超過一個目錄和您將會合併資料 （例如，如果連絡人物件對應至另一個樹系中的使用者樹系中有），則需要解除安裝 Azure AD Connect，並重新安裝它。  這是因為只可以在第一個會安裝期間設定跨樹系聯結的規則條件。 這是在下列頁面：<br><br>
 ![唯一識別您的使用者] 頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>另請參閱

[針對小組與 Skype for Business 的雲端彙總](cloud-consolidation.md)