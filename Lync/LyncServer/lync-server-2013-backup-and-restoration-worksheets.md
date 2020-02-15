---
title: Lync Server 2013： 備份和還原工作表
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
ms.openlocfilehash: 7f767a2c94e797ab43e3b5ace6b553b05bafd81f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a><span data-ttu-id="0e773-102">Lync Server 2013 的備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="0e773-102">Backup and restoration worksheets for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e773-103">_**上次修改主題：** 2013年-02-18_</span><span class="sxs-lookup"><span data-stu-id="0e773-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="0e773-104">貴組織的備份及還原計劃應該包含有關如何及何時您備份資料和設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-104">The backup and restoration plan for your organization should contain details about how and when you back up data and settings.</span></span> <span data-ttu-id="0e773-105">您可以使用此處可協助您和貴組織的備份和還原需求的特定部署此資訊的文件工作表。</span><span class="sxs-lookup"><span data-stu-id="0e773-105">You can use the worksheets presented here to help you document this information for your specific deployment and for your organization's backup and restoration requirements.</span></span>

<span data-ttu-id="0e773-106">使用下列工作表來記錄您要備份及還原資料庫、 檔案存放區，以及 Lync 伺服器集區或 Standard Edition server 的設定資訊的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-106">Use the following worksheets to record the information that you need to back up and restore database, File Store, and settings information for a Lync Server pool or Standard Edition server.</span></span> <span data-ttu-id="0e773-107">保留這些工作表的一或多個份安全的位置，以便它們是如果您需要還原 Lync Server 隨時都能存取。</span><span class="sxs-lookup"><span data-stu-id="0e773-107">Keep one or more copies of these worksheets in a secure location so that they are readily accessible if you need to restore Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e773-108">本節中的工作表涵蓋只需要還原資料和設定 Lync Server 資料庫和伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-108">The worksheets in this section cover only the information that is required to restore the data and settings of Lync Server databases and servers.</span></span> <span data-ttu-id="0e773-109">如果您需要其他還原資訊，例如重新安裝作業系統和其他軟體的資訊的文件使用您的組織部署計劃與備份和還原計劃來解決這些需求。</span><span class="sxs-lookup"><span data-stu-id="0e773-109">If you need to document other restoration information, such as the information for reinstalling operating systems and other software, use your organization's deployment plans and backup and restoration plans to address those requirements.</span></span>



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a><span data-ttu-id="0e773-110">資料庫備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="0e773-110">Database Backup and Restoration Worksheet</span></span>

<span data-ttu-id="0e773-111">使用下表來記錄您要備份及還原 Lync Server 資料庫的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-111">Use the following table to record the information that you need to back up and restore Lync Server databases.</span></span>

### <a name="database-information-for-backup-and-restoration"></a><span data-ttu-id="0e773-112">備份及還原的資料庫資訊</span><span class="sxs-lookup"><span data-stu-id="0e773-112">Database Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="0e773-113">Database</span><span class="sxs-lookup"><span data-stu-id="0e773-113">Database</span></span></th>
<th><span data-ttu-id="0e773-114">伺服器名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0e773-114">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="0e773-115">備份排程</span><span class="sxs-lookup"><span data-stu-id="0e773-115">Backup schedule</span></span></th>
<th><span data-ttu-id="0e773-116">資料庫備份工具</span><span class="sxs-lookup"><span data-stu-id="0e773-116">Database backup tool</span></span></th>
<th><span data-ttu-id="0e773-117">備份組</span><span class="sxs-lookup"><span data-stu-id="0e773-117">Backup set</span></span></th>
<th><span data-ttu-id="0e773-118">備份目的地</span><span class="sxs-lookup"><span data-stu-id="0e773-118">Backup destination</span></span></th>
<th><span data-ttu-id="0e773-119">附註</span><span class="sxs-lookup"><span data-stu-id="0e773-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e773-120">在後端伺服器上的 Rtc 資料庫的使用者資料</span><span class="sxs-lookup"><span data-stu-id="0e773-120">Rtc database on Back End Server for user data</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="0e773-121"><strong>Export-csuserdata</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e773-121"><strong>Export-CsUserData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="0e773-122">名稱：</span><span class="sxs-lookup"><span data-stu-id="0e773-122">Name:</span></span></p>
<p><span data-ttu-id="0e773-123">到期日：</span><span class="sxs-lookup"><span data-stu-id="0e773-123">Expiration:</span></span></p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e773-124">封存資料庫伺服器上的 LcsLog （預設名稱） 資料庫</span><span class="sxs-lookup"><span data-stu-id="0e773-124">LcsLog (default name) database on Archiving database server</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e773-125">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="0e773-125">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="0e773-126">名稱：</span><span class="sxs-lookup"><span data-stu-id="0e773-126">Name:</span></span></p>
<p><span data-ttu-id="0e773-127">到期日：</span><span class="sxs-lookup"><span data-stu-id="0e773-127">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e773-128">詳細通話記錄 (Cdr) 的監控資料庫伺服器上的 LcsCdr 資料庫</span><span class="sxs-lookup"><span data-stu-id="0e773-128">LcsCdr database on Monitoring database server for call detail records (CDRs)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e773-129">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="0e773-129">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="0e773-130">名稱：</span><span class="sxs-lookup"><span data-stu-id="0e773-130">Name:</span></span></p>
<p><span data-ttu-id="0e773-131">到期日：</span><span class="sxs-lookup"><span data-stu-id="0e773-131">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e773-132">經驗品質 (QoE) 資料的監控資料庫伺服器上的 QoEMetrics 資料庫</span><span class="sxs-lookup"><span data-stu-id="0e773-132">QoEMetrics database on Monitoring database server for Quality of Experience (QoE) data</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e773-133">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="0e773-133">SQL Server management tool</span></span></p></td>
<td><p><span data-ttu-id="0e773-134">名稱：</span><span class="sxs-lookup"><span data-stu-id="0e773-134">Name:</span></span></p>
<p><span data-ttu-id="0e773-135">到期日：</span><span class="sxs-lookup"><span data-stu-id="0e773-135">Expiration:</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e773-136">常設聊天室資料庫</span><span class="sxs-lookup"><span data-stu-id="0e773-136">Persistent Chat Database</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="0e773-137">SQL Server 管理工具或<strong>Export-cspersistentchatdata</strong>指令程式</span><span class="sxs-lookup"><span data-stu-id="0e773-137">SQL Server management tool or <strong>Export-CsPersistentChatData</strong> cmdlet</span></span></p></td>
<td><p><span data-ttu-id="0e773-138">名稱：</span><span class="sxs-lookup"><span data-stu-id="0e773-138">Name:</span></span></p>
<p><span data-ttu-id="0e773-139">到期日：</span><span class="sxs-lookup"><span data-stu-id="0e773-139">Expiration:</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e773-140">沒有任何備份或還原是必要的下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="0e773-140">No backup or restoration is required of the following databases:</span></span>

  - <span data-ttu-id="0e773-141">Rtcdyn。</span><span class="sxs-lookup"><span data-stu-id="0e773-141">Rtcdyn.</span></span> <span data-ttu-id="0e773-142">此資料庫中的暫時性的使用者資料不必要的服務還原。</span><span class="sxs-lookup"><span data-stu-id="0e773-142">The transient user data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="0e773-143">Rtcab。</span><span class="sxs-lookup"><span data-stu-id="0e773-143">Rtcab.</span></span> <span data-ttu-id="0e773-144">通訊錄資料庫會自動重新建立從全域通訊清單 (GAL) 在 Active Directory 網域服務中。</span><span class="sxs-lookup"><span data-stu-id="0e773-144">The Address Book database is automatically recreated from the Global Address List (GAL) in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="0e773-145">Rgsdyn。</span><span class="sxs-lookup"><span data-stu-id="0e773-145">Rgsdyn.</span></span> <span data-ttu-id="0e773-146">暫時性的回應群組服務資料，此資料庫中不需要的服務還原。</span><span class="sxs-lookup"><span data-stu-id="0e773-146">The transient Response Group service data in this database is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="0e773-147">Cpsdyn。</span><span class="sxs-lookup"><span data-stu-id="0e773-147">Cpsdyn.</span></span> <span data-ttu-id="0e773-148">通話駐留應用程式的動態資訊不必要的服務還原。</span><span class="sxs-lookup"><span data-stu-id="0e773-148">The dynamic information for the Call Park application is not necessary for restoration of service.</span></span>

  - <span data-ttu-id="0e773-149">MgcComp。</span><span class="sxs-lookup"><span data-stu-id="0e773-149">MgcComp.</span></span> <span data-ttu-id="0e773-150">常設聊天室規範資料庫不是服務的必要還原。</span><span class="sxs-lookup"><span data-stu-id="0e773-150">The compliance database for Persistent Chat is not necessary for restoration of service.</span></span>

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a><span data-ttu-id="0e773-151">檔案存放區備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="0e773-151">File Store Backup and Restoration Worksheet</span></span>

<span data-ttu-id="0e773-152">使用下表來記錄您要備份及還原檔案存放區的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-152">Use the following table to record the information that you need to back up and restore the File Stores.</span></span> <span data-ttu-id="0e773-153">檔案存放區包含資料，例如會議內容的中繼資料、 會議規範記錄，更新的裝置更新記錄和回應群組，通話駐留以及宣告應用程式的音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="0e773-153">File Stores contain data such as meeting content metadata, meeting compliance logs, update logs for device updates, and audio files for the Response Group, Call Park, and Announcement applications.</span></span>

### <a name="file-store-information-for-backup-and-restoration"></a><span data-ttu-id="0e773-154">用於備份及還原檔案存放區資訊</span><span class="sxs-lookup"><span data-stu-id="0e773-154">File Store Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="0e773-155">內容</span><span class="sxs-lookup"><span data-stu-id="0e773-155">Content</span></span></th>
<th><span data-ttu-id="0e773-156">伺服器名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0e773-156">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="0e773-157">備份排程</span><span class="sxs-lookup"><span data-stu-id="0e773-157">Backup schedule</span></span></th>
<th><span data-ttu-id="0e773-158">檔案系統備份工具</span><span class="sxs-lookup"><span data-stu-id="0e773-158">File system backup tool</span></span></th>
<th><span data-ttu-id="0e773-159">要備份的檔案共用 \*</span><span class="sxs-lookup"><span data-stu-id="0e773-159">File share to be backed up \*</span></span></th>
<th><span data-ttu-id="0e773-160">備份目的地</span><span class="sxs-lookup"><span data-stu-id="0e773-160">Backup destination</span></span></th>
<th><span data-ttu-id="0e773-161">附註</span><span class="sxs-lookup"><span data-stu-id="0e773-161">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e773-162">Lync Server 檔案存放區</span><span class="sxs-lookup"><span data-stu-id="0e773-162">Lync Server File Store</span></span></p></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="0e773-163">標準備份工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="0e773-163">Standard backup tool, such as Robocopy</span></span></p></td>
<td><p><span data-ttu-id="0e773-164">檔案在伺服器上的 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="0e773-164">On file server for Enterprise Edition.</span></span> <span data-ttu-id="0e773-165">在 Standard Edition，根據預設，Standard Edition 部署。</span><span class="sxs-lookup"><span data-stu-id="0e773-165">On Standard Edition by default, for Standard Edition deployment.</span></span> <span data-ttu-id="0e773-166">一般而言，其中每個網站。</span><span class="sxs-lookup"><span data-stu-id="0e773-166">Typically, one per site.</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e773-167"><strong>Meeting.Active</strong> 檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="0e773-167">Files named <strong>Meeting.Active</strong> should not be backed up.</span></span> <span data-ttu-id="0e773-168">這些檔案都在使用中，會議份都會被鎖定。</span><span class="sxs-lookup"><span data-stu-id="0e773-168">These files are in use and are locked while a meeting takes place.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a><span data-ttu-id="0e773-169">設定備份及還原工作表</span><span class="sxs-lookup"><span data-stu-id="0e773-169">Settings Backup and Restoration Worksheet</span></span>

<span data-ttu-id="0e773-170">使用下表來記錄您要備份及還原設定的資訊。</span><span class="sxs-lookup"><span data-stu-id="0e773-170">Use the following table to record the information that you need to back up and restore settings.</span></span>

### <a name="settings-information-for-backup-and-restoration"></a><span data-ttu-id="0e773-171">用於備份及還原的設定資訊</span><span class="sxs-lookup"><span data-stu-id="0e773-171">Settings Information for Backup and Restoration</span></span>

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
<th><span data-ttu-id="0e773-172">Database</span><span class="sxs-lookup"><span data-stu-id="0e773-172">Database</span></span></th>
<th><span data-ttu-id="0e773-173">伺服器名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0e773-173">Server name (FQDN)</span></span></th>
<th><span data-ttu-id="0e773-174">備份排程</span><span class="sxs-lookup"><span data-stu-id="0e773-174">Backup schedule</span></span></th>
<th><span data-ttu-id="0e773-175">備份工具</span><span class="sxs-lookup"><span data-stu-id="0e773-175">Backup tool</span></span></th>
<th><span data-ttu-id="0e773-176">設定檔案 (.xml) 名稱</span><span class="sxs-lookup"><span data-stu-id="0e773-176">Configuration file (.xml) name</span></span></th>
<th><span data-ttu-id="0e773-177">備份位置</span><span class="sxs-lookup"><span data-stu-id="0e773-177">Backup location</span></span></th>
<th><span data-ttu-id="0e773-178">附註</span><span class="sxs-lookup"><span data-stu-id="0e773-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e773-179">Xds 資料庫在中央管理存放區的拓撲設定 （全域）</span><span class="sxs-lookup"><span data-stu-id="0e773-179">Xds database in Central Management store for topology configuration (global)</span></span></p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><span data-ttu-id="0e773-180"><strong>Export-csconfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e773-180"><strong>Export-CsConfiguration</strong> cmdlet</span></span></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e773-181">Lis 資料庫在中央管理存放區的 E9-1-1 位置資訊 （全域）</span><span class="sxs-lookup"><span data-stu-id="0e773-181">Lis database in Central Management store for E9-1-1 location information (global)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e773-182"><strong>Export-cslisconfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e773-182"><strong>Export-CsLisConfiguration</strong> cmdlet</span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e773-183">在後端伺服器上的 RgsConfig 資料庫回應群組設定 （集區）</span><span class="sxs-lookup"><span data-stu-id="0e773-183">RgsConfig database on Back End Server for Response Group configuration (pool)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e773-184"><strong>Export-csrgsconfiguration</strong> cmdlet</span><span class="sxs-lookup"><span data-stu-id="0e773-184"><strong>Export-CsRgsConfiguration</strong> cmdlet</span></span></p></td>
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

