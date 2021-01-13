---
title: SQL 存放區設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯 SQL Server 資料庫的屬性，您必須變更 SQL Server 資料庫實例。 您無法使用 [編輯屬性] 對話方塊來執行將封存伺服器資料庫從一部電腦移至另一部的工作。 此外，您無法使用 [編輯屬性] 對話方塊來變更主控中央管理存放區的 SQL Server 實例。
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805513"
---
# <a name="sql-store-settings-expander"></a>SQL 存放區設定展開工具
 
若要編輯 SQL Server 資料庫的屬性，您必須變更 SQL Server 資料庫實例。 您無法使用 [ **編輯屬性** ] 對話方塊來執行將封存伺服器資料庫從一部電腦移至另一部的工作。 此外，您無法使用 [ **編輯屬性** ] 對話方塊來變更主控中央管理存放區的 SQL Server 實例。
  
## <a name="editing-the-properties-of-a-sql-server-database"></a>編輯 SQL Server 資料庫的屬性

若要變更中央管理存放區之外的任何資料庫所使用的 SQL Server 實例，請在拓撲產生器中完成下列程式：
  
### <a name="to-modify-an-instance-of-sql-server"></a>修改 SQL Server 實例

1. 在 [ **SQL 存放區** ] 節點下選取適當的資料庫，然後按一下 [ **編輯屬性**]。
    
2. 在 **[編輯內容]** 對話方塊中，執行下列其中一項作業：
    
   - 若要使用預設的 SQL Server 實例，請選取 [ **預設實例** ]，然後按一下 **[確定]**。
    
   - 若要使用具名的資料庫執行個體，請選取 **[具名執行個體]**，在文字方塊中輸入執行個體名稱，然後按一下 **[確定]**。 您應只輸入實例名稱 (例如，ArchivingInstance) ，而不是整個 SQL Server 路徑。
    
當您在 [ **編輯** 內容] 對話方塊中工作時，拓撲產生器將不會確認您輸入的資料庫實例是有效的實例。 例如，如果您無意間 typeArchivingInstanec 為實例名稱，然後按一下 **[確定]**，拓撲產生器會接受該不正確實例。 在發佈此拓撲之前，您必須更正這種錯誤：如果找不到 SQL Server 實例，拓撲產生器將不會為您建立該實例。
  

