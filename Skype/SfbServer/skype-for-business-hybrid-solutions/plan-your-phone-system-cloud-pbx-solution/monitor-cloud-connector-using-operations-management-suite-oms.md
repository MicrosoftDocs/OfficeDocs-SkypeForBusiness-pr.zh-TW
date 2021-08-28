---
title: 使用 Operations Management Suite (OMS) 監控 Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 閱讀此主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視您的雲端連接器版本2.1 和更新版本。
ms.openlocfilehash: 43ebfe689e113daa063a2ef2ed0d9b68a9d9d66a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627725"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 監控 Cloud Connector

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

閱讀此主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視您的雲端連接器版本2.1 和更新版本。

您現在可以使用 Operations Management Suite (OMS) Microsoft 雲端 IT 管理解決方案，監視您的雲端連接器版本2.1 和更新版本的部署。 OMS 記錄分析可讓您監視及分析資源的可用性和效能（包括實體和虛擬機器）。 如需 OMS 和記錄分析的詳細資訊，請參閱 [什麼是 Operations Management Suite (OMS) ？](/azure/operations-management-suite/operations-management-suite-overview)

本主題包含下列各節：

- 必要條件

- 設定 Cloud Connector 以使用 OMS

- 設定 OMS

- 分析 Log Analytics 存放庫中的警示

- 建議的監控集

## <a name="prerequisites"></a>必要條件

您必須先具備下列各項，您才能使用 OMS 來監視您的雲端連接器部署：

- **Azure 帳戶和 OMS 工作區。** 如果您尚無 Azure 帳戶，您必須建立一個，以使用 OMS 記錄分析。 如需如何建立 Azure 帳戶及設定 OMS 工作區的詳細資訊，請參閱 [開始使用 Log Analytics 工作區](/azure/log-analytics/log-analytics-get-started)。

- **雲端連接器版本2.1 或更新版本**

- 需要記錄分析-雲端連接器監控需要 **新的記錄搜尋**。 如需詳細資訊，請參閱 [Upgrade a Azure Log Analytics workspace to new Log search](/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>設定 Cloud Connector 以使用 OMS

您必須將雲端連接器內部部署環境設定為使用 OMS。 若要這麼做，您將需要 oms 工作區識別碼和金鑰，您可以使用 oms 入口網站來尋找，如下所示： \> \> Windows 伺服器的設定：

![雲端連接器 OMS 的螢幕擷取畫面](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

如何設定 Cloud Connector 以使用 OMS 取決於您的案例：

- 若要 **安裝新的雲端連接器裝置，或想要重新部署裝置**，請在執行 CcAppliance 之前，先遵循下列步驟：

    1. 在 [CloudConnector.ini 檔案 [通用] 區段中，將 OMSEnabled 參數設定為 True。

        每次部署或升級 Cloud Connector 時，它都會嘗試將 OMS 代理程式自動安裝至 Vm。 啟用這項功能，使 OMS 代理程式可以繼續使用雲端連接器自動更新。

    2. 若要設定 OMS 識別碼和機碼，請執行 Set-CcCredential-AccountType OMSWorkspace。 

- **若要在現有的雲端連接器裝置上安裝 OMS 代理程式**，請遵循下列步驟：

    1. 在 [CloudConnector.ini 檔案 [通用] 區段中，設定 OMSEnabled = true。 

    2. 執行匯入-CcConfiguration。 

    3. 執行安裝-CcOMSAgent。 

        > [!NOTE]
        > 如果從未設定 OMSWorkspace 認證，當您執行 install-CcOMSAgent 時，系統會提示您輸入認證。 

- **如果您想要更新 Cloud Connector 裝置中已安裝 OMS 代理程式的 OMS 工作區識別碼或機碼，請執行下列動作：**

    1. 若要設定 OMS 識別碼和機碼，請執行 Set-CcCredential-AccountType OMSWorkspace。 

    2. 若要套用更新，請執行 CcOMSAgent 安裝程式。 

- **在所有情況下，請確認代理程式已連接，如下所示：**

    在 [OMS] 入口網站中，移至設定 \> 連接的來源- \> Windows 伺服器。 您會看到已連線的電腦清單。 

## <a name="configure-oms"></a>設定 OMS

接下來，您將需要使用 OMS 入口網站指定您的 OMS 設定。 具體說來，您將需要：

- 指定事件記錄檔和效能計數器的相關資訊。

- 建立提醒。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定事件記錄檔和效能計數器的相關資訊

在 OMS 入口網站中，您必須指定事件記錄檔和效能計數器的相關資訊，如下所示：

1. 移至設定 \> 資料 \> Windows 事件記錄檔，並新增下列專案的事件記錄： 

   - Lync Server

   - 應用程式

     > [!NOTE]
     > 您必須在文字方塊中手動輸入 Lync Server。 它不會出現在下拉式清單中的選項。 

     如需詳細資訊，請參閱[在記錄分析中 Windows 事件記錄檔資料來源](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 移至設定 \> 資料 Windows 的 \> 效能計數器，並新增下列專案的效能計數器： 

   - **作業系統層級計數器**。 您可以新增作業系統層級計數器（如處理器使用量、記憶體使用量、網路使用量），也可以使用現有的解決方案（如容量和效能）、網路效能監視器（不需要明確新增計數器）。 不論您決定如何進行監視，Microsoft 建議您監視這些作業系統計數器。

   - **商務用 Skype 計數器**。 商務用 Skype 提供許多計數器。 您可以登入任何轉送伺服器並開啟效能監視器，以找到這些計數器。 這些計數器的開頭為 "LS："。 Microsoft 建議您至少從下列容量計數器開始，並新增其他感興趣的計數器：

     主動通話總數：

       - LS： MediationServer 輸入呼叫 (_Total) \- 電流 

       - LS： MediationServer 呼出通話 (_Total) \- 電流 

     Active media 旁路通話總數：

       - LS： MediationServer 輸入呼叫 (_Total) 作用中 \- 媒體旁路通話 

       - LS： MediationServer 呼出通話 (_Total) 作用中 \- 媒體旁路通話 

     > [!NOTE]
     > 您必須在文字方塊中手動輸入效能計數器。 它們不會顯示為下拉式清單中的選項。 

     如需詳細資訊，請參閱[記錄分析中的 Windows 和 Linux 效能資料來源](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>建立提醒

OMS 中有兩種警示類型： [結果] 警示和 [衡量度量值] 警示的數目。 如需建立提醒的詳細資訊，請參閱使用 [記錄分析中的警示規則](/azure/log-analytics/log-analytics-alerts-creating)。

建立提醒時，您應該考慮下列事項：

- 確定警示是結果數目的警示，也就是預設的選取範圍。 

- 演示程式查詢需要 "results 數目" 設定為 "大於 0"。 

- 建議您將時間視窗和警示頻率設定為5分鐘。 

- 建議您不要為示範提醒啟用「抑制提醒」。 

- 針對一般警示案例，Microsoft 建議建立一對警示：一個錯誤警示和一個重設警示。 若為錯誤警示，請選取嚴重層級（重要）;若為重設警示，請選取 [嚴重性層級資訊]。

下列各節說明如何建立範例警示。

 **建立警示對：「RTCMEDSRV 未在轉送伺服器中執行」和「RTCMEDSRV 會傳回轉送伺服器中的執行」**

若要建立此警示對：

- 錯誤警示的查詢如下：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查詢使用電腦  *包含 "MediationServer"*  的電腦篩選。 篩選器只會選取其名稱中包含字串 "MediationServer" 的電腦。

     您可以將篩選取代為您自己的電腦篩選，也可以只加以移除。 您可以建立沒有正則運算式的複雜字串篩選。 如需詳細資訊，請參閱 [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您也可以選擇使用正則運算式。 此外，您可以儲存搜尋查詢，並使用該群組做為提醒查詢中的電腦篩選，以建立電腦群組。 如需詳細資訊，請參閱 [Log Analytics 記錄搜尋中的電腦群組](/azure/log-analytics/log-analytics-computer-groups)。

    在每一部電腦上，錯誤查詢都會取得 RTCMEDSRV 服務啟動和服務停止的最後一個事件記錄檔。 如果最後一個事件是服務停止事件，它會傳回一個記錄，否則會傳回一個記錄。如果最後一個事件是服務啟動事件，它會傳回 nothing。 簡而言之，查詢會傳回 RTCMEDSRV 已停止在時間範圍內的伺服器清單。 

- 重設警示的查詢為：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重設查詢與錯誤查詢完全相反。 在每一部電腦上，如果最後一個事件是服務啟動事件，它會傳回一個，否則會傳回一個。如果最後一個事件是服務停止事件，它會傳回 nothing。

**建立警示對：「轉送伺服器中的同時呼叫太多」和「同時來電回到正常載入」**

若要建立此警示：

- 錯誤警示的查詢如下：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    針對每一部電腦，查詢將取得輸入呼叫和撥出電話的最後一個計數器，並為這兩個值加總。 如果總和值超過500，它會傳回一部記錄。如果不是，它會傳回 nothing。 簡而言之，查詢會傳回一份清單，其中的並行呼叫在時間範圍內太多。

- 重設警示的查詢為：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重設查詢與錯誤查詢完全相反。 針對每一部電腦，查詢將取得輸入呼叫和撥出電話的最後一個計數器，並為這兩個值加總。 如果 sum 值小於500，它會傳回一部記錄。否則會傳回 nothing。

**建立警示：「伺服器上的 CPU 使用量 \> 90 或 RTCMEDIARELAY 已停止」警示**

若要建立此警示，請執行下列查詢：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

此查詢會從所有電腦取得所有處理器使用量計數器和 service stop 事件，如果處理器使用量超過90% 或服務曾經停止，則傳回一個記錄。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存放庫中的警示

若要分析存放庫中的警示，請使用警示管理解決方案。 如需詳細資訊，請參閱 [Operations Management Suite 中的警示管理解決方案 (OMS) ](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建議的最小監控集

若要找出事件記錄及效能計數器的問題： 

- **事件記錄檔。** 針對任何問題，應有一對事件，其中一組事件會指出發生問題，另一組則表示一切正常。 在任何指定的時間期間，都是最後記錄的事件，它會指出該時段是否有 amiss。

- **效能計數器。** 監視的計數器應有一個臨界值。

下表列出 Microsoft 建議透過列出 stop 和 start 事件 IDs 來進行監視的服務：

|服務名稱  <br/> |目標伺服器角色  <br/> |停止事件識別碼  <br/> |開始事件識別碼  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中繼伺服器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

下表列出 Microsoft 建議監控的網路問題：


| 監視器名稱  <br/>                                        | 目標伺服器角色  <br/> | Success 事件識別碼運算式  <br/> | Error 事件識別碼運算式  <br/> | 失敗範例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 轉送伺服器到閘道連線失敗  <br/>    | 中繼伺服器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 轉送伺服器到閘道的呼叫完成失敗  <br/> | 中繼伺服器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重大網路問題  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

下表列出應該監控的呼叫容量計數器。 對於 Cloud Connector standard edition，這些號碼應小於500。小於50的雲端連接器最小 edition。

- LS： MediationServer 輸入呼叫 (_Total) \- 電流 

- LS： MediationServer 呼出通話 (_Total) \- 電流 

- LS： MediationServer 輸入呼叫 (_Total) 作用中 \- 媒體旁路通話

- LS： MediationServer 呼出通話 (_Total) 作用中 \- 媒體旁路通話

## <a name="see-also"></a>另請參閱

如需使用 OMS 的詳細資訊，請參閱下列各項：

- [在記錄分析中使用記錄搜尋來尋找資料](/azure/log-analytics/log-analytics-log-searches)

- [Azure 記錄分析語言參考](https://docs.loganalytics.io/docs/Language-Reference)

- [瞭解記錄分析中的警示](/azure/log-analytics/log-analytics-alerts)

- [在 Azure 中連線 Windows 電腦到記錄分析服務](/azure/log-analytics/log-analytics-windows-agents)