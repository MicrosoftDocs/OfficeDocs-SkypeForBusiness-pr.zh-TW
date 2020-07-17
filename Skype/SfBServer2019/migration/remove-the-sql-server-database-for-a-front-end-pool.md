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
localization_priority: Normal
description: 移除前端集區或將集區重新設定為使用不同的資料庫之後，您可以移除主控集區資料的 SQL Server 資料庫。 請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753405"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="b11b6-104">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="b11b6-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="b11b6-105">移除前端集區或將集區重新設定為使用不同的資料庫之後，您可以移除主控集區資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b11b6-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="b11b6-106">請使用下列程式，從拓撲產生器移除定義，然後從資料庫伺服器中移除資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b11b6-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="b11b6-107">使用拓撲產生器移除 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="b11b6-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="b11b6-108">從商務用 Skype Server 2019 前端伺服器，開啟拓撲產生器，並下載現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b11b6-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="b11b6-109">在 [拓撲產生器] 中，流覽至 [**共用元件**]，然後按一下 [ **Sql server 存放區**]，以滑鼠右鍵按一下與已移除或重新設定的前端集區相關聯的 SQL Server 實例，然後按一下 [**刪除**</span><span class="sxs-lookup"><span data-stu-id="b11b6-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="b11b6-110">發行拓撲，然後檢查複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="b11b6-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="b11b6-111">從 SQL server 移除使用者和應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="b11b6-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="b11b6-112">若要移除 SQL server 上的資料庫，您必須是要移除資料庫檔案之 SQL server 的 SQL Server 系統管理員群組成員。</span><span class="sxs-lookup"><span data-stu-id="b11b6-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="b11b6-113">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="b11b6-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="b11b6-114">移除集區使用者存放區的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="b11b6-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="b11b6-115">其中 _\<FQDN\>_ 是資料庫伺服器的完整功能變數名稱（FQDN），也就 _\<instance\>_ 是指定的資料庫實例（也就是定義的資料庫實例）。</span><span class="sxs-lookup"><span data-stu-id="b11b6-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="b11b6-116">移除集區應用程式存放區的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="b11b6-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="b11b6-117">其中 _\<FQDN\>_ 是資料庫伺服器的 FQDN，也就 _\<instance\>_ 是指定的資料庫實例（也就是定義的實例）。</span><span class="sxs-lookup"><span data-stu-id="b11b6-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="b11b6-118">當**Uninstall-CsDataBase**指令指令提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N 然後輸入如果您想要停止 Cmdlet （如果有錯誤）。</span><span class="sxs-lookup"><span data-stu-id="b11b6-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

