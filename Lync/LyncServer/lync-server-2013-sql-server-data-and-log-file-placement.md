---
title: Lync Server 2013： SQL Server 資料和記錄檔位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509620"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="3c2d9-102">Lync Server 2013 的 SQL Server 資料和記錄檔位置</span><span class="sxs-lookup"><span data-stu-id="3c2d9-102">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c2d9-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3c2d9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3c2d9-104">在規劃及部署 Lync Server 2013 前端集區的 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 期間，重要的考慮是將資料和記錄檔的位置放在實體硬碟上，以取得效能。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="3c2d9-105">建議的磁片設定是使用6個主軸來執行 1 + 0 RAID 集。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="3c2d9-106">將前端集區和相關聯的伺服器角色及服務所使用的所有資料庫及記錄檔，都設為 (（封存和監控伺服器、Lync Server 回應群組服務、Lync Server 通話駐留服務) 使用 Lync Server 部署嚮導）時，將會產生測試是否有良好效能的設定。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="3c2d9-107">下表詳述資料庫檔案及其負責內容。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c2d9-108">如果您的原則和 SQL Server 設定需要更特殊的安裝，則可以使用 Lync Server 管理命令介面，將資料庫和記錄檔安裝至任何預先定義的位置。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="3c2d9-109">如需詳細資訊，請參閱 <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">在 Lync server 2013 中使用 Lync Server 管理命令介面的資料庫安裝</A> 。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="3c2d9-110">中央管理存放區的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c2d9-111">中央管理存放區資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="3c2d9-112">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="3c2d9-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-113">Xds</span><span class="sxs-lookup"><span data-stu-id="3c2d9-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-114">中央管理存放區的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-115">Xds</span><span class="sxs-lookup"><span data-stu-id="3c2d9-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-116">維護目前 Lync Server 2013 拓撲的設定，如拓撲產生器所定義及發行的拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="3c2d9-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-117">.Lis</span><span class="sxs-lookup"><span data-stu-id="3c2d9-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-118">位置資訊服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-119">.Lis</span><span class="sxs-lookup"><span data-stu-id="3c2d9-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-120">位置資訊服務資料檔案的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="3c2d9-121">使用者、會議及通訊錄的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c2d9-122">核心 Lync Server 2013 資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="3c2d9-123">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="3c2d9-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-124">Rtc</span><span class="sxs-lookup"><span data-stu-id="3c2d9-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-125">Persistent 使用者資料 (例如，ACLs) 、連絡人、排程的會議 (的存取控制清單) </span><span class="sxs-lookup"><span data-stu-id="3c2d9-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-126">Rtc</span><span class="sxs-lookup"><span data-stu-id="3c2d9-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-127">Rtc 資料的交易記錄</span><span class="sxs-lookup"><span data-stu-id="3c2d9-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-128">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="3c2d9-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-129">維護暫時性的使用者資料 (目前狀態執行時間資料) </span><span class="sxs-lookup"><span data-stu-id="3c2d9-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-130">Rtcdyn</span><span class="sxs-lookup"><span data-stu-id="3c2d9-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-131">Rtcdyn 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-132">Rtcab</span><span class="sxs-lookup"><span data-stu-id="3c2d9-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-133">即時通訊 (RTC) 通訊錄資料庫是儲存通訊錄服務資訊的 SQL Server 存放庫</span><span class="sxs-lookup"><span data-stu-id="3c2d9-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-134">Rtcab</span><span class="sxs-lookup"><span data-stu-id="3c2d9-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-135">通訊錄服務的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-136">Rtclocal .mdb</span><span class="sxs-lookup"><span data-stu-id="3c2d9-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-137">主控會議目錄</span><span class="sxs-lookup"><span data-stu-id="3c2d9-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-138">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="3c2d9-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-139">維護使用者資料的備份</span><span class="sxs-lookup"><span data-stu-id="3c2d9-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-140">Rtcxds</span><span class="sxs-lookup"><span data-stu-id="3c2d9-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-141">Rtcxds 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="3c2d9-142">通話駐留及回應群組的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c2d9-143">應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="3c2d9-143">Application database</span></span></th>
<th><span data-ttu-id="3c2d9-144">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="3c2d9-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-145">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-146">通話駐留應用程式的動態資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="3c2d9-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-147">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-148">通話駐留應用程式資料檔案的交易記錄</span><span class="sxs-lookup"><span data-stu-id="3c2d9-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-149">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="3c2d9-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-150">服務設定的 Lync Server 回應群組服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-151">Rgsconfig</span><span class="sxs-lookup"><span data-stu-id="3c2d9-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-152">回應群組應用程式設定的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-153">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-154">執行階段作業的回應群組服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-155">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-156">回應群組服務執行階段資料檔案的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="3c2d9-157">封存和監控伺服器的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c2d9-158">封存及監控資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="3c2d9-159">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="3c2d9-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-160">LcsCdr .mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-161"> (CDR) 監控伺服器處理常式的詳細通話記錄的資料存放區</span><span class="sxs-lookup"><span data-stu-id="3c2d9-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-162">LcsCdr .ldf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-163">詳細通話記錄 (CDR) 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-164">QoEMetrics.mdf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-165">從監控伺服器儲存的經驗品質資料檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-166">QoEMetrics .ldf</span><span class="sxs-lookup"><span data-stu-id="3c2d9-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-167">監控資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c2d9-168">Lcslog</span><span class="sxs-lookup"><span data-stu-id="3c2d9-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-169">封存伺服器上的立即訊息和會議資料保留的資料檔案</span><span class="sxs-lookup"><span data-stu-id="3c2d9-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c2d9-170">Lcslog</span><span class="sxs-lookup"><span data-stu-id="3c2d9-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="3c2d9-171">封存資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="3c2d9-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3c2d9-p103">在本主題中，會參考磁碟及 RAID 集。請注意，在 SQL Server 資源的設定中，參考磁碟表示單一硬體裝置。含有兩個分割 (一個分割保留記錄檔，而另一個分割保留資料檔案) 的單一硬碟與兩個磁碟 (各專用於記錄檔或資料檔案) 不同。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="3c2d9-175">關於 RAID 集，有數個來自不同廠商的不同 RAID 技術。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="3c2d9-176">而且，隨著存放區域網路 (SAN) 的數量擴增，專用於單一系統的 RAID 集日益罕見。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="3c2d9-177">使用 Lync Server 2013 設定 SQL Server 效能時，應與您的 RAID 或 SAN 供應商協商，以判斷您的磁片配置最佳設定。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="3c2d9-178">也請注意，磁碟機的設計並非完全相同；部分磁碟機的效能可能會優於其他磁碟機。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="3c2d9-179">因為轉速、硬體快取大小及其他因素，即使是相同製造商的磁碟機，效能也可能不同。</span><span class="sxs-lookup"><span data-stu-id="3c2d9-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

