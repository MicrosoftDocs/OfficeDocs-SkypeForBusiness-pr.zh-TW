---
title: 移除後端伺服器上的 SQL Server 執行個體與資料庫
description: 移除後端伺服器上的 SQL Server 實例和資料庫。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551279"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="79c51-103">移除後端伺服器上的 SQL Server 執行個體與資料庫</span><span class="sxs-lookup"><span data-stu-id="79c51-103">Remove SQL Server instances and databases on the Back End Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c51-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="79c51-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="79c51-105">移除 Microsoft SQL Server 資料庫和實例之後，請移除執行 Lync Server 2010 的伺服器，或重新設定執行 Lync Server 2010 的伺服器以使用另一個資料庫之後。</span><span class="sxs-lookup"><span data-stu-id="79c51-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="79c51-106">當您淘汰目前的 SQL Server 或重新設定執行 Lync Server 2010 的目前伺服器時，您必須執行本主題中的程式，這樣一來，它會使資料庫過時或無法使用。</span><span class="sxs-lookup"><span data-stu-id="79c51-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="79c51-107">若要移除封存伺服器或監控伺服器的資料庫或實例，必須先移除伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="79c51-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="79c51-108">同樣地，若要移除前端集區的實例或資料庫，您必須先移除或重新設定從屬伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="79c51-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="79c51-109">不論是針對伺服器的組合資料庫或個別執行個體，這些程序都是一樣的。</span><span class="sxs-lookup"><span data-stu-id="79c51-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="79c51-110">組合資料庫並不會影響這些程序。</span><span class="sxs-lookup"><span data-stu-id="79c51-110">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79c51-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="79c51-111">In This Section</span></span>

  - [<span data-ttu-id="79c51-112">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="79c51-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="79c51-113">移除監控伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="79c51-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="79c51-114">移除封存伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="79c51-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

