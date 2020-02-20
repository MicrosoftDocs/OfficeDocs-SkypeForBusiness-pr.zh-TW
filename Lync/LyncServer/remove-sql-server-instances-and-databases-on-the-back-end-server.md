---
title: 移除 SQL Server 執行個體和後端伺服器上的資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02aa65c631e62d7ffb699d85d982858164848c2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="53087-102">移除 SQL Server 執行個體和後端伺服器上的資料庫</span><span class="sxs-lookup"><span data-stu-id="53087-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53087-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="53087-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="53087-104">或重新設定執行 Lync Server 2010 使用另一個資料庫的伺服器移除而定，伺服器執行 Lync Server 2010 之後移除 Microsoft SQL Server 資料庫和執行個體。</span><span class="sxs-lookup"><span data-stu-id="53087-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="53087-105">您要執行本主題中的程序，當您淘汰目前的 SQL Server 或重新設定目前的伺服器執行 Lync Server 2010 的方式，它會呈現資料庫已過時或無法使用。</span><span class="sxs-lookup"><span data-stu-id="53087-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="53087-106">若要移除封存伺服器或監控伺服器的執行個體的資料庫，您必須先移除伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="53087-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="53087-107">同樣地，若要移除的執行個體或前端集區的資料庫，您必須先移除或重新設定的相依伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="53087-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="53087-108">不論是針對伺服器的組合資料庫或個別執行個體，這些程序都是一樣的。</span><span class="sxs-lookup"><span data-stu-id="53087-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="53087-109">組合資料庫並不會影響這些程序。</span><span class="sxs-lookup"><span data-stu-id="53087-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="53087-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="53087-110">In This Section</span></span>

  - [<span data-ttu-id="53087-111">移除前端集區的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="53087-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="53087-112">移除監控伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="53087-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="53087-113">移除封存伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="53087-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

