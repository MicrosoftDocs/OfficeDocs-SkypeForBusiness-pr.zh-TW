---
title: Lync Server 2013：備份及還原的最佳作法
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
ms.openlocfilehash: ca14913d063a8691d0477af912e70e72b91143fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535200"
---
# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="07dcf-102">Lync Server 2013 備份及還原的最佳作法</span><span class="sxs-lookup"><span data-stu-id="07dcf-102">Best practices for backup and restoration for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07dcf-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="07dcf-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="07dcf-104">本節包含兩種最佳作法類型：</span><span class="sxs-lookup"><span data-stu-id="07dcf-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="07dcf-105">備份及還原的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="07dcf-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="07dcf-106">使災難影響降至最低的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="07dcf-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="07dcf-107">備份及還原的最佳作法</span><span class="sxs-lookup"><span data-stu-id="07dcf-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="07dcf-108">若要協助您的備份與還原程式，請在備份或還原資料時套用下列最佳作法：</span><span class="sxs-lookup"><span data-stu-id="07dcf-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="07dcf-109">以適當的間隔執行定期備份。</span><span class="sxs-lookup"><span data-stu-id="07dcf-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="07dcf-110">最簡單且最常使用的備份類型和輪替排程是完整、晚上備份整個 SQL Server 資料庫的完整備份。</span><span class="sxs-lookup"><span data-stu-id="07dcf-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="07dcf-111">這樣一來，如果需要還原，還原程式只需要一個備份，而且不會有超過一天的資料遺失。</span><span class="sxs-lookup"><span data-stu-id="07dcf-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="07dcf-112">如果您使用 Cmdlet 或 Lync Server 控制台進行設定變更，請在進行變更之後，使用 **Export-CsConfiguration** 指令程式對拓撲設定檔進行快照備份，以 () Xds，這樣就不會在您需要還原資料庫時丟失變更。</span><span class="sxs-lookup"><span data-stu-id="07dcf-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="07dcf-113">請注意，這項設定會以 XML 格式備份，並壓縮成 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="07dcf-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="07dcf-114">確定您計畫用於備份 Lync 伺服器的共用資料夾具有足夠的磁碟空間，可容納所有備份的資料。</span><span class="sxs-lookup"><span data-stu-id="07dcf-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="07dcf-115">當 Lync Server 的使用量一般很低時，排程備份，以提升伺服器效能和使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="07dcf-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="07dcf-116">請確定備份資料的位置是否安全 (建議) 遠端位置。</span><span class="sxs-lookup"><span data-stu-id="07dcf-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="07dcf-117">保留可供使用的備份檔案，以備您需要還原資料時使用。</span><span class="sxs-lookup"><span data-stu-id="07dcf-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="07dcf-118">規劃及排程定期測試組織所支援的還原程式。</span><span class="sxs-lookup"><span data-stu-id="07dcf-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="07dcf-119">請事先驗證備份與還原程式，以確定其運作如預期。</span><span class="sxs-lookup"><span data-stu-id="07dcf-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="07dcf-120">最小化災難影響的最佳作法</span><span class="sxs-lookup"><span data-stu-id="07dcf-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="07dcf-121">處理災難性服務中斷的最佳策略， (因無法管理事件（例如電源中斷或突然硬體失敗）所造成，請) 假設會發生這些事件，並據此進行規劃。</span><span class="sxs-lookup"><span data-stu-id="07dcf-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="07dcf-122">如果 Lync 服務具有最低中斷和停機時間，對您的組織而言是至關重要的，您應該考慮實施前端伺服器的配對集區（如在 [Lync Server 2013 中規劃高可用性和嚴重損壞修復中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述）。</span><span class="sxs-lookup"><span data-stu-id="07dcf-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="07dcf-123">然後，如果其中一個集區發生災難，系統管理員可以將該集區的使用者切換為由其他集區所提供，至少停機時間。</span><span class="sxs-lookup"><span data-stu-id="07dcf-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="07dcf-124">您在備份與還原策略中所制定的災難管理計畫應包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="07dcf-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="07dcf-125">讓您的軟體媒體和您的軟體和固件更新，都能隨時使用。</span><span class="sxs-lookup"><span data-stu-id="07dcf-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="07dcf-126">維護硬體和軟體記錄。</span><span class="sxs-lookup"><span data-stu-id="07dcf-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="07dcf-127">定期備份資料，並監視備份的完整性。</span><span class="sxs-lookup"><span data-stu-id="07dcf-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="07dcf-128">訓練您的員工在嚴重損壞修復、記錄程式及實施嚴重損壞修復類比訓練。</span><span class="sxs-lookup"><span data-stu-id="07dcf-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="07dcf-129">讓備用硬體可用，或者，如果您有服務層級協定 (SLA) ，請與硬體廠商和廠商簽定，以進行提示取代。</span><span class="sxs-lookup"><span data-stu-id="07dcf-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="07dcf-130">將交易記錄檔的位置分開 ( .ldf 檔案中) 和資料庫檔案)  ( .mdf 檔案。</span><span class="sxs-lookup"><span data-stu-id="07dcf-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

