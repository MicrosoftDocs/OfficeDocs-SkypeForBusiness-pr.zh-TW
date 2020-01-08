---
title: Enterprise Edition 前端集區部署中的 Lync Server 2013 伺服器組合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="2b150-102">Enterprise Edition 前端集區部署中 Lync Server 2013 的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="2b150-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b150-103">_**主題上次修改日期：** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="2b150-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="2b150-104">本節說明您可以在 Lync Server 2013 前端池部署中 collocate 的伺服器角色、資料庫及檔案共用。</span><span class="sxs-lookup"><span data-stu-id="2b150-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="2b150-105">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="2b150-105">Server Roles</span></span>

<span data-ttu-id="2b150-106">在 Lync Server 2013 中，A/V 會議服務、轉送服務、監控及封存都是在前端伺服器上 collocated，但需要進行額外的設定才能啟用它們。</span><span class="sxs-lookup"><span data-stu-id="2b150-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="2b150-107">如果您不想要 collocate 前端伺服器的中繼伺服器，您可以將它作為獨立的中繼伺服器部署在另一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="2b150-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="2b150-108">您可以使用前端伺服器 collocate 受信任的應用程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b150-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="2b150-109">下列伺服器角色必須分別部署在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="2b150-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="2b150-110">Director</span><span class="sxs-lookup"><span data-stu-id="2b150-110">Director</span></span>

  - <span data-ttu-id="2b150-111">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="2b150-111">Edge Server</span></span>

  - <span data-ttu-id="2b150-112">中繼伺服器（如果沒有與前端伺服器 collocated）</span><span class="sxs-lookup"><span data-stu-id="2b150-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="2b150-113">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="2b150-113">Office Web Apps Server</span></span>

<span data-ttu-id="2b150-114">您無法 collocate 持久聊天伺服器角色與前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b150-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="2b150-115">資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-115">Databases</span></span>

<span data-ttu-id="2b150-116">您可以在同一個資料庫伺服器上 collocate 下列每一個資料庫：</span><span class="sxs-lookup"><span data-stu-id="2b150-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="2b150-117">後端資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-117">Back-end database</span></span>

  - <span data-ttu-id="2b150-118">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-118">Monitoring database</span></span>

  - <span data-ttu-id="2b150-119">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-119">Archiving database</span></span>

  - <span data-ttu-id="2b150-120">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-120">Persistent Chat database</span></span>

  - <span data-ttu-id="2b150-121">持續聊天合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="2b150-122">您可以在單一 SQL Server 實例中 collocate 任何或任何或所有這些資料庫，或針對每個實例使用個別的 SQL Server 實例，但有下列限制：</span><span class="sxs-lookup"><span data-stu-id="2b150-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="2b150-123">每個 SQL Server 實例都只能包含一個後端資料庫、單一監視資料庫、單一封存資料庫、單一持續式聊天資料庫，以及單一持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="2b150-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="2b150-124">資料庫伺服器不支援一個以上的前端池、一個封存部署，以及一個監視部署，但不論資料庫是使用相同的 SQL Server 實例，還是不同的 SQL Server 實例，都可以支援其中一個。</span><span class="sxs-lookup"><span data-stu-id="2b150-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="2b150-125">您可以 collocate 與資料庫共用檔案，如本節稍後所述。</span><span class="sxs-lookup"><span data-stu-id="2b150-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b150-126">在 Lync Server 2013 中，您可以選擇將存檔儲存與 Exchange 2013 儲存空間整合在您的部署中的部分或所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2b150-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="2b150-127">您無法在與 Exchange 儲存空間相同的伺服器上，部署任何執行 Lync Server 或元件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b150-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b150-128">雖然支援 collocation 資料庫，但資料庫大小可以快速增加。</span><span class="sxs-lookup"><span data-stu-id="2b150-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="2b150-129">例如，當您考慮將封存資料庫與其他資料庫 collocating 時，請注意，如果您要封存的郵件超過幾個使用者，存檔資料庫所需的磁碟空間就會變得很大。</span><span class="sxs-lookup"><span data-stu-id="2b150-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="2b150-130">基於這個原因，我們不建議您 collocating 多個資料庫，特別是封存資料庫、持久聊天資料庫，或與後端資料庫的持續聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="2b150-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="2b150-131">檔案共用</span><span class="sxs-lookup"><span data-stu-id="2b150-131">File Share</span></span>

<span data-ttu-id="2b150-132">檔案共用可以是個別的伺服器，也可以與下列任一或所有專案在同一台伺服器上 collocated：</span><span class="sxs-lookup"><span data-stu-id="2b150-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="2b150-133">資料庫伺服器，包括企業版頂層端池的後端伺服器</span><span class="sxs-lookup"><span data-stu-id="2b150-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="2b150-134">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-134">Archiving database</span></span>

  - <span data-ttu-id="2b150-135">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-135">Monitoring database</span></span>

  - <span data-ttu-id="2b150-136">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-136">Persistent Chat database</span></span>

  - <span data-ttu-id="2b150-137">持續聊天合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="2b150-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="2b150-138">單一檔案共用可用於多個前端池，標準版伺服器（全部位於同一個網站中）。</span><span class="sxs-lookup"><span data-stu-id="2b150-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b150-139">在 Lync Server 2013 中，監視及封存使用 Lync Server 檔案共用作為前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b150-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="2b150-140">其他元件</span><span class="sxs-lookup"><span data-stu-id="2b150-140">Other Components</span></span>

<span data-ttu-id="2b150-141">如果您想要支援使用任何 Lync Server 2013 伺服器角色的同盟使用者共用網頁內容，則您無法 collocate 並非 Lync Server 2013 元件的反向 proxy 伺服器，但在部署中則是必要的。</span><span class="sxs-lookup"><span data-stu-id="2b150-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="2b150-142">不過，您可以針對 Lync Server 2013 部署執行反向 proxy 支援，方法是在組織中針對其他應用程式所使用的現有反向 proxy 伺服器上設定支援。</span><span class="sxs-lookup"><span data-stu-id="2b150-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="2b150-143">您無法使用任何 SharePoint Server 角色 collocate 任何 Exchange 整合訊息（UM）元件或 SharePoint 元件。</span><span class="sxs-lookup"><span data-stu-id="2b150-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

