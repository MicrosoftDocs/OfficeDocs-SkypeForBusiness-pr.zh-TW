---
title: Lync Server 2013 server 組合 in Standard Edition Server 部署
description: Lync Server 2013 server 組合 in Standard Edition server 部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af44761d36c472de1a3da5cd3b3938dc1a130836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555109"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="a6a8c-103">Lync Server 2013 的 Standard Edition server 部署中的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="a6a8c-103">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6a8c-104">_**主題上次修改日期：** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="a6a8c-104">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="a6a8c-105">本節說明您可以在 Lync Server 2013 Standard Edition server 部署中組合的伺服器角色、資料庫及檔案共用。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="a6a8c-106">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="a6a8c-106">Server Roles</span></span>

<span data-ttu-id="a6a8c-107">在 Lync Server 2013 中，A/V 會議服務、中繼服務、監控和封存都是在 Standard Edition Server 上組合，但需要進行其他設定才能加以啟用。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="a6a8c-108">您可以選擇在不同的伺服器上部署中繼服務。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-108">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="a6a8c-109">您可以使用 Standard Edition server 組合信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-109">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="a6a8c-110">下列伺服器角色必須分別部署到個別的電腦上：</span><span class="sxs-lookup"><span data-stu-id="a6a8c-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="a6a8c-111">Director</span><span class="sxs-lookup"><span data-stu-id="a6a8c-111">Director</span></span>

  - <span data-ttu-id="a6a8c-112">Edge Server</span><span class="sxs-lookup"><span data-stu-id="a6a8c-112">Edge Server</span></span>

  - <span data-ttu-id="a6a8c-113">若未使用 Standard Edition server 組合，則為轉送伺服器 () </span><span class="sxs-lookup"><span data-stu-id="a6a8c-113">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="a6a8c-114">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="a6a8c-114">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a6a8c-115">資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-115">Databases</span></span>

<span data-ttu-id="a6a8c-116">根據預設，SQL Server Express 後端資料庫是組合在 Standard Edition Server 上。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-116">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="a6a8c-117">您無法將它移動到不同的電腦。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-117">You cannot move it to a separate computer.</span></span> <span data-ttu-id="a6a8c-118">有一個例外狀況，您無法組合 Standard Edition server 上的其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-118">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="a6a8c-119">如果您選擇在 Standard Edition server 上部署 Persistent Chat Server，您可以在相同的 Standard Edition 伺服器上組合 Persistent chat 資料庫和 Persistent Chat 規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-119">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="a6a8c-120">您可以在單一資料庫伺服器上組合下列每一個資料庫：</span><span class="sxs-lookup"><span data-stu-id="a6a8c-120">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="a6a8c-121">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-121">Monitoring database</span></span>

  - <span data-ttu-id="a6a8c-122">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-122">Archiving database</span></span>

  - <span data-ttu-id="a6a8c-123">Enterprise Edition 前端集區的後端資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-123">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="a6a8c-124">您可以在單一 SQL 實例中組合任何或任何或所有這些資料庫，或針對每個資料庫使用個別的 SQL 實例，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="a6a8c-124">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="a6a8c-125">每個 SQL 實例僅能包含一個適用于 Enterprise Edition 前端集區的後端資料庫 () 、單一監控資料庫、單一封存資料庫、單一持久聊天資料庫及單一持久聊天規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-125">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="a6a8c-126">資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、一部執行封存的伺服器、單一持久聊天資料庫及單一持久聊天規範資料庫，但不論資料庫使用的是相同的 SQL Server 實例還是不同的 SQL Server 實例，它都可以支援其中一個。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-126">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="a6a8c-127">您可以如本節後面所述，將檔案共用與資料庫組合在一起。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-127">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6a8c-128">在 Lync Server 2013 中，您可以選擇將監控和封存儲存整合至部署中的部分或所有使用者的 Exchange 2013 儲存體。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-128">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="a6a8c-129">您無法在 Exchange 儲存體所在的伺服器上部署任何執行 Lync Server 或元件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-129">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a6a8c-130">雖然支援資料庫的組合，但是資料庫大小可能會快速增加。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-130">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="a6a8c-131">例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-131">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="a6a8c-132">基於這個理由，我們不建議使用企業版集區的後端資料庫，組合多個資料庫，尤其是封存資料庫、Persistent Chat 資料庫及 Persistent Chat 合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-132">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="a6a8c-133">檔案共用</span><span class="sxs-lookup"><span data-stu-id="a6a8c-133">File Shares</span></span>

<span data-ttu-id="a6a8c-134">檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：</span><span class="sxs-lookup"><span data-stu-id="a6a8c-134">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="a6a8c-135">資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="a6a8c-135">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="a6a8c-136">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-136">Archiving database</span></span>

  - <span data-ttu-id="a6a8c-137">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-137">Monitoring database</span></span>

  - <span data-ttu-id="a6a8c-138">Persistent Chat 資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-138">Persistent Chat database</span></span>

  - <span data-ttu-id="a6a8c-139">Persistent Chat 規範資料庫</span><span class="sxs-lookup"><span data-stu-id="a6a8c-139">Persistent Chat compliance database</span></span>

<span data-ttu-id="a6a8c-140">單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-140">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6a8c-141">在 Lync Server 2013 中，監控和封存使用 Lync Server 檔案共用做為 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-141">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="a6a8c-142">其他元件</span><span class="sxs-lookup"><span data-stu-id="a6a8c-142">Other Components</span></span>

<span data-ttu-id="a6a8c-143">您無法組合反向 proxy 伺服器（不是 Lync Server 2013 元件），但是如果您想要支援使用任何 Lync Server 2013 伺服器角色的同盟使用者共用網頁內容，則您的部署中也是必要的。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-143">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="a6a8c-144">不過，您可以在組織中對其他應用程式使用的現有反向 proxy 伺服器上設定支援，以執行 Lync Server 2013 部署的反向 proxy 支援。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-144">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="a6a8c-145">您無法組合任何含任何 Lync Server 2013 角色的 Exchange UM 元件或 SharePoint 元件。</span><span class="sxs-lookup"><span data-stu-id="a6a8c-145">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

