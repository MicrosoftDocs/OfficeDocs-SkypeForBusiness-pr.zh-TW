---
title: Lync Server 2013：備份和還原工作表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="4f56c-102">Lync Server 2013 的備份和還原工作表</span><span class="sxs-lookup"><span data-stu-id="4f56c-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f56c-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4f56c-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4f56c-104">貴組織的備份和還原方案應包含有關如何以及何時備份資料和設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="4f56c-105">您可以使用這裡提供的工作表，協助您針對特定的部署以及貴組織的備份與還原需求來記錄此資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="4f56c-106">使用下欄工作表記錄備份及還原 Lync Server pool 或 Standard Edition 伺服器的資料庫、檔案儲存區及設定資訊所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="4f56c-107">將這些工作表的一或多個複本保留在安全的位置，以便在您需要還原 Lync Server 時能隨時存取。</span><span class="sxs-lookup"><span data-stu-id="4f56c-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f56c-108">本節中的工作表只涵蓋還原 Lync Server 資料庫和伺服器的資料和設定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="4f56c-109">如果您需要記錄其他還原資訊（例如重新安裝作業系統及其他軟體的資訊），請使用貴組織的部署方案和備份和還原方案來解決這些需求。</span><span class="sxs-lookup"><span data-stu-id="4f56c-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="4f56c-110">資料庫備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="4f56c-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4f56c-111">使用下表來記錄備份和還原 Lync Server 資料庫所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="4f56c-112">備份與還原的資料庫資訊</span><span class="sxs-lookup"><span data-stu-id="4f56c-112">Database Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f56c-113">資料</span><span class="sxs-lookup"><span data-stu-id="4f56c-113">Database</span></span></th>
<th><span data-ttu-id="4f56c-114">伺服器名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="4f56c-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4f56c-115">備份排程</span><span class="sxs-lookup"><span data-stu-id="4f56c-115">Backup schedule</span></span></th>
<th><span data-ttu-id="4f56c-116">資料庫備份工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-116">Database backup tool</span></span></th>
<th><span data-ttu-id="4f56c-117">備份組</span><span class="sxs-lookup"><span data-stu-id="4f56c-117">Backup set</span></span></th>
<th><span data-ttu-id="4f56c-118">備份目的地</span><span class="sxs-lookup"><span data-stu-id="4f56c-118">Backup destination</span></span></th>
<th><span data-ttu-id="4f56c-119">筆記</span><span class="sxs-lookup"><span data-stu-id="4f56c-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-120">後端伺服器上使用者資料的 Rtc 資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4f56c-121"><strong>Export-CsUserData</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f56c-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4f56c-122">列名</span><span class="sxs-lookup"><span data-stu-id="4f56c-122">Name:</span></span></p>
<p><span data-ttu-id="4f56c-123">保修期</span><span class="sxs-lookup"><span data-stu-id="4f56c-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f56c-124">封存資料庫伺服器上的 LcsLog （預設名稱）資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f56c-125">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4f56c-126">列名</span><span class="sxs-lookup"><span data-stu-id="4f56c-126">Name:</span></span></p>
<p><span data-ttu-id="4f56c-127">保修期</span><span class="sxs-lookup"><span data-stu-id="4f56c-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-128">針對通話詳細資料記錄（CDRs）監控資料庫伺服器上的 LcsCdr 資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f56c-129">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4f56c-130">列名</span><span class="sxs-lookup"><span data-stu-id="4f56c-130">Name:</span></span></p>
<p><span data-ttu-id="4f56c-131">保修期</span><span class="sxs-lookup"><span data-stu-id="4f56c-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f56c-132">監視資料庫伺服器上的 QoEMetrics 資料庫，以獲得經驗（QoE）資料的品質</span><span class="sxs-lookup"><span data-stu-id="4f56c-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f56c-133">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="4f56c-134">列名</span><span class="sxs-lookup"><span data-stu-id="4f56c-134">Name:</span></span></p>
<p><span data-ttu-id="4f56c-135">保修期</span><span class="sxs-lookup"><span data-stu-id="4f56c-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-136">持續聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4f56c-137">SQL Server 管理工具或<strong>Export CsPersistentChatData</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f56c-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="4f56c-138">列名</span><span class="sxs-lookup"><span data-stu-id="4f56c-138">Name:</span></span></p>
<p><span data-ttu-id="4f56c-139">保修期</span><span class="sxs-lookup"><span data-stu-id="4f56c-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f56c-140">下列資料庫不需要備份或還原：</span><span class="sxs-lookup"><span data-stu-id="4f56c-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="4f56c-141">Rtcdyn.</span><span class="sxs-lookup"><span data-stu-id="4f56c-141">Rtcdyn.</span></span> <span data-ttu-id="4f56c-142">還原服務時，不需要此資料庫中的暫時性使用者資料。</span><span class="sxs-lookup"><span data-stu-id="4f56c-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4f56c-143">Rtcab.</span><span class="sxs-lookup"><span data-stu-id="4f56c-143">Rtcab.</span></span> <span data-ttu-id="4f56c-144">通訊錄資料庫會自動從 Active Directory 網域服務中的全域通訊清單（GAL）重新建立。</span><span class="sxs-lookup"><span data-stu-id="4f56c-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4f56c-145">Rgsdyn.</span><span class="sxs-lookup"><span data-stu-id="4f56c-145">Rgsdyn.</span></span> <span data-ttu-id="4f56c-146">還原服務時，不需要此資料庫中的暫時性回應群組服務資料。</span><span class="sxs-lookup"><span data-stu-id="4f56c-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4f56c-147">Cpsdyn.</span><span class="sxs-lookup"><span data-stu-id="4f56c-147">Cpsdyn.</span></span> <span data-ttu-id="4f56c-148">不需要通話駐留應用程式的動態資訊，就能還原服務。</span><span class="sxs-lookup"><span data-stu-id="4f56c-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="4f56c-149">MgcComp.</span><span class="sxs-lookup"><span data-stu-id="4f56c-149">MgcComp.</span></span> <span data-ttu-id="4f56c-150">還原服務不需要適用于持續聊天的合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="4f56c-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="4f56c-151">檔案儲存備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="4f56c-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4f56c-152">使用下表來記錄備份及還原檔案存放區所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="4f56c-153">檔案存放區包含諸如會議內容中繼資料、會議合規性記錄、裝置更新的更新記錄，以及回應群組、通話駐留及宣告應用程式的音訊檔案等資料。</span><span class="sxs-lookup"><span data-stu-id="4f56c-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="4f56c-154">備份與還原的檔案儲存資訊</span><span class="sxs-lookup"><span data-stu-id="4f56c-154">File Store Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f56c-155">內容</span><span class="sxs-lookup"><span data-stu-id="4f56c-155">Content</span></span></th>
<th><span data-ttu-id="4f56c-156">伺服器名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="4f56c-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4f56c-157">備份排程</span><span class="sxs-lookup"><span data-stu-id="4f56c-157">Backup schedule</span></span></th>
<th><span data-ttu-id="4f56c-158">檔案系統備份工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-158">File system backup tool</span></span></th>
<th><span data-ttu-id="4f56c-159">要備份的檔案共用 \*</span><span class="sxs-lookup"><span data-stu-id="4f56c-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="4f56c-160">備份目的地</span><span class="sxs-lookup"><span data-stu-id="4f56c-160">Backup destination</span></span></th>
<th><span data-ttu-id="4f56c-161">筆記</span><span class="sxs-lookup"><span data-stu-id="4f56c-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-162">Lync Server 檔存放區</span><span class="sxs-lookup"><span data-stu-id="4f56c-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="4f56c-163">標準備份工具，例如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="4f56c-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="4f56c-164">在企業版的檔案伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4f56c-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="4f56c-165">根據預設，在標準版版本中，針對標準版部署。</span><span class="sxs-lookup"><span data-stu-id="4f56c-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="4f56c-166">通常是每個網站一個。</span><span class="sxs-lookup"><span data-stu-id="4f56c-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4f56c-167">名為「<strong>會議」的</strong>檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="4f56c-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="4f56c-168">這些檔案正在使用中，且在會議進行時被封鎖。</span><span class="sxs-lookup"><span data-stu-id="4f56c-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="4f56c-169">設定備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="4f56c-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="4f56c-170">使用下表來記錄備份和還原設定所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="4f56c-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="4f56c-171">備份與還原的設定資訊</span><span class="sxs-lookup"><span data-stu-id="4f56c-171">Settings Information for Backup and Restoration</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f56c-172">資料</span><span class="sxs-lookup"><span data-stu-id="4f56c-172">Database</span></span></th>
<th><span data-ttu-id="4f56c-173">伺服器名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="4f56c-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="4f56c-174">備份排程</span><span class="sxs-lookup"><span data-stu-id="4f56c-174">Backup schedule</span></span></th>
<th><span data-ttu-id="4f56c-175">備份工具</span><span class="sxs-lookup"><span data-stu-id="4f56c-175">Backup tool</span></span></th>
<th><span data-ttu-id="4f56c-176">設定檔（.xml）名稱</span><span class="sxs-lookup"><span data-stu-id="4f56c-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="4f56c-177">備份位置</span><span class="sxs-lookup"><span data-stu-id="4f56c-177">Backup location</span></span></th>
<th><span data-ttu-id="4f56c-178">筆記</span><span class="sxs-lookup"><span data-stu-id="4f56c-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-179">在 [中央管理] 存放區中，Xds [拓撲設定（全域）] 的資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="4f56c-180"><strong>Export-CsConfiguration</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f56c-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f56c-181">E9-1-1-1 位置資訊（全域）的 [中央管理] 存放區中的 iis 資料庫</span><span class="sxs-lookup"><span data-stu-id="4f56c-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f56c-182"><strong>Export-CsLisConfiguration</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f56c-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f56c-183">在後端伺服器上 RgsConfig 資料庫以取得回應群組設定（pool）</span><span class="sxs-lookup"><span data-stu-id="4f56c-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f56c-184"><strong>Export-CsRgsConfiguration</strong> Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f56c-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

