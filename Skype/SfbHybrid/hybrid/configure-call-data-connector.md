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
localization_priority: Normal
ms.collection: ''
description: 設定呼叫資料連線器的指示，允許使用商務用 Skype Online 工具來查看商務用 Skype 內部部署的遙測。
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726923"
---
# <a name="configure-call-data-connector"></a>設定通話資料連接器

本文說明如何設定呼叫資料連線器--單一工具集，可使用商務用 Skype Online 通話品質儀表板來查看商務用 skype Server 呼叫品質資料 (CQD) 和呼叫分析 (CA) 工具。

如需通話資料連線器權益和必要條件的詳細資訊，例如角色需求和設定混合連線，請參閱 [Plan Call Data Connector](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>啟用監視
 
您必須設定 (CDR) 和經驗品質的呼叫資料記錄， (您的前端集區監控中 QoE) 資料收集，使用本機 LCSCdr 及 QoEMetrics 資料庫;否則，通話分析和通話品質儀表板將不會取得可使用的資料。 設定呼叫資料連線器之前，請遵循在 [商務用 Skype Server 中部署監控](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 中提供的步驟，以設定 CDR 和 QoE 以及基本監視。

> [!IMPORTANT]
> 如果前端集區上未啟用監視，則通話資料連線器將無法運作。

## <a name="enable-call-data-connector"></a>啟用呼叫資料連線器

若要設定及啟用呼叫資料連線器，您將會使用下列 Cmdlet：

| 指令程式| 描述|
| :-----------------|---------------:|
| 新 CsCloudCallDataConnection | 建立線上資料收集器的線上 Cmdlet。|
| CsCloudCallDataConnection | 可檢索現有線上資料收集器的線上 Cmdlet。|  
| CsCloudCallDataConnector | 內部部署 Cmdlet，會檢索由 CsCloudCallDataConnection Cmdlet 所建立的連線資訊。 |
| CsCloudCallDataConnector | 內部部署指令程式，可儲存 CsCloudCallDataConnection Cmdlet 所建立之連線資訊的內部部署複本。 |  
| CsCloudCallDataConnectorConfiguration | 內部部署指令程式，可讓您啟用或停用連接器及自訂範圍層級。|

> [!NOTE]
> 若要清除您的設定並從頭開始，請使用 csclouddatconnectorconfiguration Cmdlet。

### <a name="configure-your-environment"></a>設定您的環境 

若要設定環境以啟用線上資料收集器，您必須先以系統管理員身分登入商務用 Skype Online PowerShell。 如需詳細資訊，請參閱 [使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

有兩種方法可登入商務用 Skype Online PowerShell:

- 從商務用 Skype Server 2019 管理命令介面 (建議方法) 
- 從另一個 PowerShell 會話

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>從商務用 Skype Server 管理命令介面 (，登入商務用 Skype Online PowerShell 建議方法) 

1. 如果是第一次啟用連接器，請執行下列命令：

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果您收到連線已存在的錯誤，這表示您的租使用者的通話資料連線已存在。 在此情況下，請執行下列命令： 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>從其他 PowerShell 會話登入商務用 Skype Online PowerShell (選用方法) 

1.  如果是第一次啟用連接器，請執行下列命令： 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  如果您收到連線已存在的錯誤，這表示您的租使用者的通話資料連線已存在。 在此情況下，請執行下列命令： 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上述命令的輸出包含 token 值，當您設定內部部署環境時，您會需要此值，如下所示：

在商務用 Skype Server 管理命令介面中，指定下列命令：

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>設定範圍

您可以在商務用 Skype Server 管理命令介面中使用 CsCloudCallDataConnectorConfiguration 指令程式，為特定網站或整個商務用 Skype Server 部署啟用呼叫資料連線器。 例如，下列命令會在全域範圍內啟用呼叫資料連線器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了通用設定之外，也可以將呼叫資料連線器設定設定指派給網站範圍。 這會在監視時提供額外的管理彈性。 例如，系統管理員可以為 Redmond 網站啟用呼叫資料連線器轉寄，但停用都柏林網站的呼叫資料連線器轉寄，如下列範例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在網站範圍設定的設定會優先于在全域範圍設定的設定。 例如，假設在全域範圍啟用呼叫資料連線器轉移，但在 Redmond 網站) 的網站範圍 (停用。 這表示不會為 Redmond 網站中的使用者轉寄詳細通話記錄及 QoE 資訊。 不過，其他網站中的使用者 (也就是說，全域設定所管理的使用者，而不是 Redmond 網站設定) 會有其詳細通話記錄及 QoE 資訊轉寄。

下表顯示「呼叫資料連線器」所使用之最常使用設定的值：  

|屬性	|描述|預設值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |會指出是否已啟用呼叫資料連線器。 如果為 True，則監控記錄會轉寄至線上監控。  <br/> |$False  <br/> |
| 身分識別 | 決定命令的範圍層級：全域或網站。   | 全球  |

## <a name="disable-call-data-connector"></a>停用通話資料連線器

停用呼叫資料連線器時，不會解除與前端集區的關聯，也不會卸載，否則會影響後端監控資料庫。 當您停用通話資料連線器時，會停止將通話資料上傳至雲端的商務用 Skype Server。 

您可以從商務用 Skype Server 管理命令介面中，使用 CsCloudCallDataConnectorConfiguration 指令程式來停用通話資料連線器。 例如，下列命令會透過將 EnableCallDataConnector 屬性設定為 $False，停用全域範圍的呼叫資料連線器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果您想要繼續將來電資料上傳至雲端，請將 EnableCallDataConnector 屬性設定回 $True，如下列範例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>透過線上儀表板查看內部部署資料

 啟用呼叫資料連線器之後，您可以在「呼叫分析儀表板」或「通話品質」儀表板上查看您的內部部署呼叫資料，如  [使用呼叫分析來疑難排解不良品質](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) ，以及 [開啟和使用 Microsoft 小組和商務用 Skype Online 的通話品質儀表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)。

## <a name="for-more-information"></a>相關資訊

如需 Cmdlet 的詳細資訊，您可以使用來自商務用 Skype Server 管理命令介面的 Get-Help 命令。 例如：

Get-Help CsCloudCallDataConnector |更

Get-Help Set-CsCloudCallDataConnector |更

Get-Help Set-CsCloudCallDataConnectorConfiguration |更
