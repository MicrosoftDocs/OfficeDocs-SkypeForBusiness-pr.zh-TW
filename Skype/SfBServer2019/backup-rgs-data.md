---
title: 備份商務用 Skype Server 2019 中回應群組服務 (RGS) 資料
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 瞭解如何備份商務用 Skype Server 2019 中 (RGS) 資料的回應群組服務。
ms.openlocfilehash: 7e3e4116a281584da7afc1807fe58e79d2528183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581157"
---
# <a name="back-up-response-group-service-rgs-data"></a>備份回應群組服務 (RGS) 資料

隨著商務用 Skype Server 2019 年7月累計更新，我們已包含將 RGS 資料包含在標準備份中的功能。

## <a name="rgs-data-replication"></a>RGS 資料複寫

若要嘗試 RGS 資料複寫功能，請遵循下列步驟：

1. 在成對集區的所有前端 (FEs) 上安裝七月累計更新。
1. 在成對集區的兩個成員上安裝 RGS 資料庫：
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 在這兩個集區上執行下列 Cmdlet，將現有的 RGS 資料複寫到備份資料表，以供 RGSBackupService 挑選資料：
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. 啟用 RGSBackupService (此功能會在全域啟用 RGSBackupService。 如果此參數設為 true，則 RGSBackupService 會開始同步處理成對集區上的 RGS 資料 (這兩個集區都必須 CU1) 。 等候幾分鐘讓它開始。 在最初，RGS BackupService 狀態會是 NotInitialized。 ) ：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. 若要檢查 BackupServiceStatus：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 若要檢查跨集區的 DataReplication，請使用下列 Cmdlet (這些 Cmdlet 只會顯示擁有者集區資料) ：
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 若要檢查擁有者集區 RGS 資料及其備份資料：
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 在工作流程中進行音訊撥號，以確認工作流程功能。
1. 容錯移轉您的 RGS 擁有者集區。
1. 在工作流程中進行音訊撥號，以確認工作流程功能。
1. 容錯回復集區。
1. 在來源集區上更新 RGS 資料，並執行其他容錯移轉，以檢查備份組區上反映的變更。 RGS 的運作方式應該與容錯移轉之前的行為相同。

> [!TIP]
> 建議您在大量資料上執行這些步驟，並且經常進行容錯移轉和 failbacks。 在此 CU 更新之後建立的任何新的 RGS 也應複寫。

## <a name="rgs-cmdlets"></a>RGS Cmdlet

- 若要檢查 BackupServiceStatus (匯出狀態應該是 [最後] 或 [穩定] 狀態。 [匯入] 狀態應為 [正常] 狀態。 RGSBackupservice 應啟用。 ) ：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 若要在備份組區上完全同步處理 RGS 資料 (這會同步處理備份組區上的所有 RGS 資料。 ) ：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 若要完全同步處理備份組區上的 RGS 資料記錄 (這會同步處理備份組區上的所有 RGS 資料。 ) ：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 若要同步處理備份組區上的 RGS delta 資料 (這只會同步處理僅限 RGS 備份組區上的 delta 資料。 ) ：
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- 若要同步處理所有模組資料（包括 RGS）：
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- 若要停用 RGSBackupService (此方式會停用 RGSBackupService。 如果此參數設為 true，則會在所有配對的集區上停用 RGSBackupService。 ) ：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
