---
title: Lync Server 2013：設定儲存空間以進行封存
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
ms.openlocfilehash: a5a380ce6c863c54739e74488bfa3b3979664e78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="a5d4d-102">在 Lync Server 2013 中設定儲存空間以進行歸檔</span><span class="sxs-lookup"><span data-stu-id="a5d4d-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5d4d-103">_**主題上次修改日期：** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="a5d4d-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="a5d4d-104">Lync Server 2013 的歸檔儲存空間包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a5d4d-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="a5d4d-105">**需要資料儲存**   區資料儲存空間，才能儲存 IM 內容。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="a5d4d-106">\*\*\*\*    需要有檔案儲存空間儲存空間，才能儲存會議（會議）內容資料儲存與檔案儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="a5d4d-107">設定資料儲存</span><span class="sxs-lookup"><span data-stu-id="a5d4d-107">Setting Up Data Storage</span></span>

<span data-ttu-id="a5d4d-108">在 Lync Server 2013 中設定存檔資料儲存空間的需求，取決於您要儲存存檔資料的方式：</span><span class="sxs-lookup"><span data-stu-id="a5d4d-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="a5d4d-109">整合 Lync Server 2013 與 Exchange 部署的歸檔，以儲存使用 Exchange 儲存區的歸檔資料。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="a5d4d-110">設定個別的 SQL Server 資料庫伺服器來儲存存檔資料。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="a5d4d-111">設定 Exchange 儲存空間以歸檔資料</span><span class="sxs-lookup"><span data-stu-id="a5d4d-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="a5d4d-112">若要設定 Exchange 儲存存檔資料，您的 Exchange 部署必須執行 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="a5d4d-113">此外，使用者信箱必須駐留在 Exchange 2013 伺服器上，且其信箱必須放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="a5d4d-114">如需有關設定 Exchange 2013 的詳細資訊，請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="a5d4d-115">設定用於儲存存檔資料的 SQL Server 資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="a5d4d-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="a5d4d-116">Lync Server 2013 中的封存需要 SQL Server 資料庫軟體來儲存已封存的資料，除非您將部署與 Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="a5d4d-117">針對 SQL Server 封存資料庫，您必須在將裝載存檔資料庫的電腦上安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="a5d4d-118">您可以使用與您用於前端池後端資料庫的同一個 SQL 實例。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="a5d4d-119">為了獲得最佳效能，您應該將封存資料庫部署在與中央管理儲存體分開的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="a5d4d-120">如需 collocating Lync Server 2013 元件的詳細資訊，請參閱可支援性檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="a5d4d-121">每個資料庫伺服器都必須執行受支援版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="a5d4d-122">如需支援版本的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔技術需求](lync-server-2013-technical-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="a5d4d-123">您必須先設定 SQL Server 平臺，然後才能部署並啟用封存。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="a5d4d-124">如果要用來發佈拓朴的帳戶具有適當的管理員權力和許可權，您可以在發佈拓撲時建立封存資料庫（LcsLog）。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="a5d4d-125">您也可以日後建立資料庫，包括安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="a5d4d-126">如需 SQL Server 的詳細資料，請參閱 SQL Server [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)技術中心（位於）。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5d4d-127">確定 SQL Server Agent 服務啟動類型為 [自動]，且 SQL Server Agent 服務正在針對存放封存資料庫的 SQL 實例執行，因此預設的 [存檔 SQL Server 維護作業] 可以在其排程的[SQL Server 代理程式服務] 的控制權。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="a5d4d-128">設定檔案儲存空間</span><span class="sxs-lookup"><span data-stu-id="a5d4d-128">Setting Up File Storage</span></span>

<span data-ttu-id="a5d4d-129">在您設定前端池或標準版伺服器時，存檔會使用您指定的 Lync Server 2013 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="a5d4d-130">您無法變更用於封存的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="a5d4d-131">如需支援的檔案存儲系統的詳細資料，請參閱支援檔中的[Lync Server 2013 檔案儲存支援](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a5d4d-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

