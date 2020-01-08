---
title: 移除後端伺服器上的 SQL Server 執行個體與資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="afe54-102">移除後端伺服器上的 SQL Server 執行個體與資料庫</span><span class="sxs-lookup"><span data-stu-id="afe54-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afe54-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="afe54-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="afe54-104">移除伺服器上執行 Lync Server 2010 的伺服器之後，或當您將執行 Lync Server 2010 的伺服器重新設定為使用另一個資料庫之後，就會移除 Microsoft SQL Server 資料庫和實例。</span><span class="sxs-lookup"><span data-stu-id="afe54-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="afe54-105">當您淘汰目前的 SQL Server，或重新設定執行 Lync Server 2010 的目前伺服器時，您必須執行本主題中的程式，讓它呈現的資料庫過時或無法使用。</span><span class="sxs-lookup"><span data-stu-id="afe54-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="afe54-106">若要移除存檔伺服器或監視伺服器的資料庫或實例，您必須先移除伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="afe54-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="afe54-107">同樣地，若要移除前臺端池的實例或資料庫，您必須先移除或重新設定相依伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="afe54-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="afe54-108">這些程式不會區分 collocated 資料庫或伺服器的個別實例。</span><span class="sxs-lookup"><span data-stu-id="afe54-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="afe54-109">程式不會受到資料庫 collocation 的影響。</span><span class="sxs-lookup"><span data-stu-id="afe54-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afe54-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="afe54-110">In This Section</span></span>

  - [<span data-ttu-id="afe54-111">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="afe54-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="afe54-112">移除監控伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="afe54-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="afe54-113">移除封存伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="afe54-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

