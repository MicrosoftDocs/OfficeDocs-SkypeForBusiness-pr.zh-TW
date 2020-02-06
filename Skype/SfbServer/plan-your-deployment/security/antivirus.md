---
title: 商務用 Skype Server 的防病毒掃描排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 與商務用 Skype Server 的防病毒掃描程式交互操作概覽。
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815691"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="bf400-103">商務用 Skype Server 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="bf400-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="bf400-104">與商務用 Skype Server 的防病毒掃描程式交互操作概覽。</span><span class="sxs-lookup"><span data-stu-id="bf400-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="bf400-105">若要確保防病毒掃描程式不會干擾商務用 Skype Server 的作業，您必須針對執行防病毒掃描程式的每個商務用 Skype 伺服器伺服器或伺服器角色排除特定程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="bf400-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="bf400-106">下列處理常式與目錄應被排除：</span><span class="sxs-lookup"><span data-stu-id="bf400-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="bf400-107">下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="bf400-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="bf400-108">針對您未使用預設值的任何位置，請排除您指定給組織的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="bf400-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf400-109">請注意，某些防毒程式可能需要其排除清單的絕對（不是相對路徑）。</span><span class="sxs-lookup"><span data-stu-id="bf400-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="bf400-110">商務用 Skype Server 進程：</span><span class="sxs-lookup"><span data-stu-id="bf400-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="bf400-111">ABServer</span><span class="sxs-lookup"><span data-stu-id="bf400-111">ABServer.exe</span></span>

  - <span data-ttu-id="bf400-112">ASMCUSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="bf400-113">AVMCUSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="bf400-114">ChannelService</span><span class="sxs-lookup"><span data-stu-id="bf400-114">ChannelService.exe</span></span>

  - <span data-ttu-id="bf400-115">ClsAgent</span><span class="sxs-lookup"><span data-stu-id="bf400-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="bf400-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="bf400-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="bf400-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="bf400-118">DataProxy</span><span class="sxs-lookup"><span data-stu-id="bf400-118">DataProxy.exe</span></span>

  - <span data-ttu-id="bf400-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="bf400-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="bf400-120">HealthAgent</span><span class="sxs-lookup"><span data-stu-id="bf400-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="bf400-121">IMMCUSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="bf400-122">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="bf400-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="bf400-123">LysSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-123">LysSvc.exe</span></span>

  - <span data-ttu-id="bf400-124">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="bf400-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="bf400-125">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="bf400-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="bf400-126">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="bf400-127">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="bf400-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="bf400-128">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="bf400-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="bf400-129">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="bf400-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="bf400-130">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="bf400-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="bf400-131">RtcHost</span><span class="sxs-lookup"><span data-stu-id="bf400-131">RtcHost.exe</span></span>

  - <span data-ttu-id="bf400-132">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="bf400-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="bf400-133">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="bf400-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="bf400-134">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="bf400-134">XmppTGW.exe</span></span>

- <span data-ttu-id="bf400-135">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="bf400-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="bf400-136">構造 .exe</span><span class="sxs-lookup"><span data-stu-id="bf400-136">Fabric.exe</span></span>

  - <span data-ttu-id="bf400-137">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="bf400-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="bf400-138">FabricHost</span><span class="sxs-lookup"><span data-stu-id="bf400-138">FabricHost.exe</span></span>

- <span data-ttu-id="bf400-139">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="bf400-139">IIS processes:</span></span>

  - <span data-ttu-id="bf400-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="bf400-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="bf400-142">SQL Server 後端處理常式：</span><span class="sxs-lookup"><span data-stu-id="bf400-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf400-143">請注意，這些路徑是 SQL Server 版本所特有的。</span><span class="sxs-lookup"><span data-stu-id="bf400-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="bf400-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11。MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bf400-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="bf400-146">%ProgramFiles%\Microsoft SQL Server\MSAS11。MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="bf400-147">SQL Server 前端程式：</span><span class="sxs-lookup"><span data-stu-id="bf400-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="bf400-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12。LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bf400-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bf400-150">標準版安裝 RTC 實例</span><span class="sxs-lookup"><span data-stu-id="bf400-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="bf400-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bf400-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="bf400-152">目錄和檔案：</span><span class="sxs-lookup"><span data-stu-id="bf400-152">Directories and files:</span></span>

  - <span data-ttu-id="bf400-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="bf400-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="bf400-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="bf400-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="bf400-155">%systemroot%\Microsoft.NET\assembly\ GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="bf400-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf400-156">請注意，這些路徑是針對商務用 Skype 伺服器版本所特有。</span><span class="sxs-lookup"><span data-stu-id="bf400-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="bf400-157">商務用%programfiles%\Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="bf400-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="bf400-158">%programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="bf400-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="bf400-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bf400-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="bf400-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bf400-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="bf400-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="bf400-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="bf400-162">[檔案共用] 存放區（在 [拓撲建立器] 中指定）。</span><span class="sxs-lookup"><span data-stu-id="bf400-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="bf400-163">檔案存放區是在拓撲建立器中指定。</span><span class="sxs-lookup"><span data-stu-id="bf400-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="bf400-164">SQL Server 資料和記錄檔案，包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf400-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="bf400-165">您可以在拓撲結構建立器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="bf400-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="bf400-166">如需每個資料庫的資料與記錄檔（包括預設名稱）的詳細資料，請參閱部署檔中的[SQL Server 資料和記錄檔案位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bf400-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bf400-167">SQL Server 資料和記錄檔案，包括前端資料庫、商務用 Skype 商店及 RtcDatabase 書店的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf400-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="bf400-168">它們通常在%localdrive%\CSData. 下</span><span class="sxs-lookup"><span data-stu-id="bf400-168">They are normally under %localdrive%\CSData.</span></span>


