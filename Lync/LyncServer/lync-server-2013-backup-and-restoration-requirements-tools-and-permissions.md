---
title: Lync Server 2013：備份和還原需求：工具和許可權
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
ms.openlocfilehash: 96eee88d6055d7a66d858dc5c6324a2592616ceb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532640"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="3a38e-102">Lync Server 2013 中的備份和還原需求：工具和許可權</span><span class="sxs-lookup"><span data-stu-id="3a38e-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a38e-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="3a38e-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="3a38e-104">本主題識別您可以用來備份及還原 Lync Server 2013 的工具、所需的許可權，以及您是否可以從遠端或本機執行命令。</span><span class="sxs-lookup"><span data-stu-id="3a38e-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="3a38e-105">具體而言，本主題著重于 Lync Server 所提供的備份及還原工具。</span><span class="sxs-lookup"><span data-stu-id="3a38e-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="3a38e-106">備份</span><span class="sxs-lookup"><span data-stu-id="3a38e-106">Backups</span></span>

<span data-ttu-id="3a38e-107">若要備份 Lync Server，請使用下表中標出的工具。</span><span class="sxs-lookup"><span data-stu-id="3a38e-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="3a38e-108">備份 Lync Server 所需的所有命令都可以編寫腳本，而且可以從遠端執行。</span><span class="sxs-lookup"><span data-stu-id="3a38e-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="3a38e-109">備份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="3a38e-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a38e-110">若要備份這個：</span><span class="sxs-lookup"><span data-stu-id="3a38e-110">To back up this:</span></span></th>
<th><span data-ttu-id="3a38e-111">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3a38e-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-112">拓撲設定資料 (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-114">位置資訊服務 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-116">回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-118">持久性使用者資料 (Rtcxds 資料庫) </span><span class="sxs-lookup"><span data-stu-id="3a38e-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="3a38e-119">會議 ID</span><span class="sxs-lookup"><span data-stu-id="3a38e-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="3a38e-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="3a38e-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="3a38e-121">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="3a38e-122">監視詳細通話記錄資料庫 (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="3a38e-123">監視 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3a38e-124">SQL Server 資料庫工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3a38e-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-125">Persistent Chat database (Mgc) </span><span class="sxs-lookup"><span data-stu-id="3a38e-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-126">SQL Server 備份程式或 Export-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="3a38e-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="3a38e-127">Export-CsPersistentChatData 會將 Persistent Chat 資料當做檔案匯出。</span><span class="sxs-lookup"><span data-stu-id="3a38e-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-128">所有檔案存放區： Lync Server 檔存放區、封存檔存放區</span><span class="sxs-lookup"><span data-stu-id="3a38e-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a38e-129"><STRONG>Meeting.Active</STRONG> 檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="3a38e-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="3a38e-130">會議進行期間會使用這些檔案並予以鎖定。</span><span class="sxs-lookup"><span data-stu-id="3a38e-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="3a38e-131">標準檔案系統管理工具，如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="3a38e-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="3a38e-132">恢復</span><span class="sxs-lookup"><span data-stu-id="3a38e-132">Restoration</span></span>

<span data-ttu-id="3a38e-133">若要還原 Lync Server，請使用下表中的工具。</span><span class="sxs-lookup"><span data-stu-id="3a38e-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="3a38e-134">您可以為還原 Lync Server 所需的所有命令編寫腳本。</span><span class="sxs-lookup"><span data-stu-id="3a38e-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="3a38e-135">有些可以從遠端執行，但其他使用者必須在本機執行，如下表所指定。</span><span class="sxs-lookup"><span data-stu-id="3a38e-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="3a38e-136">用於還原 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="3a38e-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a38e-137">若要執行此作業：</span><span class="sxs-lookup"><span data-stu-id="3a38e-137">To do this:</span></span></th>
<th><span data-ttu-id="3a38e-138">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3a38e-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-139">建立全新的電腦</span><span class="sxs-lookup"><span data-stu-id="3a38e-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3a38e-140">Windows 作業系統安裝軟體</span><span class="sxs-lookup"><span data-stu-id="3a38e-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="3a38e-141">SQL Server 安裝軟體</span><span class="sxs-lookup"><span data-stu-id="3a38e-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="3a38e-142">如果以可匯出的私密金鑰來還原憑證，則請認證 Microsoft Management Console (MMC) 嵌入式管理單元</span><span class="sxs-lookup"><span data-stu-id="3a38e-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-143">還原檔案存放區資料</span><span class="sxs-lookup"><span data-stu-id="3a38e-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="3a38e-144">標準檔案系統管理工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="3a38e-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-145">重新建立空的資料庫，並設定下列的權限：</span><span class="sxs-lookup"><span data-stu-id="3a38e-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a38e-146">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="3a38e-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="3a38e-147">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="3a38e-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="3a38e-148">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="3a38e-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="3a38e-149">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="3a38e-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3a38e-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="3a38e-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-151">將 Active Directory 網域服務指標還原至中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="3a38e-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a38e-152">如果您在任何時候遺失服務連線點，都可以重新執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a38e-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="3a38e-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3a38e-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-154">將拓撲、原則及設定，匯入中央管理存放區 (Xds) </span><span class="sxs-lookup"><span data-stu-id="3a38e-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-155">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-156">發行及啟用拓撲</span><span class="sxs-lookup"><span data-stu-id="3a38e-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="3a38e-157">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="3a38e-157">Topology Builder</span></span></p>
<p><span data-ttu-id="3a38e-158">- 或 -</span><span class="sxs-lookup"><span data-stu-id="3a38e-158">-or-</span></span></p>
<p><span data-ttu-id="3a38e-159">Publish-CsTopology 和 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="3a38e-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-160">啟用上次發行的拓撲</span><span class="sxs-lookup"><span data-stu-id="3a38e-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="3a38e-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="3a38e-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-162">重新安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="3a38e-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="3a38e-163">Lync Server 安裝程式</span><span class="sxs-lookup"><span data-stu-id="3a38e-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a38e-164">位於 \setup\amd64\Setup.exe 的 Lync Server 安裝資料夾或媒體中。</span><span class="sxs-lookup"><span data-stu-id="3a38e-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-165">還原位置資訊 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-166">Import-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-167">還原持續使用者資料 (Rtcxds) </span><span class="sxs-lookup"><span data-stu-id="3a38e-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-168">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="3a38e-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-169">還原回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-170">Import-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a38e-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3a38e-171">若要在新部署的集區中還原設定，而該集區中沒有資料庫的回應群組資料，您應該使用– OverwriteOwner 選項。</span><span class="sxs-lookup"><span data-stu-id="3a38e-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="3a38e-172">您可以使用此選項，即使還原的資料位於具有相同完整功能變數名稱的集區中 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="3a38e-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="3a38e-173">否則，由於連絡人物件已存在於 Active Directory 中的回應群組，所以匯入將會失敗。</span><span class="sxs-lookup"><span data-stu-id="3a38e-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a38e-174">還原下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="3a38e-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a38e-175">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="3a38e-176">監視資料庫：詳細通話記錄資料庫 (LcsCDR.mdf) 及 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="3a38e-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3a38e-177">SQL Server 資料庫管理工具</span><span class="sxs-lookup"><span data-stu-id="3a38e-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a38e-178">Persistent Chat database (Mgs) </span><span class="sxs-lookup"><span data-stu-id="3a38e-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="3a38e-179">SQL Server 還原程式或 Import-CsPersistentChatData。</span><span class="sxs-lookup"><span data-stu-id="3a38e-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="3a38e-180">您可以使用 Import-CsPersistentChatData 與 Export-CsPersistentChatData 建立的檔案，然後將資料匯入至 Persistent Chat database。</span><span class="sxs-lookup"><span data-stu-id="3a38e-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="3a38e-181">必要權限</span><span class="sxs-lookup"><span data-stu-id="3a38e-181">Required Permissions</span></span>

<span data-ttu-id="3a38e-182">使用者必須是 **RTCUniversalServerAdmins** 群組的成員，才可執行本主題中所述的所有命令。</span><span class="sxs-lookup"><span data-stu-id="3a38e-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="3a38e-183">大多數備份及還原命令不支援以角色為基礎的存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="3a38e-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="3a38e-184">有兩個例外狀況是 Persistent Chat Cmdlet Export-CsPersistentChatData 和 Import-CsPersistentChatData，必須由 CsPersistentChatAdministrator 群組成員的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="3a38e-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="3a38e-185">若要執行 Lync Server 部署嚮導，使用者還必須是本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3a38e-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

