---
title: Lync Server 2013 Standard Edition server 部署中的伺服器共同配置
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
ms.openlocfilehash: 1122605aabea32d86fbacd1f23675fcdef687539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="73250-102">Lync Server 2013 Standard Edition server 部署中的伺服器共同配置</span><span class="sxs-lookup"><span data-stu-id="73250-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73250-103">_**上次修改主題：** 2013年-01-20 個_</span><span class="sxs-lookup"><span data-stu-id="73250-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="73250-104">本節說明伺服器角色、 資料庫及檔案共用，您可以在 Lync Server 2013 Standard Edition server 部署中組合。</span><span class="sxs-lookup"><span data-stu-id="73250-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="73250-105">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="73250-105">Server Roles</span></span>

<span data-ttu-id="73250-106">在 Lync Server 2013 中，A / V 會議服務、 中繼服務、 監控和封存都組合於 Standard Edition Server，但其他設定，才能加以啟用。</span><span class="sxs-lookup"><span data-stu-id="73250-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="73250-107">您可以選擇部署中繼服務在個別伺服器上。</span><span class="sxs-lookup"><span data-stu-id="73250-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="73250-108">您可以組合信任的應用程式伺服器與 Standard Edition 伺服器。</span><span class="sxs-lookup"><span data-stu-id="73250-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="73250-109">下列伺服器角色必須分別部署到個別的電腦上：</span><span class="sxs-lookup"><span data-stu-id="73250-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="73250-110">Director</span><span class="sxs-lookup"><span data-stu-id="73250-110">Director</span></span>

  - <span data-ttu-id="73250-111">Edge Server</span><span class="sxs-lookup"><span data-stu-id="73250-111">Edge Server</span></span>

  - <span data-ttu-id="73250-112">中繼伺服器 （如果沒有與 Standard Edition server 組合）</span><span class="sxs-lookup"><span data-stu-id="73250-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="73250-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="73250-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="73250-114">資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-114">Databases</span></span>

<span data-ttu-id="73250-115">根據預設，SQL Server Express 後端資料庫組合在 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="73250-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="73250-116">您無法將其移至另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="73250-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="73250-117">有一個例外狀況，您不能組合 Standard Edition server 上的其他資料庫。</span><span class="sxs-lookup"><span data-stu-id="73250-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="73250-118">如果您選擇在 Standard Edition 伺服器上部署 Persistent Chat Server，您可以組合常設聊天室資料庫及相同的 Standard Edition server 上的常設聊天室規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="73250-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="73250-119">您可以組合每一個單一資料庫伺服器上的下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="73250-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="73250-120">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-120">Monitoring database</span></span>

  - <span data-ttu-id="73250-121">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-121">Archiving database</span></span>

  - <span data-ttu-id="73250-122">Enterprise Edition 前端集區後端資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="73250-123">您可以組合任何或所有這些資料庫中的單一 SQL 執行個體，或使用個別的 SQL 執行個體各有下列限制：</span><span class="sxs-lookup"><span data-stu-id="73250-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="73250-124">只有 （適用於 Enterprise Edition 前端集區中） 的單一後端資料庫、 一個監控資料庫、 一個封存資料庫、 單一常設聊天室資料庫和單一常設聊天室規範資料庫，可以包含每個 SQL 執行個體。</span><span class="sxs-lookup"><span data-stu-id="73250-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="73250-125">資料庫伺服器不支援一個以上的 Enterprise Edition 前端集區、 一部伺服器執行封存，一部伺服器執行監控、 單一常設聊天室資料庫和單一常設聊天室規範資料庫，但是可支援的每個，其中一個不論資料庫是否使用相同的 SQL Server 執行個體或個別的 SQL Server 執行個體。</span><span class="sxs-lookup"><span data-stu-id="73250-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="73250-126">您可以如本節後面所述，將檔案共用與資料庫組合在一起。</span><span class="sxs-lookup"><span data-stu-id="73250-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73250-127">在 Lync Server 2013 中，您可以選擇整合監控和封存儲存與您在部署中的部分或所有使用者的 Exchange 2013 儲存體。</span><span class="sxs-lookup"><span data-stu-id="73250-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="73250-128">您無法在部署任何為 Exchange 存放在相同伺服器上執行 Lync Server 或元件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="73250-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73250-129">雖然支援資料庫的組合，但是資料庫大小可能會快速增加。</span><span class="sxs-lookup"><span data-stu-id="73250-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="73250-130">例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。</span><span class="sxs-lookup"><span data-stu-id="73250-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="73250-131">基於這個理由，我們不建議組合多個資料庫，尤其是封存資料庫、 常設聊天室資料庫及與 Enterprise 集區的後端資料庫常設聊天室規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="73250-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="73250-132">檔案共用</span><span class="sxs-lookup"><span data-stu-id="73250-132">File Shares</span></span>

<span data-ttu-id="73250-133">檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：</span><span class="sxs-lookup"><span data-stu-id="73250-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="73250-134">資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="73250-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="73250-135">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-135">Archiving database</span></span>

  - <span data-ttu-id="73250-136">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-136">Monitoring database</span></span>

  - <span data-ttu-id="73250-137">常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-137">Persistent Chat database</span></span>

  - <span data-ttu-id="73250-138">常設聊天室規範資料庫</span><span class="sxs-lookup"><span data-stu-id="73250-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="73250-139">單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。</span><span class="sxs-lookup"><span data-stu-id="73250-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73250-140">在 Lync Server 2013 中，監控和封存會使用 Lync Server 檔案共用作為 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="73250-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="73250-141">其他元件</span><span class="sxs-lookup"><span data-stu-id="73250-141">Other Components</span></span>

<span data-ttu-id="73250-142">您無法將組合在一起的反向 proxy 伺服器，這不是 Lync Server 2013 的元件，但如果您想要支援共用與任何 Lync Server 2013 伺服器角色的同盟使用者的 web 內容所需部署中。</span><span class="sxs-lookup"><span data-stu-id="73250-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="73250-143">您，不過，可實作 Lync Server 2013 部署的反向 proxy 支援適用於其他應用程式的組織中現有的反向 proxy 伺服器上設定的支援。</span><span class="sxs-lookup"><span data-stu-id="73250-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="73250-144">您無法將任何 Exchange UM 元件或 SharePoint 元件與任何 Lync Server 2013 角色的組合。</span><span class="sxs-lookup"><span data-stu-id="73250-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

