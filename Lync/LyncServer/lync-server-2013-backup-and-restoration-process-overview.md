---
title: Lync Server 2013：備份和還原程式概述
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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="96cf3-102">Lync Server 2013 的備份與還原程式概述</span><span class="sxs-lookup"><span data-stu-id="96cf3-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96cf3-103">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="96cf3-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="96cf3-104">本節概要說明 Lync Server 2013 的備份與還原程式的運作方式。</span><span class="sxs-lookup"><span data-stu-id="96cf3-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="96cf3-105">無論其位置為何，您都可以針對所有標準版伺服器和企業版伺服器使用相同的程式。</span><span class="sxs-lookup"><span data-stu-id="96cf3-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="96cf3-106">一般來說，備份程式的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="96cf3-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="96cf3-107">您將備份位置建立為獨立電腦上的共用資料夾（不屬於任何文件庫）。</span><span class="sxs-lookup"><span data-stu-id="96cf3-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="96cf3-108">備份的位置參照于 **$Backup**。</span><span class="sxs-lookup"><span data-stu-id="96cf3-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="96cf3-109">在正常的排程基礎上，您會備份 lync server [2013 中備份與還原需求](lync-server-2013-backup-and-restoration-requirements-data.md)中描述的所有 Lync Server 資料庫及所有檔案存儲區：資料請按照[備份 lync server 2013](lync-server-2013-backing-up-lync-server.md)中所述的程式在中央管理儲存體中所述，包括所有伺服器設定和設定。</span><span class="sxs-lookup"><span data-stu-id="96cf3-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="96cf3-110">每次執行後續的備份時，您會建立新的共用資料夾，並變更 **$Backup**參照的路徑。</span><span class="sxs-lookup"><span data-stu-id="96cf3-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="96cf3-111">一般來說，還原程式的運作方式如下：</span><span class="sxs-lookup"><span data-stu-id="96cf3-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="96cf3-112">當發生失敗或停機時，您會將 **$Backup**參照的位置中的資料還原至 [新增] 或 [清除電腦]。</span><span class="sxs-lookup"><span data-stu-id="96cf3-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="96cf3-113">這個還原程式無法將資料還原到現有的伺服器狀態。</span><span class="sxs-lookup"><span data-stu-id="96cf3-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="96cf3-114">也就是說，這個程式要求伺服器乾淨或新。</span><span class="sxs-lookup"><span data-stu-id="96cf3-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="96cf3-115">若要讓您的使用者與會議資訊可復原至失敗的位置，您可以使用成對的前端池來實施災害復原拓朴，如在[Lync Server 2013 規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原中所述。</span><span class="sxs-lookup"><span data-stu-id="96cf3-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="96cf3-116">所有網域名稱系統（DNS）設定、動態主機設定通訊協定（DHCP）設定、功能變數名稱、電腦的完整功能變數名稱（Fqdn）、檔案儲存路徑等在以下時間的還原時間都必須相同：退後。</span><span class="sxs-lookup"><span data-stu-id="96cf3-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="96cf3-117">如果執行 Lync Server 的伺服器失敗，復原包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="96cf3-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="96cf3-118">在新的或乾淨的電腦上安裝作業系統，其 FQDN 與失敗的電腦相同。</span><span class="sxs-lookup"><span data-stu-id="96cf3-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="96cf3-119">重新安裝證書。</span><span class="sxs-lookup"><span data-stu-id="96cf3-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="96cf3-120">如果伺服器託管資料庫，請安裝 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="96cf3-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="96cf3-121">一般來說，如果伺服器是託管資料庫，請執行拓撲建立器來建立並安裝資料庫，並設定存取控制清單（Acl）。</span><span class="sxs-lookup"><span data-stu-id="96cf3-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="96cf3-122">一般來說，如果伺服器是託管伺服器角色，請執行 [Lync Server 部署嚮導] 中的步驟1至步驟4來安裝本機設定檔案、安裝伺服器角色元件、指派證書，以及啟動服務。</span><span class="sxs-lookup"><span data-stu-id="96cf3-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96cf3-123">如果伺服器是以伺服器角色裝載資料庫 collocated，執行 Lync Server 部署嚮導中的步驟2即可重新建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="96cf3-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="96cf3-124">如果伺服器裝載資料庫，請還原備份的資料。</span><span class="sxs-lookup"><span data-stu-id="96cf3-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

