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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192951"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="b2c09-103">商務用 Skype Server 的防病毒掃描排除</span><span class="sxs-lookup"><span data-stu-id="b2c09-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="b2c09-104">與商務用 Skype Server 的防病毒掃描程式交互操作概覽。</span><span class="sxs-lookup"><span data-stu-id="b2c09-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="b2c09-105">本文包含的建議可協助管理員決定在執行受支援版本 Microsoft Windows 的電腦上, 當該電腦與 Active Directory 網域中的防毒軟體搭配使用時, 可能造成不穩定的原因環境或在受管理的商務環境中。</span><span class="sxs-lookup"><span data-stu-id="b2c09-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="b2c09-106">我們建議您暫時將這些程式套用到評估系統。</span><span class="sxs-lookup"><span data-stu-id="b2c09-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="b2c09-107">如果您的系統效能或穩定性是由本文所述的建議所改善, 請與您的防毒軟體廠商聯繫, 以取得相關指示或更新版本的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="b2c09-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="b2c09-108">本文包含的資訊說明如何協助降低安全性設定, 或如何暫時關閉電腦上的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="b2c09-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="b2c09-109">您可以進行這些變更, 瞭解特定問題的性質。</span><span class="sxs-lookup"><span data-stu-id="b2c09-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="b2c09-110">在進行這些變更之前, 我們建議您評估與在您的特定環境中實施此因應措施相關的風險。</span><span class="sxs-lookup"><span data-stu-id="b2c09-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="b2c09-111">如果您實現此因應措施, 請採取任何適當的額外步驟, 以協助保護電腦以找出您的防毒軟體不再進行掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="b2c09-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="b2c09-112">若要確保防病毒掃描程式不會干擾商務用 Skype Server 的作業, 您必須針對執行防病毒掃描程式的每個商務用 Skype 伺服器伺服器或伺服器角色排除特定程式和目錄。</span><span class="sxs-lookup"><span data-stu-id="b2c09-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="b2c09-113">下列處理常式與目錄應被排除:</span><span class="sxs-lookup"><span data-stu-id="b2c09-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="b2c09-114">下列列出的資料夾和檔案位置是商務用 Skype Server 的預設位置。</span><span class="sxs-lookup"><span data-stu-id="b2c09-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="b2c09-115">針對您未使用預設值的任何位置, 請排除您指定給組織的位置, 而不是本主題中指定的預設位置。</span><span class="sxs-lookup"><span data-stu-id="b2c09-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2c09-116">請注意, 某些防毒程式可能需要其排除清單的絕對 (不是相對路徑)。</span><span class="sxs-lookup"><span data-stu-id="b2c09-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="b2c09-117">商務用 Skype Server 進程:</span><span class="sxs-lookup"><span data-stu-id="b2c09-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="b2c09-118">ABServer</span><span class="sxs-lookup"><span data-stu-id="b2c09-118">ABServer.exe</span></span>

  - <span data-ttu-id="b2c09-119">ASMCUSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="b2c09-120">AVMCUSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="b2c09-121">ChannelService</span><span class="sxs-lookup"><span data-stu-id="b2c09-121">ChannelService.exe</span></span>

  - <span data-ttu-id="b2c09-122">ClsAgent</span><span class="sxs-lookup"><span data-stu-id="b2c09-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="b2c09-123">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="b2c09-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="b2c09-124">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="b2c09-125">DataProxy</span><span class="sxs-lookup"><span data-stu-id="b2c09-125">DataProxy.exe</span></span>

  - <span data-ttu-id="b2c09-126">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="b2c09-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="b2c09-127">HealthAgent</span><span class="sxs-lookup"><span data-stu-id="b2c09-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="b2c09-128">IMMCUSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="b2c09-129">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="b2c09-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="b2c09-130">LysSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-130">LysSvc.exe</span></span>

  - <span data-ttu-id="b2c09-131">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="b2c09-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="b2c09-132">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="b2c09-133">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="b2c09-134">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="b2c09-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="b2c09-135">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="b2c09-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="b2c09-136">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="b2c09-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="b2c09-137">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="b2c09-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="b2c09-138">RtcHost</span><span class="sxs-lookup"><span data-stu-id="b2c09-138">RtcHost.exe</span></span>

  - <span data-ttu-id="b2c09-139">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="b2c09-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="b2c09-140">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="b2c09-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="b2c09-141">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="b2c09-141">XmppTGW.exe</span></span>

- <span data-ttu-id="b2c09-142">Windows Fabric 主機服務處理常式:</span><span class="sxs-lookup"><span data-stu-id="b2c09-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="b2c09-143">構造 .exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-143">Fabric.exe</span></span>

  - <span data-ttu-id="b2c09-144">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="b2c09-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="b2c09-145">FabricHost</span><span class="sxs-lookup"><span data-stu-id="b2c09-145">FabricHost.exe</span></span>

- <span data-ttu-id="b2c09-146">IIS 處理常式:</span><span class="sxs-lookup"><span data-stu-id="b2c09-146">IIS processes:</span></span>

  - <span data-ttu-id="b2c09-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="b2c09-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="b2c09-149">SQL Server 後端處理常式:</span><span class="sxs-lookup"><span data-stu-id="b2c09-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2c09-150">請注意, 這些路徑是 SQL Server 版本所特有的。</span><span class="sxs-lookup"><span data-stu-id="b2c09-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="b2c09-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11。MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b2c09-152">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="b2c09-153">%ProgramFiles%\Microsoft SQL Server\MSAS11。MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="b2c09-154">SQL Server 前端程式:</span><span class="sxs-lookup"><span data-stu-id="b2c09-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="b2c09-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12。LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b2c09-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="b2c09-157">標準版安裝 RTC 實例</span><span class="sxs-lookup"><span data-stu-id="b2c09-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="b2c09-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12。RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b2c09-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="b2c09-159">目錄和檔案:</span><span class="sxs-lookup"><span data-stu-id="b2c09-159">Directories and files:</span></span>

  - <span data-ttu-id="b2c09-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b2c09-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="b2c09-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b2c09-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="b2c09-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="b2c09-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2c09-163">請注意, 這些路徑是針對商務用 Skype 伺服器版本所特有。</span><span class="sxs-lookup"><span data-stu-id="b2c09-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="b2c09-164">商務用%programfiles%\Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="b2c09-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="b2c09-165">%programfiles%\Common Files\Skype for Business Server 2015 \ 觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="b2c09-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="b2c09-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b2c09-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="b2c09-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b2c09-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="b2c09-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="b2c09-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="b2c09-169">[檔案共用] 存放區 (在 [拓撲建立器] 中指定)。</span><span class="sxs-lookup"><span data-stu-id="b2c09-169">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="b2c09-170">檔案存放區是在拓撲建立器中指定。</span><span class="sxs-lookup"><span data-stu-id="b2c09-170">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="b2c09-171">SQL Server 資料和記錄檔案, 包括後端資料庫、使用者儲存、封存儲存、監視儲存及應用程式存放區的檔案。</span><span class="sxs-lookup"><span data-stu-id="b2c09-171">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="b2c09-172">您可以在拓撲結構建立器中指定資料庫和記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b2c09-172">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="b2c09-173">如需每個資料庫的資料與記錄檔 (包括預設名稱) 的詳細資料, 請參閱部署檔中的[SQL Server 資料和記錄檔案位置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b2c09-173">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="b2c09-174">SQL Server 資料和記錄檔案, 包括前端資料庫、商務用 Skype 商店及 RtcDatabase 書店的檔案。</span><span class="sxs-lookup"><span data-stu-id="b2c09-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="b2c09-175">它們通常在%localdrive%\CSData. 下</span><span class="sxs-lookup"><span data-stu-id="b2c09-175">They are normally under %localdrive%\CSData.</span></span>


