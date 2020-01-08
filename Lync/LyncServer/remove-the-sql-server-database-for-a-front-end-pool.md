---
title: 移除前端集區的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="ad72d-102">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="ad72d-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad72d-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ad72d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ad72d-104">在您移除 Microsoft Lync Server 2010 前端池或將該池重新設定為使用其他資料庫之後，您可以移除託管該池資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="ad72d-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="ad72d-105">使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ad72d-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="ad72d-106">使用拓撲產生器移除 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="ad72d-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="ad72d-107">從 Lync Server 2013 前端伺服器，開啟拓撲產生器並下載現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ad72d-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="ad72d-108">在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置的 [前端] 池相關聯的 SQL Server 實例，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ad72d-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="ad72d-109">發佈拓撲，然後檢查複製狀態。</span><span class="sxs-lookup"><span data-stu-id="ad72d-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="ad72d-110">從 SQL Server 移除使用者和應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="ad72d-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="ad72d-111">若要移除 SQL Server 上的資料庫，您必須是您要移除資料庫檔案之 SQL Server 的 SQL Server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ad72d-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="ad72d-112">開啟 Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="ad72d-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="ad72d-113">若要移除 [pool 使用者] 商店的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="ad72d-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="ad72d-114">其中\<FQDN\>是資料庫伺服器的完整功能變數名稱（fqdn），而\<實例\>是命名的資料庫實例（也就是已定義）。</span><span class="sxs-lookup"><span data-stu-id="ad72d-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="ad72d-115">若要移除 [pool] 應用程式存放區的資料庫，請輸入：</span><span class="sxs-lookup"><span data-stu-id="ad72d-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="ad72d-116">其中\<fqdn\>是資料庫伺服器的 fqdn，而\<實例\>是命名的資料庫實例（也就是已定義）。</span><span class="sxs-lookup"><span data-stu-id="ad72d-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="ad72d-117">當**CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按**Y** （或按 enter）繼續，或按 N，然後按**N** ，然後輸入您是否要停止 Cmdlet （也就是在發生錯誤時）。</span><span class="sxs-lookup"><span data-stu-id="ad72d-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

