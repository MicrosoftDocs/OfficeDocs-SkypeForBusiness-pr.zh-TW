---
title: Lync Server 2013：備份和還原需求：工具和許可權
description: Lync Server 2013：備份和還原需求：工具和許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553462"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="e7c4f-103">Lync Server 2013 中的備份和還原需求：工具和許可權</span><span class="sxs-lookup"><span data-stu-id="e7c4f-103">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7c4f-104">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="e7c4f-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="e7c4f-105">本主題識別您可以用來備份及還原 Lync Server 2013 的工具、所需的許可權，以及您是否可以從遠端或本機執行命令。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-105">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="e7c4f-106">具體而言，本主題著重于 Lync Server 所提供的備份及還原工具。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-106">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="e7c4f-107">備份</span><span class="sxs-lookup"><span data-stu-id="e7c4f-107">Backups</span></span>

<span data-ttu-id="e7c4f-108">若要備份 Lync Server，請使用下表中標出的工具。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-108">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="e7c4f-109">備份 Lync Server 所需的所有命令都可以編寫腳本，而且可以從遠端執行。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-109">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="e7c4f-110">備份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="e7c4f-110">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7c4f-111">若要備份這個：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-111">To back up this:</span></span></th>
<th><span data-ttu-id="e7c4f-112">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-112">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-113">拓撲設定資料 (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-113">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-114">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-114">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-115">位置資訊服務 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-115">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-116">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-116">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-117">回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-117">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-118">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-118">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-119">持久性使用者資料 (Rtcxds 資料庫) </span><span class="sxs-lookup"><span data-stu-id="e7c4f-119">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="e7c4f-120">會議 ID</span><span class="sxs-lookup"><span data-stu-id="e7c4f-120">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-121">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="e7c4f-121">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="e7c4f-122">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-122">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-123">監視詳細通話記錄資料庫 (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-123">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-124">監視 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-124">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e7c4f-125">SQL Server 資料庫工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7c4f-125">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-126">Persistent Chat database (Mgc) </span><span class="sxs-lookup"><span data-stu-id="e7c4f-126">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-127">SQL Server 備份程式或 Export-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-127">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="e7c4f-128">Export-CsPersistentChatData 會將 Persistent Chat 資料當做檔案匯出。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-128">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-129">所有檔案存放區： Lync Server 檔存放區、封存檔存放區</span><span class="sxs-lookup"><span data-stu-id="e7c4f-129">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e7c4f-130"><STRONG>Meeting.Active</STRONG> 檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-130">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="e7c4f-131">會議進行期間會使用這些檔案並予以鎖定。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-131">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="e7c4f-132">標準檔案系統管理工具，如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-132">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="e7c4f-133">恢復</span><span class="sxs-lookup"><span data-stu-id="e7c4f-133">Restoration</span></span>

<span data-ttu-id="e7c4f-134">若要還原 Lync Server，請使用下表中的工具。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-134">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="e7c4f-135">您可以為還原 Lync Server 所需的所有命令編寫腳本。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-135">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="e7c4f-136">有些可以從遠端執行，但其他使用者必須在本機執行，如下表所指定。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-136">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="e7c4f-137">用於還原 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="e7c4f-137">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7c4f-138">若要執行此作業：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-138">To do this:</span></span></th>
<th><span data-ttu-id="e7c4f-139">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-139">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-140">建立全新的電腦</span><span class="sxs-lookup"><span data-stu-id="e7c4f-140">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e7c4f-141">Windows 作業系統安裝軟體</span><span class="sxs-lookup"><span data-stu-id="e7c4f-141">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-142">SQL Server 安裝軟體</span><span class="sxs-lookup"><span data-stu-id="e7c4f-142">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-143">如果以可匯出的私密金鑰來還原憑證，則請認證 Microsoft Management Console (MMC) 嵌入式管理單元</span><span class="sxs-lookup"><span data-stu-id="e7c4f-143">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-144">還原檔案存放區資料</span><span class="sxs-lookup"><span data-stu-id="e7c4f-144">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-145">標準檔案系統管理工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="e7c4f-145">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-146">重新建立空的資料庫，並設定下列的權限：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-146">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e7c4f-147">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="e7c4f-147">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-148">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="e7c4f-148">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-149">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="e7c4f-149">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-150">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="e7c4f-150">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e7c4f-151">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="e7c4f-151">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-152">將 Active Directory 網域服務指標還原至中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="e7c4f-152">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e7c4f-153">如果您在任何時候遺失服務連線點，都可以重新執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-153">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="e7c4f-154">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e7c4f-154">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-155">將拓撲、原則及設定，匯入中央管理存放區 (Xds) </span><span class="sxs-lookup"><span data-stu-id="e7c4f-155">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-156">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-156">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-157">發行及啟用拓撲</span><span class="sxs-lookup"><span data-stu-id="e7c4f-157">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-158">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="e7c4f-158">Topology Builder</span></span></p>
<p><span data-ttu-id="e7c4f-159">- 或 -</span><span class="sxs-lookup"><span data-stu-id="e7c4f-159">-or-</span></span></p>
<p><span data-ttu-id="e7c4f-160">Publish-CsTopology 和 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="e7c4f-160">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-161">啟用上次發行的拓撲</span><span class="sxs-lookup"><span data-stu-id="e7c4f-161">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-162">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="e7c4f-162">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-163">重新安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="e7c4f-163">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-164">Lync Server 安裝程式</span><span class="sxs-lookup"><span data-stu-id="e7c4f-164">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e7c4f-165">位於 \setup\amd64\Setup.exe 的 Lync Server 安裝資料夾或媒體中。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-165">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-166">還原位置資訊 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-166">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-167">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-167">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-168">還原持續使用者資料 (Rtcxds) </span><span class="sxs-lookup"><span data-stu-id="e7c4f-168">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-169">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="e7c4f-169">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-170">還原回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-170">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-171">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c4f-171">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e7c4f-172">若要在新部署的集區中還原設定，而該集區中沒有資料庫的回應群組資料，您應該使用– OverwriteOwner 選項。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-172">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="e7c4f-173">您可以使用此選項，即使還原的資料位於具有相同完整功能變數名稱的集區中 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-173">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="e7c4f-174">否則，由於連絡人物件已存在於 Active Directory 中的回應群組，所以匯入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-174">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7c4f-175">還原下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="e7c4f-175">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="e7c4f-176">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-176">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="e7c4f-177">監視資料庫：詳細通話記錄資料庫 (LcsCDR.mdf) 及 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="e7c4f-177">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e7c4f-178">SQL Server 資料庫管理工具</span><span class="sxs-lookup"><span data-stu-id="e7c4f-178">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7c4f-179">Persistent Chat database (Mgs) </span><span class="sxs-lookup"><span data-stu-id="e7c4f-179">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e7c4f-180">SQL Server 還原程式或 Import-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-180">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="e7c4f-181">您可以使用 Import-CsPersistentChatData 與 Export-CsPersistentChatData 建立的檔案，然後將資料匯入至 Persistent Chat database。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-181">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="e7c4f-182">必要權限</span><span class="sxs-lookup"><span data-stu-id="e7c4f-182">Required Permissions</span></span>

<span data-ttu-id="e7c4f-183">使用者必須是 **RTCUniversalServerAdmins** 群組的成員，才可執行本主題中所述的所有命令。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-183">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="e7c4f-184">大多數備份及還原命令不支援以角色為基礎的存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-184">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="e7c4f-185">有兩個例外狀況是 Persistent Chat Cmdlet Export-CsPersistentChatData 和 Import-CsPersistentChatData，必須由 CsPersistentChatAdministrator 群組成員的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-185">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="e7c4f-186">若要執行 Lync Server 部署嚮導，使用者還必須是本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e7c4f-186">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

