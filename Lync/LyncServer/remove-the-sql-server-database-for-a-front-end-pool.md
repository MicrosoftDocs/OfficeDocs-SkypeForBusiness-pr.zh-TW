---
title: 移除前端集區的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a6aba3f084be6c40d5019af5da37f1a682f6eb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="d22fb-102">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="d22fb-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d22fb-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="d22fb-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d22fb-104">在您移除 Microsoft Lync Server 2010 前端集區或重新設定要使用不同的資料庫之集區之後，您可以移除裝載的集區資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d22fb-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="d22fb-105">使用下列程序從拓撲產生器中，移除定義]，然後從資料庫伺服器中移除的資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d22fb-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d22fb-106">若要移除使用拓撲產生器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="d22fb-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="d22fb-107">從 Lync Server 2013 前端伺服器，開啟拓撲產生器，並下載現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="d22fb-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="d22fb-108">在拓撲產生器中，瀏覽至**共用元件**] 後再按一下 [ **SQL Server 存放區**移除或重新設定前端集區，相關聯的 SQL Server 執行個體上按一下滑鼠右鍵，然後按一下 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="d22fb-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="d22fb-109">發行拓撲，然後檢查複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="d22fb-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="d22fb-110">從 SQL Server 移除使用者和應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="d22fb-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="d22fb-111">若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="d22fb-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="d22fb-112">開啟 Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="d22fb-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="d22fb-113">移除集區使用者存放區的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d22fb-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="d22fb-114">其中\<FQDN\>是完整的網域名稱 (FQDN) 的資料庫伺服器，以及\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="d22fb-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="d22fb-115">移除集區應用程式存放區的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d22fb-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="d22fb-116">其中\<FQDN\>是資料庫伺服器的 FQDN 和\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="d22fb-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="d22fb-117">當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。</span><span class="sxs-lookup"><span data-stu-id="d22fb-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

