---
title: 'Lync Server 2013: SQL Server 資料和記錄檔位置'
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
ms.openlocfilehash: fc1ae5f876986f6387ce4b1038f89115b746de49
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="f8107-102">Lync Server 2013 的 SQL Server 資料和記錄檔位置</span><span class="sxs-lookup"><span data-stu-id="f8107-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8107-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="f8107-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f8107-104">期間規劃和部署 Microsoft SQL Server 2012 或 Microsoft SQL Server 2008 R2 SP1 的 Lync Server 2013 前端集區，很重要的考量是效能到的實體硬碟上的資料和記錄檔的位置。</span><span class="sxs-lookup"><span data-stu-id="f8107-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="f8107-105">建議的磁碟組態是實作使用 6 個主軸 RAID 設定為 1 + 0。</span><span class="sxs-lookup"><span data-stu-id="f8107-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="f8107-106">將所有資料庫和記錄檔所使用的前端集區相關聯的伺服器角色和設定使用 Lync Server 的 RAID 磁碟機上的服務 （也就是封存和監控伺服器、 Lync Server 回應群組服務、 Lync Server 通話駐留服務）部署精靈會導致效能良好已測試的組態。</span><span class="sxs-lookup"><span data-stu-id="f8107-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="f8107-107">下表詳述資料庫檔案及其負責內容。</span><span class="sxs-lookup"><span data-stu-id="f8107-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8107-108">如果您的原則和 SQL Server 組態需要更多特定的安裝，資料庫和記錄檔可以安裝到任何預先定義的位置，使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="f8107-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="f8107-109">如需詳細資訊，請參閱<A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">資料庫安裝使用 Lync Server 2013 中的 Lync Server 管理命令介面</A>。</span><span class="sxs-lookup"><span data-stu-id="f8107-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="f8107-110">中央管理存放區的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8107-111">中央管理存放區資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="f8107-112">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="f8107-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8107-113">Xds.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-114">中央管理存放區的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-115">Xds.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-116">維護目前的 Lync Server 2013 拓撲中，設定為拓撲產生器所定義及發行</span><span class="sxs-lookup"><span data-stu-id="f8107-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-117">Lis.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-118">位置資訊服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-119">Lis.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-120">位置資訊服務資料檔案的交易記錄</span><span class="sxs-lookup"><span data-stu-id="f8107-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="f8107-121">使用者、會議及通訊錄的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8107-122">核心 Lync Server 2013 資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="f8107-123">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="f8107-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8107-124">Rtc.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-125">持續性的使用者資料 （例如，存取控制清單 (Acl)，連絡人，排程會議）</span><span class="sxs-lookup"><span data-stu-id="f8107-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-126">Rtc.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-127">Rtc 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-128">Rtcdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-129">維護暫時性的使用者資料 （平台服務執行階段資料）</span><span class="sxs-lookup"><span data-stu-id="f8107-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-130">Rtcdyn.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-131">Rtcdyn 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-132">Rtcab.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-133">即時通訊 (RTC) 通訊錄資料庫是儲存通訊錄服務資訊的 SQL Server 存放庫</span><span class="sxs-lookup"><span data-stu-id="f8107-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-134">Rtcab.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-135">通訊錄服務的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-136">Rtclocal.mdb</span><span class="sxs-lookup"><span data-stu-id="f8107-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="f8107-137">裝載會議目錄</span><span class="sxs-lookup"><span data-stu-id="f8107-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-138">Rtcxds.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-139">維護使用者資料，則備份</span><span class="sxs-lookup"><span data-stu-id="f8107-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-140">Rtcxds.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-141">Rtcxds 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="f8107-142">通話駐留及回應群組的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8107-143">應用程式資料庫</span><span class="sxs-lookup"><span data-stu-id="f8107-143">Application database</span></span></th>
<th><span data-ttu-id="f8107-144">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="f8107-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8107-145">Cpsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-146">通話駐留應用程式的動態資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="f8107-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-147">Cpsdyn.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-148">通話駐留應用程式資料檔案的交易記錄</span><span class="sxs-lookup"><span data-stu-id="f8107-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-149">Rgsconfig.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-150">服務設定的 Lync Server 回應群組服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-151">Rgsconfig.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-152">回應群組應用程式設定的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-153">Rgsdyn.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-154">執行階段作業的回應群組服務資料檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-155">Rgsdyn.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-156">回應群組服務執行階段資料檔案的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="f8107-157">封存和監控伺服器的資料及記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8107-158">封存及監控資料庫檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="f8107-159">資料檔案或記錄檔目的</span><span class="sxs-lookup"><span data-stu-id="f8107-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8107-160">LcsCdr.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-161">詳細通話記錄 (CDR) 程序將監控伺服器的資料存放區</span><span class="sxs-lookup"><span data-stu-id="f8107-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-162">LcsCdr.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-163">詳細通話記錄 (CDR) 資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-164">QoEMetrics.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-165">品質的體驗資料檔案儲存與監控伺服器</span><span class="sxs-lookup"><span data-stu-id="f8107-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-166">QoEMetrics.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-167">監控資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8107-168">Lcslog.mdf</span><span class="sxs-lookup"><span data-stu-id="f8107-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="f8107-169">封存伺服器上的立即訊息和會議資料保留資料檔案</span><span class="sxs-lookup"><span data-stu-id="f8107-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8107-170">Lcslog.ldf</span><span class="sxs-lookup"><span data-stu-id="f8107-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="f8107-171">封存資料的交易記錄檔</span><span class="sxs-lookup"><span data-stu-id="f8107-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f8107-p103">在本主題中，會參考磁碟及 RAID 集。請注意，在 SQL Server 資源的設定中，參考磁碟表示單一硬體裝置。含有兩個分割 (一個分割保留記錄檔，而另一個分割保留資料檔案) 的單一硬碟與兩個磁碟 (各專用於記錄檔或資料檔案) 不同。</span><span class="sxs-lookup"><span data-stu-id="f8107-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="f8107-175">關於 RAID 集，有數個來自不同廠商的不同 RAID 技術。</span><span class="sxs-lookup"><span data-stu-id="f8107-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="f8107-176">而且，隨著存放區域網路 (SAN) 的數量擴增，專用於單一系統的 RAID 集日益罕見。</span><span class="sxs-lookup"><span data-stu-id="f8107-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="f8107-177">您應請洽詢您的 RAID 或 SAN 廠商，以判斷內容的最佳組態為何您磁碟配置時設定 SQL Server 與 Lync Server 2013 的效能。</span><span class="sxs-lookup"><span data-stu-id="f8107-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="f8107-178">也請注意，磁碟機的設計並非完全相同；部分磁碟機的效能可能會優於其他磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f8107-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="f8107-179">因為轉速、硬體快取大小及其他因素，即使是相同製造商的磁碟機，效能也可能不同。</span><span class="sxs-lookup"><span data-stu-id="f8107-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

