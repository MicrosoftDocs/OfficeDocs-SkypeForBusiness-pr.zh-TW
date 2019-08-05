---
title: SQL Store 設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯 SQL Server 資料庫的屬性, 您必須變更 SQL Server 資料庫實例。 您無法使用 [編輯屬性] 對話方塊來執行工作, 例如, 將您的封存伺服器資料庫從一部電腦移到另一部。 此外, 您無法使用 [編輯屬性] 對話方塊來變更託管中央管理儲存區的 SQL Server 實例。
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193484"
---
# <a name="sql-store-settings-expander"></a>SQL Store 設定擴展器
 
若要編輯 SQL Server 資料庫的屬性, 您必須變更 SQL Server 資料庫實例。 您無法使用 [**編輯屬性**] 對話方塊來執行工作, 例如, 將您的封存伺服器資料庫從一部電腦移到另一部。 此外, 您無法使用 [**編輯屬性**] 對話方塊來變更託管中央管理儲存區的 SQL Server 實例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>編輯 SQL Server 資料庫的屬性

若要變更由中央管理儲存體以外的任何資料庫所使用的 SQL Server 實例, 請在拓撲建立器中完成下列程式:
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改 SQL Server 實例

1. 在 [ **SQL 店鋪**] 節點下選取適當的資料庫, 然後按一下 [**編輯屬性**]。
    
2. 在 [**編輯屬性**] 對話方塊中, 執行下列其中一項操作:
    
   - 若要使用預設的 SQL Server 實例, 請選取 [**預設實例**], 然後按一下 **[確定]**。
    
   - 若要使用命名資料庫實例, 請選取 [**命名實例**], 在文字方塊中輸入實例名稱, 然後按一下 **[確定]**。 您應該只輸入實例名稱 (例如, ArchivingInstance), 而非整個 SQL Server 路徑。
    
當您在 [**編輯屬性**] 對話方塊中工作時, 拓撲建立器不會確認您輸入的資料庫實例是有效的實例。 例如, 如果您無意間 typeArchivingInstanec 為實例名稱, 然後按一下 **[確定]**, 拓撲建立器就會接受不正確實例。 您必須修正此錯誤, 才能發佈此拓朴: 如果找不到 SQL Server 實例, 拓撲建立器就不會為您建立該實例。
  

