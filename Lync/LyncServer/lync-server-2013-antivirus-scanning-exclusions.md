---
title: Lync Server 2013：防毒掃描排除項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90847830d9f2586e0d111846f2867400c52fc940
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="99c79-102">Lync Server 2013 的防毒掃描排除項目</span><span class="sxs-lookup"><span data-stu-id="99c79-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c79-103">_**主題上次修改日期：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="99c79-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="99c79-104">若要確保防病毒掃描程式不會干擾 Lync Server 2013 的作業，您必須針對執行防病毒掃描程式的每個 Lync Server 2013 伺服器或伺服器角色排除特定程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="99c79-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="99c79-105">下列處理常式與目錄應被排除：</span><span class="sxs-lookup"><span data-stu-id="99c79-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="99c79-106">下列列出的資料夾和檔案位置為 Lync Server 2013 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="99c79-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="99c79-107">針對您未使用預設值的任何位置，請排除您指定給組織的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="99c79-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99c79-108">請注意，某些防毒程式可能需要其排除清單的絕對（不是相對路徑）。</span><span class="sxs-lookup"><span data-stu-id="99c79-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="99c79-109">Lync Server 2013 處理常式：</span><span class="sxs-lookup"><span data-stu-id="99c79-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="99c79-110">ABServer</span><span class="sxs-lookup"><span data-stu-id="99c79-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="99c79-111">AcpMcuSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-112">ASMCUSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-113">AVMCUSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-114">ChannelService</span><span class="sxs-lookup"><span data-stu-id="99c79-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="99c79-115">ClsAgent</span><span class="sxs-lookup"><span data-stu-id="99c79-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="99c79-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="99c79-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="99c79-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-118">DataProxy</span><span class="sxs-lookup"><span data-stu-id="99c79-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="99c79-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="99c79-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="99c79-120">IMMCUSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-121">LysSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-122">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="99c79-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="99c79-123">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="99c79-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="99c79-124">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-125">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="99c79-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="99c79-126">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="99c79-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="99c79-127">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="99c79-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="99c79-128">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="99c79-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="99c79-129">RtcHost</span><span class="sxs-lookup"><span data-stu-id="99c79-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="99c79-130">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="99c79-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="99c79-131">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="99c79-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="99c79-132">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="99c79-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="99c79-133">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="99c79-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="99c79-134">構造 .exe</span><span class="sxs-lookup"><span data-stu-id="99c79-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="99c79-135">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="99c79-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="99c79-136">FabricHost</span><span class="sxs-lookup"><span data-stu-id="99c79-136">FabricHost.exe</span></span>

  - <span data-ttu-id="99c79-137">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="99c79-137">IIS processes:</span></span>
    
      - <span data-ttu-id="99c79-138">% systemroot%\\system32\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="99c79-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="99c79-139">% systemroot%\\SysWOW64\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="99c79-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="99c79-140">SQL Server 後端處理常式：</span><span class="sxs-lookup"><span data-stu-id="99c79-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="99c79-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\SQLServr</span><span class="sxs-lookup"><span data-stu-id="99c79-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="99c79-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService .exe</span><span class="sxs-lookup"><span data-stu-id="99c79-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="99c79-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv</span><span class="sxs-lookup"><span data-stu-id="99c79-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="99c79-144">SQL Server 前端程式：</span><span class="sxs-lookup"><span data-stu-id="99c79-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="99c79-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\SQLServr</span><span class="sxs-lookup"><span data-stu-id="99c79-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="99c79-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\SQLServr</span><span class="sxs-lookup"><span data-stu-id="99c79-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="99c79-147">目錄和檔案：</span><span class="sxs-lookup"><span data-stu-id="99c79-147">Directories and files:</span></span>
    
      - <span data-ttu-id="99c79-148">% systemroot%\\System32\\日誌</span><span class="sxs-lookup"><span data-stu-id="99c79-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="99c79-149">% systemroot%\\SysWow64\\的日誌</span><span class="sxs-lookup"><span data-stu-id="99c79-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="99c79-150">% systemroot%\\Microsoft.NET\\元件\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="99c79-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="99c79-151">% programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c79-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="99c79-152">% programfiles%\\常見檔案\\Microsoft Lync Server 2013\\觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="99c79-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="99c79-153">% programfiles%\\常見檔案\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c79-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="99c79-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="99c79-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="99c79-155">[檔案共用] 存放區（在 [拓撲建立器] 中指定）。</span><span class="sxs-lookup"><span data-stu-id="99c79-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="99c79-156">檔案存放區是在拓撲建立器中指定。</span><span class="sxs-lookup"><span data-stu-id="99c79-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="99c79-157">SQL Server 資料和記錄檔案，包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="99c79-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="99c79-158">您可以在拓撲結構建立器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="99c79-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="99c79-159">如需每個資料庫的資料和記錄檔案（包括預設名稱）的詳細資料，請參閱部署檔中[Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md)。</span><span class="sxs-lookup"><span data-stu-id="99c79-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="99c79-160">SQL Server 資料和記錄檔案，包括前端資料庫、Lync store 及 RtcDatabase store 的檔案。</span><span class="sxs-lookup"><span data-stu-id="99c79-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="99c79-161">它們通常在 [% localdrive%\\CSData] 下。</span><span class="sxs-lookup"><span data-stu-id="99c79-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

