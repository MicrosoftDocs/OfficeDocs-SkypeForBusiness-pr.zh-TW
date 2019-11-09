---
title: 商務用 Skype Server 的防病毒掃描排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 與商務用 Skype Server 的防病毒掃描程式交互操作概覽。
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074625"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="fbaec-103">商務用 Skype Server 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="fbaec-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="fbaec-104">與商務用 Skype Server 的防病毒掃描程式交互操作概覽。</span><span class="sxs-lookup"><span data-stu-id="fbaec-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="fbaec-105">若要確保防病毒掃描程式不會干擾商務用 Skype Server 的作業，您必須針對執行防病毒掃描程式的每個商務用 Skype 伺服器伺服器或伺服器角色排除特定程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="fbaec-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="fbaec-106">下列處理常式與目錄應被排除：</span><span class="sxs-lookup"><span data-stu-id="fbaec-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="fbaec-107">下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="fbaec-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="fbaec-108">針對您未使用預設值的任何位置，請排除您指定給組織的位置，而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="fbaec-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fbaec-109">請注意，某些防毒程式可能需要其排除清單的絕對（不是相對路徑）。</span><span class="sxs-lookup"><span data-stu-id="fbaec-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="fbaec-110">商務用 Skype Server 進程：</span><span class="sxs-lookup"><span data-stu-id="fbaec-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="fbaec-111">ABServer</span><span class="sxs-lookup"><span data-stu-id="fbaec-111">ABServer.exe</span></span>

  - <span data-ttu-id="fbaec-112">ASMCUSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="fbaec-113">AVMCUSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="fbaec-114">ChannelService</span><span class="sxs-lookup"><span data-stu-id="fbaec-114">ChannelService.exe</span></span>

  - <span data-ttu-id="fbaec-115">ClsAgent</span><span class="sxs-lookup"><span data-stu-id="fbaec-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="fbaec-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="fbaec-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="fbaec-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="fbaec-118">DataProxy</span><span class="sxs-lookup"><span data-stu-id="fbaec-118">DataProxy.exe</span></span>

  - <span data-ttu-id="fbaec-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="fbaec-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="fbaec-120">HealthAgent</span><span class="sxs-lookup"><span data-stu-id="fbaec-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="fbaec-121">IMMCUSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="fbaec-122">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="fbaec-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="fbaec-123">LysSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-123">LysSvc.exe</span></span>

  - <span data-ttu-id="fbaec-124">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="fbaec-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="fbaec-125">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="fbaec-126">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="fbaec-127">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="fbaec-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="fbaec-128">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="fbaec-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="fbaec-129">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="fbaec-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="fbaec-130">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="fbaec-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="fbaec-131">RtcHost</span><span class="sxs-lookup"><span data-stu-id="fbaec-131">RtcHost.exe</span></span>

  - <span data-ttu-id="fbaec-132">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="fbaec-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="fbaec-133">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="fbaec-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="fbaec-134">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="fbaec-134">XmppTGW.exe</span></span>

- <span data-ttu-id="fbaec-135">Windows Fabric 主機服務處理常式：</span><span class="sxs-lookup"><span data-stu-id="fbaec-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="fbaec-136">構造 .exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-136">Fabric.exe</span></span>

  - <span data-ttu-id="fbaec-137">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="fbaec-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="fbaec-138">FabricHost</span><span class="sxs-lookup"><span data-stu-id="fbaec-138">FabricHost.exe</span></span>

- <span data-ttu-id="fbaec-139">IIS 處理常式：</span><span class="sxs-lookup"><span data-stu-id="fbaec-139">IIS processes:</span></span>

  - <span data-ttu-id="fbaec-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="fbaec-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="fbaec-142">SQL Server 後端處理常式：</span><span class="sxs-lookup"><span data-stu-id="fbaec-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbaec-143">請注意，這些路徑是 SQL Server 版本所特有的。</span><span class="sxs-lookup"><span data-stu-id="fbaec-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="fbaec-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11。MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fbaec-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="fbaec-146">%ProgramFiles%\Microsoft SQL Server\MSAS11。MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="fbaec-147">SQL Server 前端程式：</span><span class="sxs-lookup"><span data-stu-id="fbaec-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="fbaec-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12。LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fbaec-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="fbaec-150">標準版安裝 RTC 實例</span><span class="sxs-lookup"><span data-stu-id="fbaec-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="fbaec-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fbaec-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="fbaec-152">目錄和檔案：</span><span class="sxs-lookup"><span data-stu-id="fbaec-152">Directories and files:</span></span>

  - <span data-ttu-id="fbaec-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="fbaec-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="fbaec-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="fbaec-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="fbaec-155">%systemroot%\Microsoft.NET\assembly\ GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="fbaec-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbaec-156">請注意，這些路徑是針對商務用 Skype 伺服器版本所特有。</span><span class="sxs-lookup"><span data-stu-id="fbaec-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="fbaec-157">商務用%programfiles%\Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="fbaec-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="fbaec-158">%programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="fbaec-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="fbaec-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fbaec-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="fbaec-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fbaec-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="fbaec-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="fbaec-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="fbaec-162">[檔案共用] 存放區（在 [拓撲建立器] 中指定）。</span><span class="sxs-lookup"><span data-stu-id="fbaec-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="fbaec-163">檔案存放區是在拓撲建立器中指定。</span><span class="sxs-lookup"><span data-stu-id="fbaec-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="fbaec-164">SQL Server 資料和記錄檔案，包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="fbaec-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="fbaec-165">您可以在拓撲結構建立器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="fbaec-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="fbaec-166">如需每個資料庫的資料與記錄檔（包括預設名稱）的詳細資料，請參閱部署檔中的[SQL Server 資料和記錄檔案位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fbaec-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fbaec-167">SQL Server 資料和記錄檔案，包括前端資料庫、商務用 Skype 商店及 RtcDatabase 書店的檔案。</span><span class="sxs-lookup"><span data-stu-id="fbaec-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="fbaec-168">它們通常在%localdrive%\CSData. 下</span><span class="sxs-lookup"><span data-stu-id="fbaec-168">They are normally under %localdrive%\CSData.</span></span>


