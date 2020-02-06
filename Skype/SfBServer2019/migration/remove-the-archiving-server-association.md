---
title: 移除封存伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 若要移除封存伺服器，您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性，以移除相依性。 在您清除相依性並刪除拓撲建立器中的伺服器之後，系統會通知您在拓撲建立器中相關聯的資料庫存放物件也會被刪除。
ms.openlocfilehash: 7b6e35131005866feed04a4e9b68c43558b6c1e1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812971"
---
# <a name="remove-the-archiving-server-association"></a>移除封存伺服器關聯

若要移除封存伺服器，您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性，以移除相依性。 清除相依性並刪除拓撲建立器中的伺服器之後，系統會通知您，拓撲結構庫中相關聯的資料庫存放物件也會被刪除。
  
### <a name="to-remove-the-archiving-server-association"></a>移除存檔伺服器關聯

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲建立器。
    
2. 流覽至舊版 [安裝] 節點。
    
3. 在 [拓撲建立器] 中，展開 [**企業版前端] 池**、[**標準版前端伺服器**] 或 [**分支網站**]，視存檔伺服器的定義位置而定。
    
4. 如果您有關聯的 Survivable 分支伺服器，請展開 [**分支網站**]，展開分支網站名稱，然後展開 [ **Survivable 分支裝置**]。
    
    > [!NOTE]
    > 使用者介面中的**Survivable 分支裝置**同時適用于 Survivable 分支伺服器和 Survivable 分支裝置。 
  
5. 以滑鼠右鍵按一下與封存伺服器相關聯的 [池]、[伺服器] 或 [裝置]，然後按一下 [**編輯屬性**]。
    
6. 在 [**編輯屬性**] 的 **[一般** > **關聯**] 底下，清除 [**關聯存檔伺服器**] 核取方塊，然後按一下 **[確定]**。
    
7. 針對與您要移除之存檔伺服器相關聯的任何其他池、伺服器或裝置，重複上述步驟。
    
8. 以滑鼠右鍵按一下 [封存伺服器]，然後按一下 [**刪除**]。
    
9. 在 [**刪除相依儲存區**] 中，按一下 **[確定]**。
    
10. 發佈拓撲，檢查 [複製狀態]，然後視需要執行商務用 Skype Server 部署嚮導。 
    

