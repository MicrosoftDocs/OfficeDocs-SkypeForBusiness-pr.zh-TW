---
title: 使用 Azure 監視器部署Microsoft Teams 會議室監視
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 本文探討如何使用 Azure 監視器，以整合的端對端方式部署Microsoft Teams 會議室監控。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5dbea45008024762f30d9555f4762c4377d2ed1f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606412"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>使用部署 :::no-loc text="Microsoft Teams Rooms"::: 監控 :::no-loc text="Azure Monitor":::

本文探討如何使用 :::no-loc text="Azure Monitor"::: 裝置的整合式端對端監視 :::no-loc text="Microsoft Teams Rooms"::: 來設定和部署。

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

您可以在 :::no-loc text="Azure Monitor"::: 內部進行設定 :::no-loc text="Log Analytics"::: ，以提供可協助您管理 :::no-loc text="Microsoft Teams Rooms"::: 的基本遙測和警示。 隨著管理解決方案的成熟，您可能會決定部署其他資料和管理功能，以建立更詳細的裝置可用性和效能檢視。

若要遵循本指南，您可以使用類似下列範例的儀表板，取得裝置可用性、應用程式和硬體健康情況，以及 :::no-loc text="Microsoft Teams Rooms"::: 應用程式與作業系統版本發佈等詳細狀態報表。

![Microsoft Teams 會議室的 [記錄分析] 檢視範例螢幕擷取畫面。](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 會議室 的 [記錄分析] 檢視範例")

在高階上，您必須執行下列工作：


1. [:::no-loc text="Log Analytics":::驗證設定](azure-monitor-deploy.md#validate_LogAnalytics)
2. [設定測試裝置以進行 :::no-loc text="Log Analytics"::: 管理設定](azure-monitor-deploy.md#configure_test_devices)
3. [對應自訂欄位](azure-monitor-deploy.md#Custom_fields)
4. [定義中的 :::no-loc text="Microsoft Teams Rooms"::: 檢視 :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [定義提醒](azure-monitor-deploy.md#Alerts)
6. [設定所有裝置以進行監視](azure-monitor-deploy.md#configure_all_devices)
7. [設定其他 :::no-loc text="Azure Monitor"::: 解決方案](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> 雖然設定最少， :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 但可以監視執行 :::no-loc text="Windows"::: 作業系統的電腦，在開始將代理程式部署到所有 :::no-loc text="Microsoft Teams Rooms"::: 裝置之前，您仍需採取一些 :::no-loc text="Microsoft Teams Rooms"::: 特定步驟。
> 因此，我們強烈建議您以正確的循序執行所有設定步驟，以進行受控設定和設定。 最終結果的品質非常取決於初始設定的品質。

## <a name="validate-no-loc-textlog-analytics-configuration"></a>:::no-loc text="Log Analytics":::驗證設定
<a name="validate_LogAnalytics"> </a>

您需要有 :::no-loc text="Log Analytics"::: 工作區，才能開始從 :::no-loc text="Microsoft Teams Rooms"::: 中收集記錄。 工作區是一個獨特的 :::no-loc text="Log Analytics"::: 環境，擁有自己的資料存放庫、資料來源和解決方案。 如果您已經有現有的 :::no-loc text="Log Analytics"::: 工作區，您可能會使用它來監視您的 :::no-loc text="Microsoft Teams Rooms"::: 部署，或者，您可以建立專屬於您 :::no-loc text="Microsoft Teams Rooms"::: 監視需求的專用 :::no-loc text="Log Analytics"::: 工作區。

如果您需要建立新的 :::no-loc text="Log Analytics"::: 工作區，請依照在[入口網站中建立工作區一 :::no-loc text="Log Analytics"::: 文中的 :::no-loc text="Azure"::: ](/azure/azure-monitor/learn/quick-create-workspace)指示進行。

> [!NOTE]
> 若要搭配 :::no-loc text="Azure Monitor"::: 使用 :::no-loc text="Log Analytics"::: ，您需要有有效的 :::no-loc text="Azure"::: 訂閱。 如果您沒有 :::no-loc text="Azure"::: 訂閱，可以建立 [免費試用訂閱](https://azure.microsoft.com/free) 做為起點。

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>設定 :::no-loc text="Log Analytics"::: 為收集 :::no-loc text="Microsoft Teams Rooms"::: 事件記錄檔

:::no-loc text="Log Analytics"::: 只會從 :::no-loc text="Windows"::: 設定中指定的事件記錄收集事件。 針對每一個記錄，只會收集具有所選取之嚴重性的事件。

您必須設定 :::no-loc text="Log Analytics"::: 為收集監控 :::no-loc text="Microsoft Teams Rooms"::: 裝置和應用程式狀態所需的記錄。 :::no-loc text="Microsoft Teams Rooms":::**:::no-loc text="Skype Room System":::** 使用事件記錄檔。

若要設定 :::no-loc text="Log Analytics"::: 收集 :::no-loc text="Microsoft Teams Rooms"::: 事件，[請參閱 :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)

![事件記錄檔設定的螢幕擷取畫面。](../media/Deploy-Azure-Monitor-2.png "事件記錄檔設定")

> [!IMPORTANT]
> :::no-loc text="Windows":::設定事件記錄檔設定並輸入 **:::no-loc text="Skype Room System":::** 為事件記錄檔名稱，然後選取 [**錯誤**、**警告** 和 **資訊]** 核取方塊。

## <a name="configure-test-devices-for-azure-monitoring"></a>設定 Azure 監控的測試裝置
<a name="configure_test_devices"> </a>

您必須做好準備 :::no-loc text="Log Analytics"::: ，才能監視 :::no-loc text="Microsoft Teams Rooms"::: –相關事件。 首先，您需要將代理程式部署 :::no-loc text="Microsoft Monitoring"::: 到您有權實體存取的一或兩 :::no-loc text="Microsoft Teams Rooms"::: 部裝置，並取得那些測試裝置來產生一些資料，並將它推送到 :::no-loc text="Log Analytics"::: 工作區。

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>安裝代理 :::no-loc text="Microsoft Monitoring"::: 程式以測試裝置

使用將 :::no-loc text="Microsoft Monitoring"::: 電腦連線到[服務中 :::no-loc text="Windows"::: 所提供的指示，將代理程式部署到 :::no-loc text="Log Analytics"::: 測試裝置。 :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows) 本文提供有關部署 :::no-loc text="Microsoft Monitoring"::: 代理程式之步驟的 :::no-loc text="Windows"::: 詳細資訊、取得 :::no-loc text="Log Analytics":::  * **Workspace ID** _ 和 _ *_primary key_** 以讓 :::no-loc text="Microsoft Teams Rooms"::: 裝置連線到您的 :::no-loc text="Azure Monitor"::: 部署的指示，以及驗證代理程式連線至 :::no-loc text="Log Analytics"::: 實例的步驟。

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>產生範例 :::no-loc text="Microsoft Teams Rooms"::: 事件

將 :::no-loc text="Microsoft Monitoring"::: 代理程式部署到測試裝置之後，請確認必要事件記錄檔資料是由 :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 在安裝 :::no-loc text="Microsoft Monitoring"::: 專員之後將裝置重新開機，並確定 :::no-loc text="Microsoft Teams Rooms"::: 已啟動會議應用程式，以便在事件記錄檔中產生新事件。

1.  登入[入口網站， :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)然後移至 :::no-loc text="Log Analytics"::: 並選取您的工作區。

2.  列出裝置所 :::no-loc text="Microsoft Teams Rooms"::: 產生的心跳事件：
    1.  選取您的工作區，然後移至 [ **記錄** ] 並使用查詢來擷取具有自訂欄位 :::no-loc text="Microsoft Teams Rooms"::: 的心跳記錄。
    2.  範例查詢： `Event | where Source == "SRS-App" and EventID == 2000`

3.  請確定查詢會傳回包含會議應用程式所產生事件的 :::no-loc text="Microsoft Teams Rooms"::: 記錄。

4.  產生硬體問題，並驗證已登入 :::no-loc text="Azure Log Analytics"::: 必要的事件。
    1.  拔除測試 :::no-loc text="Microsoft Teams Rooms"::: 系統上的其中一個周邊裝置。 這可能是相機、喇叭、麥克風或前方會議室顯示器
    2.  等候 10 分鐘，讓事件記錄檔填入。 :::no-loc text="Azure Log Analytics":::
    3.  使用查詢列出硬體錯誤事件： `Event | where Source == "SRS-App" and EventID == 3001`

5.  產生應用程式問題，並驗證已記錄必要的事件。
    1.  修改 :::no-loc text="Microsoft Teams Rooms"::: 帳戶設定，並輸入不正確的Email/密碼配對。
    2.  等候 10 分鐘，讓事件記錄檔填入。 :::no-loc text="Azure Log Analytics":::
    3.  使用查詢列出應用程式錯誤事件： `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> 這些範例事件記錄檔在可以設定自訂欄位之前是必要的。 除非您已收集必要的事件記錄檔，否則請勿繼續下一個步驟。

## <a name="map-custom-fields"></a>對應自訂欄位
<a name="Custom_fields"> </a>

您可以使用自訂欄位從事件記錄檔擷取特定資料。 您必須定義稍後會與磚、儀表板檢視和警示搭配使用的自訂欄位。 開始建立[自訂欄位之前，請參閱自訂欄位 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/custom-fields)並熟悉概念。

若要從擷取的事件記錄檔中擷取自訂欄位，請遵循下列步驟：

1.  登入[入口網站， :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)然後移至 :::no-loc text="Log Analytics"::: 並選取您的工作區。

2. 列出裝置所 :::no-loc text="Microsoft Teams Rooms"::: 產生的事件：
   1.  移至 [ **記錄** ]，並使用查詢來擷取具有自訂欄位的記錄。
   2.  範例查詢： `Event | where Source == "SRS-App" and EventID == 2000`

3. 選取其中一筆記錄，選取左側的按鈕，然後啟動欄位抽取精靈。
4. 醒目提示您要從 RenderedDescription 擷取的資料，並提供欄位標題。 您應該使用的功能變數名稱會在資料表 1 中提供。
5. 使用 *表格 1* 中顯示的對應。 :::no-loc text="Log Analytics":::當您定義新欄位時，**\_** 會自動附加 CF 字串。

> [!IMPORTANT]
> 請記住，所有 JSON 和 :::no-loc text="Log Analytics"::: 欄位都會區分大小寫。
> 
> 請注意下表中每個自訂欄位所需的查詢。 您必須使用正確的查詢 :::no-loc text="Log Analytics"::: ，才能成功擷取自訂域值。
> 
**資料表 1**

| **JSON 功能變數**                   | **:::no-loc text="Log Analytics"::: 自訂欄位** | **事件識別碼** | **用於抽取的查詢**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| 描述                      | SRSEventDescription         | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| ResourceState                    | SRSResourceState            | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| OperationName                    | SRSOperationName            | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| OperationResult                  | SRSOperationResult          | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| 作業系統                               | SRSOSVersion                | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| 別名                            | SRSAlias                    | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| DisplayName                      | SRSDisplayName              | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| AppVersion                       | SRSAppVersion               | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Source == 「SRS-App」 和 EventID == 2000 的事件 \| |
| 會議麥克風狀態     | SRSConfMicrophoneStatus     | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| 會議演講者狀態        | SRSConfSpeakerStatus        | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| 預設喇叭狀態           | SRSDefaultSpeakerStatus     | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| 相機狀態                    | SRSRaStatus             | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| [會議室前方顯示] 狀態     | SRSFORDStatus               | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| 動作感應器狀態             | SRSMotionSensorStatus       | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |
| HDMI Ingest 狀態               | SRSHDMIIngestStatus         | **3001**     | Source == 「SRS-App」 和 EventID == 3001 的事件 \| |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>定義中的 :::no-loc text="Microsoft Teams Rooms"::: 檢視 :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

收集資料並對應自訂欄位之後，您可以使用 [檢視設計工具] 開發包含各種磚的儀表板來監控 :::no-loc text="Microsoft Teams Rooms"::: 事件。 使用 [檢視設計工具] 建立下列磚。 如需詳細資訊，請參[閱在 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> 本指南中的先前步驟應該已經完成，儀表板磚才能正常運作。
>
> [!IMPORTANT]
> [Azure 監視器中的檢視設計工具將于 2023 年 8 月 31 日淘汰](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) ，且建立和複製功能已于 2020 年 11 月 30 日停用。 您可以改用活頁簿。 如需有關活頁簿檢視設計工具轉換指南的詳細資訊，請參閱 [使用預設檢視設計工具範本快速入門](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)。

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>手動建立Microsoft Teams 會議室儀表板

或者，您可以建立自己的儀表板，並只新增您要監視的磚。

#### <a name="configure-the-overview-tile"></a>設定概觀磚

1.  開 **啟 [檢視設計工具]**。
2.  選取 **[概觀磚**]，然後從圖庫中選取 **[兩個數字** ]。
3.  為磚 **:::no-loc text="Microsoft Teams Rooms":::** 命名 。
4.  定義 **第一個磚**：<br>
    **傳說：** 上個月至少傳送一次心跳的裝置<br>
    **查詢：** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  定義 **第二個磚**：<br>
    **傳說：** 在最後一小時內傳送心跳的主動式裝置<br>
    **查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  選取 **套用**。

### <a name="create-a-tile-that-displays-active-devices"></a>建立顯示使用中裝置的磚

1.  選 **取 [檢視儀表板** ] 以開始新增磚。
2.  從圖庫中選 **取 [編號&清單** ]
3.  定義 [ **一般]** 屬性：<br>
    **群組標題：** 心跳狀態<br>
    **新群組：** 選擇
4.  定義 **磚** 屬性：<br>
    **傳說：** 最近 20 分鐘內傳送 (活動裝置的心跳) <br>
    **磚查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  定義 **清單** 屬性：<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  定義 **欄標題**：<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 最後一個心跳
7.  定義 **導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 [ **套用**]，然後選取 [ **關閉]**。

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>建立磚，顯示有連線問題的裝置

1.  從圖 **庫中選取 [編號&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性：<br>
    **群組標題：** 保留空白<br>
    **新群組：** 未選取
3.  定義 **磚** 屬性：<br>
    **傳說：** 非作用中的裝置 (過去 20 分鐘內沒有傳送任何心跳訊息) <br>
    **磚查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  定義 **清單** 屬性：<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  定義 **欄標題**：<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 最後一個心跳
6.  定義 **導覽查詢**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  選取 [ **套用**]，然後選取 [ **關閉]**。

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>建立顯示有硬體錯誤之裝置的磚

1.  從圖 **庫中選取 [編號&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性：<br>
    **群組標題：** 硬體狀態<br>
    **新群組：** 選擇
3.  定義 **磚** 屬性：<br>
    **傳說：** 在最後一小時發生硬體錯誤的裝置<br>
    **磚查詢：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定義 **清單** 屬性：<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定義 **欄標題**：<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 上次錯誤
6.  定義 **導覽查詢**：<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  選取 [ **套用**]，然後選取 [ **關閉]**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>建立顯示 :::no-loc text="Microsoft Teams Rooms"::: 作業系統版本的磚

1.  從圖 **庫中選取 [環圈&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性：<br>
    **群組標題：** 作業系統詳細資料<br>
    **新群組：** 選擇
3.  定義 **頁首** 屬性：<br>
    **標題：** 作業系統版本<br>
    **字幕：** 執行特定作業系統版本的裝置
4.  定義 **Donut** 屬性：<br>
    **查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **文字置中：** 設備<br>
    **操作：** 和
5.  定義 **清單** 屬性。<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **隱藏圖形：** 選擇<br>
    **啟用走勢圖：** 未選取
6.  定義 **欄標題**。<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 清空
7.  定義 **導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 **[套** 用]，然後 **選取 [關閉]**。

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>建立顯示 :::no-loc text="Microsoft Teams Rooms"::: 應用程式版本的磚

1.  從圖 **庫中選取 [環圈&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性：<br>
    **群組標題：** :::no-loc text="Microsoft Teams Rooms"::: 應用程式詳細資料<br>
    **新群組：** 選擇
3.  定義 **頁首** 屬性：<br>
    **標題：** 應用程式版本<br>
    **字幕：** 執行特定應用程式版本的裝置
4.  定義 **Donut** 屬性：<br>
    **查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **文字置中：** 設備<br>
    **操作：** 和
5.  定義 **清單** 屬性。<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **隱藏圖形：** 選擇<br>
    **啟用走勢圖：** 未選取
6.  定義 **欄標題**。<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 清空
7.  定義 **導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  選取 **[套** 用]，然後 **選取 [關閉]**。

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>建立顯示有應用程式錯誤之裝置的磚

1.  從圖 **庫中選取 [編號&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性。<br>
    **群組標題：** 保留空白<br>
    **新群組：** 未選取
3.  定義 **磚** 屬性。<br>
    **傳說：** 過去一小時發生應用程式錯誤的裝置<br>
    **磚查詢：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  定義 **清單** 屬性。<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  定義 **欄標題**。<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 上次錯誤
6.  定義 **導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  選取 **[套** 用]，然後 **選取 [關閉]**。

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>建立顯示已重新開機之裝置的磚

1.  從圖 **庫中選取 [編號&清單** ]，然後新增磚。
2.  定義 [ **一般]** 屬性。<br>
    **群組標題：** 保留空白<br>
    **新群組：** 未選取
3.  定義 **磚** 屬性。<br>
    **傳說：** 應用程式在過去 24 小時內重新開機的裝置，以及重新開機次數<br>
    **磚查詢：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  定義 **清單** 屬性。<br>
    **清單查詢：** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  定義 **欄標題**。<br>
    **名字：** 電腦名稱稱<br>
    **價值：** 重新開機次數
6.  定義 **導覽查詢**。<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  選取 **[套** 用]，然後 **選取 [關閉]**。
8.  選 **取 [儲存** ] 以儲存您的儀表板。

現在您已完成建立檢視。

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>在 :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: 當主機遇到問題時 :::no-loc text="Microsoft Teams Rooms"::: ，可以提高通知以通知系統管理員。

:::no-loc text="Azure Monitor"::: 包含定期透過排程記錄搜尋執行的內建警示機制。 如果記錄搜尋結果符合某些特定準則，就會建立警示記錄。

規則接著可以自動執行一或多個動作，主動通知您警示或叫用另一個程式。 包含警示的可能選項如下：
-   傳送電子郵件
-   透過 HTTP POST 要求叫用外部程式
-   在服務中 :::no-loc text="Azure Automation"::: 啟動運行簿

若要深入瞭解中的警示，請參閱[登入 :::no-loc text="Azure Monitor"::: 記錄通知](/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor"::: 。

> [!NOTE]
> 下列範例會在裝置產生硬體或應用程式錯誤時 :::no-loc text="Microsoft Teams Rooms"::: 傳送電子郵件通知。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>設定硬體問題的電子郵件警示 :::no-loc text="Microsoft Teams Rooms":::

設定提醒規則，檢查 :::no-loc text="Microsoft Teams Rooms"::: 過去一小時內發生硬體問題的裝置。
1.  登入[入口網站， :::no-loc text="Microsoft Azure"::: ](https://portal.azure.com)然後移至 :::no-loc text="Log Analytics"::: 並選取您的工作區。

2. 流覽至您的 :::no-loc text="Log Analytics"::: 工作區，然後選取 **[通知]** ，然後選取 **[新增通知規則]**

3. 選取 **[新增條件]** ，然後 **選取 [自訂記錄搜尋]**

4.  在 [搜尋查詢] 文字方塊中輸入下列查詢。<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  設定警示邏輯設定：<br>
    **基於：** 結果數目<br>
    **條件：** 大於<br>
    **閾值：** 0<br>

6. 設定評估設定，然後選取 [ **完成]**： <br>
    **以分鐘為單位 () ：** 60<br>
    **) 分鐘 (頻率：** 60<br>

7. 設定動作群組：
    1.  選取 **[建立新]**
    2.  為 *[動作] 組名* 和 [ *簡短名稱] 字* 段提供適當的名稱。
    3.  指定唯一 *的動作名稱*，然後選 **Email/SMS/推播/語音**，然後選取 **[編輯詳細資料]**。
    4.  選 **取Email** 核取方塊，並提供接收警示之人員或群組的電子郵件地址。
    5.  您也可以提供您的電話號碼，以便透過簡訊、語音通話或兩者同時收到通知。
    6. 選取 **[確定]**。

8. 如果您想要覆寫警示電子郵件的主旨行，請 **自訂動作**。

9. 指定規則名稱和描述。<br>
    **規則名稱：** :::no-loc text="Microsoft Teams Rooms"::: 硬體故障警示<br>
    **描述：** 過去一小時內發生硬體問題的裝置清單<br>

10. 選取預定的嚴重性，並確定已啟用規則。

11. 選 **取 [建立警示規則]**。

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>設定應用程式問題的電子郵件警示 :::no-loc text="Microsoft Teams Rooms":::

重複相同的程式，但使用下列查詢列出過去一小時內發生應用程式問題的裝置。

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

現在您已完成定義通知。 您可以使用上述範例來定義其他警示。

產生警示時，您會收到一封電子郵件，其中列出在最後一小時內發生問題的裝置。

![範例 :::no-loc text="Azure Monitor"::: 提醒電子郵件] (../media/Deploy-Azure-Monitor-6.png「警示電子郵件範例 :::no-loc text="Azure Monitor"::: 」) 

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>設定所有裝置 :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a>設定儀表板和警示之後，您可以在所有 :::no-loc text="Microsoft Teams Rooms"::: 裝置上設定代理 :::no-loc text="Microsoft Monitoring"::: 程式，以完成監視部署。

雖然您可以在每部裝置上手動安裝及設定 :::no-loc text="Microsoft Monitoring"::: 代理程式，但我們強烈建議您運用現有的軟體部署工具和方法。

如果您是第一次建置 :::no-loc text="Microsoft Teams Rooms"::: 裝置，建議您在組建程式中加入 :::no-loc text="Microsoft Monitoring"::: 代理程式設定和設定步驟。 如需詳細資訊，請參閱 [使用命令列安裝代理程式](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)。

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>:::no-loc text="Microsoft Monitoring":::使用 群組原則 物件 (GPO) 部署代理程式

如果您在實 :::no-loc text="Azure Monitoring"::: 作之前已經部署 :::no-loc text="Microsoft Teams Rooms"::: 裝置，您可以使用提供的腳本，使用 :::no-loc text="Active Directory"::: 群組原則物件來設定及設定代理程式。

1.  建立共用網路路徑，並授與 **網域電腦** 群組的讀取權。

2.  下載 64 位版本的 :::no-loc text="Microsoft Monitoring"::: 代理程式 :::no-loc text="Windows"::: ， <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  將安裝套件的內容擷取到網路共用中。
    1.  開啟命令提示字元視窗，然後執行 **MMASetup-AMD64.exe /c**
    2.  指定您剛才建立的共用，然後擷取內容。

4.  建立新的群組原則物件，並將它指派給機器帳戶所在的 :::no-loc text="Microsoft Teams Rooms"::: 組織單位。

5.  設定 PowerShell 執行原則：
    1.  編輯新建立的群組原則物件，並流覽至電腦群組態 \\ 原則 \\ 系統管理 :::no-loc text="Windows"::: \\ 範本元件 \\ :::no-loc text="Windows PowerShell":::
    2.  啟 **用 [開啟腳本執行**]，並設定 **[執行原則****] 以允許本機腳本**。

6.  設定啟動腳本：
    1.  複製下列腳本並將它儲存為Install-MMAgent.ps1。
    2.  修改 WorkspaceId、WorkspaceKey 和 SetupPath 參數以符合您的設定。
    3.  編輯相同的群組原則物件，並流覽至電腦群組態 \\ 原則 \\ :::no-loc text="Windows"::: 設定 \\ 腳本 (啟動/關機) 
    4.  按兩下以選取 [ **啟動**]，然後選取 **[PowerShell 腳本]**。
    5.  選 **取 [顯示檔案**]，然後將 **Install-MMAgent.ps1** 檔案複製到該資料夾。
    6.  選取 **[新增**]，然後選取 **[流覽]**。
    7.  選取您剛複製的 ps1 腳本。

7.  :::no-loc text="Microsoft Teams Rooms"::: 應該會在第二次 :::no-loc text="Microsoft Monitoring"::: 重新開機時安裝並設定專員。

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
> 當您需要重新設定代理程式、將它移至不同的工作區，或是在初始安裝之後修改 Proxy 設定時，您可以參閱 [管理及維護 :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) 代理程式一文。

## <a name="additional-solutions"></a>其他解決方案
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: 透過其 [解決方案庫](/azure/azure-monitor/insights/solutions) 提供內建的管理解決方案，以進一步協助您監控環境。 我們強烈建議您在工作區中新增[警示管理和](/azure/azure-monitor/platform/alert-management-solution)[ :::no-loc text="Azure Log Analytics"::: 代理健康](/azure/azure-monitor/insights/solution-agenthealth)情況解決方案。

> [!NOTE]
> 專員健康情況解決方案可協助您識別環境中過時或損壞 :::no-loc text="Microsoft Monitoring"::: 的代理程式，而警示管理解決方案則提供特定期間內所提出之警示的詳細資料。

## <a name="see-also"></a>另請參閱

[方案 :::no-loc text="Microsoft Teams Rooms"::: 管理與 :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[使用 :::no-loc text="Microsoft Teams Rooms"::::::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
