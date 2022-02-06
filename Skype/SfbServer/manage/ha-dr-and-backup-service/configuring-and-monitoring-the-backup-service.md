---
title: 設定及監視備份服務
ms.reviewer: null
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 您可以使用商務用 Skype Server 管理命令介面命令來設定及監視備份服務。
---

# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>在商務用 Skype Server 中設定及監視備份服務

您可以使用下列商務用 Skype Server 管理命令介面命令來設定及監視備份服務。 若要還原儲存在前端集區之檔案存放區中的會議資訊，請參閱下面 [的使用備份服務還原會議內容](#restore-conference-contents-using-the-backup-service)。

> [!NOTE]  
> 根據預設，RTCUniversalServerAdmins 群組是具有執行 **Get-CsBackupServiceStatus** 許可權的唯一群組。 若要使用此 Cmdlet，請以此群組的成員身分登入。 或者，您可以將此命令的存取權授與其他群組 (例如，使用 **Set-CsBackupServiceConfiguration** 指令程式 CSAdministrator) 。

## <a name="to-see-the-backup-service-configuration"></a>若要查看備份服務設定

執行下列 Cmdlet：<br/><br/>Get-CsBackupServiceConfiguration

SyncInterval 的預設值是兩分鐘。

## <a name="to-set-the-backup-service-sync-interval"></a>設定備份服務同步處理間隔

執行下列 Cmdlet：<br/><br/>Set-CsBackupServiceConfiguration SyncInterval 間隔

例如，下列會將間隔設定為3分鐘。<br/><br/>Set-CsBackupServiceConfiguration-SyncInterval 00:03:00


> [!IMPORTANT]  
> 雖然您可以使用此 Cmdlet 變更備份服務的預設同步處理間隔，但除非完全必要，否則不應這麼做，因為同步處理間隔對備份服務效能具有極大的影響，而且復原點目標 (RPO) 。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>取得特定集區的備份服務狀態

執行下列 Cmdlet：<br/><br/>Get-CsBackupServiceStatus PoolFqdn \<pool-FQDN>

> [!NOTE]  
> 備份服務同步處理狀態是從 (P1) 集區 unidirectionally 至其備份組區 (P2) 所定義。 從 P1 到 P2 的同步處理狀態可能不同于從 P2 到 P1 的狀態。 若為 P1，當 P1 中所做的所有變更都會在同步處理間隔內完全複寫至 P2 時，備份服務處於「穩定」狀態。 如果沒有其他要從 P1 同步處理的變更，則為 "final" 狀態。 這兩種狀態都會指出執行 Cmdlet 時備份服務的快照。 這並不表示傳回的狀態會在此後保留。 特別是，當執行 Cmdlet 後，如果 P1 不會產生任何變更，則 "final" 狀態會繼續保留。 當 p1 成為 **CsPoolfailover** 執行邏輯的一部分時，p1 被置於唯讀模式後，就會發生失敗的情況。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要取得特定集區之備份關係的相關資訊

執行下列 Cmdlet：<br/><br/>Get-CsPoolBackupRelationship PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>強制執行備份服務同步處理

執行下列 Cmdlet：<br/><br/>Invoke-CsBackupServiceSync PoolFqdn \<poolFqdn> [-BackupModule {All |PresenceFocus |DataConf |CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>使用備份服務還原會議內容 

如果在前端集區的檔案存放區中儲存的會議資訊無法使用，則必須還原此資訊，以便集區中的使用者保留其會議資料。 如果已遺失會議資料的前端集區與另一個前端集區成對，您可以使用備份服務還原資料。

如果整個集區失敗，而必須將使用者容錯移轉至備份集區，也必須執行此工作。當這些使用者容錯移轉回原始集區時，也必須使用此程序，將會議內容複製回原始集區。

假設 Pool1 與 Pool2 配對，而 Pool1 中的會議資料遺失。 您可以使用下列 Cmdlet 來調用備份服務，以還原內容：<br/><br/>Invoke-CsBackupServiceSync PoolFqdn \<Pool2 FQDN> BackupModule ConfServices。 DataConf

視會議內容的大小而定，還原會議內容可能需要一些時間。可以使用下列 Cmdlet 檢查處理狀態：<br/><br/>Get-CsBackupServiceStatus PoolFqdn \<Pool2 FQDN> BackupModule ConfServices。 DataConf

當此 Cmdlet 傳回資料會議模組的「穩定狀態」值時，處理就已完成。
