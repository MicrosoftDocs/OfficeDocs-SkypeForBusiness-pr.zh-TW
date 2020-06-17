---
title: 移除監控伺服器的 SQL Server 資料庫
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
description: 在您移除監控伺服器之後，您可以移除主控伺服器資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753325"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>移除監控伺服器的 SQL Server 資料庫

在您移除監控伺服器之後，您可以移除主控伺服器資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。
    
2. 在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後按一下 [ **Sql server 存放區**]，以滑鼠右鍵按一下與已移除或已重新設定之監控伺服器關聯的 SQL Server 實例，然後按一下 [**刪除**
    
3. 發行拓撲，然後檢查複寫狀態。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1. 若要移除 SQL Server 之伺服器上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL server 系統管理員群組成員。
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 在命令列輸入下列命令：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中 _\<FQDN\>_ 是資料庫伺服器的完整功能變數名稱（FQDN），也 _\<instance\>_ 就是選用的名稱資料庫實例。 
    
4. 當**Uninstall-CsDataBase**指令指令提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N 然後輸入如果您想要停止 Cmdlet （如果有錯誤）。 
    

