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
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="c68b6-104">移除監控伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="c68b6-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="c68b6-105">移除監視伺服器之後，您可以移除託管伺服器資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="c68b6-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="c68b6-106">使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c68b6-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c68b6-107">使用拓撲產生器移除 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="c68b6-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c68b6-108">在商務用 Skype Server 2019 前端伺服器上，開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="c68b6-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c68b6-109">在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置之監視伺服器相關聯的 SQL Server 實例，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c68b6-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c68b6-110">發佈拓撲，然後檢查 [複製狀態]。</span><span class="sxs-lookup"><span data-stu-id="c68b6-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="c68b6-111">從 SQL Server 移除資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="c68b6-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="c68b6-112">若要在 SQL Server 的伺服器上移除資料庫，您必須是您要移除資料庫檔案之 SQL Server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c68b6-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="c68b6-113">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c68b6-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c68b6-114">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="c68b6-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c68b6-115">其中_ \<FQDN\> _是資料庫伺服器的完整功能變數名稱（fqdn），而_ \<實例\> _是選用的命名資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="c68b6-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="c68b6-116">當**卸載 CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 Y （或 Enter）繼續，或按 N，然後按 Enter 鍵以停止 Cmdlet （如果有錯誤）。</span><span class="sxs-lookup"><span data-stu-id="c68b6-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

