---
title: Lync Server 2013 Enterprise Edition 前端集區部署中的伺服器共同配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ccfb87966008d471d879e2c25a73e098fb28f19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="eea56-102">在 Enterprise Edition 前端集區部署 Lync Server 2013 中的伺服器共同配置</span><span class="sxs-lookup"><span data-stu-id="eea56-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eea56-103">_**上次修改主題：** 2013年-11-11_</span><span class="sxs-lookup"><span data-stu-id="eea56-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="eea56-104">本節說明伺服器角色、 資料庫及檔案共用，您可以在 Lync Server 2013 前端集區部署中組合。</span><span class="sxs-lookup"><span data-stu-id="eea56-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="eea56-105">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="eea56-105">Server Roles</span></span>

<span data-ttu-id="eea56-106">在 Lync Server 2013 中，A / V 會議服務、 中繼服務、 監控和封存都組合於前端伺服器，但其他設定，才能加以啟用。</span><span class="sxs-lookup"><span data-stu-id="eea56-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="eea56-107">如果您不想將中繼伺服器與前端伺服器組合在一起，您可以在另一部電腦上將其部署為獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="eea56-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="eea56-108">您可以將信任的應用程式伺服器與前端伺服器組合在一起。</span><span class="sxs-lookup"><span data-stu-id="eea56-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="eea56-109">下列伺服器角色必須分別部署到個別的電腦上：</span><span class="sxs-lookup"><span data-stu-id="eea56-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="eea56-110">Director</span><span class="sxs-lookup"><span data-stu-id="eea56-110">Director</span></span>

  - <span data-ttu-id="eea56-111">Edge Server</span><span class="sxs-lookup"><span data-stu-id="eea56-111">Edge Server</span></span>

  - <span data-ttu-id="eea56-112">中繼伺服器 (如果未與前端伺服器組合在一起)</span><span class="sxs-lookup"><span data-stu-id="eea56-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="eea56-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="eea56-113">Office Web Apps Server</span></span>

<span data-ttu-id="eea56-114">您無法組合常設聊天室伺服器角色與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="eea56-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="eea56-115">資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-115">Databases</span></span>

<span data-ttu-id="eea56-116">您可以在相同的資料庫伺服器中組合下列每一個資料庫：</span><span class="sxs-lookup"><span data-stu-id="eea56-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="eea56-117">後端資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-117">Back-end database</span></span>

  - <span data-ttu-id="eea56-118">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-118">Monitoring database</span></span>

  - <span data-ttu-id="eea56-119">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-119">Archiving database</span></span>

  - <span data-ttu-id="eea56-120">常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-120">Persistent Chat database</span></span>

  - <span data-ttu-id="eea56-121">常設聊天室規範資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="eea56-122">您可以組合任何或所有這些資料庫的 SQL Server 的單一執行個體，或使用 SQL Server 個別執行個體各有下列限制：</span><span class="sxs-lookup"><span data-stu-id="eea56-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="eea56-123">每個 SQL Server 執行個體可以包含單一後端資料庫、 一個監控資料庫、 一個封存資料庫、 單一常設聊天室資料庫及單一常設聊天室規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="eea56-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="eea56-124">資料庫伺服器不支援一個以上的前端集區、 一個封存部署以及監控部署，但是可支援一個的每一個，不論資料庫是否使用相同的 SQL Server 執行個體或個別的 SQL Server 執行個體。</span><span class="sxs-lookup"><span data-stu-id="eea56-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="eea56-125">您可以如本節後面所述，將檔案共用與資料庫組合在一起。</span><span class="sxs-lookup"><span data-stu-id="eea56-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eea56-126">在 Lync Server 2013 中，您必須與您在部署中的部分或所有使用者的 Exchange 2013 儲存體整合封存存放區的選項。</span><span class="sxs-lookup"><span data-stu-id="eea56-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="eea56-127">您無法在部署任何為 Exchange 存放在相同伺服器上執行 Lync Server 或元件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="eea56-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eea56-128">雖然支援資料庫的組合，但是資料庫大小可能會快速增加。</span><span class="sxs-lookup"><span data-stu-id="eea56-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="eea56-129">例如，當您考慮將封存資料庫與其他資料庫組合在一起時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。</span><span class="sxs-lookup"><span data-stu-id="eea56-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="eea56-130">基於這個理由，我們不建議組合多個資料庫，尤其是封存資料庫、 常設聊天室資料庫或後端資料庫的常設聊天室規範資料庫。</span><span class="sxs-lookup"><span data-stu-id="eea56-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="eea56-131">檔案共用</span><span class="sxs-lookup"><span data-stu-id="eea56-131">File Share</span></span>

<span data-ttu-id="eea56-132">檔案共用可以是個別的伺服器，或是在相同的伺服器上組合為下列任何一種或所有情況：</span><span class="sxs-lookup"><span data-stu-id="eea56-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="eea56-133">資料庫伺服器，包括 Enterprise Edition 前端集區的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="eea56-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="eea56-134">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-134">Archiving database</span></span>

  - <span data-ttu-id="eea56-135">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-135">Monitoring database</span></span>

  - <span data-ttu-id="eea56-136">常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-136">Persistent Chat database</span></span>

  - <span data-ttu-id="eea56-137">常設聊天室規範資料庫</span><span class="sxs-lookup"><span data-stu-id="eea56-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="eea56-138">單一檔案共用可以用於多個前端集區、Standard Edition Server (全部在同一個網站中)。</span><span class="sxs-lookup"><span data-stu-id="eea56-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eea56-139">在 Lync Server 2013 中，監控和封存會使用 Lync Server 檔案共用作為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="eea56-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="eea56-140">其他元件</span><span class="sxs-lookup"><span data-stu-id="eea56-140">Other Components</span></span>

<span data-ttu-id="eea56-141">您無法將組合在一起的反向 proxy 伺服器，這不是 Lync Server 2013 的元件，但如果您想要支援共用與任何 Lync Server 2013 伺服器角色的同盟使用者的 web 內容所需部署中。</span><span class="sxs-lookup"><span data-stu-id="eea56-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="eea56-142">您，不過，可實作 Lync Server 2013 部署的反向 proxy 支援適用於其他應用程式的組織中現有的反向 proxy 伺服器上設定的支援。</span><span class="sxs-lookup"><span data-stu-id="eea56-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="eea56-143">您無法將任何 Exchange 整合通訊 (UM) 元件或 SharePoint 元件與任何 SharePoint Server 角色的組合。</span><span class="sxs-lookup"><span data-stu-id="eea56-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

