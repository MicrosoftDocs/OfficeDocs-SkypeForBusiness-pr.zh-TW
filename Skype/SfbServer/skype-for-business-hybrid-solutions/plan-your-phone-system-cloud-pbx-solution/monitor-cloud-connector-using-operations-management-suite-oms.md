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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite （OMS）來監控雲端連接器版本2.1 及更新版本的部署。
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888632"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>使用 Operations Management Suite (OMS) 監控 Cloud Connector

閱讀本主題以瞭解如何使用 Microsoft Operations Management Suite （OMS）來監控雲端連接器版本2.1 及更新版本的部署。

您現在可以使用 Operations Management Suite （OMS）（Microsoft 雲端 IT 管理解決方案）來監視雲端連接器版本2.1 及更新版本的部署。 OMS 記錄分析可讓您監視及分析資源的可用性與效能，包括物理電腦和虛擬機器。 如需 OMS 和 Log Analytics 的詳細資訊，請參閱[什麼是作業管理套件（OMS）？](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

本主題包含下列各節：

- 先決條件

- 將雲端連接器設定為使用 OMS

- 設定 OMS

- 分析 Log Analytics 儲存庫中的警示

- 建議的監視設定

## <a name="prerequisites"></a>先決條件

您必須先進行下列作業，才能使用 OMS 來監視雲端連接器部署：

- **Azure 帳戶和 OMS 工作區。** 如果您還沒有 Azure 帳戶，您將需要建立一個，才能使用 OMS 記錄分析。 如需如何建立 Azure 帳戶並設定 OMS 工作區的相關資訊，請參閱[開始使用 Log Analytics 工作區](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)。

- **雲端連接器版本2.1 或更新版本**

- 需要進行記錄分析的是雲端連接器監視所需的**新記錄搜尋**。 如需詳細資訊，請參閱[將您的 Azure Log Analytics 工作區升級至新的記錄搜尋](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)。

## <a name="configure-cloud-connector-to-use-oms"></a>將雲端連接器設定為使用 OMS

您必須將雲端連接器內部部署環境設定為使用 OMS。 若要這麼做，您需要您的 OMS 工作區識別碼和金鑰，您可以使用 OMS 入口網站來尋找這些專案，如下所\>示： [設定\> ]-[連線的來源]-[Windows 伺服器]：

![雲端連接器 OMS 的螢幕擷取畫面](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

如何將雲端連接器設定為使用 OMS，取決於您的案例：

- **如果您要安裝新的雲端連接器裝置，或想要重新部署裝置**，請在執行安裝程式前按照下列步驟進行： CcAppliance：

    1. 在 CloudConnector 檔案 [Common] （通用）區段中，將 OMSEnabled 參數設定為 True。

        每次部署或升級雲端連接器時，都會嘗試將 OMS 代理程式自動安裝到 Vm。 啟用這項功能，以讓 OMS 代理程式可在雲端連接器自動更新後繼續進行。

    2. 若要設定 OMS 識別碼和金鑰，請執行 CcCredential-AccountType OMSWorkspace。 

- **如果您要在現有的雲端連接器裝置上安裝 OMS 代理程式**，請遵循下列步驟：

    1. 在 CloudConnector 檔案 [Common] （通用）區段中，設定 OMSEnabled = true。 

    2. 執行匯入-CcConfiguration。 

    3. 執行安裝-CcOMSAgent。 

        > [!NOTE]
        > 如果您還沒有設定 OMSWorkspace 認證，當您執行安裝-CcOMSAgent 時，系統會提示您輸入認證。 

- **如果您想要在已安裝 OMS 代理程式的雲端連接器裝置中更新 OMS 工作區識別碼或金鑰：**

    1. 若要設定 OMS 識別碼和金鑰，請執行 CcCredential-AccountType OMSWorkspace。 

    2. 若要套用更新，請執行安裝-CcOMSAgent。 

- **針對所有案例，請確認 agent 已連線，如下所示：**

    在 OMS 入口網站中，移至 [\>設定-連線\>的來源-Windows 伺服器]。 您會看到一份已連接的電腦清單。 

## <a name="configure-oms"></a>設定 OMS

接下來，您將需要使用 OMS 入口網站來指定您的 OMS 配置。 具體說來，您將需要：

- 指定事件記錄和效能計數器的相關資訊。

- 建立提醒。 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>指定事件記錄和效能計數器的相關資訊

在 OMS 入口網站中，您必須指定事件記錄和效能計數器的相關資訊，如下所示：

1. 移至 [設定\>]-\>[資料-資料-Windows 事件記錄]，並為下列專案新增事件記錄： 

   - Lync Server

   - 應用程式

     > [!NOTE]
     > 您必須在文字方塊中手動輸入 Lync Server。 它不會顯示在下拉式清單中的選項。 

     如需詳細資訊，請參閱[Log Analytics 中的 Windows 事件記錄資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. 移至 [設定\>]-\> [資料-Windows 效能計數器]，並為下列專案新增效能計數器： 

   - **OS 層級計數器**。 您可以新增 OS 階層計數器，例如處理器使用量、記憶體使用量、網路使用量，或者您可以使用現有的解決方案（例如容量和效能）、網路效能監視器，而不需明確地新增計數器。 不論您決定如何監視它們，Microsoft 建議您監視這些 OS 計數器。

   - **商務用 Skype 計數器**。 商務用 Skype 提供大量的計數器。 您可以登入任何中繼伺服器並開啟效能監視器，以找到這些計數器。 這些計數器開頭為 "LS："。 Microsoft 建議您至少從下列容量計數器開始，並新增感興趣的其他人：

     總活動通話：

       - LS： MediationServer-撥入電話（_Total\- ）電流 

       - LS： MediationServer-呼出通話（_Total\- ）電流 

     總活動媒體旁路通話：

       - LS： MediationServer-撥入通話（_Total\- ）使用中的媒體旁路通話 

       - LS： MediationServer-呼出通話（_Total\- ）動態媒體旁路通話 

     > [!NOTE]
     > 您必須在文字方塊中手動輸入效能計數器。 它們不會顯示為下拉式清單中的選項。 

     如需詳細資訊，請參閱[Log Analytics 中的 Windows 與 Linux 效能資料來源](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>建立提醒

OMS 中有兩種類型的警示： [結果] 通知數和 [公制測量] 警示。 如需建立通知的詳細資訊，請參閱[在 Log Analytics 中使用警示規則](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)。

建立提醒時，請考慮下列事項：

- 確認 [警示] 為 [結果數] 警示，這是預設的選取專案。 

- 示範查詢需要將 [結果數] 設為 [大於 0 "。 

- 建議您將 [時間] 視窗和 [警示頻率] 都設定為5分鐘。 

- 建議您不要為示範通知啟用「抑制通知」。 

- 針對一般通知案例，Microsoft 建議您建立一組通知：一個錯誤通知和一項重設警示。 針對錯誤警報，選取嚴重等級嚴重度;針對 [重設通知]，選取 [嚴重等級資訊]。

下列各節說明如何建立範例通知。

 **建立警示對：「未在轉送伺服器中執行 RTCMEDSRV」和「RTCMEDSRV 已回到轉送伺服器中」**

若要建立此通知對：

- 錯誤預警的查詢如下：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    查詢使用電腦*中包含 "MediationServer"* 的電腦篩選。 篩選只會選取名稱中包含字串 "MediationServer" 的電腦。

     您可以將篩選取代成您自己的電腦篩選，或直接將它移除。 您可以建立不含一般運算式的複雜字串篩選。 如需詳細資訊，請參閱[字串運算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。 您也可以選擇使用正則運算式。 此外，您也可以透過儲存搜尋查詢，並使用該群組作為您的通知查詢中的電腦篩選，來建立電腦群組。 如需詳細資訊，請參閱[Log Analytics 記錄搜尋中的電腦群組](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)。

    針對每個電腦，錯誤查詢都會取得 RTCMEDSRV 服務啟動和服務停止的最後一個事件記錄。 如果最後一個事件是服務停止事件，它會傳回一個記錄;如果最後一個事件是服務啟動事件，它將不會傳回任何內容。 簡言之，查詢會傳回 RTCMEDSRV 已停止在時間視窗中的伺服器清單。 

- [重設警示] 的查詢是：

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    重設查詢與錯誤查詢完全相反。 針對每個電腦，如果最後一個事件是服務啟動事件，則會傳回一個，否則返回一個如果最後一個事件是服務停止事件，它將不會傳回任何內容。

**建立警示對：「在中繼伺服器中過多的併發通話」和「併發呼叫回到標準載入」**

若要建立此通知：

- 錯誤預警的查詢如下：

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    針對每個電腦，查詢會取得撥入通話和撥出通話的最後一個計數器，並加總這兩個值。 如果 sum 值超過500，則會傳回一個記錄;如果不是，它將不會返回任何內容。 簡言之，查詢會傳回時間視窗中其併發呼叫太多的伺服器清單。

- [重設警示] 的查詢是：

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    重設查詢與錯誤查詢完全相反。 針對每個電腦，查詢會取得撥入通話和撥出通話的最後一個計數器，並加總這兩個值。 如果 sum 值小於500，則會傳回一個記錄;否則不會傳回任何內容。

**建立警示：「伺服器上的\> CPU 使用量90或 RTCMEDIARELAY 已停止在伺服器中」警報**

若要建立此通知，查詢是：

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

如果處理器使用量超過90% 或服務曾停止，查詢會從所有電腦取得所有的處理器使用方式計數器與服務停止事件，並傳回一個記錄。 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>分析 Log Analytics 儲存庫中的警示

若要在您的儲存庫中分析警示，請使用通知管理方案。 如需詳細資訊，請參閱[作業管理套件（OMS）中的警示管理解決方案](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>建議的最小監視設定

若要找出事件記錄和效能計數器的相關問題： 

- **事件記錄。** 針對任何問題，都應該有一個事件對，其中一組事件指示有問題，另一個則表示一切正常。 在任何指定的時間期間，都是記錄的最後一個事件，指出該時間段中是否有 amiss 的內容。

- **效能計數器。** 監視的計數器應該有一個閾值。

下表列出 Microsoft 建議的 [停止] 和 [開始] 事件識別碼進行監視的服務：

|服務名稱  <br/> |目標伺服器角色  <br/> |停止事件識別碼  <br/> |開始事件 ID  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |中繼伺服器  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge 伺服器  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge 伺服器  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge 伺服器  <br/> |22003  <br/> |22002  <br/> |

下表列出 Microsoft 建議監視的網路問題：


| 監視器名稱  <br/>                                        | 目標伺服器角色  <br/> | 成功事件識別碼運算式  <br/> | 錯誤事件識別碼運算式  <br/> | 失敗範例  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| 中繼伺服器到閘道連線失敗  <br/>    | 中繼伺服器  <br/>   | 25062                              |                                  | 25002  <br/>           |
| 中繼伺服器到閘道的呼叫完成失敗  <br/> | 中繼伺服器  <br/>   | 25064                              |                                  | 25002  <br/>           |
| 重要的網路問題  <br/>                           | Edge 伺服器  <br/>        | 14353                              |                                  | 12288  <br/>           |

下列清單列出應監視的通話容量計數器。 對於雲端連接器標準版，這些數位應該少於 500;低於雲端連接器最小版本的50。

- LS： MediationServer-撥入電話（_Total\- ）電流 

- LS： MediationServer-呼出通話（_Total\- ）電流 

- LS： MediationServer-撥入通話（_Total\- ）使用中的媒體旁路通話

- LS： MediationServer-呼出通話（_Total\- ）動態媒體旁路通話

## <a name="see-also"></a>另請參閱

如需使用 OMS 的詳細資訊，請參閱下列內容：

- [在 Log Analytics 中使用記錄搜尋來尋找資料](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Azure Log Analytics 語言參考](https://docs.loganalytics.io/docs/Language-Reference)

- [瞭解記錄分析中的通知](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [將 Windows 電腦連線至 Azure 中的 Log Analytics 服務](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


