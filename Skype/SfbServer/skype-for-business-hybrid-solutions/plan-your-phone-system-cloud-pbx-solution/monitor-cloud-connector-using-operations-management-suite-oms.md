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
description: 閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視 Cloud Connector 2.1 版和更新版本的部署。
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676505"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 監控 Cloud Connector

> [!Important]
> Cloud Connector Edition 將于 2021 年 7 月 31 日與 商務用 Skype Online 一起淘汰。 一旦您的組織升級至Teams，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將內部部署電話語音網路連線到Teams。

閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite (OMS) 來監視 Cloud Connector 2.1 版和更新版本的部署。

您現在可以使用 Operations Management Suite (Microsoft 雲端 IT 管理解決方案 OMS) ，來監視 Cloud Connector 2.1 版和更新版本的部署。 OMS Log Analytics 可讓您監視及分析資源的可用性和效能，包括實體和虛擬機器。 如需 OMS 和 Log Analytics 的詳細資訊，請參閱 [什麼是 Operations Management Suite (OMS) ？](/azure/operations-management-suite/operations-management-suite-overview)

本主題包含下列各節：

- 必要條件

- 設定 Cloud Connector 以使用 OMS

- 設定 OMS

- 分析 Log Analytics 存放庫中的警示

- 建議的監視集

## <a name="prerequisites"></a>必要條件

在您可以使用 OMS 監視 Cloud Connector 部署之前，您需要下列專案：

- **Azure 帳戶和 OMS 工作區。** 如果您還沒有 Azure 帳戶，您必須建立一個帳戶才能使用 OMS Log Analytics。 如需如何建立 Azure 帳戶和設定 OMS 工作區的相關資訊，請[參閱使用 Log Analytics 工作區開始](/azure/log-analytics/log-analytics-get-started)。

- **Cloud Connector 2.1 版或更新版本**

- 雲端連接器監視需要 **Log Analytics 新的記錄搜尋**。 如需詳細資訊，請參閱 [將 Azure Log Analytics 工作區升級為新的記錄搜尋](/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>設定 Cloud Connector 以使用 OMS

您必須將 Cloud Connector 內部部署環境設定為使用 OMS。 若要這樣做，您需要 OMS 工作區識別碼和金鑰，您可以使用 OMS 入口網站找到這些識別碼和金鑰，如下所示：設定 -- \> Connected Sources -- \> Windows Servers：

![Cloud Connector OMS 的螢幕擷取畫面。](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

設定 Cloud Connector 使用 OMS 的方式取決於您的案例：

- **如果您要安裝新的 Cloud Connector 設備，或想要重新部署設備**，請先遵循下列步驟，再執行 Install-CcAppliance：

  1. 在 [CloudConnector.ini 檔案 [Common] 區段中，將 OMSEnabled 參數設定為 True。

     每次部署或升級 Cloud Connector 時，都會嘗試將 OMS 代理程式自動安裝到 VM 上。 啟用此功能，讓 OMS 代理程式可以在 Cloud Connector 自動更新後存取。

  2. 若要設定 OMS 識別碼和金鑰，請執行 Set-CcCredential -AccountType OMSWorkspace。

- **如果您要將 OMS 代理程式安裝到現有的 Cloud Connector 設備上**，請遵循下列步驟：

  1. 在 [CloudConnector.ini 檔案 [Common] 區段中，設定 OMSEnabled=true。

  2. 執行 Import-CcConfiguration。

  3. 執行 Install-CcOMSAgent。

     > [!NOTE]
     > 如果從未設定過 OMSWorkspace 認證，當您執行 install-CcOMSAgent 時，系統會提示您輸入認證。

- **如果您想要在已安裝 OMS 代理程式的雲端連接器設備中更新 OMS 工作區識別碼或金鑰：**

  1. 若要設定 OMS 識別碼和金鑰，請執行 Set-CcCredential -AccountType OMSWorkspace。

  2. 若要套用更新，請執行 Install-CcOMSAgent。

- **針對所有案例，請確認代理程式已連線，如下所示：**

    在 OMS 入口網站中，移至 [設定 - \> 連線的來源 - \> Windows伺服器]。 您會看到已連線的機器清單。

## <a name="configure-oms"></a>設定 OMS

接下來，您必須使用 OMS 入口網站來指定 OMS 設定。 具體而言，您必須：

- 指定事件記錄檔和效能計數器的相關資訊。

- 建立提醒。

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定事件記錄檔和效能計數器的相關資訊

在 OMS 入口網站中，您必須指定事件記錄檔和效能計數器的相關資訊，如下所示：

1. 移至 設定- \> Data-Windows \> 事件記錄檔，並新增下列事件記錄檔：

   - Lync Server

   - 應用程式

     > [!NOTE]
     > 您必須在文字方塊中手動輸入 Lync Server。 它不會顯示為下拉式清單中的選項。

     如需詳細資訊，[請參閱在 Log Analytics 中Windows事件記錄檔資料來源](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 移至 設定- \> Data- \> Windows 效能計數器，並新增下列專案的效能計數器：

   - **OS 層級計數器**。 您可以新增 OS 層級計數器，例如處理器使用量、記憶體使用量、網路使用量，也可以使用現有的解決方案，例如容量和效能、網路效能監視器，而不需要明確地新增計數器。 無論您如何決定監視它們，Microsoft 都建議您監視這些 OS 計數器。

   - **商務用 Skype計數器**。 商務用 Skype提供許多計數器。 您可以登入任何轉送伺服器並開啟效能監視器，以找到這些計數器。 這些計數器的開頭為 「LS：」。 Microsoft 建議您至少從下列容量計數器開始，並新增其他感興趣的計數器：

     作用中呼叫總數：

     - LS：MediationServer - 目前 (_Total) \- 的輸入呼叫

     - LS：MediationServer - 目前 (_Total) \- 的輸出呼叫

     作用中媒體略過呼叫總數：

     - LS：MediationServer - 使用中媒體略過呼叫 (_Total) \- 來電

     - LS：MediationServer - 使用中媒體略過呼叫 (_Total) \- 連出通話

     > [!NOTE]
     > 您必須在文字方塊中手動輸入效能計數器。 它們不會顯示為下拉式清單中的選項。

     如需詳細資訊，[請參閱 log Analytics 中的 Windows 和 Linux 效能資料來源](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>建立警示

OMS 中有兩種類型的警示：結果警示數目和計量度量警示。 如需建立警示的詳細資訊，請 [參閱在 Log Analytics 中使用警示規則](/azure/log-analytics/log-analytics-alerts-creating)。

建立警示時，您應該考慮下列事項：

- 請確定警示為結果數警示，這是預設選項。

- 示範查詢需要將 [結果數目] 設定為 [大於 0]。

- 建議您將 [時間] 視窗和 [警示頻率] 設定為 5 分鐘。

- 建議您不要啟用示範警示的「隱藏警示」。

- 針對一般警示案例，Microsoft 建議建立一組警示：一個錯誤警示和一個重設警示。 針對錯誤警示，選取嚴重性層級 [重大];針對重設警示，選取 [嚴重性層級][資訊]。

下列各節說明如何建立範例警示。

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>建立警示組：「RTCMEDSRV 未在轉送伺服器中執行」和「RTCMEDSRV 已在轉送伺服器中重新執行」

若要建立此警示組：

- 錯誤警示的查詢為：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查詢會使用電腦篩選器，*其中 Computer 包含 「MediationServer」。* 篩選準則只會選取其名稱包含字串 「MediationServer」 的電腦。

     您會將篩選取代為您自己的電腦篩選準則，或直接移除它。 您可以建立不含正則運算式的複雜字串篩選。 您也可以選擇使用正則運算式。 此外，您可以藉由儲存搜尋查詢，並在警示查詢中使用該群組作為電腦篩選器來建立電腦群組。 如需詳細資訊，請參閱 [Log Analytics 記錄搜尋中的電腦群組](/azure/log-analytics/log-analytics-computer-groups)。

    針對每部電腦，錯誤查詢會取得 RTCMEDSRV 服務啟動和服務停止的最後一個事件記錄檔。 如果最後一個事件是服務停止事件，它會傳回一個記錄檔;如果最後一個事件是服務啟動事件，則不會傳回任何內容。 簡言之，查詢會傳回在時間範圍中停止 RTCMEDSRV 的伺服器清單。

- 重設警示的查詢如下：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重設查詢與錯誤查詢完全相反。 針對每部電腦，如果最後一個事件是服務啟動事件，則會傳回一部;如果最後一個事件是服務停止事件，則不會傳回任何內容。

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>建立警示配對：「轉送伺服器中的並行呼叫太多」和「並行呼叫回復為正常負載」

若要建立此警示：

- 錯誤警示的查詢為：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    針對每部電腦，查詢會取得輸入呼叫和輸出呼叫的最後一個計數器，並加總這兩個值。 如果總和值超過 500，則會傳回一個記錄檔;如果沒有，則不會傳回任何內容。 簡言之，查詢會傳回在時間範圍中並行呼叫過多的伺服器清單。

- 重設警示的查詢如下：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重設查詢與錯誤查詢完全相反。 針對每部電腦，查詢會取得輸入呼叫和輸出呼叫的最後一個計數器，並加總這兩個值。 如果總和值小於 500，則會傳回一個記錄檔;否則不會傳回任何內容。

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>建立警示：「伺服器中的 CPU 使用量 \> 90 或 RTCMEDIARELAY 已停止」警示

若要建立此警示，查詢為：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

查詢會從所有電腦取得所有處理器使用計數器和服務停止事件，並在處理器使用量超過 90% 或服務停止時傳回一個記錄檔。

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 存放庫中的警示

若要分析存放庫中的警示，請使用警示管理解決方案。 如需詳細資訊，請參閱 [Operations Management Suite 中的警示管理解決方案 (OMS) ](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建議的最低監視集

若要識別事件記錄檔和效能計數器的問題：

- **事件記錄檔。** 對於任何問題，都應該有事件配對，其中一組事件表示發生錯誤，而另一個則表示一切正常。 針對任何指定的時間週期，這是記錄的最後一個事件，會指出該時間週期是否有問題。

- **效能計數器。** 受監視的計數器應該有臨界值。

下表列出 Microsoft 建議監視的服務，方法是列出停止和啟動事件識別碼：

|服務名稱  <br/> |目標伺服器角色  <br/> |停止事件識別碼  <br/> |開始事件識別碼  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中繼伺服器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

下表列出 Microsoft 建議監視的網路問題：


| 監視器名稱  <br/>                                        | 目標伺服器角色  <br/> | 成功事件識別碼運算式  <br/> | 錯誤事件識別碼運算式  <br/> | 失敗範例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 轉送伺服器到閘道連線失敗  <br/>    | 中繼伺服器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 轉送伺服器到閘道的呼叫完成失敗  <br/> | 中繼伺服器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重大網路問題  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

下列列出應監視的呼叫容量計數器。 Cloud Connector 標準版的這些數位應該小於 500;Cloud Connector 最低版本小於 50。

- LS：MediationServer - 目前 (_Total) \- 的輸入呼叫

- LS：MediationServer - 目前 (_Total) \- 的輸出呼叫

- LS：MediationServer - 使用中媒體略過呼叫 (_Total) \- 來電

- LS：MediationServer - 使用中媒體略過呼叫 (_Total) \- 連出通話

## <a name="see-also"></a>另請參閱

如需使用 OMS 的詳細資訊，請參閱下列各項：

- [在 Log Analytics 中使用記錄搜尋來尋找資料](/azure/log-analytics/log-analytics-log-searches)

- [瞭解 Log Analytics 中的警示](/azure/log-analytics/log-analytics-alerts)

- [將電腦連線 Windows至 Azure 中的 Log Analytics 服務](/azure/log-analytics/log-analytics-windows-agents)