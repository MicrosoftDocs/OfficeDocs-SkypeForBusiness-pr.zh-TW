---
title: 移除監控伺服器的 SQL Server 資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f877f7d8d1ade4d260ed137f52046c21f29cf11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="d973b-102">移除監控伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="d973b-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d973b-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d973b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d973b-104">移除 Microsoft Lync Server 2010 監視伺服器之後，您可以移除託管伺服器資料的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d973b-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="d973b-105">使用下列程式從拓撲建立器移除定義，然後從資料庫伺服器移除資料庫及記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d973b-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d973b-106">使用拓撲產生器移除 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="d973b-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="d973b-107">在 Lync Server 2013 前端伺服器上，開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="d973b-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="d973b-108">在拓撲建立器中，流覽至 [**共用元件**]，然後按一下 [ **sql server 商店**]，以滑鼠右鍵按一下與已移除或重新配置之監視伺服器相關聯的 SQL Server 實例，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d973b-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="d973b-109">發佈拓撲，然後檢查 [複製狀態]。</span><span class="sxs-lookup"><span data-stu-id="d973b-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="d973b-110">從 SQL Server 移除資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="d973b-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="d973b-111">若要在 SQL Server 的伺服器上移除資料庫，您必須是您要移除資料庫檔案之 SQL Server 系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d973b-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="d973b-112">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d973b-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="d973b-113">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="d973b-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="d973b-114">其中\<FQDN\>是資料庫伺服器的完整功能變數名稱（fqdn），而\<實例\>是選用的命名資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="d973b-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="d973b-115">當**CsDataBase** Cmdlet 提示您確認動作時，請閱讀資訊，然後按**Y** （或按 enter）繼續，或按 N，然後按**N** ，然後輸入您是否要停止 Cmdlet （也就是在發生錯誤時）。</span><span class="sxs-lookup"><span data-stu-id="d973b-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

