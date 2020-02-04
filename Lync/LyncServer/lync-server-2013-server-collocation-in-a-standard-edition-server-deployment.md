---
title: Standard Edition Server 部署中的 Lync Server 2013 伺服器組合
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
ms.openlocfilehash: 6fa25655fd9bdd2551e10d1fbbf0de617b89be64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="1c113-102">Standard Edition Server 部署中 Lync Server 2013 的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="1c113-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c113-103">_**主題上次修改日期：** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="1c113-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="1c113-104">本節說明您可以在 Lync Server 2013 標準版 server 部署中 collocate 的伺服器角色、資料庫及檔案共用。</span><span class="sxs-lookup"><span data-stu-id="1c113-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="1c113-105">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="1c113-105">Server Roles</span></span>

<span data-ttu-id="1c113-106">在 Lync Server 2013 中，A/V 會議服務、轉送服務、監控及封存都是在標準版 Server 上 collocated，但需要進行額外的設定才能啟用它們。</span><span class="sxs-lookup"><span data-stu-id="1c113-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="1c113-107">您可以選擇在不同的伺服器上部署轉送服務。</span><span class="sxs-lookup"><span data-stu-id="1c113-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="1c113-108">您可以使用標準版伺服器 collocate 受信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="1c113-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="1c113-109">下列伺服器角色必須分別部署在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="1c113-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="1c113-110">Director</span><span class="sxs-lookup"><span data-stu-id="1c113-110">Director</span></span>

  - <span data-ttu-id="1c113-111">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="1c113-111">Edge Server</span></span>

  - <span data-ttu-id="1c113-112">中繼伺服器（如果未 collocated 與標準版伺服器）</span><span class="sxs-lookup"><span data-stu-id="1c113-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="1c113-113">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="1c113-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="1c113-114">資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-114">Databases</span></span>

<span data-ttu-id="1c113-115">根據預設，SQL Server Express 後端資料庫是 collocated 在標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1c113-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="1c113-116">您無法將它移到另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="1c113-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="1c113-117">有一個例外狀況，您無法 collocate 標準版伺服器上的其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="1c113-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="1c113-118">如果您選擇要在標準版 server 上部署持久聊天伺服器，您可以在相同的標準版伺服器上 collocate 持續聊天資料庫和持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="1c113-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="1c113-119">您可以在單一資料庫伺服器上 collocate 下列每個資料庫：</span><span class="sxs-lookup"><span data-stu-id="1c113-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="1c113-120">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-120">Monitoring database</span></span>

  - <span data-ttu-id="1c113-121">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-121">Archiving database</span></span>

  - <span data-ttu-id="1c113-122">企業版前端池的後端資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="1c113-123">您可以在單一 SQL 實例中 collocate 任何或任何或所有這些資料庫，或針對每個實例使用個別的 SQL 實例，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="1c113-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="1c113-124">每個 SQL 實例都只能包含一個後端資料庫（適用于企業版前端池）、單一監視資料庫、單一封存資料庫、單一持續式聊天資料庫，以及單一持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="1c113-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="1c113-125">資料庫伺服器不支援一個以上的企業版前端池、一個伺服器執行封存、一個伺服器執行監視、單一持續聊天資料庫，以及單一持續聊天合規性資料庫，但它可以支援其中一個專案，不論資料庫是使用相同的 SQL Server 實例，還是要使用不同的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="1c113-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="1c113-126">您可以 collocate 與資料庫共用檔案，如本節稍後所述。</span><span class="sxs-lookup"><span data-stu-id="1c113-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c113-127">在 Lync Server 2013 中，您可以選擇將監控與封存儲存空間與 Exchange 2013 儲存空間結合在您的部署中的部分或所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1c113-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="1c113-128">您無法在與 Exchange 儲存空間相同的伺服器上，部署任何執行 Lync Server 或元件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1c113-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c113-129">雖然支援 collocation 資料庫，但資料庫大小可以快速增加。</span><span class="sxs-lookup"><span data-stu-id="1c113-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="1c113-130">例如，當您考慮將封存資料庫與其他資料庫 collocating 時，請注意，如果您要封存的郵件超過幾個使用者，存檔資料庫所需的磁碟空間就會變得很大。</span><span class="sxs-lookup"><span data-stu-id="1c113-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="1c113-131">基於這個原因，我們不建議您 collocating 多個資料庫，特別是封存資料庫、持續聊天資料庫，以及與企業版池後端資料庫的持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="1c113-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="1c113-132">檔案共用</span><span class="sxs-lookup"><span data-stu-id="1c113-132">File Shares</span></span>

<span data-ttu-id="1c113-133">檔案共用可以是個別的伺服器，也可以與下列任一或所有專案在同一台伺服器上 collocated：</span><span class="sxs-lookup"><span data-stu-id="1c113-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="1c113-134">資料庫伺服器，包括企業版頂層端池的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="1c113-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="1c113-135">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-135">Archiving database</span></span>

  - <span data-ttu-id="1c113-136">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-136">Monitoring database</span></span>

  - <span data-ttu-id="1c113-137">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-137">Persistent Chat database</span></span>

  - <span data-ttu-id="1c113-138">持續聊天合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="1c113-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="1c113-139">單一檔案共用可用於多個前端池，標準版伺服器（全部位於同一個網站中）。</span><span class="sxs-lookup"><span data-stu-id="1c113-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c113-140">在 Lync Server 2013 中，監視及封存使用 Lync Server 檔案共用作為標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="1c113-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="1c113-141">其他元件</span><span class="sxs-lookup"><span data-stu-id="1c113-141">Other Components</span></span>

<span data-ttu-id="1c113-142">如果您想要支援使用任何 Lync Server 2013 伺服器角色的同盟使用者共用網頁內容，則您無法 collocate 並非 Lync Server 2013 元件的反向 proxy 伺服器，但在部署中則是必要的。</span><span class="sxs-lookup"><span data-stu-id="1c113-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="1c113-143">不過，您可以針對 Lync Server 2013 部署執行反向 proxy 支援，方法是在組織中針對其他應用程式所使用的現有反向 proxy 伺服器上設定支援。</span><span class="sxs-lookup"><span data-stu-id="1c113-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="1c113-144">您無法使用任何 Lync Server 2013 角色 collocate 任何 Exchange UM 元件或 SharePoint 元件。</span><span class="sxs-lookup"><span data-stu-id="1c113-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

