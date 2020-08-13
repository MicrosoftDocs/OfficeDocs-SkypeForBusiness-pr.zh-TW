---
title: Lync Server 2013：設定封存的存放區
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
ms.openlocfilehash: a6f299b01b95cddd461893b35518e3c2fe40c694
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c68d1-102">在 Lync Server 2013 中設定儲存區封存</span><span class="sxs-lookup"><span data-stu-id="c68d1-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68d1-103">_**主題上次修改日期：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="c68d1-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="c68d1-104">Lync Server 2013 的封存儲存區包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="c68d1-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="c68d1-105">**資料儲存**    需要有資料存放區才能儲存 IM 內容。</span><span class="sxs-lookup"><span data-stu-id="c68d1-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="c68d1-106">**檔存放區**    需要有檔案存放區，才能儲存會議 (會議) 內容資料儲存區和檔案儲存區。</span><span class="sxs-lookup"><span data-stu-id="c68d1-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="c68d1-107">設定資料儲存區</span><span class="sxs-lookup"><span data-stu-id="c68d1-107">Setting Up Data Storage</span></span>

<span data-ttu-id="c68d1-108">在 Lync Server 2013 中設定封存資料儲存的需求，取決於您想要儲存封存資料的方式：</span><span class="sxs-lookup"><span data-stu-id="c68d1-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="c68d1-109">整合 Lync Server 2013 封存與 Exchange 部署，以儲存使用 Exchange 儲存體的封存資料。</span><span class="sxs-lookup"><span data-stu-id="c68d1-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="c68d1-110">設定個別的 SQL Server 資料庫伺服器以儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="c68d1-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="c68d1-111">設定用於封存資料的 Exchange 存放區</span><span class="sxs-lookup"><span data-stu-id="c68d1-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="c68d1-112">若要設定 Exchange 封存資料的儲存，您的 Exchange 部署必須執行 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="c68d1-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="c68d1-113">此外，使用者信箱必須位於 Exchange 2013 伺服器上，而且其信箱必須置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="c68d1-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="c68d1-114">如需設定 Exchange 2013 的詳細資訊，請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="c68d1-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="c68d1-115">設定用於儲存封存資料的 SQL Server 資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="c68d1-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="c68d1-116">Lync Server 2013 中的封存需要 SQL Server 資料庫軟體儲存封存的資料，除非您將部署與 Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="c68d1-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="c68d1-117">針對 SQL Server 封存資料庫，您必須在將裝載封存資料庫的電腦上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c68d1-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="c68d1-118">您可以使用相同的 SQL 實例，用於前端集區的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c68d1-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="c68d1-119">為了達到最佳效能，您應該在與中央管理存放區分開的電腦上部署封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="c68d1-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="c68d1-120">如需組合 Lync Server 2013 元件的詳細資訊，請參閱支援檔中的[支援的伺服器組合（Lync server 2013](lync-server-2013-supported-server-collocation.md) ）。</span><span class="sxs-lookup"><span data-stu-id="c68d1-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c68d1-121">每個資料庫伺服器都必須執行支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="c68d1-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="c68d1-122">如需支援的版本的詳細資訊，請參閱規劃檔中的在[Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md)中封存的技術需求。</span><span class="sxs-lookup"><span data-stu-id="c68d1-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="c68d1-123">在部署及啟用封存之前，您必須先設定 SQL Server 平臺。</span><span class="sxs-lookup"><span data-stu-id="c68d1-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="c68d1-124">若要用來發行拓撲的帳戶具有適當的系統管理員許可權，您可以在發行拓撲時，建立封存資料庫 (LcsLog) 。</span><span class="sxs-lookup"><span data-stu-id="c68d1-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="c68d1-125">您也可以之後再建立資料庫，包括在安裝程序中。</span><span class="sxs-lookup"><span data-stu-id="c68d1-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="c68d1-126">如需 SQL Server 的詳細資訊，請參閱 SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) 。</span><span class="sxs-lookup"><span data-stu-id="c68d1-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c68d1-127">確定 SQL Server Agent Service 的啟動類型為 [自動]，且 SQL Server 代理程式服務執行的是存放封存資料庫的 SQL 實例，因此預設的封存 SQL Server 維護工作可以根據 SQL Server 代理程式服務的控制，以排程的方式來執行。</span><span class="sxs-lookup"><span data-stu-id="c68d1-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="c68d1-128">設定檔存放區</span><span class="sxs-lookup"><span data-stu-id="c68d1-128">Setting Up File Storage</span></span>

<span data-ttu-id="c68d1-129">封存會使用您在設定前端集區或 Standard Edition Server 時所指定的 Lync Server 2013 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="c68d1-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="c68d1-130">您無法變更封存所用的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="c68d1-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="c68d1-131">如需支援的檔案儲存系統的詳細資訊，請參閱支援檔中的檔案[儲存支援（Lync Server 2013](lync-server-2013-file-storage-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="c68d1-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

