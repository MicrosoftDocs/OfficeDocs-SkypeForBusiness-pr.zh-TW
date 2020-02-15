---
title: Lync Server 2013： 防毒掃描排除項目
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
ms.openlocfilehash: f8faeba1d3b661110bcaf633d3c780dc2c2ad2b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="f1824-102">防毒掃描排除的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1824-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1824-103">_**主題上次修改日期：** 2015年-11-02_</span><span class="sxs-lookup"><span data-stu-id="f1824-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="f1824-104">若要確保防毒掃描程式不干擾 Lync Server 2013 的作業，您必須排除特定處理程序和每個 Lync Server 2013 伺服器或伺服器角色您用來執行防毒掃描程式的目錄。</span><span class="sxs-lookup"><span data-stu-id="f1824-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="f1824-105">應該排除下列程序及目錄：</span><span class="sxs-lookup"><span data-stu-id="f1824-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1824-106">以下列出的資料夾和檔案位置是 Lync Server 2013 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="f1824-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="f1824-107">沒有使用預設的任何位置，但不包括為您的組織，而不在本主題中所指定的預設位置是您所指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f1824-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f1824-108">請注意，某些防毒程式可能需要絕對、 而非相對路徑，其排除項目清單。</span><span class="sxs-lookup"><span data-stu-id="f1824-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="f1824-109">Lync Server 2013 的程序：</span><span class="sxs-lookup"><span data-stu-id="f1824-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="f1824-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="f1824-111">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="f1824-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="f1824-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="f1824-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="f1824-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="f1824-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f1824-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="f1824-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="f1824-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="f1824-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f1824-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="f1824-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="f1824-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="f1824-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="f1824-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="f1824-133">Windows Fabric 主機服務處理程序：</span><span class="sxs-lookup"><span data-stu-id="f1824-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="f1824-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="f1824-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="f1824-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-136">FabricHost.exe</span></span>

  - <span data-ttu-id="f1824-137">IIS 程序：</span><span class="sxs-lookup"><span data-stu-id="f1824-137">IIS processes:</span></span>
    
      - <span data-ttu-id="f1824-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="f1824-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="f1824-140">SQL Server 後端程序：</span><span class="sxs-lookup"><span data-stu-id="f1824-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="f1824-141">%Programfiles%\\Microsoft SQL Server\\MSSQL11。MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f1824-142">%Programfiles%\\Microsoft SQL Server\\MSRS11。MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="f1824-143">%Programfiles%\\Microsoft SQL Server\\MSAS11。MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="f1824-144">SQL Server 前端程序：</span><span class="sxs-lookup"><span data-stu-id="f1824-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="f1824-145">%Programfiles%\\Microsoft SQL Server\\MSSQL11。LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f1824-146">%Programfiles%\\Microsoft SQL Server\\MSSQL11。RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="f1824-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="f1824-147">目錄和檔案：</span><span class="sxs-lookup"><span data-stu-id="f1824-147">Directories and files:</span></span>
    
      - <span data-ttu-id="f1824-148">%systemroot%\\System32\\記錄檔</span><span class="sxs-lookup"><span data-stu-id="f1824-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="f1824-149">%systemroot%\\SysWow64\\記錄檔</span><span class="sxs-lookup"><span data-stu-id="f1824-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="f1824-150">%systemroot%\\Microsoft.NET\\組件\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="f1824-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="f1824-151">%programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1824-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f1824-152">%programfiles%\\通用檔案\\Microsoft Lync Server 2013\\監看員節點</span><span class="sxs-lookup"><span data-stu-id="f1824-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="f1824-153">%programfiles%\\通用檔案\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1824-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f1824-154">%Systemdrive%並\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="f1824-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="f1824-155">檔案共用存放區 （在拓撲產生器中指定）。</span><span class="sxs-lookup"><span data-stu-id="f1824-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="f1824-156">拓撲產生器] 中，會指定檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="f1824-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="f1824-157">SQL Server 資料和記錄檔，包括後端資料庫、 使用者存放區、 封存存放區、 監控存放區和應用程式存放區。</span><span class="sxs-lookup"><span data-stu-id="f1824-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="f1824-158">在拓撲產生器可以指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="f1824-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="f1824-159">如需每個資料庫的資料與記錄檔的詳細資訊，包括預設名稱，請參閱[Lync Server 2013 的 SQL Server 資料和記錄檔位置](lync-server-2013-sql-server-data-and-log-file-placement.md) 部署 > 文件中。</span><span class="sxs-lookup"><span data-stu-id="f1824-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f1824-160">SQL Server 資料和記錄檔，包括前端資料庫、 Lync 存放區中，與 RtcDatabase 存放區。</span><span class="sxs-lookup"><span data-stu-id="f1824-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="f1824-161">它們通常是在 %localdrive%下\\CSData。</span><span class="sxs-lookup"><span data-stu-id="f1824-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

