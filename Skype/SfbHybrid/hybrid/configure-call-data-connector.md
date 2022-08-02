---
title: 設定通話資料連接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 設定通話資料連線器的指示，允許使用 商務用 Skype Online 工具檢視來自內部部署商務用 Skype遙測。
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156931"
---
# <a name="configure-call-data-connector"></a>設定通話資料連接器

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


本文說明如何設定通話資料連線器，這是單一工具組，可讓您使用 Microsoft 通話品質儀表板 商務用 Skype Server (CQD) 和通話分析 (CA) 工具檢視通話品質資料。

如需通話資料連線器優點和必要條件的詳細資訊，例如角色需求和設定混合式連線，請參閱 [規劃通話資料連線器](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>啟用監視
 
您必須在使用本機 LCSCdr 和 QoEMetrics 資料庫監視的前端集區中，設定通話資料記錄 (CDR) 和體驗品質 (QoE) 資料收集;否則，通話分析和通話品質儀表板將無法取得要使用的資料。 設定通話資料連線器之前，請遵循在[商務用 Skype Server 中部署監視中](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)提供的步驟來設定 CDR 和 QoE 以及基本監視。

> [!IMPORTANT]
> 如果前端集區上未啟用監視，呼叫資料連線器將無法運作。

## <a name="enable-call-data-connector"></a>啟用通話資料連線器

若要設定並啟用通話資料連線器，您將使用下列 Cmdlet：

| 指令程式| 描述|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 建立線上資料收集器的線上 Cmdlet。|
| Get-CsCloudCallDataConnection | 可擷取現有線上資料收集器的線上 Cmdlet。|  
| Get-CsCloudCallDataConnector | 內部部署 Cmdlet，擷取 New-CsCloudCallDataConnection Cmdlet 所建立的連線資訊。 |
| Set-CsCloudCallDataConnector | 內部部署 Cmdlet，可儲存New-CsCloudCallDataConnection Cmdlet 所建立之連線資訊的內部部署複本。 |  
| Set-CsCloudCallDataConnectorConfiguration | 內部部署 Cmdlet，可讓您啟用或停用連接器，並自訂範圍層級。|

> [!NOTE]
> 若要清除您的設定並重新開始，請使用 Remove-csclouddatconnectorconfiguration Cmdlet。

### <a name="configure-your-environment"></a>設定您的環境 

若要設定環境以啟用線上資料收集器，您必須先以系統管理員身分登入 Microsoft Teams PowerShell 模組。 如需詳細資訊，請參閱 [Microsoft Teams PowerShell 概觀](/microsoftteams/teams-powershell-overview)。

登入 Microsoft Teams PowerShell 模組的方法有兩種：

- 從 商務用 Skype Server 2019 管理命令介面 (建議的方法) 
- 從另一個 PowerShell 會話

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>從商務用 Skype Server管理命令介面 (建議的方法登入 Microsoft Teams PowerShell 模組) 

1. 如果第一次啟用連接器，請執行下列命令：

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果您收到連線已存在的錯誤，這表示您的租使用者的呼叫資料連線已經存在。 在此情況下，請執行 命令： 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>從另一個 PowerShell 會話 (選擇性方法登入 Microsoft Teams PowerShell 模組) 

1.  如果第一次啟用連接器，請執行下列命令： 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  如果您收到連線已存在的錯誤，這表示您的租使用者的呼叫資料連線已經存在。 在此情況下，請執行 命令： 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上述命令的輸出包含權杖值，您在設定內部部署環境時需要此值，如下所示：

從商務用 Skype Server管理命令介面內，指定下列命令：

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>設定範圍

您可以從商務用 Skype Server管理命令介面內使用 Set-CsCloudCallDataConnectorConfiguration Cmdlet，為特定月臺或整個商務用 Skype Server部署啟用呼叫資料連線器。 例如，下列命令會在全域範圍啟用呼叫資料連線器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全域設定之外，通話資料連線器組態設定也可以指派給月臺範圍。 這可在監視方面提供額外的管理彈性。 例如，系統管理員可以啟用 Redmond 網站的通話資料連線器轉送，但停用為愛爾蘭月臺的通話資料連線器轉送，如下列範例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在網站範圍設定的設定優先于全域範圍設定的設定。 例如，假設呼叫資料連線器轉送已在全域範圍啟用，但在 Redmond 網站) 的網站範圍 (停用。 這表示 Redmond 網站中的使用者不會轉接通話詳細資料錄製和 QoE 資訊。 不過，其他網站中的使用者 (也就是說，由全域設定所管理的使用者，而不是 Redmond 網站設定) 將會轉送其通話詳細資料記錄和 QoE 資訊。

呼叫資料連線器所使用之最常用設定的值如下表所示：  

|屬性	|描述|預設值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指出是否啟用呼叫資料連線器。 如果為 True，則會將監視記錄轉送到線上監視。  <br/> |$False  <br/> |
| 身分識別 | 決定命令的範圍層級：全域或網站。   | 全球  |

## <a name="disable-call-data-connector"></a>停用呼叫資料連線器

停用呼叫資料連線器不會解除監視存放區與前端集區的關聯，也不會卸載或影響後端監視資料庫。 當您停用通話資料連線器時，您會停止商務用 Skype Server將通話資料上傳至雲端。 

您可以從商務用 Skype Server管理殼層內使用 Set-CsCloudCallDataConnectorConfiguration Cmdlet 來停用呼叫資料連線器。 例如，下列命令會將 EnableCallDataConnector 屬性設定為 $False，以停用全域範圍的呼叫資料連線器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果您想要繼續將呼叫資料上傳至雲端，請將 EnableCallDataConnector 屬性設定回 $True，如下列範例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>透過線上儀表板檢視內部部署資料

 啟用通話資料連線器之後，您可以在通話分析儀表板或通話品質儀表板上檢視內部部署通話資料，如[使用通話分析來疑難排解品質不佳](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)和[開啟並使用 Microsoft Teams 和 商務用 Skype Online 的通話品質儀表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)中所述。

## <a name="for-more-information"></a>相關資訊

如需 Cmdlet 的詳細資訊，您可以從 商務用 Skype Server 管理命令介面使用 Get-Help 命令。 例如：

Get-Help Get-CsCloudCallDataConnector |更多

Get-Help Set-CsCloudCallDataConnector |更多

Get-Help Set-CsCloudCallDataConnectorConfiguration |更多
