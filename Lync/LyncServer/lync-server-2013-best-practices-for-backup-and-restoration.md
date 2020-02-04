---
title: Lync Server 2013：備份和還原的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="5ab89-102">Lync Server 2013 備份和還原的最佳做法</span><span class="sxs-lookup"><span data-stu-id="5ab89-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ab89-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5ab89-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5ab89-104">本節包含兩種類型的最佳做法：</span><span class="sxs-lookup"><span data-stu-id="5ab89-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="5ab89-105">備份與還原的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5ab89-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="5ab89-106">將災難影響降至最低的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="5ab89-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="5ab89-107">備份與還原的最佳做法</span><span class="sxs-lookup"><span data-stu-id="5ab89-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="5ab89-108">若要協助您的備份和還原程式，請在備份或還原資料時，套用下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="5ab89-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="5ab89-109">以適當的間隔執行定期備份。</span><span class="sxs-lookup"><span data-stu-id="5ab89-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="5ab89-110">最簡單且最常使用的備份類型和輪換排程是完整、晚上備份整個 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="5ab89-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="5ab89-111">然後，如果需要還原，還原程式只需要一個備份，而且一天的資料就不會遺失。</span><span class="sxs-lookup"><span data-stu-id="5ab89-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="5ab89-112">如果您使用 [Cmdlet] 或 [Lync Server 控制台] 進行設定變更，請在進行變更之後，使用**Export CsConfiguration** Cmdlet 來製作拓撲設定檔案（Xds）的快照備份，以免您需要還原資料庫時才遺失所做的變更。</span><span class="sxs-lookup"><span data-stu-id="5ab89-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="5ab89-113">請注意，此設定是以 XML 格式來備份，並壓縮為 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="5ab89-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="5ab89-114">請確定您打算用來備份 Lync Server 的共用資料夾有足夠的磁碟空間來容納所有備份的資料。</span><span class="sxs-lookup"><span data-stu-id="5ab89-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="5ab89-115">在 Lync 伺服器使用量通常較低時排程備份，以提升伺服器效能和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5ab89-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="5ab89-116">確定備份資料的位置是安全的（我們建議遠端位置）。</span><span class="sxs-lookup"><span data-stu-id="5ab89-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="5ab89-117">將備份檔案保留在其中，以備您需要還原資料時使用。</span><span class="sxs-lookup"><span data-stu-id="5ab89-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="5ab89-118">規劃並排程您組織所支援之還原處理程式的定期測試。</span><span class="sxs-lookup"><span data-stu-id="5ab89-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="5ab89-119">事先驗證您的備份和還原程式，以確保它們能如期運作。</span><span class="sxs-lookup"><span data-stu-id="5ab89-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="5ab89-120">將災難影響降至最低的最佳做法</span><span class="sxs-lookup"><span data-stu-id="5ab89-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="5ab89-121">處理災難性服務中斷的最佳策略（由無法管理的事件（例如電源中斷或突然硬體故障）所造成）是假設它們將會發生，並據此規劃。</span><span class="sxs-lookup"><span data-stu-id="5ab89-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="5ab89-122">如果 Lync 服務的中斷和停機時間最低，對於您的組織而言是至關重要的，您應該考慮實現前端伺服器的成對池，如在[Lync Server 2013 規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原中所述。</span><span class="sxs-lookup"><span data-stu-id="5ab89-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="5ab89-123">然後，如果其中一個池有災難，系統管理員可以將該池的使用者切換為由其他池提供，但停機時間最低。</span><span class="sxs-lookup"><span data-stu-id="5ab89-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="5ab89-124">您在備份和還原策略中開發的災難管理方案應包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5ab89-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="5ab89-125">讓您的軟體媒體和軟體及固件更新保持在隨時可用。</span><span class="sxs-lookup"><span data-stu-id="5ab89-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="5ab89-126">維護硬體和軟體記錄。</span><span class="sxs-lookup"><span data-stu-id="5ab89-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="5ab89-127">定期備份您的資料，並監控備份的完整性。</span><span class="sxs-lookup"><span data-stu-id="5ab89-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="5ab89-128">在災難復原中訓練您的員工、記錄程式，以及實施災害復原類比訓練。</span><span class="sxs-lookup"><span data-stu-id="5ab89-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="5ab89-129">讓備用硬體保持可用，或如果您有服務等級協定（SLA），請與硬體廠商和供應商進行提示取代。</span><span class="sxs-lookup"><span data-stu-id="5ab89-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="5ab89-130">分隔事務日誌檔（.ldf 檔案）和資料庫檔案（.mdf 檔案）的位置。</span><span class="sxs-lookup"><span data-stu-id="5ab89-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

