---
title: Lync Server 2013：SQL Server 資料和記錄檔位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a528ba7a348ebb5c8f865a795f8b1f1c1bc30cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="67700-102">Lync Server 2013 的 SQL Server 資料和記錄檔位置</span><span class="sxs-lookup"><span data-stu-id="67700-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67700-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="67700-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="67700-104">在針對 Lync Server 2013 前端池規劃與部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 期間，重要的考慮是將資料和記錄檔案放置在物理硬碟上以提高效能。</span><span class="sxs-lookup"><span data-stu-id="67700-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="67700-105">建議的磁片設定是使用6個心軸來實施 1 + 0 RAID 組。</span><span class="sxs-lookup"><span data-stu-id="67700-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="67700-106">將頂層端池所使用的所有資料庫和記錄檔案，以及相關聯的伺服器角色和服務（也就是使用 Lync Server 的 [封存及監視伺服器]、[Lync Server 回應群組服務]、[Lync Server 呼叫駐留服務]）放在 RAID 磁片磁碟機上。[部署嚮導] 會產生經過測試以取得良好效能的配置。</span><span class="sxs-lookup"><span data-stu-id="67700-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="67700-107">下表詳細說明資料庫檔案及它們的負責人。</span><span class="sxs-lookup"><span data-stu-id="67700-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67700-108">如果您的原則與 SQL Server 設定需要更特殊的安裝，可以使用 Lync Server 管理命令介面將資料庫和記錄檔安裝到任何預先定義的位置。</span><span class="sxs-lookup"><span data-stu-id="67700-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="67700-109">如需詳細資訊，請參閱<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync server 2013 中使用 Lync Server Management Shell 的資料庫安裝</A>。</span><span class="sxs-lookup"><span data-stu-id="67700-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="67700-110">集中式管理存放區的資料和記錄檔</span><span class="sxs-lookup"><span data-stu-id="67700-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67700-111">中央管理儲存資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="67700-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="67700-112">資料檔案或記錄用途</span><span class="sxs-lookup"><span data-stu-id="67700-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67700-113">Xds</span><span class="sxs-lookup"><span data-stu-id="67700-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-114">中央管理存放區的事務日誌檔</span><span class="sxs-lookup"><span data-stu-id="67700-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-115">Xds</span><span class="sxs-lookup"><span data-stu-id="67700-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-116">維持目前 Lync Server 2013 拓朴的設定，如 [拓撲建立器] 定義及發佈</span><span class="sxs-lookup"><span data-stu-id="67700-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-117">.Lis. .mdf</span><span class="sxs-lookup"><span data-stu-id="67700-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-118">位置資訊服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="67700-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-119">.Lis</span><span class="sxs-lookup"><span data-stu-id="67700-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-120">位置資訊服務資料檔案的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="67700-121">使用者、會議和通訊錄的資料與記錄檔</span><span class="sxs-lookup"><span data-stu-id="67700-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67700-122">核心 Lync Server 2013 資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="67700-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="67700-123">資料檔案或記錄用途</span><span class="sxs-lookup"><span data-stu-id="67700-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67700-124">Rtc</span><span class="sxs-lookup"><span data-stu-id="67700-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-125">持久性使用者資料（例如，存取控制清單（Acl）、連絡人、預定的會議）</span><span class="sxs-lookup"><span data-stu-id="67700-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-126">Rtc</span><span class="sxs-lookup"><span data-stu-id="67700-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-127">Rtc 資料的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-128">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="67700-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-129">維護暫時的使用者資料（目前狀態執行時間資料）</span><span class="sxs-lookup"><span data-stu-id="67700-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-130">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="67700-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-131">Rtcdyn 資料的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-132">Rtcab</span><span class="sxs-lookup"><span data-stu-id="67700-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-133">即時通訊（RTC）通訊錄資料庫是儲存通訊錄服務資訊的 SQL Server 儲備庫</span><span class="sxs-lookup"><span data-stu-id="67700-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-134">Rtcab</span><span class="sxs-lookup"><span data-stu-id="67700-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-135">通訊錄服務的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-136">Rtclocal .mdb</span><span class="sxs-lookup"><span data-stu-id="67700-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="67700-137">主持會議目錄</span><span class="sxs-lookup"><span data-stu-id="67700-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-138">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="67700-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-139">維護使用者資料的備份</span><span class="sxs-lookup"><span data-stu-id="67700-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-140">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="67700-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-141">Rtcxds 資料的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="67700-142">通話寄存與回應群組的資料和記錄檔案</span><span class="sxs-lookup"><span data-stu-id="67700-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67700-143">應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="67700-143">Application database</span></span></th>
<th><span data-ttu-id="67700-144">資料檔案或記錄用途</span><span class="sxs-lookup"><span data-stu-id="67700-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67700-145">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="67700-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-146">通話駐留應用程式的動態資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="67700-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-147">Cpsdyn</span><span class="sxs-lookup"><span data-stu-id="67700-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-148">通話駐留應用程式資料檔案的事務記錄</span><span class="sxs-lookup"><span data-stu-id="67700-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-149">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="67700-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-150">Lync Server 回應群組服務資料檔案以瞭解服務的設定</span><span class="sxs-lookup"><span data-stu-id="67700-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-151">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="67700-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-152">回應群組應用程式設定的事務日誌檔</span><span class="sxs-lookup"><span data-stu-id="67700-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-153">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="67700-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-154">回應群組服務資料檔案以供執行時間作業</span><span class="sxs-lookup"><span data-stu-id="67700-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-155">Rgsdyn</span><span class="sxs-lookup"><span data-stu-id="67700-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-156">回應群組服務執行時間資料檔案的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="67700-157">存檔及監視伺服器的資料和記錄檔</span><span class="sxs-lookup"><span data-stu-id="67700-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67700-158">封存與監控資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="67700-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="67700-159">資料檔案或記錄用途</span><span class="sxs-lookup"><span data-stu-id="67700-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67700-160">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="67700-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-161">監視伺服器的通話詳細資料錄製（CDR）程式的資料存放區</span><span class="sxs-lookup"><span data-stu-id="67700-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-162">LcsCdr</span><span class="sxs-lookup"><span data-stu-id="67700-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-163">通話詳細資料錄製（CDR）資料的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-164">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="67700-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-165">從監視伺服器儲存的經驗資料檔案品質</span><span class="sxs-lookup"><span data-stu-id="67700-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-166">QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="67700-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-167">監視資料的事務日誌</span><span class="sxs-lookup"><span data-stu-id="67700-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67700-168">Lcslog</span><span class="sxs-lookup"><span data-stu-id="67700-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="67700-169">存檔伺服器上立即訊息和會議資料的保留資料檔案</span><span class="sxs-lookup"><span data-stu-id="67700-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67700-170">Lcslog</span><span class="sxs-lookup"><span data-stu-id="67700-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="67700-171">封存資料的事務記錄檔</span><span class="sxs-lookup"><span data-stu-id="67700-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67700-172">在本主題中，會對磁片和 RAID 集進行參照。</span><span class="sxs-lookup"><span data-stu-id="67700-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="67700-173">請注意，在 SQL Server 資源的設定中，參照磁片代表單一硬體裝置。</span><span class="sxs-lookup"><span data-stu-id="67700-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="67700-174">含有兩個分區的硬碟，其中一個保留記錄檔，另一個存放資料檔的磁碟分割，不是兩個磁片，每個磁片都專用於記錄或資料檔案。</span><span class="sxs-lookup"><span data-stu-id="67700-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="67700-175">在參照 RAID 集時，各廠商都有許多不同的 RAID 技術。</span><span class="sxs-lookup"><span data-stu-id="67700-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="67700-176">而且隨著存放區域網路（SAN）的急劇增加，專用於單一系統的 RAID 集是 rarer。</span><span class="sxs-lookup"><span data-stu-id="67700-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="67700-177">在使用 Lync Server 2013 設定 SQL Server 效能時，請諮詢您的 RAID 或 SAN 供應商，以判斷您的磁片佈局最佳配置。</span><span class="sxs-lookup"><span data-stu-id="67700-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="67700-178">另請注意，並非所有磁片磁碟機都同等地建立;部分的執行效果比其他更好。</span><span class="sxs-lookup"><span data-stu-id="67700-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="67700-179">即使是相同製造商的磁片磁碟機，也可能會因轉速、硬體快取大小，以及其他因素而有所不同。</span><span class="sxs-lookup"><span data-stu-id="67700-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

