---
title: 移除封存伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移除封存伺服器之後，您可以移除主持該池資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
ms.openlocfilehash: 149342f49fded4af294f76028140a9f76f190ed1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988998"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>移除封存伺服器的 SQL Server 資料庫

移除封存伺服器之後，您可以移除主持該池資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲建立器。
    
2. 在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置的存檔伺服器相關的 SQL Server 實例，然後按一下 [**刪除**]。
    
3. 發佈拓撲，然後檢查 [複製狀態]。 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1. 若要移除 SQL Server 上的資料庫，您必須是您要移除資料庫檔案之 SQL Server 的 SQL Server 系統管理員群組的成員。 
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 在命令列中，輸入下列內容：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<FQDN\> _是資料庫伺服器的完整功能變數名稱（fqdn），而_ \<實例\> _是命名的資料庫實例（也就是已定義）。 
    
4. 當**卸載 CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N，然後按 Enter 鍵以停止 Cmdlet （如果有錯誤）。 
    

