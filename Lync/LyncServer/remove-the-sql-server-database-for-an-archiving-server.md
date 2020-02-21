---
title: 移除封存伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d077b21b1b45cc73c268b3dc6294f0a476f48809
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="64a26-102">移除封存伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="64a26-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64a26-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="64a26-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="64a26-104">移除 Microsoft Lync Server 2010 封存伺服器之後，您可以移除裝載的集區資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="64a26-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="64a26-105">使用下列程序從拓撲產生器中，移除定義]，然後從資料庫伺服器中移除的資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="64a26-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="64a26-106">若要移除使用拓撲產生器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="64a26-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="64a26-107">在 Lync Server 2013 前端伺服器上，開啟拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="64a26-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="64a26-108">在拓撲產生器中，瀏覽至**共用元件**] 後再按一下 [ **SQL Server 存放區**SQL Server 執行個體相關聯與已移除或重新設定封存伺服器，以滑鼠右鍵按一下，然後按一下 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="64a26-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="64a26-109">發行拓撲，然後檢查複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="64a26-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="64a26-110">從 SQL Server 移除資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="64a26-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="64a26-111">若要移除 SQL Server 上的資料庫，您必須是要移除資料庫檔案之 SQL Server 的 SQL Server sysadmins 群組成員。</span><span class="sxs-lookup"><span data-stu-id="64a26-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="64a26-112">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="64a26-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="64a26-113">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="64a26-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="64a26-114">其中\<FQDN\>是完整的網域名稱 (FQDN) 的資料庫伺服器，以及\<執行個體\>（亦即，如果已定義） 是已命名的資料庫執行個體。</span><span class="sxs-lookup"><span data-stu-id="64a26-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="64a26-115">當 **Uninstall-CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按 **Y** (或按 Enter) 繼續作業，或是依序按 **N** 及 Enter 停止 Cmdlet (例如發生錯誤時)。</span><span class="sxs-lookup"><span data-stu-id="64a26-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

