---
title: Lync Server 2013：設定封存的存放區
description: Lync Server 2013：設定封存的存放區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554239"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="91f6d-103">在 Lync Server 2013 中設定儲存區封存</span><span class="sxs-lookup"><span data-stu-id="91f6d-103">Setting up storage for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91f6d-104">_**主題上次修改日期：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="91f6d-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="91f6d-105">Lync Server 2013 的封存儲存區包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="91f6d-105">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="91f6d-106">**資料儲存**    需要有資料存放區才能儲存 IM 內容。</span><span class="sxs-lookup"><span data-stu-id="91f6d-106">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="91f6d-107">**檔存放區**    需要有檔案存放區，才能儲存會議 (會議) 內容資料儲存區和檔案儲存區。</span><span class="sxs-lookup"><span data-stu-id="91f6d-107">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="91f6d-108">設定資料儲存區</span><span class="sxs-lookup"><span data-stu-id="91f6d-108">Setting Up Data Storage</span></span>

<span data-ttu-id="91f6d-109">在 Lync Server 2013 中設定封存資料儲存的需求，取決於您想要儲存封存資料的方式：</span><span class="sxs-lookup"><span data-stu-id="91f6d-109">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="91f6d-110">整合 Lync Server 2013 封存與 Exchange 部署，以儲存使用 Exchange 儲存體的封存資料。</span><span class="sxs-lookup"><span data-stu-id="91f6d-110">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="91f6d-111">設定個別的 SQL Server 資料庫伺服器以儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="91f6d-111">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="91f6d-112">設定用於封存資料的 Exchange 存放區</span><span class="sxs-lookup"><span data-stu-id="91f6d-112">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="91f6d-113">若要設定 Exchange 封存資料的儲存，您的 Exchange 部署必須執行 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="91f6d-113">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="91f6d-114">此外，使用者信箱必須位於 Exchange 2013 伺服器上，而且其信箱必須置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="91f6d-114">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="91f6d-115">如需設定 Exchange 2013 的詳細資訊，請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="91f6d-115">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="91f6d-116">設定用於儲存封存資料的 SQL Server 資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="91f6d-116">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="91f6d-117">Lync Server 2013 中的封存需要 SQL Server 資料庫軟體儲存封存的資料，除非您將部署與 Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="91f6d-117">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="91f6d-118">針對 SQL Server 封存資料庫，您必須在將裝載封存資料庫的電腦上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="91f6d-118">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="91f6d-119">您可以使用相同的 SQL 實例，用於前端集區的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="91f6d-119">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="91f6d-120">為了達到最佳效能，您應該在與中央管理存放區分開的電腦上部署封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="91f6d-120">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="91f6d-121">如需組合 Lync Server 2013 元件的詳細資訊，請參閱支援檔中的 [支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。</span><span class="sxs-lookup"><span data-stu-id="91f6d-121">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="91f6d-122">每個資料庫伺服器都必須執行支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="91f6d-122">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="91f6d-123">如需支援的版本的詳細資訊，請參閱規劃檔中的在 [Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) 中封存的技術需求。</span><span class="sxs-lookup"><span data-stu-id="91f6d-123">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="91f6d-124">在部署及啟用封存之前，您必須先設定 SQL Server 平臺。</span><span class="sxs-lookup"><span data-stu-id="91f6d-124">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="91f6d-125">若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。</span><span class="sxs-lookup"><span data-stu-id="91f6d-125">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="91f6d-126">您也可以之後再建立資料庫，包括在安裝程序中。</span><span class="sxs-lookup"><span data-stu-id="91f6d-126">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="91f6d-127">如需 SQL Server 的詳細資訊，請參閱 SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。</span><span class="sxs-lookup"><span data-stu-id="91f6d-127">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91f6d-128">確定 SQL Server Agent Service 的啟動類型為 [自動]，且 SQL Server 代理程式服務執行的是存放封存資料庫的 SQL 實例，因此預設的封存 SQL Server 維護工作可以根據 SQL Server 代理程式服務的控制，以排程的方式來執行。</span><span class="sxs-lookup"><span data-stu-id="91f6d-128">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="91f6d-129">設定檔存放區</span><span class="sxs-lookup"><span data-stu-id="91f6d-129">Setting Up File Storage</span></span>

<span data-ttu-id="91f6d-130">封存會使用您在設定前端集區或 Standard Edition Server 時所指定的 Lync Server 2013 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="91f6d-130">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="91f6d-131">您無法變更封存所用的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="91f6d-131">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="91f6d-132">如需支援的檔案儲存系統的詳細資訊，請參閱支援檔中的檔案 [儲存支援（Lync Server 2013](lync-server-2013-file-storage-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="91f6d-132">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

