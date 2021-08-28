---
title: 移除封存伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 移除封存伺服器之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
ms.openlocfilehash: 9305109e38c265b919d9ec22fa626d27efb19225
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621915"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>移除封存伺服器的 SQL Server 資料庫

移除封存伺服器之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。
    
2. 在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後 **SQL Server 儲存區** 中，以滑鼠右鍵按一下與已移除或重新設定之封存伺服器相關聯的 SQL Server 實例，然後按一下 [**刪除**]。
    
3. 發行拓撲，然後檢查複寫狀態。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1. 若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。 
    
2. 開啟 [商務用 Skype Server 管理命令介面]。
    
3. 在命令列輸入下列命令：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中  _\<FQDN\>_ 是資料庫伺服器的 FQDN) 的完整功能變數名稱 (，也就是  _\<instance\>_ 指定的資料庫實例 (也就是說，如果有一個定義) 。 
    
4. 當 **Uninstall-CsDataBase** 指令指令提示您確認動作時，請閱讀資訊，然後按 Y (或輸入) 繼續; 如果想要停止 Cmdlet () 時，請按 N，然後輸入。 
    

