---
title: 商務用 Skype Server 的防病毒掃描排除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 與商務用 Skype Server 的防病毒掃描程式互用性。
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104239"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="8561d-103">商務用 Skype Server 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="8561d-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="8561d-104">與商務用 Skype Server 的防病毒掃描程式互用性。</span><span class="sxs-lookup"><span data-stu-id="8561d-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="8561d-105">為了確保防病毒掃描程式不會干擾商務用 Skype Server 的運作，您必須針對每個執行防病毒掃描程式的商務用 Skype Server 伺服器或伺服器角色排除特定的程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="8561d-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="8561d-106">應該排除下列程式和目錄：</span><span class="sxs-lookup"><span data-stu-id="8561d-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="8561d-107">下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="8561d-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="8561d-108">針對您未使用預設值的任何位置，請排除您為組織所指定的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="8561d-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8561d-109">請注意，某些防毒程式可能需要絕對的相對路徑，其排除清單。</span><span class="sxs-lookup"><span data-stu-id="8561d-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="8561d-110">商務用 Skype 伺服器處理常式：</span><span class="sxs-lookup"><span data-stu-id="8561d-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="8561d-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-111">ABServer.exe</span></span>

  - <span data-ttu-id="8561d-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="8561d-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="8561d-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-114">ChannelService.exe</span></span>

  - <span data-ttu-id="8561d-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="8561d-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="8561d-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="8561d-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-118">DataProxy.exe</span></span>

  - <span data-ttu-id="8561d-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="8561d-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="8561d-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="8561d-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="8561d-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-123">LysSvc.exe</span></span>

  - <span data-ttu-id="8561d-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="8561d-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="8561d-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="8561d-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="8561d-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="8561d-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="8561d-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="8561d-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-131">RtcHost.exe</span></span>

  - <span data-ttu-id="8561d-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="8561d-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="8561d-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-134">XmppTGW.exe</span></span>

- <span data-ttu-id="8561d-135">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="8561d-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="8561d-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-136">Fabric.exe</span></span>

  - <span data-ttu-id="8561d-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="8561d-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-138">FabricHost.exe</span></span>

- <span data-ttu-id="8561d-139">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="8561d-139">IIS processes:</span></span>

  - <span data-ttu-id="8561d-140">% systemroot% \system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="8561d-141">% systemroot% \SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="8561d-142">SQL Server Back-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="8561d-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="8561d-143">請注意，這些路徑是 SQL Server 版本特有的。</span><span class="sxs-lookup"><span data-stu-id="8561d-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="8561d-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="8561d-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="8561d-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="8561d-147">SQL Server Front-End 處理常式：</span><span class="sxs-lookup"><span data-stu-id="8561d-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="8561d-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="8561d-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="8561d-150">Standard Edition 安裝 RTC 實例</span><span class="sxs-lookup"><span data-stu-id="8561d-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="8561d-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="8561d-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="8561d-152">目錄及檔案：</span><span class="sxs-lookup"><span data-stu-id="8561d-152">Directories and files:</span></span>

  - <span data-ttu-id="8561d-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="8561d-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="8561d-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="8561d-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="8561d-155">%systemroot%\Microsoft.NET\assembly\ GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="8561d-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="8561d-156">請注意，這些路徑是商務用 Skype Server 版本特有的。</span><span class="sxs-lookup"><span data-stu-id="8561d-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="8561d-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8561d-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="8561d-158">%programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="8561d-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="8561d-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8561d-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="8561d-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8561d-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="8561d-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="8561d-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="8561d-162">在拓撲產生器) 中指定的檔案共用儲存區 (。</span><span class="sxs-lookup"><span data-stu-id="8561d-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="8561d-163">檔存放區是在拓撲產生器中指定的。</span><span class="sxs-lookup"><span data-stu-id="8561d-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="8561d-164">SQL Server 資料和記錄檔，包括後端資料庫、使用者存放區、封存儲存區、監控儲存區及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="8561d-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="8561d-165">您可以在拓撲產生器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="8561d-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="8561d-166">如需每個資料庫之資料和記錄檔（包括預設名稱）的詳細資訊，請參閱部署檔中的 [SQL Server 資料和記錄檔位置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) 。</span><span class="sxs-lookup"><span data-stu-id="8561d-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8561d-167">SQL Server 資料和記錄檔，包括前端資料庫、商務用 Skype 書店和 RtcDatabase 存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="8561d-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="8561d-168">它們通常是在%localdrive%\CSData。</span><span class="sxs-lookup"><span data-stu-id="8561d-168">They are normally under %localdrive%\CSData.</span></span>