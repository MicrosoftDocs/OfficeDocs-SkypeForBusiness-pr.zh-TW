---
title: Lync Server 2013： 備份和還原需求： 工具和權限
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
ms.openlocfilehash: 900421ed081d5fb8e37fb6b23ddbb80dc85963eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="c4164-102">Lync Server 2013 中的備份和還原需求： 工具和權限</span><span class="sxs-lookup"><span data-stu-id="c4164-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4164-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="c4164-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="c4164-104">本主題會識別的工具，您可用於備份及還原 Lync Server 2013 中，您需要的權限，是否可以執行命令從遠端還是在本機。</span><span class="sxs-lookup"><span data-stu-id="c4164-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="c4164-105">具體而言，本主題著重於隨附的備份和還原 Lync Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="c4164-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="c4164-106">備份</span><span class="sxs-lookup"><span data-stu-id="c4164-106">Backups</span></span>

<span data-ttu-id="c4164-107">若要備份 Lync Server，請使用下表中所識別的工具。</span><span class="sxs-lookup"><span data-stu-id="c4164-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="c4164-108">您必須備份 Lync Server 的所有命令可以寫成指令碼，且可以從遠端執行。</span><span class="sxs-lookup"><span data-stu-id="c4164-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="c4164-109">備份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="c4164-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4164-110">若要備份這個：</span><span class="sxs-lookup"><span data-stu-id="c4164-110">To back up this:</span></span></th>
<th><span data-ttu-id="c4164-111">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c4164-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4164-112">拓撲設定資料 (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-113">Export-csconfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-114">位置資訊服務 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-115">Export-cslisconfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-116">回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-117">Export-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-118">持續性的使用者資料 （Rtcxds.mdf 資料庫）</span><span class="sxs-lookup"><span data-stu-id="c4164-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="c4164-119">會議 ID</span><span class="sxs-lookup"><span data-stu-id="c4164-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="c4164-120">Export-csuserdata</span><span class="sxs-lookup"><span data-stu-id="c4164-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="c4164-121">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c4164-122">監視詳細通話記錄資料庫 (LcsCDR.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c4164-123">監視 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c4164-124">SQL Server 資料庫工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c4164-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-125">常設聊天室資料庫 (Mgc.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-126">SQL Server 備份程序或 Export-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="c4164-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="c4164-127">Export-cspersistentchatdata 會將常設聊天室資料匯出成檔案。</span><span class="sxs-lookup"><span data-stu-id="c4164-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-128">所有檔案存放區： Lync Server 檔案存放區、 封存檔案存放區</span><span class="sxs-lookup"><span data-stu-id="c4164-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4164-129"><STRONG>Meeting.Active</STRONG> 檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="c4164-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="c4164-130">會議進行期間會使用這些檔案並予以鎖定。</span><span class="sxs-lookup"><span data-stu-id="c4164-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="c4164-131">標準檔案系統管理工具，如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="c4164-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="c4164-132">還原</span><span class="sxs-lookup"><span data-stu-id="c4164-132">Restoration</span></span>

<span data-ttu-id="c4164-133">若要還原 Lync Server，請在下表中使用的工具。</span><span class="sxs-lookup"><span data-stu-id="c4164-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="c4164-134">您需要還原 Lync Server 的所有命令可以寫成指令都碼。</span><span class="sxs-lookup"><span data-stu-id="c4164-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="c4164-135">部分可在遠端執行，但其他都需要在本機執行下, 表所示。</span><span class="sxs-lookup"><span data-stu-id="c4164-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="c4164-136">用來還原 Lync Server 工具</span><span class="sxs-lookup"><span data-stu-id="c4164-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4164-137">若要執行此作業：</span><span class="sxs-lookup"><span data-stu-id="c4164-137">To do this:</span></span></th>
<th><span data-ttu-id="c4164-138">使用此工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c4164-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4164-139">建立全新的電腦</span><span class="sxs-lookup"><span data-stu-id="c4164-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c4164-140">Windows 作業系統安裝軟體</span><span class="sxs-lookup"><span data-stu-id="c4164-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="c4164-141">SQL Server 安裝軟體</span><span class="sxs-lookup"><span data-stu-id="c4164-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="c4164-142">如果以可匯出的私密金鑰來還原憑證，則請認證 Microsoft Management Console (MMC) 嵌入式管理單元</span><span class="sxs-lookup"><span data-stu-id="c4164-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-143">還原檔案存放區資料</span><span class="sxs-lookup"><span data-stu-id="c4164-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="c4164-144">標準檔案系統管理工具，如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="c4164-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-145">重新建立空的資料庫，並設定下列的權限：</span><span class="sxs-lookup"><span data-stu-id="c4164-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4164-146">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="c4164-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="c4164-147">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="c4164-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="c4164-148">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="c4164-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="c4164-149">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="c4164-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c4164-150">Install-csdatabase</span><span class="sxs-lookup"><span data-stu-id="c4164-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-151">還原中央管理存放區的 Active Directory 網域服務指標</span><span class="sxs-lookup"><span data-stu-id="c4164-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4164-152">如果您在任何時候遺失服務連線點，都可以重新執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c4164-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="c4164-153">Set-csconfigurationstorelocation</span><span class="sxs-lookup"><span data-stu-id="c4164-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-154">拓撲、 原則及組態設定匯入至中央管理存放區 (Xds.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-155">Import-csconfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-156">發佈及啟用拓撲</span><span class="sxs-lookup"><span data-stu-id="c4164-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="c4164-157">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="c4164-157">Topology Builder</span></span></p>
<p><span data-ttu-id="c4164-158">-或-</span><span class="sxs-lookup"><span data-stu-id="c4164-158">-or-</span></span></p>
<p><span data-ttu-id="c4164-159">Publish-cstopology 和 Enable-cstopology</span><span class="sxs-lookup"><span data-stu-id="c4164-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-160">啟用上次發行的拓撲</span><span class="sxs-lookup"><span data-stu-id="c4164-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="c4164-161">Enable-cstopology</span><span class="sxs-lookup"><span data-stu-id="c4164-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-162">重新安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="c4164-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="c4164-163">Lync Server 安裝程式</span><span class="sxs-lookup"><span data-stu-id="c4164-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4164-164">位在 Lync Server 安裝資料夾或媒體 \setup\amd64\Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="c4164-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-165">還原位置資訊 (E9-1-1) 資料 (Lis.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-166">匯入 CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-167">還原持續性的使用者資料 (Rtcxds.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-168">Import-csuserdata</span><span class="sxs-lookup"><span data-stu-id="c4164-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-169">還原回應群組設定資料 (RgsConfig.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-170">Import-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="c4164-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4164-171">若要還原設定資料庫中有沒有回應群組資料的新部署集區中，您應該使用 – OverwriteOwner 選項。</span><span class="sxs-lookup"><span data-stu-id="c4164-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="c4164-172">即使要還原的資料位於相同的完整的網域名稱 (FQDN) 與集區，請使用此選項。</span><span class="sxs-lookup"><span data-stu-id="c4164-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c4164-173">否則，匯入就會失敗，因為已在 Active Directory 中存在的回應群組的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c4164-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4164-174">還原下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="c4164-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4164-175">封存資料庫 (LcsLog.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="c4164-176">監視資料庫：詳細通話記錄資料庫 (LcsCDR.mdf) 及 QoE 資料庫 (QoEMetrics.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c4164-177">SQL Server 資料庫管理工具</span><span class="sxs-lookup"><span data-stu-id="c4164-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4164-178">常設聊天室資料庫 (Mgs.mdf)</span><span class="sxs-lookup"><span data-stu-id="c4164-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="c4164-179">SQL Server 還原程序或 Import-cspersistentchatdata。</span><span class="sxs-lookup"><span data-stu-id="c4164-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="c4164-180">您可以使用 Import-cspersistentchatdata Export-cspersistentchatdata，所建立的檔案和資料會匯入常設聊天室資料庫。</span><span class="sxs-lookup"><span data-stu-id="c4164-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="c4164-181">必要權限</span><span class="sxs-lookup"><span data-stu-id="c4164-181">Required Permissions</span></span>

<span data-ttu-id="c4164-182">使用者必須要執行本主題所述的所有命令的**RTCUniversalServerAdmins**群組成員。</span><span class="sxs-lookup"><span data-stu-id="c4164-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="c4164-183">大部分的備份與還原命令不支援角色型存取控制 (RBAC)。</span><span class="sxs-lookup"><span data-stu-id="c4164-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="c4164-184">兩個例外狀況，而常設聊天 cmdlet Export-cspersistentchatdata Import-cspersistentchatdata，必須執行由使用者身為 CsPersistentChatAdministrator 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c4164-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="c4164-185">若要執行 Lync Server 部署精靈，使用者也必須是本機系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c4164-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

