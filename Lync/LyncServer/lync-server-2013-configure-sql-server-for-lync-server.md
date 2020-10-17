---
title: Lync Server 2013：設定 Lync Server 的 SQL Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c35f1d82913c71523412c791d9b6a945f443e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535130"
---
# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="22fc7-102">針對 Lync Server 2013 設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="22fc7-102">Configure SQL Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22fc7-103">_**主題上次修改日期：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="22fc7-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="22fc7-104">本節中的主題將討論如何部署及設定要在 Lync Server 的企業部署中使用的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="22fc7-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="22fc7-105">Standard Edition server 使用適合 Standard Edition Server 工作負載大小的 sql server Express 版本的 SQL Server Express 版本。</span><span class="sxs-lookup"><span data-stu-id="22fc7-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="22fc7-106">Lync Server 2013 中央管理存放區保留集區中所有 Enterprise Edition 伺服器的使用者資料，且設計為位於以 SQL Server 為基礎的後端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="22fc7-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="22fc7-107">集中式存放庫會將中央管理存放區與任何其他 Lync Server 2013 角色安裝在相同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="22fc7-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="22fc7-108">中央管理存放區不可位於集區中的 Enterprise Edition 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="22fc7-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="22fc7-109">當您第一次發行拓撲並選取建立資料庫時，會自動建立中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="22fc7-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="22fc7-110">指定為後端伺服器的電腦必須已執行 SQL Server 資料庫軟體，安裝才能成功。</span><span class="sxs-lookup"><span data-stu-id="22fc7-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="22fc7-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="22fc7-111">In This Section</span></span>

  - [<span data-ttu-id="22fc7-112">Lync Server 2013 的 SQL Server 資料和記錄檔位置</span><span class="sxs-lookup"><span data-stu-id="22fc7-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="22fc7-113">在 Lync Server 2013 中設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="22fc7-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="22fc7-114">Lync Server 2013 中 SQL Server 的部署許可權</span><span class="sxs-lookup"><span data-stu-id="22fc7-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="22fc7-115">在 Lync Server 2013 中使用 Lync Server 管理命令介面安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="22fc7-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="22fc7-116">瞭解具有 Lync Server 2013 之 SQL Server 的防火牆需求</span><span class="sxs-lookup"><span data-stu-id="22fc7-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="22fc7-117">設定 Lync Server 2013 的 SQL Server 叢集</span><span class="sxs-lookup"><span data-stu-id="22fc7-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

