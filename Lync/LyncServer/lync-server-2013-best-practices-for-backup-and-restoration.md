---
title: Lync Server 2013： 用於備份及還原的最佳作法
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
ms.openlocfilehash: 7fc2aac99251c0b2e5bc950b3dc11e8e2044b440
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="9f949-102">備份及還原 Lync Server 2013 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="9f949-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f949-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="9f949-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9f949-104">本節包含兩種類型的最佳作法：</span><span class="sxs-lookup"><span data-stu-id="9f949-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="9f949-105">用於備份及還原的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="9f949-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="9f949-106">降低災害影響程度的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="9f949-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="9f949-107">備份及還原的最佳作法</span><span class="sxs-lookup"><span data-stu-id="9f949-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="9f949-108">當您備份或還原您的資料，以利您備份和還原程序，套用下列最佳作法：</span><span class="sxs-lookup"><span data-stu-id="9f949-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="9f949-109">在適當的時間間隔執行定期備份。</span><span class="sxs-lookup"><span data-stu-id="9f949-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="9f949-110">簡單且最常使用的備份類型和旋轉排程是完整、 夜間整個 SQL Server 資料庫的備份。</span><span class="sxs-lookup"><span data-stu-id="9f949-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="9f949-111">然後，如果需要還原，復原程序需要只有一個備份，並不超過一天的資料不會遺失。</span><span class="sxs-lookup"><span data-stu-id="9f949-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="9f949-112">如果您使用 cmdlet 或 Lync Server Control Panel 以進行組態變更，使用**Export-csconfiguration** cmdlet 之後要採取的拓撲組態檔 (Xds.mdf) 快照備份進行的變更，使您不會遺失所做的變更，如果您需要還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="9f949-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="9f949-113">請注意，此組態是以 XML 格式，備份壓縮的 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="9f949-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="9f949-114">請確定您計劃要用於備份 Lync 伺服器之共用的資料夾有足夠的磁碟空間可容納所有備份的資料。</span><span class="sxs-lookup"><span data-stu-id="9f949-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="9f949-115">排程備份 Lync Server 使用狀況通常較低，以改善伺服器效能及提升使用者經驗時。</span><span class="sxs-lookup"><span data-stu-id="9f949-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="9f949-116">請確定備份資料的位置是安全 （建議使用遠端位置）。</span><span class="sxs-lookup"><span data-stu-id="9f949-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="9f949-117">保留他們將可使用位置，以便在需要時還原資料的備份檔案。</span><span class="sxs-lookup"><span data-stu-id="9f949-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="9f949-118">規劃及排程定期測試組織所支援的還原程序。</span><span class="sxs-lookup"><span data-stu-id="9f949-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="9f949-119">驗證事先以確保其運作如預期般您備份和還原程序。</span><span class="sxs-lookup"><span data-stu-id="9f949-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="9f949-120">降低災害影響程度的最佳作法</span><span class="sxs-lookup"><span data-stu-id="9f949-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="9f949-121">（例如電力中斷或突然硬體故障不事件所造成） 的慘服務中斷的處理的最佳策略是假設他們將會發生，並據此規劃。</span><span class="sxs-lookup"><span data-stu-id="9f949-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="9f949-122">如果 Lync 服務，最少的干擾及中斷，商務關鍵的組織，您應該考慮實作的前端伺服器，配對集區中[的高可用性和災害復原 Lync Server 2013 中的規劃](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="9f949-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="9f949-123">然後，如果其中一個這些集區有災害時，系統管理員可以切換至其他集區，最少的停機時間由該集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="9f949-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="9f949-124">您開發以備份和還原策略的一部分的嚴重損壞管理計劃應包含下列：</span><span class="sxs-lookup"><span data-stu-id="9f949-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="9f949-125">追蹤您的軟體媒體，以及軟體與韌體更新，隨時可用。</span><span class="sxs-lookup"><span data-stu-id="9f949-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="9f949-126">維護硬體與軟體記錄。</span><span class="sxs-lookup"><span data-stu-id="9f949-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="9f949-127">定期備份資料和監控備份的完整性。</span><span class="sxs-lookup"><span data-stu-id="9f949-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="9f949-128">訓練人員相關的嚴重損壞修復、 記載的程序，以及實作災害復原模擬操演。</span><span class="sxs-lookup"><span data-stu-id="9f949-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="9f949-129">預留備用硬體，或者，如果您有服務層級協議 (SLA)，與硬體廠商與供應商的提示取代訂立。</span><span class="sxs-lookup"><span data-stu-id="9f949-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="9f949-130">分開保存交易記錄檔 （.ldf 檔案） 與資料庫檔案 （.mdf 檔案）。</span><span class="sxs-lookup"><span data-stu-id="9f949-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

