---
title: Lync Server 2013：備份及還原程式概述
description: Lync Server 2013：備份及還原程式概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b833a05021d3a848e9de1ee8768f7daa194c6a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563169"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="1741c-103">Lync Server 2013 的備份與還原程式概述</span><span class="sxs-lookup"><span data-stu-id="1741c-103">Backup and restoration process overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1741c-104">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="1741c-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="1741c-105">本節提供 Lync Server 2013 備份與還原程式運作方式的概述。</span><span class="sxs-lookup"><span data-stu-id="1741c-105">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="1741c-106">不論其位置為何，所有的 Standard Edition server 和 Enterprise Edition 伺服器都使用相同的處理常式。</span><span class="sxs-lookup"><span data-stu-id="1741c-106">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="1741c-107">一般來說，備份程式的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="1741c-107">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="1741c-108">您將備份位置建立為獨立電腦上的共用資料夾，而不是任何集區的一部分。</span><span class="sxs-lookup"><span data-stu-id="1741c-108">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="1741c-109">備份的位置參照于 **$Backup**。</span><span class="sxs-lookup"><span data-stu-id="1741c-109">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="1741c-110">在定期、排程的基礎上，您會以 [Lync server 2013](lync-server-2013-backup-and-restoration-requirements-data.md) 中所述的程式備份所有的 lync 伺服器資料庫和所有檔案存放區，如備份與還原需求中所述的程式，請遵循 [備份 lync server 2013](lync-server-2013-backing-up-lync-server.md) 中所述的程式。中央管理存放區包括所有的伺服器設定及設定。</span><span class="sxs-lookup"><span data-stu-id="1741c-110">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="1741c-111">每次執行後續備份時，會建立新的共用資料夾，並變更 **$Backup** 參照的路徑。</span><span class="sxs-lookup"><span data-stu-id="1741c-111">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="1741c-112">一般來說，還原程式的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="1741c-112">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="1741c-113">當發生故障或中斷時，您會將 **$Backup** 所參照的位置資料還原至新的或全新的電腦。</span><span class="sxs-lookup"><span data-stu-id="1741c-113">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1741c-114">這種還原程式不會將資料還原到現有的伺服器狀態。</span><span class="sxs-lookup"><span data-stu-id="1741c-114">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="1741c-115">也就是說，此程式要求伺服器為全新或全新。</span><span class="sxs-lookup"><span data-stu-id="1741c-115">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="1741c-116">若要讓您的使用者和會議資訊可恢復至失敗點，您可以使用成對的前端集區來執行災難修復拓撲，如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="1741c-116">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="1741c-117">所有網域名稱系統 (DNS) 設定、動態主機設定通訊協定 (DHCP) 設定、功能變數名稱、電腦完全限定功能變數名稱 (Fqdn) 、檔案存放區路徑等等，在還原時，必須在備份時相同。</span><span class="sxs-lookup"><span data-stu-id="1741c-117">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="1741c-118">如果執行 Lync Server 的伺服器失敗，復原作業會包含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1741c-118">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="1741c-119">使用與失敗電腦相同的 FQDN，在新的或全新的電腦上安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="1741c-119">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="1741c-120">重新安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="1741c-120">Reinstall certificates.</span></span>

  - <span data-ttu-id="1741c-121">如果伺服器主控資料庫，請安裝 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="1741c-121">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="1741c-122">一般來說，如果伺服器主控資料庫，請執行拓撲產生器以建立及安裝資料庫，並設定 (ACLs) 的存取控制清單。</span><span class="sxs-lookup"><span data-stu-id="1741c-122">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="1741c-123">一般來說，如果伺服器主控伺服器角色，請執行 Lync Server 部署嚮導的步驟1到步驟4，以安裝本機設定檔、安裝伺服器角色元件、指派憑證，以及啟動服務。</span><span class="sxs-lookup"><span data-stu-id="1741c-123">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1741c-124">如果伺服器主控的資料庫組合是伺服器角色，則執行 Lync Server 部署嚮導的步驟2，會重新建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="1741c-124">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="1741c-125">如果伺服器主控資料庫，請還原備份的資料。</span><span class="sxs-lookup"><span data-stu-id="1741c-125">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

