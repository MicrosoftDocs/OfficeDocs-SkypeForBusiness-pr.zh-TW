---
title: 移除後端伺服器上的 SQL Server 實例和資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移除依賴這些伺服器的伺服器, 或在您重新設定伺服器以使用其他資料庫之後, 移除 Microsoft SQL Server 資料庫和實例。 當您淘汰目前的 SQL Server, 或以其呈現資料庫過時或無法使用的方式來重新設定目前伺服器時, 您必須執行本主題中的程式。
ms.openlocfilehash: 2d0902293c675143609dd720cd33734edd538d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193280"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="0c0bb-104">移除後端伺服器上的 SQL Server 實例和資料庫</span><span class="sxs-lookup"><span data-stu-id="0c0bb-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="0c0bb-105">移除依賴這些伺服器的伺服器, 或在您重新設定伺服器以使用其他資料庫之後, 移除 Microsoft SQL Server 資料庫和實例。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="0c0bb-106">當您淘汰目前的 SQL Server, 或以其呈現資料庫過時或無法使用的方式來重新設定目前伺服器時, 您必須執行本主題中的程式。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="0c0bb-107">若要移除存檔伺服器或監視伺服器的資料庫或實例, 您必須先移除伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="0c0bb-108">同樣地, 若要移除前臺端池的實例或資料庫, 您必須先移除或重新設定相依伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="0c0bb-109">這些程式不會區分 collocated 資料庫或伺服器的個別實例。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="0c0bb-110">程式不會受到資料庫 collocation 的影響。</span><span class="sxs-lookup"><span data-stu-id="0c0bb-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0c0bb-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="0c0bb-111">In this section</span></span>

- [<span data-ttu-id="0c0bb-112">移除前端池的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="0c0bb-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="0c0bb-113">移除監視伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="0c0bb-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="0c0bb-114">移除存檔伺服器的 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="0c0bb-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

