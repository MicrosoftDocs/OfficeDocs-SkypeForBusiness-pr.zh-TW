---
title: 移除監視伺服器關聯
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要移除監視伺服器, 您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性, 以移除相依性。 清除相依性並刪除拓撲建立器中的伺服器之後, 系統會通知您, 拓撲結構庫中相關聯的資料庫存放物件也會被刪除。
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193277"
---
# <a name="remove-the-monitoring-server-association"></a>移除監視伺服器關聯

若要移除監視伺服器, 您需要變更或清除相關聯的 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的相依性。 您可以編輯 [前端] 池、[前端伺服器]、[Survivable 分支裝置] 和 [Survivable 分支伺服器] 的屬性, 以移除相依性。 清除相依性並刪除拓撲建立器中的伺服器之後, 系統會通知您, 拓撲結構庫中相關聯的資料庫存放物件也會被刪除。
  
### <a name="to-remove-the-monitoring-server-association"></a>移除監視伺服器關聯

1. 在商務用 Skype Server 2019 前端伺服器上, 開啟拓撲建立器。
    
2. 流覽至 [舊版安裝] 節點。
    
3. 在拓撲建立器中, 根據監視伺服器的定義位置, 展開 [**企業版前端池**]、[**標準版前端伺服器**] 或 [**分支網站**]。
    
4. 如果您有關聯的 Survivable 分支伺服器, 請展開 [**分支網站**], 展開分支網站名稱, 然後展開 [ **Survivable 分支裝置**]。
    
    > [!NOTE]
    > 使用者介面中的**Survivable 分支裝置**同時適用于 Survivable 分支伺服器和 Survivable 分支裝置。 
  
5. 以滑鼠右鍵按一下與監視伺服器相關聯的 [池]、[伺服器] 或 [裝置], 然後按一下 [**編輯屬性**]。
    
6. 在 [**編輯屬性**] 的 **[一般** > **關聯**] 底下, 清除 [**建立監視伺服器關聯**] 核取方塊, 然後按一下 **[確定]**。
    
7. 針對與監視伺服器相關聯的任何其他池、伺服器或裝置, 重複上述步驟。
    
8. 以滑鼠右鍵按一下監視伺服器, 然後按一下 [**刪除**]。 
    
9. 在 [**刪除相依儲存區**] 中, 按一下 **[確定]**。
    
10. 如有需要, 請發佈拓撲、檢查複製狀態, 以及執行商務用 Skype Server 部署嚮導。 
    

