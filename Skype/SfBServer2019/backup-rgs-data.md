---
title: 在商務用 Skype Server 2019 中備份回應群組服務 (RGS) 資料
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 瞭解如何在商務用 Skype Server 2019 中備份回應群組服務 (RGS) 資料。
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2019
ms.locfileid: "36194116"
---
# <a name="back-up-response-group-service-rgs-data"></a>備份回應群組服務 (RGS) 資料

使用商務用 Skype Server 2019 的 [累計更新], 我們已提供將 RGS 資料納入標準備份的一部分。

## <a name="rgs-data-replication"></a>RGS 資料複製

若要嘗試 RGS 資料複製功能, 請遵循下列步驟:

1. 在您的配對池的所有前端 (FEs) 上安裝7月累計更新。
1. 在成對的池中的兩個成員上安裝 RGS 資料庫:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 在這兩個池上執行下列 Cmdlet, 將現有的 RGS 資料複製到備份資料表, 讓 RGSBackupService 可以拾取資料:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. 啟用 RGSBackupService (這會將 RGSBackupService 全域啟用。 如果此參數設定為 true, RGSBackupService 會開始同步處理成對的池中的 RGS 資料 (兩個池都必須是 CU1)。 稍等幾分鐘, 即可開始使用。 首先, RGS BackupService 狀態將會 NotInitialized。):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. 若要檢查 BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 若要在各個池中檢查 DataReplication, 請使用這些 Cmdlet (這些 Cmdlet 只會顯示擁有者池資料):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 若要檢查擁有者池 RGS 資料及其備份資料:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 透過進行音訊通話來驗證工作流程的功能。
1. 容錯移轉您的 RGS 擁有者池。
1. 透過進行音訊通話來驗證工作流程的功能。
1. 自動回復池。
1. 在來源池中更新 RGS 資料, 然後執行另一個容錯移轉, 以檢查備份池中是否反映了變更。 在容錯移轉前, RGS 的運作方式與行為相同。

> [!TIP]
> 建議您在大量資料上執行這些步驟, 並經常進行容錯移轉與 failbacks。 在此 CU 更新之後建立的任何新的 RGS, 也應該進行複製。

## <a name="rgs-cmdlets"></a>RGS Cmdlet

- 若要檢查 BackupServiceStatus (匯出狀態應為 [最終] 或 [穩定] 狀態)。 [匯入狀態] 應該處於 [正常] 狀態。 RGSBackupservice 應該已啟用。):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 若要在備份池中完全同步處理 RGS 資料 (這會同步處理備份池中的完整 RGS 資料):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 若要完全同步處理備份池中的 RGS 檔資料檔案 (這會同步處理備份池中的完整 RGS 資料):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 若要同步處理備份池中的 RGS delta 資料 (這只會同步處理僅限 RGS 備份區上的增量資料):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- 若要同步處理包括 RGS 在內的所有模組資料:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- 若要停用 RGSBackupService (這會將 RGSBackupService 全域停用。 如果此參數設定為 true, RGSBackupService 將會在所有配對的池上停用。):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
