---
title: 使用 Azure 監視器部署 Microsoft 團隊聊天室管理
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文將說明如何使用 Azure 監視器，以整合的端對端方式部署 Microsoft 團隊機房裝置的管理。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0e0e810bb2932918947a011a9d2091858d0819eb
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160087"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>部署:::no-loc text="Microsoft Teams Rooms":::管理:::no-loc text="Azure Monitor":::

本文將討論如何使用:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor":::設定及部署裝置的整合端對端管理。

您可以在:::no-loc text="Log Analytics":::內部:::no-loc text="Azure Monitor":::進行設定，以提供可協助您管理:::no-loc text="Microsoft Teams Rooms":::會議室裝置的基本遙測及警示。 隨著您的管理解決方案逐漸成熟，您可能會決定要部署其他資料和管理功能來建立更詳細的裝置可用性與效能的視圖。

透過遵循本指南，您可以使用類似下列範例的儀表板，來取得裝置可用性、應用程式和硬體健康情況，以及:::no-loc text="Microsoft Teams Rooms":::應用程式與作業系統版本發佈的詳細狀態報表。

![Microsoft 團隊聊天室範例記錄分析視圖範例的螢幕擷取畫面](../media/Deploy-Azure-Monitor-1.png "Microsoft 團隊聊天室的 [Log Analytics 分析] 視圖範例")

在較高的層次，您必須執行下列工作：


1. [驗證:::no-loc text="Log Analytics":::配置](azure-monitor-deploy.md#validate_LogAnalytics)
2. [針對:::no-loc text="Log Analytics":::管理設定設定測試裝置](azure-monitor-deploy.md#configure_test_devices)
3. [對應自訂欄位](azure-monitor-deploy.md#Custom_fields)
4. [中定義:::no-loc text="Microsoft Teams Rooms":::視圖:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [定義警示](azure-monitor-deploy.md#Alerts)
6. [設定所有要監視的裝置](azure-monitor-deploy.md#configure_all_devices)
7. [設定其他:::no-loc text="Azure Monitor":::解決方案](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 雖然使用最低的設定:::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: ，但可以監視執行:::no-loc text="Windows":::作業系統的電腦，但在開始部署:::no-loc text="Microsoft Teams Rooms":::代理程式到所有:::no-loc text="Microsoft Teams Rooms":::裝置之前，仍需要採取一些特定步驟。
> 因此，我們強烈建議您以正確的循序執行所有設定步驟，以進行受控設定和設定。 最終結果的品質很高，取決於初始配置的品質。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>驗證:::no-loc text="Log Analytics":::配置
<a name="validate_LogAnalytics"> </a>

您必須具備:::no-loc text="Log Analytics":::工作區，才能開始從:::no-loc text="Microsoft Teams Rooms":::裝置收集記錄。 工作區是一種:::no-loc text="Log Analytics":::獨特的環境，擁有自己的資料存放庫、資料來源及解決方案。 :::no-loc text="Log Analytics":::如果您已經有現有的工作區，您可以使用它來監視:::no-loc text="Microsoft Teams Rooms":::您的部署，或者，您也可以:::no-loc text="Log Analytics":::建立特定于您:::no-loc text="Microsoft Teams Rooms":::的監視需求的專用工作區。

如果您需要建立新:::no-loc text="Log Analytics":::的工作區，請依照文章在[ :::no-loc text="Log Analytics"::: :::no-loc text="Azure":::入口網站中建立工作區](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)中的指示操作。

> [!NOTE]
> 若要:::no-loc text="Log Analytics":::搭配:::no-loc text="Azure Monitor":::使用，您必須擁有有效:::no-loc text="Azure":::的訂閱。 如果您沒有:::no-loc text="Azure":::訂閱，您可以建立[免費試用訂閱](https://azure.microsoft.com/free)作為起始點。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>設定:::no-loc text="Log Analytics":::以收集:::no-loc text="Microsoft Teams Rooms":::事件記錄

:::no-loc text="Log Analytics":::僅收集設定中指定:::no-loc text="Windows":::的事件記錄中的事件。 針對每個記錄，只會收集已選取嚴重性的事件。

您需要設定:::no-loc text="Log Analytics":::以收集監視:::no-loc text="Microsoft Teams Rooms":::裝置和應用程式狀態所需的記錄。 :::no-loc text="Microsoft Teams Rooms":::裝置會使用**:::no-loc text="Skype Room System":::** 事件記錄。

若要:::no-loc text="Log Analytics":::設定收集:::no-loc text="Microsoft Teams Rooms":::事件，請參閱[ :::no-loc text="Windows":::中的:::no-loc text="Azure Monitor":::事件記錄資料來源](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![事件記錄檔設定的螢幕擷取畫面](../media/Deploy-Azure-Monitor-2.png "事件記錄檔設定")

> [!IMPORTANT]
> 設定:::no-loc text="Windows":::事件記錄的設定， **:::no-loc text="Skype Room System":::** 並以事件記錄名稱的形式輸入，然後選取 [**錯誤**]、[**警告**] 及 [**資訊**] 核取方塊。

## <a name="configure-test-devices-for-azure-monitoring"></a>針對 Azure 監視設定測試裝置
<a name="configure_test_devices"> </a>

您必須準備好:::no-loc text="Log Analytics":::監視:::no-loc text="Microsoft Teams Rooms":::相關事件。 首先，您必須將代理部署:::no-loc text="Microsoft Monitoring":::到一個或兩個:::no-loc text="Microsoft Teams Rooms":::您有實際存取權的裝置，並讓這些測試裝置產生一些資料並將它推入:::no-loc text="Log Analytics":::工作區。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>安裝:::no-loc text="Microsoft Monitoring":::代理程式以測試裝置

使用[[將電腦連線:::no-loc text="Windows":::至:::no-loc text="Log Analytics":::服務:::no-loc text="Azure":::]](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)中提供的指示，將:::no-loc text="Microsoft Monitoring":::代理部署到測試裝置。 本文提供有關:::no-loc text="Microsoft Monitoring":::部署代理程式之步驟的詳細資訊:::no-loc text="Windows":::，以及如何取得:::no-loc text="Log Analytics"::: ***工作區識別碼***和***主鍵***以:::no-loc text="Microsoft Teams Rooms":::取得連接到您:::no-loc text="Azure Monitor":::部署的裝置，以及驗證代理程式連線至:::no-loc text="Log Analytics":::實例的相關步驟。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>產生範例:::no-loc text="Microsoft Teams Rooms":::事件

將:::no-loc text="Microsoft Monitoring":::代理部署到測試裝置之後，請確認已收集所需的事件記錄資料:::no-loc text="Azure Monitor":::。

> [!NOTE]
> 安裝完:::no-loc text="Microsoft Monitoring":::代理程式後重新開機裝置，並確定:::no-loc text="Microsoft Teams Rooms":::會議 app 已啟動，讓它能夠在事件記錄中產生新的事件。

1.  登入[ :::no-loc text="Microsoft Azure":::入口網站](https://portal.azure.com)，然後前往:::no-loc text="Log Analytics":::並選取您的工作區。

2.  列出:::no-loc text="Microsoft Teams Rooms":::裝置產生的心跳事件：
    1.  選取您的工作區並移至 [**記錄**]，然後使用查詢來檢索將有自訂欄位的:::no-loc text="Microsoft Teams Rooms":::心跳記錄。
    2.  範例查詢：`Event | where Source == "SRS-App" and EventID == 2000`

3.  確認查詢傳回包含:::no-loc text="Microsoft Teams Rooms":::會議 app 所產生之事件的記錄記錄。

4.  產生硬體問題，並驗證所需的事件已登入:::no-loc text="Azure Log Analytics":::。
    1.  在測試:::no-loc text="Microsoft Teams Rooms":::系統上拔掉其中一個週邊裝置。 這可能是相機、免提、麥克風或前置房間顯示器
    2.  等待10分鐘，以填入事件記錄檔:::no-loc text="Azure Log Analytics":::。
    3.  使用查詢列出硬體錯誤事件：`Event | where Source == "SRS-App" and EventID == 3001`

5.  產生應用程式問題，並驗證所需的事件已記錄。
    1.  修改:::no-loc text="Microsoft Teams Rooms":::應用程式設定，並輸入不正確的會話初始通訊協定（SIP）位址/密碼對。
    2.  等待10分鐘，以填入事件記錄檔:::no-loc text="Azure Log Analytics":::。
    3.  使用查詢來列出應用程式錯誤事件：`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 在可以設定自訂欄位之前，必須先進行這些範例事件記錄。 請不要繼續進行下一個步驟，直到您收集到所需的事件記錄為止。

## <a name="map-custom-fields"></a>對應自訂欄位
<a name="Custom_fields"> </a>

您可以使用自訂欄位來提取事件記錄中的特定資料。 您需要定義自訂欄位，稍後會在您的磚、儀表板視圖和通知中使用。 在開始建立自訂欄位之前，請參閱[中:::no-loc text="Log Analytics":::的自訂欄位](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields)，並熟悉這些概念。

若要將自訂欄位從捕獲的事件記錄提取出來，請依照下列步驟進行：

1.  登入[ :::no-loc text="Microsoft Azure":::入口網站](https://portal.azure.com)，然後前往:::no-loc text="Log Analytics":::並選取您的工作區。

2. 列出:::no-loc text="Microsoft Teams Rooms":::裝置產生的事件：
   1.  移至 [**記錄**] 並使用查詢來檢索將擁有自訂欄位的記錄。
   2.  範例查詢：`Event | where Source == "SRS-App" and EventID == 2000`

3. 選取其中一個記錄，選取左側的按鈕，然後啟動欄位提取嚮導。
4. 醒目提示您想要從 RenderedDescription 提取的資料，並提供欄位標題。 您應該使用的功能變數名稱會在資料表1中提供。

   ![自訂欄位定義](../media/Deploy-Azure-Monitor-4.png "自訂欄位定義")

5. 使用*資料表 1*中所示的對應。 :::no-loc text="Log Analytics":::當您定義新欄位時，會自動附加** \_CF**字串。

> [!IMPORTANT]
> 請記住，所有 JSON :::no-loc text="Log Analytics":::和欄位都區分大小寫。
> 
> 請注意下表中每個自訂欄位所需的查詢。 您必須使用正確的查詢， :::no-loc text="Log Analytics":::才能成功地提取自訂欄位值。
> 
 ![自訂欄位定義](../media/Deploy-Azure-Monitor-5.png "自訂欄位定義")

**表格1**

| **JSON 欄位**                   | **:::no-loc text="Log Analytics":::自訂欄位** | **事件識別碼** | **要與提取搭配使用的查詢**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 說明                      | SRSEventDescription         | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| ResourceState                    | SRSResourceState            | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| End                    | SRSOperationName            | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OperationResult                  | SRSOperationResult          | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OS                               | SRSOSVersion                | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| 昵稱                            | SRSAlias                    | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| DisplayName                      | SRSDisplayName              | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| AppVersion                       | SRSAppVersion               | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | 來源\| = = "SRS-App" 和 EventID = = 2000 的事件 |
| 會議麥克風狀態     | SRSConfMicrophoneStatus     | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 會議演講者狀態        | SRSConfSpeakerStatus        | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 預設演講者狀態           | SRSDefaultSpeakerStatus     | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 相機狀態                    | SRSCameraStatus             | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 房間顯示狀態的正面     | SRSFORDStatus               | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| 動作感應器狀態             | SRSMotionSensorStatus       | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |
| HDMI 攝取狀態               | SRSHDMIIngestStatus         | **3001**     | 來源\| = = "SRS-App" 和 EventID = = 3001 的事件 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>中定義:::no-loc text="Microsoft Teams Rooms":::視圖:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

收集資料並對應自訂欄位之後，您可以使用 [視圖設計工具] 來開發包含各種磚的儀錶:::no-loc text="Microsoft Teams Rooms":::板，以監視事件。 使用 [視圖設計工具] 建立下列磚。 如需詳細資訊，請參閱[使用視圖設計:::no-loc text="Log Analytics":::工具建立自訂視圖](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 本指南中的上述步驟應該已完成，儀表板磚才能正常運作。

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>使用 import 方法建立 Microsoft 團隊聊天室儀表板

您可以匯入:::no-loc text="Microsoft Teams Rooms":::儀表板並快速開始監控您的裝置。 請採取下列步驟匯入儀表板：

1.  取得[SkypeRoomSystems_v2 的 omsview](https://go.microsoft.com/fwlink/?linkid=835675)儀表板檔案。
2.  登入[ :::no-loc text="Microsoft Azure":::入口網站](https://portal.azure.com)，然後前往:::no-loc text="Log Analytics":::並選取您的工作區。
3.  開啟 [**視圖設計**工具]。
4.  選取 [匯**入**]，然後選取**SkypeRoomSystems_v2 的 omsview**檔案。
5.  選取 [**儲存**]。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手動建立 Microsoft 團隊聊天室儀表板

或者，您也可以建立自己的儀表板，然後只新增您想要監視的磚。

#### <a name="configure-the-overview-tile"></a>設定 [概覽] 磚

1.  開啟 [**視圖設計**工具]。
2.  選取 **[一覽磚**]，然後從圖庫中選取**兩個數字**。
3.  為磚**:::no-loc text="Microsoft Teams Rooms":::** 命名。
4.  定義**第一個磚**：<br>
    **圖例：** 在上個月內至少傳送過一次心跳的裝置<br>
    **Query：**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定義**第二個磚**：<br>
    **圖例：** 在過去一個小時內傳送心跳的活動裝置<br>
    **Query：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  選取 **[** 套用]。

### <a name="create-a-tile-that-displays-active-devices"></a>建立顯示活動裝置的磚

1.  選取 [**查看儀表板**] 以開始新增您的磚。
2.  從圖庫選取 [**編號] & 清單**
3.  定義**一般**屬性：<br>
    [**群組標題]：** 心跳狀態<br>
    [**新增] 群組：** 選定
4.  定義**磚**屬性：<br>
    **圖例：** 作用中裝置（在最近20分鐘內傳送的心跳）<br>
    **磚查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定義**清單**屬性：<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定義**欄標題**：<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 上次心跳
7.  定義**導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 **[** 套用]，然後按一下 [**關閉**]。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>建立顯示有連線問題之裝置的磚

1.  從圖庫選取 [**編號 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性：<br>
    [**群組標題]：** 留空<br>
    [**新增] 群組：** 未選取
3.  定義**磚**屬性：<br>
    **圖例：** 非作用中的裝置（最近20分鐘內未傳送任何心跳訊息）<br>
    **磚查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定義**清單**屬性：<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定義**欄標題**：<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 上次心跳
6.  定義**導覽查詢**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  選取 **[** 套用]，然後按一下 [**關閉**]。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>建立顯示有硬體錯誤之裝置的磚

1.  從圖庫選取 [**編號 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性：<br>
    [**群組標題]：** 硬體狀態<br>
    [**新增] 群組：** 選定
3.  定義**磚**屬性：<br>
    **圖例：** 過去一個小時內遇到硬體錯誤的裝置<br>
    **磚查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定義**清單**屬性：<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定義**欄標題**：<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 上一個錯誤
6.  定義**導覽查詢**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  選取 **[** 套用]，然後按一下 [**關閉**]。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>建立顯示:::no-loc text="Microsoft Teams Rooms":::作業系統版本的磚

1.  從圖庫中選取 [**同心圓 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性：<br>
    [**群組標題]：** 作業系統詳細資料<br>
    [**新增] 群組：** 選定
3.  定義**標頭**屬性：<br>
    **標題：** 作業系統版本<br>
    **副標題：** 運行特定作業系統版本的裝置
4.  定義**同心圓**屬性：<br>
    **Query：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **文字置中：** 台<br>
    **操作：** 總計
5.  定義**清單**屬性。<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隱藏圖形：** 選定<br>
    **啟用**走勢圖：未選取
6.  定義**欄標題**。<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 留空
7.  定義**導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 **[套用] 然後按一下**[**關閉**]。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>建立顯示:::no-loc text="Microsoft Teams Rooms":::應用程式版本的磚

1.  從圖庫中選取 [**同心圓 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性：<br>
    **群組標題：** :::no-loc text="Microsoft Teams Rooms":::應用程式詳細資料<br>
    [**新增] 群組：** 選定
3.  定義**標頭**屬性：<br>
    **標題：** 應用程式版本<br>
    **副標題：** 運行特定應用程式版本的裝置
4.  定義**同心圓**屬性：<br>
    **Query：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **文字置中：** 台<br>
    **操作：** 總計
5.  定義**清單**屬性。<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隱藏圖形：** 選定<br>
    **啟用**走勢圖：未選取
6.  定義**欄標題**。<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 留空
7.  定義**導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 **[套用] 然後按一下**[**關閉**]。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>建立顯示有應用程式錯誤之裝置的磚

1.  從圖庫選取 [**編號 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性。<br>
    [**群組標題]：** 留空<br>
    [**新增] 群組：** 未選取
3.  定義**磚**屬性。<br>
    **圖例：** 過去一個小時內遇到應用程式錯誤的裝置<br>
    **磚查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定義**清單**屬性。<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定義**欄標題**。<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 上一個錯誤
6.  定義**導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  選取 **[套用] 然後按一下**[**關閉**]。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>建立顯示已重新開機之裝置的磚

1.  從圖庫選取 [**編號 & 清單**]，然後新增新的磚。
2.  定義**一般**屬性。<br>
    [**群組標題]：** 留空<br>
    [**新增] 群組：** 未選取
3.  定義**磚**屬性。<br>
    **圖例：** 在過去24小時內重新開機應用程式的裝置，以及重新開機的次數<br>
    **磚查詢：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定義**清單**屬性。<br>
    **清單查詢：**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定義**欄標題**。<br>
    **名稱：** 電腦名稱稱<br>
    **值：** 重新開機次數
6.  定義**導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  選取 **[套用] 然後按一下**[**關閉**]。
8.  選取 [**儲存**] 以儲存您的儀表板。

現在您已經完成建立您的視圖了。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>中的 [設定警示]:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::當:::no-loc text="Microsoft Teams Rooms":::主控台遇到問題時，可以提出通知來通知系統管理員。

:::no-loc text="Azure Monitor":::包含可透過定期時間間隔執行排程記錄搜尋的內建警示機制。 如果記錄搜尋的結果符合特定準則，就會建立警示記錄。

然後，規則會自動執行一或多個動作，主動通知您警報或喚醒呼叫另一個處理常式。 警報的可能選項如下：
-   傳送電子郵件
-   透過 HTTP POST 要求喚醒操作外部程式
-   在服務中:::no-loc text="Azure Automation":::啟動 runbook

請參閱[中:::no-loc text="Azure Monitor":::的記錄警示](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log)，以深入瞭解中:::no-loc text="Azure Monitor":::的警示。

> [!NOTE]
> 下列範例會在:::no-loc text="Microsoft Teams Rooms":::裝置產生硬體或應用程式錯誤時，傳送電子郵件警示。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>針對:::no-loc text="Microsoft Teams Rooms":::硬體問題設定電子郵件通知

設定警報規則，檢查在過去:::no-loc text="Microsoft Teams Rooms":::一個小時內遇到過硬體問題的裝置。
1.  登入[ :::no-loc text="Microsoft Azure":::入口網站](https://portal.azure.com)，然後前往:::no-loc text="Log Analytics":::並選取您的工作區。

2. 流覽至您:::no-loc text="Log Analytics":::的工作區並選取 [**通知**]，然後選取 [**新增通知規則**]。

3. 選取 [**新增條件**]，然後選擇 [**自訂記錄搜尋**]。

4.  在 [搜尋查詢] 文字方塊中輸入下列查詢。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  設定警報邏輯設定：<br>
    **依據：** 結果數<br>
    **條件：** 較大的<br>
    **閾值：** 0<br>

6. 設定評估設定，然後選取 [**完成**]： <br>
    **句號（分鐘）：** 60<br>
    **Frequency （分鐘）：** 60<br>

7. 設定動作群組：
    1.  選取 [**建立新**的]
    2.  針對 [*動作組名稱*] 和 [*簡稱*] 欄位提供適當的名稱。
    3.  指定唯一的*動作名稱*，然後選取 [**電子郵件/SMS/推播/語音**]，然後選取 [**編輯詳細資料**]。
    4.  選取 [**電子郵件**] 核取方塊，並提供將接收通知之人員或群組的電子郵件地址。
    5.  您也可以提供您的電話號碼，以取得 SMS、語音通話或兩者的通知。
    6. 選取 **[確定]**。

8. 如果您想要覆蓋提醒電子郵件的主旨行，請**自訂 [動作**]。

9. 指定 [規則名稱] 和 [描述]。<br>
    **規則名稱：** :::no-loc text="Microsoft Teams Rooms":::硬體失敗警示<br>
    **描述：** 過去一個小時內遇到硬體問題的裝置清單<br>

10. 選取預期的嚴重性，並確認已啟用規則。

11. 選取 [**建立警示規則**]。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>針對:::no-loc text="Microsoft Teams Rooms":::應用程式問題設定電子郵件通知

重複相同的程式，但使用下列查詢來列出在過去一個小時內遇到應用程式問題的裝置。

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

您現在已完成定義通知。 您可以使用上述範例來定義其他警示。

產生預警時，您會收到一封電子郵件，其中列出在過去一個小時內遇到問題的裝置。

![警示:::no-loc text="Azure Monitor":::電子郵件範例](../media/Deploy-Azure-Monitor-6.png 「示範:::no-loc text="Azure Monitor":::通知電子郵件」）

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>設定所有裝置:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a>在儀表板和通知設定之後，您可以在所有:::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms":::裝置上設定和設定代理程式，以完成您的監視部署。

雖然您可以在每個裝置:::no-loc text="Microsoft Monitoring":::上手動安裝及設定代理，但我們強烈建議您利用現有的軟體部署工具和方法。

如果您是第一:::no-loc text="Microsoft Teams Rooms":::次建立裝置，您可能會想要在組建程式:::no-loc text="Microsoft Monitoring":::中包含代理設定和設定步驟。 如需詳細資訊，請參閱[使用命令列安裝代理程式](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>使用:::no-loc text="Microsoft Monitoring":::群組原則物件（GPO）部署代理程式

如果您在實施:::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::前已部署裝置，您可以使用提供的腳本來設定和設定代理程式，方法是使用:::no-loc text="Active Directory":::群組原則物件。

1.  建立共用的網路路徑，並授予 [**網域電腦**] 群組的 [讀取存取權]。

2.  下載64位版本的:::no-loc text="Microsoft Monitoring":::代理程式，從:::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  將安裝套件的內容解壓縮至網路共用。
    1.  開啟命令提示字元視窗，然後執行**MMASetup-AMD64/c**
    2.  指定您剛建立的共用，並解壓縮內容。

4.  建立新的群組原則物件，然後將它指派給:::no-loc text="Microsoft Teams Rooms":::電腦帳戶所在的組織單位。

5.  設定 PowerShell 執行原則：
    1.  編輯新建立的 [群組原則] 物件，然後流覽\\至\\ [電腦\\ :::no-loc text="Windows":::設定\\原則] 管理範本元件:::no-loc text="Windows PowerShell":::
    2.  啟用 [**開啟腳本執行**]，並將**執行原則**設定為 [**允許本機腳本**]。

6.  設定啟動腳本：
    1.  複製下列腳本，並將其儲存為 Install-MMAgent. ps1。
    2.  修改 WorkspaceId、WorkspaceKey 和 SetupPath 參數，以符合您的配置。
    3.  編輯相同的群組原則物件，並流覽至 [ \\電腦\\ :::no-loc text="Windows":::設定\\原則] 設定腳本（啟動/關閉）
    4.  按兩下以選取 [**啟動**]，然後選取 [ **PowerShell 腳本**]。
    5.  選取 [**顯示**檔案]，然後將**Install-MMAgent**檔案複製到該資料夾。
    6.  選取 [**新增**]，然後按一下 **[流覽]**。
    7.  選取您剛才複製的 ps1 腳本。

7.  :::no-loc text="Microsoft Teams Rooms":::裝置應該在第二次:::no-loc text="Microsoft Monitoring":::重新開機時安裝並設定代理程式。

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> 您可以參閱[管理與維護:::no-loc text="Log Analytics":::代理程式](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)的文章，當您需要重新設定代理程式、將其移到不同的工作區，或在初始安裝之後修改 proxy 設定。

## <a name="additional-solutions"></a>其他解決方案
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::透過其[方案庫](https://docs.microsoft.com/azure/azure-monitor/insights/solutions)提供內建管理解決方案，進一步協助您監控您的環境。 我們強烈建議您同時在工作區中新增[警報管理](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution)和[ :::no-loc text="Azure Log Analytics":::代理程式健康](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth)方案。

> [!NOTE]
> Agent 健康方案可協助您找出您的環境:::no-loc text="Microsoft Monitoring":::中過時或損毀的代理程式，且通知管理解決方案會提供在指定期間內所產生之警報的詳細資料。

## <a name="see-also"></a>另請參閱

[規劃:::no-loc text="Microsoft Teams Rooms":::管理:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[管理:::no-loc text="Microsoft Teams Rooms":::裝置:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
