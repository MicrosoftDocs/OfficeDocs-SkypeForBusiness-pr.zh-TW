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
ms.openlocfilehash: ea5e4ce57e61be50bfd1e2a78529830b4a40e3ed
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a><span data-ttu-id="7b594-102">Lync Server 2013 中的備份和還原需求：工具和許可權</span><span class="sxs-lookup"><span data-stu-id="7b594-102">Backup and restoration requirements in Lync Server 2013: tools and permissions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b594-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7b594-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="7b594-104">本主題識別您可以用來備份及還原 Lync Server 2013 的工具、所需的許可權，以及您是否可以遠端或本機執行命令。</span><span class="sxs-lookup"><span data-stu-id="7b594-104">This topic identifies the tools that you can use to back up and restore Lync Server 2013, the permissions that you need, and whether you can run commands remotely or locally.</span></span> <span data-ttu-id="7b594-105">具體來說，本主題將重點放在 Lync Server 提供以進行備份和還原的工具上。</span><span class="sxs-lookup"><span data-stu-id="7b594-105">Specifically, this topic focuses on tools that are provided with Lync Server for backup and restoration.</span></span>

<div>

## <a name="backups"></a><span data-ttu-id="7b594-106">資料備份</span><span class="sxs-lookup"><span data-stu-id="7b594-106">Backups</span></span>

<span data-ttu-id="7b594-107">若要備份 Lync Server，請使用下表中所述的工具。</span><span class="sxs-lookup"><span data-stu-id="7b594-107">To back up Lync Server, use the tools identified in the following table.</span></span> <span data-ttu-id="7b594-108">您需要用來備份 Lync Server 的所有命令都可以進行腳本化，而且可以遠端執行。</span><span class="sxs-lookup"><span data-stu-id="7b594-108">All the commands that you need to back up Lync Server can be scripted and can be run remotely.</span></span>

### <a name="tools-for-backing-up-lync-server"></a><span data-ttu-id="7b594-109">備份 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="7b594-109">Tools for Backing Up Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b594-110">若要備份，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7b594-110">To back up this:</span></span></th>
<th><span data-ttu-id="7b594-111">使用這個工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7b594-111">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b594-112">拓朴配置資料（Xds）</span><span class="sxs-lookup"><span data-stu-id="7b594-112">Topology configuration data (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-113">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-113">Export-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-114">位置資訊服務（E9-1-1）資料（.Lis）</span><span class="sxs-lookup"><span data-stu-id="7b594-114">Location information service (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-115">Export-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-115">Export-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-116">回應群組設定資料（RgsConfig）</span><span class="sxs-lookup"><span data-stu-id="7b594-116">Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-117">Export-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-117">Export-CsRgsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-118">持久性使用者資料（Rtcxds .mdf 資料庫）</span><span class="sxs-lookup"><span data-stu-id="7b594-118">Persistent user data (Rtcxds.mdf database)</span></span></p>
<p><span data-ttu-id="7b594-119">會議 Id</span><span class="sxs-lookup"><span data-stu-id="7b594-119">Conference IDs</span></span></p></td>
<td><p><span data-ttu-id="7b594-120">Export-CsUserData</span><span class="sxs-lookup"><span data-stu-id="7b594-120">Export-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="7b594-121">存檔資料庫（LcsLog）</span><span class="sxs-lookup"><span data-stu-id="7b594-121">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="7b594-122">監控通話詳細資料記錄資料庫（LcsCDR）</span><span class="sxs-lookup"><span data-stu-id="7b594-122">Monitoring call detail record database (LcsCDR.mdf)</span></span></p></li>
<li><p><span data-ttu-id="7b594-123">監視 QoE 資料庫（QoEMetrics）</span><span class="sxs-lookup"><span data-stu-id="7b594-123">Monitoring QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7b594-124">SQL server 資料庫工具，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b594-124">SQL Server database tool, such as SQL Server Management Studio</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-125">持續聊天資料庫（Mgc）</span><span class="sxs-lookup"><span data-stu-id="7b594-125">Persistent Chat database (Mgc.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-126">[SQL Server 備份程式] 或 [匯出-CsPersistentChatData]。</span><span class="sxs-lookup"><span data-stu-id="7b594-126">SQL Server backup procedures or Export-CsPersistentChatData.</span></span> <span data-ttu-id="7b594-127">Export-CsPersistentChatData 會將永久性聊天資料匯出為檔案。</span><span class="sxs-lookup"><span data-stu-id="7b594-127">Export-CsPersistentChatData exports Persistent Chat data as a file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-128">所有檔案儲存區： Lync Server 檔存放區、封存檔案存放區</span><span class="sxs-lookup"><span data-stu-id="7b594-128">All file stores: Lync Server file store, Archiving file store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7b594-129">名為「<STRONG>會議」的</STRONG>檔案不應備份。</span><span class="sxs-lookup"><span data-stu-id="7b594-129">Files named <STRONG>Meeting.Active</STRONG> should not be backed up.</span></span> <span data-ttu-id="7b594-130">在會議進行時，這些檔案正在使用中且已鎖定。</span><span class="sxs-lookup"><span data-stu-id="7b594-130">These files are in use and locked while a meeting takes place.</span></span>


</div></td>
<td><p><span data-ttu-id="7b594-131">標準檔案系統管理工具，例如 Robocopy。</span><span class="sxs-lookup"><span data-stu-id="7b594-131">Standard file system management tool, such as Robocopy.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a><span data-ttu-id="7b594-132">還原</span><span class="sxs-lookup"><span data-stu-id="7b594-132">Restoration</span></span>

<span data-ttu-id="7b594-133">若要還原 Lync Server，請使用下表中的工具。</span><span class="sxs-lookup"><span data-stu-id="7b594-133">To restore Lync Server, use the tools in the following table.</span></span> <span data-ttu-id="7b594-134">您可以為還原 Lync Server 所需的所有命令進行腳本化。</span><span class="sxs-lookup"><span data-stu-id="7b594-134">All the commands that you need to restore Lync Server can be scripted.</span></span> <span data-ttu-id="7b594-135">有些可以在遠端執行，但其他人需要在本機執行，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="7b594-135">Some can be run remotely, but others need to be run locally, as specified in the following table.</span></span>

### <a name="tools-for-restoring-lync-server"></a><span data-ttu-id="7b594-136">還原 Lync Server 的工具</span><span class="sxs-lookup"><span data-stu-id="7b594-136">Tools for Restoring Lync Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b594-137">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="7b594-137">To do this:</span></span></th>
<th><span data-ttu-id="7b594-138">使用這個工具或 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7b594-138">Use this tool or cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b594-139">建立新的或乾淨的電腦</span><span class="sxs-lookup"><span data-stu-id="7b594-139">Build a new or clean computer</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7b594-140">Windows 作業系統安裝軟體</span><span class="sxs-lookup"><span data-stu-id="7b594-140">Windows operating system installation software</span></span></p></li>
<li><p><span data-ttu-id="7b594-141">SQL Server 安裝軟體</span><span class="sxs-lookup"><span data-stu-id="7b594-141">SQL Server installation software</span></span></p></li>
<li><p><span data-ttu-id="7b594-142">[憑證 Microsoft 管理主控台（MMC）] 管理單元（如果使用可匯出的私密金鑰還原憑證）</span><span class="sxs-lookup"><span data-stu-id="7b594-142">Certificates Microsoft Management Console (MMC) snap-in, if restoring certificates with an exportable private key</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-143">還原檔案儲存區資料</span><span class="sxs-lookup"><span data-stu-id="7b594-143">Restore file store data</span></span></p></td>
<td><p><span data-ttu-id="7b594-144">標準檔案系統管理工具，例如 Robocopy</span><span class="sxs-lookup"><span data-stu-id="7b594-144">Standard file system management tool, such as Robocopy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-145">重新建立空白資料庫並設定下列專案的許可權：</span><span class="sxs-lookup"><span data-stu-id="7b594-145">Recreate empty databases and set permissions for the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7b594-146">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="7b594-146">Central Management store</span></span></p></li>
<li><p><span data-ttu-id="7b594-147">後端伺服器</span><span class="sxs-lookup"><span data-stu-id="7b594-147">Back End Server</span></span></p></li>
<li><p><span data-ttu-id="7b594-148">監控資料庫</span><span class="sxs-lookup"><span data-stu-id="7b594-148">Monitoring database</span></span></p></li>
<li><p><span data-ttu-id="7b594-149">封存資料庫</span><span class="sxs-lookup"><span data-stu-id="7b594-149">Archiving database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7b594-150">Install-CsDatabase</span><span class="sxs-lookup"><span data-stu-id="7b594-150">Install-CsDatabase</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-151">將 Active Directory 網域服務指標還原到中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="7b594-151">Restore the Active Directory Domain Services pointer to the Central Management store</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7b594-152">如果您在任何時候遺失服務連接點，您可以重新執行這個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b594-152">If you lose the service connection point at any time, you can rerun this cmdlet.</span></span>


</div></td>
<td><p><span data-ttu-id="7b594-153">Set-CsConfigurationStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7b594-153">Set-CsConfigurationStoreLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-154">將拓撲、原則和設定的設定匯入中央管理商店（Xds）</span><span class="sxs-lookup"><span data-stu-id="7b594-154">Import the topology, policies, and configuration settings to the Central Management store (Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-155">匯入-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-155">Import-CsConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-156">發佈並啟用拓撲</span><span class="sxs-lookup"><span data-stu-id="7b594-156">Publish and enable the topology</span></span></p></td>
<td><p><span data-ttu-id="7b594-157">拓撲建立器</span><span class="sxs-lookup"><span data-stu-id="7b594-157">Topology Builder</span></span></p>
<p><span data-ttu-id="7b594-158">或</span><span class="sxs-lookup"><span data-stu-id="7b594-158">-or-</span></span></p>
<p><span data-ttu-id="7b594-159">發佈-CsTopology 和 Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="7b594-159">Publish-CsTopology and Enable-CsTopology</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-160">啟用上次發佈的拓撲</span><span class="sxs-lookup"><span data-stu-id="7b594-160">Enable the last published topology</span></span></p></td>
<td><p><span data-ttu-id="7b594-161">Enable-CsTopology</span><span class="sxs-lookup"><span data-stu-id="7b594-161">Enable-CsTopology</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-162">重新安裝 Lync Server 元件</span><span class="sxs-lookup"><span data-stu-id="7b594-162">Reinstall Lync Server components</span></span></p></td>
<td><p><span data-ttu-id="7b594-163">Lync Server 設定</span><span class="sxs-lookup"><span data-stu-id="7b594-163">Lync Server Setup</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7b594-164">位於 Lync Server 安裝資料夾或 \setup\amd64\Setup.exe. 中的媒體</span><span class="sxs-lookup"><span data-stu-id="7b594-164">Located in the Lync Server installation folder or media at \setup\amd64\Setup.exe.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-165">還原位置資訊（E9-1-1）資料（.Lis）</span><span class="sxs-lookup"><span data-stu-id="7b594-165">Restore location information (E9-1-1) data (Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-166">匯入-CsLisConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-166">Import-CsLisConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-167">還原永久性使用者資料（Rtcxds）</span><span class="sxs-lookup"><span data-stu-id="7b594-167">Restore persistent user data (Rtcxds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-168">匯入-CsUserData</span><span class="sxs-lookup"><span data-stu-id="7b594-168">Import-CsUserData</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-169">還原回應群組設定資料（RgsConfig）</span><span class="sxs-lookup"><span data-stu-id="7b594-169">Restore Response Group configuration data (RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-170">匯入-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="7b594-170">Import-CsRgsConfiguration</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7b594-171">如果在新部署的池中，在資料庫中沒有任何回應群組資料的配置，則應使用– OverwriteOwner 選項。</span><span class="sxs-lookup"><span data-stu-id="7b594-171">If the configuration is being restored in a newly deployed pool that has no Response Group data in the database, then you should use the –OverwriteOwner option.</span></span> <span data-ttu-id="7b594-172">即使要還原的資料位於擁有相同完整功能變數名稱（FQDN）的池中，您也能使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="7b594-172">Use this option even if the data being restored is in a pool with the same fully qualified domain name (FQDN).</span></span> <span data-ttu-id="7b594-173">否則，匯入將無法成功，因為連絡人物件已存在 Active Directory 中的回應群組。</span><span class="sxs-lookup"><span data-stu-id="7b594-173">Otherwise, the import will not succeed, due to the contact objects to the Response Groups already existing in Active Directory.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b594-174">還原下列資料庫：</span><span class="sxs-lookup"><span data-stu-id="7b594-174">Restore the following databases:</span></span></p>
<ul>
<li><p><span data-ttu-id="7b594-175">存檔資料庫（LcsLog）</span><span class="sxs-lookup"><span data-stu-id="7b594-175">Archiving database (LcsLog.mdf)</span></span></p></li>
<li><p><span data-ttu-id="7b594-176">監視資料庫：通話詳細資料記錄資料庫（LcsCDR .mdf）和 QoE 資料庫（QoEMetrics）</span><span class="sxs-lookup"><span data-stu-id="7b594-176">Monitoring databases: call detail record database (LcsCDR.mdf) and QoE database (QoEMetrics.mdf)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7b594-177">SQL Server 資料庫管理工具</span><span class="sxs-lookup"><span data-stu-id="7b594-177">SQL Server database management tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b594-178">持續聊天資料庫（Mgs）</span><span class="sxs-lookup"><span data-stu-id="7b594-178">Persistent Chat database (Mgs.mdf)</span></span></p></td>
<td><p><span data-ttu-id="7b594-179">[SQL Server 還原程式] 或 [匯入-CsPersistentChatData]。</span><span class="sxs-lookup"><span data-stu-id="7b594-179">SQL Server restore procedures or Import-CsPersistentChatData.</span></span> <span data-ttu-id="7b594-180">您可以使用匯入-CsPersistentChatData 搭配由 Export CsPersistentChatData 建立的檔案，然後將資料匯入到持久聊天資料庫中。</span><span class="sxs-lookup"><span data-stu-id="7b594-180">You can use Import-CsPersistentChatData with a file created by Export-CsPersistentChatData, and the data will be imported into the Persistent Chat database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a><span data-ttu-id="7b594-181">所需許可權</span><span class="sxs-lookup"><span data-stu-id="7b594-181">Required Permissions</span></span>

<span data-ttu-id="7b594-182">使用者必須是**RTCUniversalServerAdmins**群組的成員，才能執行本主題中所述的所有命令。</span><span class="sxs-lookup"><span data-stu-id="7b594-182">Users must be a member of the **RTCUniversalServerAdmins** group to perform all the commands described in this topic.</span></span> <span data-ttu-id="7b594-183">大多數的備份和還原命令不支援以角色為基礎的存取控制（RBAC）。</span><span class="sxs-lookup"><span data-stu-id="7b594-183">Most backup and restore commands do not support role-based access control (RBAC).</span></span> <span data-ttu-id="7b594-184">有兩個例外情況是永久聊天 Cmdlet 的 Export CsPersistentChatData 和 Import-CsPersistentChatData，這必須由成為 CsPersistentChatAdministrator 群組成員的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="7b594-184">Two exceptions are the Persistent Chat cmdlets Export-CsPersistentChatData and Import-CsPersistentChatData, which must be run by a user who is a member of the CsPersistentChatAdministrator group.</span></span> <span data-ttu-id="7b594-185">若要執行 Lync Server 部署嚮導，使用者也必須是本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7b594-185">To run Lync Server Deployment Wizard, a user must also be a member of the Local Adminstrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

