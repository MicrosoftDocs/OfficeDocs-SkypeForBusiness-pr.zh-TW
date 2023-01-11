---
title: GCC High 和 DoD 的自動語音應答和通話佇列歷史報告
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何使用 Teams 自動語音應答&通話佇列歷史報告 Power BI 報告，以檢視 GCC High 和 DoD 客戶的自動語音應答和通話佇列歷史資料。
ms.openlocfilehash: cde953bfd8e9c95c60c795f6de91488506c2addf
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763674"
---
# <a name="auto-attendant-and-call-queue-historical-reports-for-gcc-high-and-dod"></a>GCC High 和 DoD 的自動語音應答和通話佇列歷史報告

> [!IMPORTANT]
> V1.63 範本的公用雲端支援將于 2022 年 11 月 25 日終止。
>
> 公用雲端客戶應使用 V3.x.x 的 [自動語音應答&通話佇列歷史報告](aa-cq-cqd-historical-reports.md)

## <a name="v163-published-on-august-24-2022"></a>2022 年 8 月 24 日發佈的 V1.63

**Teams 自動語音應答&通話佇列歷史報告 Power BI 範本** 提供下列三個報告：

- 自動 [語音應答](media/aa-cq-historical-report-sample-aa-v163.png) 報告會顯示自動語音應答中來電的分析資料。
- [ [通話佇列](media/aa-cq-historical-report-sample-cq-v163.png) ] 報告會顯示來電進入通話佇列的分析資料。
- [專員時程表](media/aa-cq-historical-report-sample-at-v163.png)報告顯示代理程式在通話佇列通話中作用中的時程表檢視。

這些報告會使用來自 [[通話品質儀表板] (CQD) ](CQD-Power-BI-query-templates.md) 資料存放區的資料。 

## <a name="v163-prerequisites"></a>V1.63 必要條件

### <a name="power-bi-desktop"></a>Power BI Desktop
您必須安裝Power BI Desktop。 您可以從 [Microsoft Windows 市](https://aka.ms/pbidesktopstore)集安裝並使用免費版本。

最小相容版本為 2.85.681.0 (2020 年 9 月) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管線的許可權

您用來檢視歷史報告的帳戶必須具備存取 CQD 資料管線的許可權。 如需詳細資訊，請參閱 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="v163-installation"></a>V1.63 安裝 

下列步驟假設您已經在電腦上安裝Power BI Desktop，而且您的帳戶擁有存取 CQD 資料管線的必要許可權。

執行下列步驟：

1. 下載並儲存 [電腦上的 CQD Power BI 查詢範本](https://www.microsoft.com/download/details.aspx?id=102291) zip 檔案。

2. 開啟 zip 檔案。

3. 開啟 `CQD Teams Auto Attendant & Call Queue Historical Report V1.63.pbit` 範本檔案。 Power BI Desktop應該會啟動。

4. 系統會提示您選取 CQD 資料管線區域。 選取租使用者所在的地區。

     :::image type="content" source="media/aa-cq-historical-report-01-v163.png" alt-text="選取 CQD 資料管線區域的螢幕擷取畫面。":::

    公用雲端租使用者

5. 您可以使用 [Get-CsTenant](/powershell/module/skype/get-cstenant) Cmdlet 取得租使用者所在的地區。

    ```powershell
    (Get-CsTenant).ServiceInstance

    microsoftcommunicationsonline/noam-4a-s7
    ```

    在上述地區為 `noam` 的範例中，區域會顯示在上述範例之後 **/** 。

    GCC High 和 DoD 租使用者

6. 更新範本以使用下列其中一個連接器：

   - GCCH： `https://data.cqd.gov.teams.microsoft.us/RunQuery`
   - 國防部： `https://data.cqd.dod.teams.microsoft.us/RunQuery`


7. 報告隨即會以範例資料啟動。
 
8. 若要查看您自己的資料 **，請在**[**常用**] 索引標籤的 [Power BI Desktop中的查詢] 底下選取 [**重新** 整理]。

   :::image type="content" source="media/aa-cq-historical-report-02-v163.png" alt-text="選取重新整理選項的螢幕擷取畫面。":::

9. 系統會提示您登入。 選取 **[組織帳戶**]，然後選取 [ **登入]**。

   :::image type="content" source="media/aa-cq-historical-report-03-v163.png" alt-text="顯示 V1.63 登入的螢幕擷取畫面。":::

10. 選取 **[連線**]，資料就會重新整理。

## <a name="data-latency-for-aa-and-cq-analytics"></a>AA 和 CQ 分析的資料延遲

資料通常會在通話完成後的 30 分鐘內取得;不過，在某些情況下，資料可能需要數小時才會顯示。

您必須重新整理資料，才能看到任何新資料。

## <a name="customization"></a>定制

您可以自訂報表的特定視覺效果層面，例如新增或移除要在各種視覺效果中顯示的欄位、變更圖表類型等等。

報表包含目前可用的所有資料計量。

### <a name="change-color-schema"></a>變更色彩架構

下列步驟假設您已經完成安裝步驟。

執行下列步驟：

1. 選取功能區上的 [ **檢視** ] 索引標籤。

    :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="選取 [檢視] 索引標籤以變更色彩配置的螢幕擷取畫面。":::

2. 從下拉式清單中選取色彩架構。

    :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="顯示各種色彩配置的螢幕擷取畫面。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動語音應答和通話佇列歷史報告定義

### <a name="cloud-auto-attendant-analytics-report"></a>雲端自動語音應答分析報告

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|來電來源<sup>1</sup>        |以內部/外部通話來源分派通話            |
|目錄搜尋方法                 |依搜尋類型分派通話                              |
|來電者動作計數                     |根據通話期間所用的號碼動作來分派通話       |
|AA 中的平均秒數                   |在 AA 中，來電者花費的平均秒數                 |
|平均來電者動作                  |來電者在 AA 中執行的動作平均數目               |
|通話結果                            |以最終通話狀態分派通話                         |
|報表的下方區段                 |通話流程明細                                               |



#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤            |報表表格名稱     |來源資料表名稱            |全域篩選                          |
|:---------------------|:---------------------|:----------------------------|:--------------------------------------|
|自動語音應答        |fAutoAttendant        |AutoAttendant                |無                                   |

|報表區段                                  |欄位 (已使用)                               |已套用篩選     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期選擇器                                   |AAStartTime                                |無                |
|時間範圍選取器                             |AAStartHour                                |無                |
|自動語音應答                                  |AA 名稱                                    |無                |
|來電來源<sup>1</sup>                |通話類型<br>SumCallCount (Measure)  |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|目錄搜尋方法                         |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod 為 abs_search_dtmf 或 abs_search_name    |
|來電者動作計數                             |AACallerActionCount<br>TotalCallCount      |無                                                             |
|AA 中的平均秒數                           |AAChainDuration (測量)                   |無                                                             |
|平均來電者動作                          |AACallerActionCount (量)               |無                                                             |
|通話結果                                    |AACallResult<br>AACallResultLegend<br>TotalCallCount             |無                                       |
|報表的下方區段                         |AA 名稱<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話類型<br>MM-DD<br>TotalCallCount |無       |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                 |文本                     |附加至自動語音應答的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **aa_test@microsoft.com**，則此值會是： **aa_test** |
|AACallerActionCount                     |整數             |摘要：加總<br>來電者在通話期間在自動語音應答中選取的動作數目  |
|AACallerActionCount (量)           |整數             |與上述相同，如果沒有來電而非空白，則會是 0。                              |
|AACallFlow                              |文本                     |封裝式顯示自動語音應答通話的不同狀態--可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |文本                     |最終通話結果--可能的值：<br><br>§ failed_to_establish_media (無法建立通話的媒體部分) <br>§ 一般由於系統錯誤) ，failover_to_operator (來電轉接給電信業者<br>§ AA) 中oaa_chain_too_long (過多的雙腳<br>§ oaa_session_too_long (AA 會話太長) <br>§ service_declined (AA 未接受通話) <br>§ service_terminated (AA 設定中斷通話或通話掛斷) <br>§ terminated_automatic_selection (AA 設定會中斷通話) <br>§ terminated_no_operator (呼叫因錯誤而終止，但未定義) 運算子 <br>§ terminated_transfer_failed (呼叫因轉接失敗而終止 - 通常是外部號碼) <br>§ transfer_in_progress (AA->AA 傳輸) <br>§ transferred_to_operator (來電轉接給電信業者 - 通常是因為使用者錯誤) <br>§ transferred_to_receptionist (與 transferred_to_operator) 相同<br>§ transferred_to_self (通話已返回 AA 的開頭 - 通常是從功能表公告選項) <br>§ transferred_to_shared_voicemail (通話已轉接至共用語音信箱) <br>§ transferred_to_user (電話已轉接給使用者 - 包括通話佇列) <br>§ 不明 (發生未知狀況) <br>§ user_terminated (來電者掛斷)  |
|AA 通話圖例                          |文本                     |根據 AACallResult 設定圖例專案                               |
|AAChainDuration                         |小數           |摘要：加總<br>自動語音應答中的通話持續時間                     |
|AAChainDuration (測量)                |小數           |與上述相同，如果沒有來電而非空白，則會是 0。              |
|AAChainIndex                            |文本                     |                                                                         |
|AAConnectivityType                      |文本                     |通話類型--可能的值：<br><br>§ ExternalCall<br>§ 內部電話 |
|AACount                                 |文本                     |參與通話的自動語音應答數目                               |
|AADirectorySearchMethod                 |文本                     |最後一個通訊錄搜尋方法--可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartHour                             |小數           |自動語音應答通話開始時間                                           |
|AAStartTime                             |日期/時間                |自動語音應答通話開始時間                                           |
|AATransferAction                        |文本                     |來電轉接目標型別--可能的值：<br><br>§ 應用程式 - 語音應用程式實體<br>§ external_pstn<br>§ hunt_group - 通話佇列實體<br>§ orgaa - 自動語音應答實體<br>§ shared_voicemail<br>§ 未知<br>§ 使用者 |
|通話類型<sup>1</sup>                   |文本                     |通話類型--可能的值：<br><br>§ 外部<br>§ 內部           |
|IsAAInvolved                            |文本                     |一律 1                                                                 |
|MM-DD                                   |文本                     |自動語音應答每月通話                                            |
|PSTNMinutes                             |整數             |摘要：加總<br>分鐘總使用量                                     |
|TotalCallCount                          |整數             |摘要：加總<br>一律 1 - 用來提供所有通話的總和            |
|SumCallCount (Measure)          |整數             |與上述相同，如果沒有來電而非空白，則會是 0。              |


### <a name="cloud-call-queue-analytics-report"></a>雲端通話佇列分析報告

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|來電來源<sup>1</sup>        |以內部/外部通話來源分派通話             |
|平均等待時間 (秒)              |等待接聽電話和已放棄通話的時間                          |
|通話音量和專員加入宣告計數      |依通話佇列分派通話 /最大代理人加入宣告計數  |
|通話結果                            |依通話結果分派通話                               |
|已放棄通話                         |以通話佇列分派已放棄的通話                     |
|平均會話長度 (秒)         |以通話結果分組的秒數來通話長度                      |
|通話溢位/逾時目的地      |分派逾時或溢出的來電                 |


#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤            |報表表格名稱                                   |來源資料表名稱                               |全域篩選       |
|:---------------------|:---------------------------------------------------|:-----------------------------------------------|:-------------------|
|通話佇列            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |CallQueueAnalytics<br>CallQueueFinalStateAction |無                |

|報表區段                      |資料表 -> 欄位 () 使用                |已套用篩選       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                       |fCallQueueAnalytics -> Date           |無                  |
|時間範圍選取器                 |fCallQueueAnalytics -> CQHour         |無                  |
|通話佇列資源帳戶         |fCallQueueAnalytics -> CQ 名稱        |無                  |
|來電來源<sup>1</sup>    |fCallQueueAnalytics ->通話次數加總 (量) <br>fCallQueueAnalytics ->通話類型    |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|Avg 等待時間 (秒) 答 |fCallQueueFinalStateAction ->平均 CQ 工期 (量的 Avg)  |通話佇列通話結果agent_joined_conference或transferred_to_agent|
|Avg 等待時間 (秒) -之前已放棄 |fCallQueueFinalStateAction ->平均通話持續時間 (量的 Avg)  |通話佇列通話結果不agent_joined_conference、transferred_to_agent、溢位、timed_out |
|通話量和專員Opt-In計數   |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->撥號佇列代理程式加入宣告計數<br>fCallQueueAnalytics -> CQ 名稱<br>fCallQueueAnalytics -> Date |無 |
|已放棄通話                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | 通話佇列通話結果圖例已放棄 |
|平均會話長度 (秒)     |fCallQueueFinalStateAction ->平均通話佇列持續時間 (秒) <br>通話佇列通話結果圖例 |平均通話佇列持續時間 (秒) > 0 |
|通話溢位/逾時目的地  |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列目標型別<br>fCallQueue 目標型別圖例 |通話佇列目標型別圖例不包含已放棄和專員已接聽 |


#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話數                              |整數             |摘要：加總<br>通話數目                                          |
|通話佇列代理人計數                  |整數             |摘要：加總<br>在通話佇列中設定的代理程式數目            |
|通話佇列代理人加入宣告計數           |整數             |摘要：加總<br>加入宣告通話佇列的專員數目              |
|通話佇列通話結果                  |文本                     |通話佇列通話的最終狀態--可能的值：<br><br>§ agent_joined_conference (接聽的會議模式電話) <br>§ 已拒絕<br>§ 已中斷連線<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 符合溢位 (溢出條件的溢位) <br>§ timed_out (逾時條件符合) <br>§ transferred_to_agent (接聽的轉接模式通話 {default})  |
|通話佇列通話結果圖例           |文本                     |根據通話佇列結果設定圖例專案                             |
|通話佇列目標型別                  |文本                     |***呼叫重新導向目標型別--可能的值：***<br><br>§ ApplicationEndpoint<br>§ 信箱<br>§ 其他<br>§ 使用者 |
|通話佇列目標型別圖例           |文本                     |根據通話佇列目標型別設定圖例專案                        |
|通話類型<sup>1</sup>                   |文本                     |通話類型--可能的值：<br><br>§ 外部<br>§ 內部             |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|CQ 小時                                 |整數             |通話佇列通話開始時間                                                 |
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)                                  | 
|DateTimeCQName                          |文本                     |在 fCallQueueFinalStateAction 上篩選的唯一金鑰                     |
|PSTN 連線類型                  |文本                     |通話類型--可能的值：<br><br>§ ExternalCall<br>§ 內部電話     |
|PSTN 總分鐘數                      |整數             |摘要：加總<br>PSTN 通話的總分鐘數使用量                       |
|通話次數 (量) 總和             |整數             |與通話計數相同，在沒有通話時會是 0                          |
|TotalCallCount (量)                 |整數             |摘要：加總<br>通話數                                                |


#### <a name="fcallqueuefinalstateaction-cqd-fields-description"></a>fCallQueueFinalStateAction CQD 欄位描述

|名稱                                    |資料類型                |描述                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話持續時間 (秒)          |小數           |摘要：加總<br>已放棄通話的平均通話持續時間為秒內    |
|平均通話佇列持續時間 (秒)        |小數           |摘要：加總<br>在已接聽的通話中等候幾秒鐘的平均值           |
|平均通話持續時間 (測量)   |整數             |與平均通話持續時間 (秒數) 但是在沒有通話時會是 0   |
|平均 CQ 工期 (量)     |整數             |與平均通話佇列持續時間 (秒) 相同，但是沒有來電時會是 0 |
|通話數                              |整數             |摘要：加總<br>通話數目                                         |
|通話佇列通話結果                  |文本                     |通話佇列通話的最終狀態--可能的值：<br><br>§ agent_joined_conference (接聽的會議模式電話) <br>§ 已拒絕<br>§ 已中斷連線<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 符合溢位 (溢出條件的溢位) <br>§ timed_out (逾時條件符合) <br>§ transferred_to_agent (接聽的轉接模式通話 {default} |
|通話佇列通話結果圖例           |文本                     |根據通話佇列通話結果設定圖例專案                      |
|通話佇列最終狀態動作           |文本                     |通話佇列最終動作--可能的值：<br><br>§ 中斷 (timed_out通話) <br>§ disconnect_with_busy (溢位通話) <br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ 其他<br>§ 語音信箱                |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)                                  |
|DateTimeCQName                          |文本                     |在 fCallQueueFinalStateAction 上篩選的唯一金鑰                     |
|IsAbandoned                             |True/false               |如果專員未接聽來電，則為 True                                   |


### <a name="cloud-call-queue-agent-timeline-report"></a>雲端通話佇列代理時間軸報告

#### <a name="report-description"></a>報告描述

|報表區段                                          |描述                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|由專員撥打的通話號碼                                |依通話佇列和代理人分派通話                |
|由專員和所有佇列發佈                     |由代理人和通話佇列分派通話                |
|表格 (右下)                                     |由代理人以平均和總通話持續時間分派通話 |
|專員)  (秒的平均通話持續時間                |專員) 通話的平均持續時間 (秒                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤            |報表表格名稱           |來源資料表名稱         |全域篩選       |
|:---------------------|:---------------------------|:-------------------------|:-------------------|
|專員時間軸        |fAgentTimelineAnalytics     |fAgentTimelineAnalytics   |無                |


|報表區段                                |欄位 (已使用)                          |已套用篩選       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                                 |Datetime                              |無                  |
|代理使用者名稱選取器                       |專員名稱                            |無                  |
|呼叫佇列資源帳戶選取器          |CQ 名稱                               |無                  |
|由專員撥打的通話號碼                      |專員名稱<br>通話數<br>小時      |無                  |
|由專員和通話佇列發佈          |專員名稱<br>平均通話持續時間 (秒) <br>通話數<br>CQ 名稱 |無                      |
|左下角                                   |專員名稱<br>平均通話持續時間 (秒) <br>通話數<br>通話持續時間 (分鐘) <br>CQ 名稱<br>小時<br>MM-DD | 無 |
|專員)  (秒的平均通話持續時間      |專員名稱<br>平均通話持續時間 (秒)  | 無 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|專員名稱                              |文本                     |使用者 UPN<br>如果完整使用者名稱 **user@microsoft.com**，則此值為： **使用者** |
|平均通話持續時間 (秒)          |小數           |摘要：加總<br>在幾秒鐘內接聽來電佇列通話的平均持續時間 |
|通話數                              |整數             |摘要：加總<br>專員接聽的電話數     |
|通話持續時間 (分鐘)                  |整數             |摘要：加總<br>已接聽來電佇列通話的總通話持續時間， (無條件舍位到最接近的分鐘)   |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|日期                                    |日期                     |通話日期                                             |
|Datetime                                |Datetime                 |通話日期                                             |
|小時                                    |整數             |通話時間                                             |
|MM-DD                                   |文本                     |月與日通話                                    |


> [!NOTE]
> 當電話到達第一個通話佇列時，如果該佇列中已經等待的來電數已達到 [ **通話溢位處理** ] 限制，而且如果重新導向選項將新電話傳送到第二個通話佇列，則第二個通話佇列中的代理程式會顯示為此報告中的第一個通話佇列。 

## <a name="known-issues"></a>已知的問題

- 通話佇列和自動語音應答會以資源帳戶的識別碼顯示，而不是通話佇列/自動語音應答名稱。  若要顯示自動語音應答或通話佇列的所有流量，您必須選取指派給自動語音應答或通話佇列的所有資源帳戶。

- 儀表板中僅提供 28 天歷程記錄，因為通話佇列/自動語音應答資料會被視為個人資料，並受限於資料隱私權保留原則。

- 在某些情況下， **雲端通話佇列代理時間軸** 報告中的代理人接聽來電計數可能與 Teams 用戶端通話記錄中顯示的通話數目不同。 Teams 用戶端通話記錄正確無誤。 支援正在調查中，但目前沒有可供修復的估計時間。

- <sup>1</sup>自動語音 **應答中的來電來源** 和通話佇列圖形會顯示最後一個通話列源，而不是初始通話列源。 例如，如果自動語音應答接聽外部來電，並將通話轉接到另一個自動語音應答或通話佇列，則來 **電來源** 會被回報為 [內部]。

## <a name="version-1xx-history"></a>版本 1.xx 歷程記錄

參考：CQD Teams 自動語音應答&通話佇列歷史報告 - 變更下載 zip 檔案中的Log.docx，以取得詳細的變更清單                         

|版本  |發佈日期     |檔案名                                                           |描述                                         |
|:--------|:------------------|:------------------------------------------------------------------|:---------------------------------------------------
|1.63     |2022 年 8 月 24 日    |CQD Teams 自動語音應答&通話佇列歷史報告 V1.63.pbit |                                                    |
|1.60     |2022 年 7 月 22 日      |CQD Teams 自動語音應答&通話佇列歷史報告 V1.60.pbit |                                                    |
|1.00     |2020 年 11 月 5 日   |CQ 和 AA 合併分析 20201105.pbit                         |初次發行                                     |

