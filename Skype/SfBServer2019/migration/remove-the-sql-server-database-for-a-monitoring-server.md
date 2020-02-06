---
title: 移除監控伺服器的 SQL Server 資料庫
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
description: 移除監視伺服器之後，您可以移除託管伺服器資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
ms.openlocfilehash: 275c69f2c35428bcff2d12799cad3fbc129abc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812821"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>移除監控伺服器的 SQL Server 資料庫

移除監視伺服器之後，您可以移除託管伺服器資料的 SQL Server 資料庫。 使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>使用拓撲產生器移除 SQL Server 資料庫

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲建立器。
    
2. 在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置之監視伺服器相關聯的 SQL Server 實例，然後按一下 [**刪除**]。
    
3. 發佈拓撲，然後檢查 [複製狀態]。
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>從 SQL Server 移除資料庫檔案

1. 若要在 SQL Server 的伺服器上移除資料庫，您必須是您要移除資料庫檔案之 SQL Server 系統管理員群組的成員。
    
2. 開啟商務用 Skype Server 管理命令介面。
    
3. 在命令列中，輸入下列內容：
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    其中_ \<FQDN\> _是資料庫伺服器的完整功能變數名稱（fqdn），而_ \<實例\> _是選用的命名資料庫實例。 
    
4. 當**卸載 CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N，然後按 Enter 鍵以停止 Cmdlet （如果有錯誤）。 
    

