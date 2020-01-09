---
title: 移除前端集區的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移除前端池或將該池重新設定為使用不同的資料庫之後，您可以移除託管該池資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
ms.openlocfilehash: f26cf1f93abb8538c068a4ab2d6f81c9c36d759d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989088"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>移除前端集區的 SQL Server 資料庫

移除前端池或將該池重新設定為使用不同的資料庫之後，您可以移除託管該池資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 從商務用 Skype Server 2019 前端伺服器，開啟拓撲產生器並下載現有的拓撲。 
    
2. 在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置的 [前端] 池相關聯的 SQL Server 實例，然後按一下 [**刪除**]。
    
3. 發佈拓撲，然後檢查複製狀態。 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>從 SQL server 移除使用者和應用程式資料庫

1. 若要移除 SQL server 上的資料庫，您必須是您要移除資料庫檔案之 SQL server 的 SQL Server 系統管理員群組的成員。 
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 若要移除 [pool 使用者] 商店的資料庫，請輸入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<FQDN\> _是資料庫伺服器的完整功能變數名稱（fqdn），而_ \<實例\> _是命名的資料庫實例（也就是已定義）。 
    
4. 若要移除 [pool] 應用程式存放區的資料庫，請輸入：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<fqdn\> _是資料庫伺服器的 fqdn，而_ \<實例\> _是命名的資料庫實例（也就是已定義）。 
    
5. 當**卸載 CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N，然後按 Enter 鍵以停止 Cmdlet （如果有錯誤）。 
    

