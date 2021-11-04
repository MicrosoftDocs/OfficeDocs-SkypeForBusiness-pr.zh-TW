---
title: 設定商務用 Skype Server 中的詳細通話記錄及經驗品質設定
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 摘要：瞭解如何在商務用 Skype Server 中設定 CDR 和 QoE。
ms.openlocfilehash: abb6996a7483afb8526731ac69404174883ce313
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745319"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>設定商務用 Skype Server 中的詳細通話記錄及經驗品質設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定 CDR 和 QoE。
  
使用商務用 Skype Server SQL Server Reporting Services 報表設定 CDR 和 QoE 監視。
  
## <a name="configure-cdr-and-qoe"></a>設定 CDR 和 QoE

在您將監視存放區與前端集區相關聯之後，請先設定監視儲存體，然後安裝及設定 SQL Server Reporting Services 和監控報告，以 (CDR) 和經驗品質 (QoE) 管理命令介面商務用 Skype Server 監視。 商務用 Skype Server管理命令介面 Cmdlet 可讓您啟用及停用特定網站或您整個商務用 Skype Server 部署的 CDR 和/或 QoE 監視;您可以使用下列方式做為簡單的命令：
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

當您安裝商務用 Skype Server 時，您也會為 CDR 和 QoE 安裝一組預先定義的全域配置設定。 下表顯示詳細通話記錄較常用的一些設定的預設值：
  
|**屬性**|**描述**|**預設值**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |表示是否啟用 CDR。若為 True，則會收集所有 CDR 記錄並寫入監控資料庫。  <br/> |True  <br/> |
|EnablePurging  <br/> |表示是否要從資料庫定期刪除 CDR 記錄。若為 True，則會在過了 KeepCallDetailForDays (適用於 CDR 記錄) 和 KeepErrorReportForDays (適用於 CDR 錯誤) 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 CDR 記錄。  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |表示在資料庫保留 CDR 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。  <br/> 您可以將 KeepCallDetailForDays 設為 1 到 2562 天 (大約 7 年) 之間的任何整數值。  <br/> |60 天  <br/> |
|KeepErrorReportForDays  <br/> |表示保留 CDR 錯誤報告的天數；任何超過指定天數的報告都將自動刪除。 CDR 錯誤報表是由用戶端應用程式（例如商務用 Skype Server）上傳的診斷報告。  <br/> 您可以將此屬性設為 1 到 2562 天之間的任何整數值。  <br/> |60 天  <br/> |
   
同樣地，下表顯示所選 QoE 設定的預設值：
  
|**屬性**|**描述**|**預設值**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |表示是否啟用 QoE 監控。若為 True，則會收集所有 QoE 記錄並寫入監控資料庫。  <br/> |True  <br/> |
|EnablePurging  <br/> |表示是否要從資料庫定期刪除 QoE 記錄。若為 True，則會在過了 KeepQoEDataForDays 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 QoE 記錄。  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |表示在資料庫保留 QoE 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。  <br/> 您可以將 KeepCallDetailForDays 設為 1 到 2562 天之間的任何整數值。  <br/> |60 天  <br/> |
   
如果您需要修改這些全域設定，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration Cmdlet 執行這項操作。 例如，此命令 (從商務用 Skype Server 管理命令介面內執行) 停用全域範圍內的 CDR 監控;這是透過將 EnableCDR 屬性設定為 False ($False) 進行的：
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

請注意，停用監控並不會解除監控儲存區與前端集區的關聯，也不會解除安裝或影響後端監控資料庫。 當您使用商務用 Skype Server 管理命令介面停用 CDR 或 QoE 監控時，您實際執行的工作會暫時停止商務用 Skype Server 收集和封存監控資料。 在此情況下，如果您想繼續收集及封存 CDR 資料，只需要將 EnableCDR 屬性設回 True ($True) 即可：
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

同樣地，此命令會在全域範圍停止清除 QoE 記錄：
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

除了全域設定之外，也可以對網站範圍指派 CDR 和 QoE 組態設定。這會提供監控作業額外的管理彈性；例如，系統管理員可以啟用 Redmond 網站的 CDR 監控，但停用 Dublin 網站的 CDR 監控。若要在網站範圍建立新的 CDR 組態設定，請使用類似如下的命令：
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

請注意，在網站範圍進行的設定優先順序高於在全域範圍進行的設定。例如，假設在全域範圍啟用 CDR 監控，但在網站範圍 (Redmond 網站) 停用 CDR 監控。這表示不會封存 Redmond 網站使用者的詳細通話記錄資訊，但是會封存其他網站使用者 (亦即全域設定 (而非 Redmond 網站設定) 所管理的使用者) 的詳細通話記錄資訊。
  
您可以使用類似如下的命令，在網站範圍建立新的 QoE 組態設定：
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

如需詳細資訊，請從商務用 Skype Server 管理命令介面內輸入下列命令：
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
