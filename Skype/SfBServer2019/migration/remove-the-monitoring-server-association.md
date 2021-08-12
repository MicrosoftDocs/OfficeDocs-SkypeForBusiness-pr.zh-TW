---
title: 移除監控伺服器關聯
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要移除監控伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。 您可以編輯前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器的屬性，以移除相依性。 在 [拓撲產生器] 中清除相依性和刪除伺服器之後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。
ms.openlocfilehash: 8e4c4b08c6126f6ac2c03d66e9ddcfe921b79850e704c54c65d6951c1449aa9f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280398"
---
# <a name="remove-the-monitoring-server-association"></a>移除監控伺服器關聯

若要移除監控伺服器，您必須變更或清除關聯的前端集區、前端伺服器、Survivable 分支裝置和 Survivable 分支伺服器上的相依性。 您可以編輯前端集區、前端伺服器、Survivable 分支裝置及 Survivable 分支伺服器的屬性，以移除相依性。 在 [拓撲產生器] 中清除相依性和刪除伺服器之後，系統會通知您也會刪除拓撲產生器中相關聯的資料庫存放區物件。
  
### <a name="to-remove-the-monitoring-server-association"></a>若要移除監控伺服器關聯

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。
    
2. 流覽至 [舊版安裝] 節點。
    
3. 在 [拓撲產生器] 中，根據監控伺服器的定義位置，展開 [ **Enterprise Edition 前端** 集區]、[ **Standard Edition 前端伺服器**] 或 [**分支網站**]。
    
4. 如果您有相關聯的 Survivable 分支伺服器，請展開 [ **分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。
    
    > [!NOTE]
    > 使用者介面中的 **Survivable 分支裝置** 會同時套用至 Survivable branch Server 和 Survivable branch 裝置。 
  
5. 以滑鼠右鍵按一下與監控伺服器相關聯的集區、伺服器或裝置，然後按一下 [ **編輯屬性**]。
    
6. 在 [**編輯屬性**] 的 **[一般**  >  **關聯**] 底下，清除 [**關聯監控伺服器**] 核取方塊，然後按一下 **[確定]**。
    
7. 針對與監控伺服器關聯的任何其他集區、伺服器或裝置，重複上述步驟。
    
8. 以滑鼠右鍵按一下監控伺服器，然後按一下 [ **刪除**]。 
    
9. 在 [刪除相依存放區] 上，按一下 [確定]。
    
10. 發佈拓撲，檢查複寫狀態，然後視需要執行商務用 Skype Server 部署嚮導。 
    

