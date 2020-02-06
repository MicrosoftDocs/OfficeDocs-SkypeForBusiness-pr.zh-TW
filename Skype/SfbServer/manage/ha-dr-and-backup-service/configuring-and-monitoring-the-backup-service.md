---
title: 設定和監控備份服務
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用商務用 Skype Server Management Shell 命令來設定及監視備份服務。
ms.openlocfilehash: 80b15b2306807fe5bfc36449e16953466e3af75c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818214"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>在商務用 Skype Server 中設定及監視備份服務

您可以使用下列商務用 Skype Server Management Shell 命令來設定及監視備份服務。 若要還原儲存在前端文件庫檔案存放區中的會議資訊，請參閱下方的[使用備份服務還原會議內容](#restore-conference-contents-using-the-backup-service)。

> [!NOTE]  
> RTCUniversalServerAdmins 群組是唯一具有執行**CsBackupServiceStatus**預設許可權的群組。 若要使用這個 Cmdlet，請以這個群組的成員身分登入。 或者，您可以使用**CsBackupServiceConfiguration** Cmdlet，將此命令的存取權授與其他群組（例如，CSAdministrator）。

## <a name="to-see-the-backup-service-configuration"></a>若要查看備份服務設定

執行下列 Cmdlet：

    Get-CsBackupServiceConfiguration

SyncInterval 的預設值是兩分鐘。

## <a name="to-set-the-backup-service-sync-interval"></a>設定備份服務同步處理間隔

執行下列 Cmdlet：

    Set-CsBackupServiceConfiguration -SyncInterval interval

例如，下列會將間隔設定為三分鐘。

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> 雖然您可以使用這個 Cmdlet 來變更備份服務的預設同步處理間隔，但除非是絕對必要，否則您不應該這麼做，因為同步處理間隔對備份服務效能和復原點目標（RPO）有很大的影響。

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>取得特定文件庫的備份服務狀態

執行下列 Cmdlet：

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> 備份服務同步處理狀態是從池（P1）定義 unidirectionally 到其備份池（P2）。 從 P1 到 P2 的同步處理狀態，可能與 P2 與 P1 不同。 針對 P1 到 P2，如果在 P1 中所做的所有變更都會在同步處理間隔內完全複製到 P2，則備份服務處於「穩定」狀態。 如果沒有其他變更要從 P1 同步處理到 P2，則會處於 [最終] 狀態。 這兩種狀態表示執行 Cmdlet 時備份服務的快照。 這並不表示傳回的狀態將會持續保持不變。 特別是，只有在執行 Cmdlet 之後，P1 不會產生任何變更時，才會繼續保留 [最終] 狀態。 在 P1 成為**CsPoolfailover**執行邏輯的一部分之後，p1 被置於唯讀模式之後，就會發生失敗情況。

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>若要取得特定資源庫之備份關聯的相關資訊

執行下列 Cmdlet：

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>強制備份服務同步處理

執行下列 Cmdlet：

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>使用備份服務還原會議內容 

如果在 [前端] 池的 [檔案存放區] 中儲存的會議資訊無法使用，您必須還原此資訊，讓駐留在該池中的使用者保留其會議資料。 如果有遺失會議資料的前端池是與另一個前端池進行配對，您可以使用 [備份服務] 來還原資料。

如果整個池失敗，而且您必須將其使用者容錯移轉至備份池，也必須執行此工作。 當這些使用者傳回容錯移轉至原始池時，您必須使用此程式將其會議內容複寫回其原始池。

假設 Pool1 與 Pool2 成對，而 Pool1 中的會議資料遺失。 您可以使用下列 Cmdlet 來喚醒呼叫備份服務來還原內容：

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

還原會議內容可能需要一些時間，視其大小而定。 您可以使用下列 Cmdlet 來檢查進程狀態：

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

此程式會在此 Cmdlet 針對資料會議模組傳回穩定狀態的值時完成。
