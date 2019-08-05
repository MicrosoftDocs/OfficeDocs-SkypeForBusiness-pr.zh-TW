---
title: 設定通話資料連線器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 設定呼叫資料連線器的指示, 可讓您使用商務用 Skype Online 工具查看商務用 skype 內部部署的遙測。
ms.openlocfilehash: 1851e1e0c430107a27d706f7bc16ad974c5abaed
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185554"
---
# <a name="configure-call-data-connector"></a>設定通話資料連線器

本文說明如何設定 [呼叫資料連線器]-單一工具集, 可讓您使用商務用 Skype Online 通話品質儀表板 (CQD) 和通話分析 (CA) 工具來查看商務用 Skype Server 通話品質資料。 

> [!NOTE]
> 在公開預覽版發行時, 只有 [呼叫分析] 儀表板可供使用。

如需通話資料連線器優點與必備元件 (例如角色需求及設定混合式連線) 的詳細資訊, 請參閱[規劃通話資料連線器](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>啟用監視
 
您必須在前端池監控中設定呼叫資料錄製 (CDR) 與品質 (QoE) 資料收集, 並使用本機 LCSCdr 和 QoEMetrics 資料庫;否則, [通話分析] 與 [通話品質儀表板] 不會取得資料來使用。 在您設定呼叫資料連線器之前, 請遵循在[商務用 Skype Server 中部署監視](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)中提供的步驟, 來設定 CDR 與 QoE, 以及基本監視。

> [!IMPORTANT]
> 如果未在前端池中啟用監視, 則呼叫資料連線器將無法運作。

## <a name="enable-call-data-connector"></a>啟用呼叫資料連線器

若要設定及啟用呼叫資料連線器, 您將會使用下列 Cmdlet:

| Cmdlet| 說明|
| :-----------------|---------------:|
| 新-CsCloudCallDataConnection | 建立線上資料收集器的線上 Cmdlet。|
| CsCloudCallDataConnection | 可檢索現有線上資料收集器的線上 Cmdlet。|  
| CsCloudCallDataConnector | 可檢索由 CsCloudCallDataConnection Cmdlet 建立之連線資訊的內部部署 Cmdlet。 |
| Set-CsCloudCallDataConnector | 儲存由 CsCloudCallDataConnection Cmdlet 所建立之連線資訊之內部部署複本的內部部署 Cmdlet。 |  
| Set-CsCloudCallDataConnectorConfiguration | 可讓您啟用或停用連接器及自訂範圍層級的內部部署 Cmdlet。|

> [!NOTE]
> 若要清除您的設定並重新開始, 請使用 csclouddatconnectorconfiguration Cmdlet。

### <a name="configure-your-environment"></a>設定您的環境 

若要設定您的環境以啟用線上資料收集器, 您必須先以系統管理員身分登入商務用 Skype Online PowerShell。 如需詳細資訊, 請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

有兩種方法可以登入商務用 Skype Online PowerShell:

- 從商務用 Skype Server 2019 管理命令介面 (建議的方法)
- 從另一個 PowerShell 會話

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>從商務用 Skype Server management shell 登入商務用 Skype Online PowerShell (建議的方法)

1. 如果是第一次啟用連接器, 請執行下列命令:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果您收到連線已存在的錯誤, 這表示您的租使用者已存在呼叫資料連線。 在這種情況下, 請執行命令: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>從另一個 PowerShell 會話登入商務用 Skype Online PowerShell (選用方法)

1.  如果是第一次啟用連接器, 請執行下列命令: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  如果您收到連線已存在的錯誤, 這表示您的租使用者已存在呼叫資料連線。 在這種情況下, 請執行命令: 

    ```
    Get-CsCloudCallDataConnection  
    ```

上述命令的輸出包含標記值, 在您設定內部部署環境時, 您需要按照下列步驟進行:

在商務用 Skype Server management 命令介面中, 指定下列命令:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>設定範圍

您可以從商務用 Skype Server management shell 中使用 CsCloudCallDataConnectorConfiguration Cmdlet, 為特定網站或整個商務用 Skype Server 部署啟用呼叫資料連線器。 例如, 下列命令可在全域範圍內啟用呼叫資料連線器:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全域設定之外, 您還可以將呼叫資料連線器配置設定指派給網站範圍。 這可在監視時提供額外的管理靈活性。 例如, 管理員可以為雷德蒙的網站啟用呼叫資料連線器轉寄, 但停用都柏林網站的呼叫資料連線器轉移, 如下列範例所示:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在網站範圍設定的設定, 會優先于在全域範圍中設定的設定。 例如, 假設在全域範圍內啟用 [呼叫資料連線器轉寄], 但在網站範圍停用 (針對雷德蒙的網站)。 這表示不會針對雷德蒙者網站上的使用者轉寄通話詳細資料錄製及 QoE 資訊。 不過, 其他網站中的使用者 (也就是由全域設定所管理的使用者, 而不是雷德蒙板網站設定), 會將通話詳細資料錄製並 QoE 資訊轉寄。

[通話資料連線器] 使用的最常用設定值, 如下表所示:  

|Property|說明|預設值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指出是否已啟用 [呼叫資料連線器]。 如果為 True, 則會將監視記錄轉寄到線上監視。  <br/> |$False  <br/> |
| Identity | 決定命令的範圍階層: [全域] 或 [網站]。   | 化  |

## <a name="disable-call-data-connector"></a>停用通話資料連線器

停用 [呼叫資料連線器] 不會解除與 [前端] 池中的 [監視] 儲存體的關聯, 也不會卸載或以其他方式影響後端監視資料庫。 當您停用 [呼叫資料連線器] 時, 您將無法將商務用 Skype Server 從上傳通話資料到雲端。 

您可以從商務用 Skype Server management shell 中使用 CsCloudCallDataConnectorConfiguration Cmdlet 來停用呼叫資料連線器。 例如, 下列命令會透過將 EnableCallDataConnector 屬性設定為 $False 來停用全域範圍的呼叫資料連線器:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果您想要繼續上傳通話資料至雲端, 請將 EnableCallDataConnector 屬性設回 $True, 如下列範例所示:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>透過線上儀表板來查看內部部署資料

 啟用 [呼叫資料連線器] 之後, 您可以在 [通話分析] 儀表板上查看您的內部部署呼叫資料, 如[使用通話分析來排查品質差的問題](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)所述。


## <a name="for-more-information"></a>如需詳細資訊

如需有關 Cmdlet 的詳細資訊, 您可以使用商務用 Skype Server Management Shell 中的 [取得協助] 命令。 例如：

Get-help CsCloudCallDataConnector |等

Get-help CsCloudCallDataConnector |等

Get-help CsCloudCallDataConnectorConfiguration |等
