---
title: Lync Server 2013：防病毒掃描排除
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
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508970"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="93d03-102">Lync Server 2013 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="93d03-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93d03-103">_**主題上次修改日期：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="93d03-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="93d03-104">為了確保防病毒掃描程式不會干擾 Lync Server 2013 的運作，您必須針對每個執行防病毒掃描程式的 Lync Server 2013 伺服器或伺服器角色排除特定的程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="93d03-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="93d03-105">應該排除下列程式和目錄：</span><span class="sxs-lookup"><span data-stu-id="93d03-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93d03-106">下列列出的資料夾和檔案位置是 Lync Server 2013 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="93d03-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="93d03-107">針對您未使用預設值的任何位置，請排除您為組織所指定的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="93d03-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="93d03-108">請注意，某些防毒程式可能需要絕對的相對路徑，其排除清單。</span><span class="sxs-lookup"><span data-stu-id="93d03-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="93d03-109">Lync Server 2013 處理常式：</span><span class="sxs-lookup"><span data-stu-id="93d03-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="93d03-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="93d03-111">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="93d03-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="93d03-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="93d03-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="93d03-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="93d03-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="93d03-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="93d03-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="93d03-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="93d03-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="93d03-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="93d03-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="93d03-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="93d03-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="93d03-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="93d03-133">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="93d03-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="93d03-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="93d03-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="93d03-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-136">FabricHost.exe</span></span>

  - <span data-ttu-id="93d03-137">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="93d03-137">IIS processes:</span></span>
    
      - <span data-ttu-id="93d03-138">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="93d03-139">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="93d03-140">SQL Server Back-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="93d03-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="93d03-141">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="93d03-142">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="93d03-143">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="93d03-144">SQL Server Front-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="93d03-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="93d03-145">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="93d03-146">%ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="93d03-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="93d03-147">目錄及檔案：</span><span class="sxs-lookup"><span data-stu-id="93d03-147">Directories and files:</span></span>
    
      - <span data-ttu-id="93d03-148">% systemroot% \\ System32 \\ 日誌</span><span class="sxs-lookup"><span data-stu-id="93d03-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="93d03-149">% systemroot% \\ SysWow64 \\ 日誌</span><span class="sxs-lookup"><span data-stu-id="93d03-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="93d03-150">% systemroot% \\ Microsoft.NET \\ 元件 \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="93d03-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="93d03-151">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93d03-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="93d03-152">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013 監看員 \\ 節點</span><span class="sxs-lookup"><span data-stu-id="93d03-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="93d03-153">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93d03-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="93d03-154">% 系統磁片% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="93d03-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="93d03-155">在拓撲產生器) 中指定的檔案共用儲存區 (。</span><span class="sxs-lookup"><span data-stu-id="93d03-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="93d03-156">檔存放區是在拓撲產生器中指定的。</span><span class="sxs-lookup"><span data-stu-id="93d03-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="93d03-157">SQL Server 資料和記錄檔，包括後端資料庫、使用者存放區、封存儲存區、監控儲存區及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="93d03-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="93d03-158">您可以在拓撲產生器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="93d03-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="93d03-159">如需每個資料庫之資料和記錄檔（包括預設名稱）的詳細資訊，請參閱部署檔中的 [SQL Server 資料和記錄檔位置（適用于 Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) ）。</span><span class="sxs-lookup"><span data-stu-id="93d03-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="93d03-160">SQL Server 資料和記錄檔，包括前端資料庫、Lync 存放區和 RtcDatabase 存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="93d03-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="93d03-161">它們一般位於% localdrive% \\ CSData。</span><span class="sxs-lookup"><span data-stu-id="93d03-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

