---
title: 移除前端集區的 SQL Server 資料庫
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
description: 移除前端集區或將集區重新設定為使用不同的資料庫之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
ms.openlocfilehash: 2a11057811035b0dc51810d3a6b7eb8220c7df1f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580107"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>移除前端集區的 SQL Server 資料庫

移除前端集區或將集區重新設定為使用不同的資料庫之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 從商務用 Skype Server 2019 前端伺服器，開啟拓撲產生器，並下載現有的拓撲。 
    
2. 在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後 **SQL Server 儲存區**，以滑鼠右鍵按一下與已移除或重新設定的前端集區相關聯的 SQL Server 實例，然後按一下 [**刪除**]。
    
3. 發行拓撲，然後檢查複寫狀態。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>從 SQL 伺服器移除使用者和應用程式資料庫

1. 若要移除 SQL server 上的資料庫，您必須是要移除資料庫檔案之 SQL 伺服器的 SQL Server 系統管理員群組成員。 
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 移除集區使用者存放區的資料庫，請輸入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中  _\<FQDN\>_ 是資料庫伺服器的 FQDN) 的完整功能變數名稱 (，也就是  _\<instance\>_ 指定的資料庫實例 (也就是說，如果有一個定義) 。 
    
4. 移除集區應用程式存放區的資料庫，請輸入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中  _\<FQDN\>_ 是資料庫伺服器的 FQDN，也  _\<instance\>_ 就是指定的資料庫實例 (，也就是) 中已定義。 
    
5. 當 **Uninstall-CsDataBase** 指令指令提示您確認動作時，請閱讀資訊，然後按 Y (或輸入) 繼續; 如果想要停止 Cmdlet () 時，請按 N，然後輸入。 
    

