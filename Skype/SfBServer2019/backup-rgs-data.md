---
title: 在商務用 Skype Server 2019 中備份回應群組服務（RGS）資料
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 瞭解如何在商務用 Skype Server 2019 中備份回應群組服務（RGS）資料。
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824067"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="519ad-103">備份回應群組服務（RGS）資料</span><span class="sxs-lookup"><span data-stu-id="519ad-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="519ad-104">使用商務用 Skype Server 2019 的 [累計更新]，我們已提供將 RGS 資料納入標準備份的一部分。</span><span class="sxs-lookup"><span data-stu-id="519ad-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="519ad-105">RGS 資料複製</span><span class="sxs-lookup"><span data-stu-id="519ad-105">RGS data replication</span></span>

<span data-ttu-id="519ad-106">若要嘗試 RGS 資料複製功能，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="519ad-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="519ad-107">在您的配對池的所有前端（FEs）上安裝7月累計更新。</span><span class="sxs-lookup"><span data-stu-id="519ad-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="519ad-108">在成對的池中的兩個成員上安裝 RGS 資料庫：</span><span class="sxs-lookup"><span data-stu-id="519ad-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="519ad-109">在這兩個池上執行下列 Cmdlet，將現有的 RGS 資料複製到備份資料表，讓 RGSBackupService 可以拾取資料：</span><span class="sxs-lookup"><span data-stu-id="519ad-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="519ad-110">啟用 RGSBackupService （這會將 RGSBackupService 全域啟用。</span><span class="sxs-lookup"><span data-stu-id="519ad-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="519ad-111">如果此參數設定為 true，RGSBackupService 會開始同步處理成對的池中的 RGS 資料（兩個池都必須是 CU1）。</span><span class="sxs-lookup"><span data-stu-id="519ad-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="519ad-112">稍等幾分鐘，即可開始使用。</span><span class="sxs-lookup"><span data-stu-id="519ad-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="519ad-113">首先，RGS BackupService 狀態將會 NotInitialized。）：</span><span class="sxs-lookup"><span data-stu-id="519ad-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="519ad-114">若要檢查 BackupServiceStatus：</span><span class="sxs-lookup"><span data-stu-id="519ad-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="519ad-115">若要在各個池中檢查 DataReplication，請使用這些 Cmdlet （這些 Cmdlet 只會顯示擁有者池資料）：</span><span class="sxs-lookup"><span data-stu-id="519ad-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="519ad-116">若要檢查擁有者池 RGS 資料及其備份資料：</span><span class="sxs-lookup"><span data-stu-id="519ad-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="519ad-117">透過進行音訊通話來驗證工作流程的功能。</span><span class="sxs-lookup"><span data-stu-id="519ad-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="519ad-118">容錯移轉您的 RGS 擁有者池。</span><span class="sxs-lookup"><span data-stu-id="519ad-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="519ad-119">透過進行音訊通話來驗證工作流程的功能。</span><span class="sxs-lookup"><span data-stu-id="519ad-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="519ad-120">自動回復池。</span><span class="sxs-lookup"><span data-stu-id="519ad-120">Failback the pool.</span></span>
1. <span data-ttu-id="519ad-121">在來源池中更新 RGS 資料，然後執行另一個容錯移轉，以檢查備份池中是否反映了變更。</span><span class="sxs-lookup"><span data-stu-id="519ad-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="519ad-122">在容錯移轉前，RGS 的運作方式與行為相同。</span><span class="sxs-lookup"><span data-stu-id="519ad-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="519ad-123">建議您在大量資料上執行這些步驟，並經常進行容錯移轉與 failbacks。</span><span class="sxs-lookup"><span data-stu-id="519ad-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="519ad-124">在此 CU 更新之後建立的任何新的 RGS，也應該進行複製。</span><span class="sxs-lookup"><span data-stu-id="519ad-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="519ad-125">RGS Cmdlet</span><span class="sxs-lookup"><span data-stu-id="519ad-125">RGS cmdlets</span></span>

- <span data-ttu-id="519ad-126">若要檢查 BackupServiceStatus （匯出狀態應為 [最終] 或 [穩定] 狀態）。</span><span class="sxs-lookup"><span data-stu-id="519ad-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="519ad-127">[匯入狀態] 應該處於 [正常] 狀態。</span><span class="sxs-lookup"><span data-stu-id="519ad-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="519ad-128">RGSBackupservice 應該已啟用。）：</span><span class="sxs-lookup"><span data-stu-id="519ad-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="519ad-129">若要在備份池中完全同步處理 RGS 資料（這會同步處理備份池中的完整 RGS 資料）：</span><span class="sxs-lookup"><span data-stu-id="519ad-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="519ad-130">若要完全同步處理備份池中的 RGS 檔資料檔案（這會同步處理備份池中的完整 RGS 資料）：</span><span class="sxs-lookup"><span data-stu-id="519ad-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="519ad-131">若要同步處理備份池中的 RGS delta 資料（這只會同步處理僅限 RGS 備份區上的增量資料）：</span><span class="sxs-lookup"><span data-stu-id="519ad-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="519ad-132">若要同步處理包括 RGS 在內的所有模組資料：</span><span class="sxs-lookup"><span data-stu-id="519ad-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="519ad-133">若要停用 RGSBackupService （這會將 RGSBackupService 全域停用。</span><span class="sxs-lookup"><span data-stu-id="519ad-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="519ad-134">如果此參數設定為 true，RGSBackupService 將會在所有配對的池上停用。）：</span><span class="sxs-lookup"><span data-stu-id="519ad-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
