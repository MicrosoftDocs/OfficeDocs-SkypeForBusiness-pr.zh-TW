---
title: Lync Server 2013：防病毒掃描排除
description: Lync Server 2013：防病毒掃描排除專案。
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561909"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="1013f-103">Lync Server 2013 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="1013f-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1013f-104">_**主題上次修改日期：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="1013f-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="1013f-105">為了確保防病毒掃描程式不會干擾 Lync Server 2013 的運作，您必須針對每個執行防病毒掃描程式的 Lync Server 2013 伺服器或伺服器角色排除特定的程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="1013f-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="1013f-106">應該排除下列程式和目錄：</span><span class="sxs-lookup"><span data-stu-id="1013f-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1013f-107">下列列出的資料夾和檔案位置是 Lync Server 2013 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="1013f-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="1013f-108">針對您未使用預設值的任何位置，請排除您為組織所指定的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="1013f-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1013f-109">請注意，某些防毒程式可能需要絕對的相對路徑，其排除清單。</span><span class="sxs-lookup"><span data-stu-id="1013f-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="1013f-110">Lync Server 2013 處理常式：</span><span class="sxs-lookup"><span data-stu-id="1013f-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="1013f-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="1013f-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="1013f-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="1013f-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="1013f-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="1013f-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="1013f-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="1013f-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="1013f-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="1013f-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="1013f-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="1013f-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="1013f-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="1013f-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="1013f-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="1013f-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="1013f-134">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="1013f-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="1013f-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="1013f-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="1013f-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-137">FabricHost.exe</span></span>

  - <span data-ttu-id="1013f-138">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="1013f-138">IIS processes:</span></span>
    
      - <span data-ttu-id="1013f-139">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="1013f-140">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="1013f-141">SQL Server Back-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="1013f-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="1013f-142">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="1013f-143">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="1013f-144">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="1013f-145">SQL Server Front-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="1013f-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="1013f-146">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="1013f-147">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="1013f-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="1013f-148">目錄及檔案：</span><span class="sxs-lookup"><span data-stu-id="1013f-148">Directories and files:</span></span>
    
      - <span data-ttu-id="1013f-149">% systemroot% \\ System32 \\ 日誌</span><span class="sxs-lookup"><span data-stu-id="1013f-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="1013f-150">% systemroot% \\ SysWow64 \\ 日誌</span><span class="sxs-lookup"><span data-stu-id="1013f-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="1013f-151">% systemroot% \\ Microsoft.NET \\ 元件 \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="1013f-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="1013f-152">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1013f-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="1013f-153">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013 監看員 \\ 節點</span><span class="sxs-lookup"><span data-stu-id="1013f-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="1013f-154">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1013f-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="1013f-155">% 系統磁片% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="1013f-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="1013f-156">在拓撲產生器) 中指定的檔案共用儲存區 (。</span><span class="sxs-lookup"><span data-stu-id="1013f-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="1013f-157">檔存放區是在拓撲產生器中指定的。</span><span class="sxs-lookup"><span data-stu-id="1013f-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="1013f-158">SQL Server 資料和記錄檔，包括後端資料庫、使用者存放區、封存儲存區、監控儲存區及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="1013f-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="1013f-159">您可以在拓撲產生器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="1013f-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="1013f-160">如需每個資料庫之資料和記錄檔（包括預設名稱）的詳細資訊，請參閱部署檔中的 [SQL Server 資料和記錄檔位置（適用于 Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) ）。</span><span class="sxs-lookup"><span data-stu-id="1013f-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="1013f-161">SQL Server 資料和記錄檔，包括前端資料庫、Lync 存放區和 RtcDatabase 存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="1013f-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="1013f-162">它們一般位於% localdrive% \\ CSData。</span><span class="sxs-lookup"><span data-stu-id="1013f-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

