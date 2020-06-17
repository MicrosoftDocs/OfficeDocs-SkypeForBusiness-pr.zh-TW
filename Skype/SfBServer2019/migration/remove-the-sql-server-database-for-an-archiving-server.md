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
localization_priority: Normal
description: 移除封存伺服器之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753305"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="6e186-104">移除封存伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="6e186-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="6e186-105">移除封存伺服器之後，您可以移除主控集區資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6e186-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="6e186-106">請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6e186-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="6e186-107">使用拓撲產生器移除 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="6e186-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="6e186-108">在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="6e186-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="6e186-109">在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後按一下 [ **Sql server 存放區**]，以滑鼠右鍵按一下與已移除或重新設定之封存伺服器相關聯的 SQL server 實例，然後按一下 [**刪除**</span><span class="sxs-lookup"><span data-stu-id="6e186-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="6e186-110">發行拓撲，然後檢查複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="6e186-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="6e186-111">從 SQL Server 移除資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="6e186-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="6e186-112">若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="6e186-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="6e186-113">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="6e186-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="6e186-114">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="6e186-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="6e186-115">其中 _\<FQDN\>_ 是資料庫伺服器的完整功能變數名稱（FQDN），也就 _\<instance\>_ 是指定的資料庫實例（也就是定義的資料庫實例）。</span><span class="sxs-lookup"><span data-stu-id="6e186-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="6e186-116">當**Uninstall-CsDataBase**指令指令提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N 然後輸入如果您想要停止 Cmdlet （如果有錯誤）。</span><span class="sxs-lookup"><span data-stu-id="6e186-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

