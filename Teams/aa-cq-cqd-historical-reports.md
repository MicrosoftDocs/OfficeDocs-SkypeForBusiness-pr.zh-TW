---
title: 自動語音應答&通話佇列歷史報告
author: CarolynRowe
ms.author: crowe
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
description: 瞭解如何使用通話品質儀表板Power BI報告來檢視自動語音應答和通話佇列歷程記錄資料。
ms.openlocfilehash: e2d71410d10fb809debd1699afcf452c71a6e088
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046445"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動語音應答&通話佇列歷史報告

Teams自動語音應答&通話佇列歷史報告Power BI範本提供下列三個報告：

- [自動語音應答](media/cqd-teams-aa-cq-historical-report-sample-aa.png) ： 顯示自動語音應答中來電的分析資料。
- [通話佇列](media/cqd-teams-aa-cq-historical-report-sample-cq.png) ： 顯示來電進入通話佇列的分析資料。
- [專員時間軸](media/cqd-teams-aa-cq-historical-report-sample-at.png) ： 顯示代理程式在通話佇列通話中作用中的時程表檢視。

這些報告會使用來自 [通話品質儀表板](CQD-Power-BI-query-templates.md) 資料存放區的資料。 報告可讓組織報告自動語音應答和通話佇列處理的通話數目。  報告也會提供通話佇列中專員效能的深入解析。

## <a name="prerequisites"></a>必要條件

### <a name="power-bi-desktop"></a>Power BI Desktop
您必須安裝Power BI Desktop。 您可以從[Microsoft Windows Microsoft Store](https://aka.ms/pbidesktopstore)安裝。

您可以使用免費版本的 Power BI Desktop。 最小相容版本為 2.85.681.0 (2020 年 9 月) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管線的許可權

您用來檢視歷史報告的帳戶必須具備存取 CQD 資料管線的許可權。 如需詳細資訊，請參閱 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>安裝 

下列步驟假設您已經在電腦上安裝Power BI Desktop，而且您的帳戶具有存取 CQD 資料管線的必要許可權。

執行下列步驟：

- 下載[[CQD Power BI查詢範本](https://www.microsoft.com/download/details.aspx?id=102291)]，並將 zip 檔案儲存到電腦上的目錄。

- 按兩下 zip 檔案加以開啟。

- 按兩下 「CQ 和 AA 結合分析 20201105.pbit」範本檔案。 Power BI Desktop應該會啟動。

- 系統會提示您選取 CQD 資料管線區域。 選取租使用者所在的地區。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="選取 CQD 資料管線區域的螢幕擷取畫面。":::

- 您可以使用 [Get-CsTenant](/powershell/module/skype/get-cstenant) Cmdlet 取得租使用者所在的地區。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 在上述範例中，區域為：noam 之後 **/** 將會顯示區域

 - 報告隨即會以範例資料啟動。
 
 - 若要查看您自己的資料 **，請在**[常用] 索引標籤的 [Power BI Desktop中的查詢] 底下選取 [重新整理]。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="選取重新整理選項的螢幕擷取畫面。":::

- 系統會提示您登入。 選 **取 [組織帳戶]** ，然後選取 **[登入]**。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="顯示登入的螢幕擷取畫面。":::

- 選 **連線** 並觀看資料重新整理。

## <a name="data-latency-and-aa--cq-analytics"></a>資料延遲和 AA & CQ 分析

資料會在 30 分鐘內出現在 CQD 資料管線中。

您必須重新整理資料，才能查看新的分析資料。 

## <a name="customization"></a>定制 

您可以自訂報表的特定視覺效果層面，例如新增或移除要在各種視覺效果中顯示的欄位、變更圖表類型等等。

您無法新增更多資料欄位至報表。

### <a name="change-color-schema"></a>變更色彩架構 

下列步驟假設您已經完成安裝步驟。

執行下列步驟：
- 選取功能區上的 [ **檢視** ] 索引標籤。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="選取 [檢視] 索引標籤以變更色彩配置的螢幕擷取畫面。":::

- 從下拉式清單中選取色彩架構。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="顯示各種色彩配置的螢幕擷取畫面。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動語音應答和通話佇列歷史報告定義

### <a name="cloud-auto-attendant-analytics"></a>雲端自動語音應答分析

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|來電來源<sup>1</sup>        |以內部/外部通話來源分派通話             |
|目錄搜尋方法總計          |依搜尋類型分派通話                               |
|來電者動作                           |依來電接收器分派通話                             |
|通話結果                             |以最終通話狀態分派通話                          |
|來電者動作計數                     |根據通話期間所用的號碼動作來分派通話        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤            |報表表格名稱     |全域篩選                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動語音應答        |fAutoAttendant        |AAStartTime 在最近 28 天內 |


|報表表格名稱            |來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |AutoAttendant                |Source = AutoAttendant， <br>#「Filtered Rows」 = Table.SelectRows (Source， each true) ， <br>#「Auto Attendant」 = Table.AddColumn (#「Filtered Rows」， 「AA Name」， each List.First (Text.Split ([AAIdentity]， 「@」) ) ) ， <br>#「Changed Type」 = Table.TransformColumnTypes (#「Auto Attendant」，{{「AAStartTime」，輸入 datetime}}) ， <br>#「Remove Columns」 = Table.RemoveColumns (#「Changed Type」，{「AAIdentity」})  |


|報表區段                                  |欄位 (已使用)                               |已套用篩選     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期選擇器                                   |AAStartTime                                |無                |
|自動語音應答                                  |AA 名稱                                    |無                |
|來電來源<sup>1</sup>                |通話類型<br>TotalCallCount                |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|目錄搜尋方法總計                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod 為 abs_search_dtmf 或 abs_search_name    |
|來電者動作                                  |AATransferAction<br>TotalCallCount         |無                                                             |
|AA 中的平均秒數<br>平均來電者動作 |AAChainDuration<br>AACallerActionCount     |無                                                             |
|通話結果                                    |AACallResult<br>TotalCallCount             |無                                                             |
|來電者動作計數                            |AACallerActionCount<br>TotalCallCount      |無                                                             |
|報表的下方區段                         |AA 名稱<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話類型<br>TotalCallCount |無                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                 |文本                     |附加至自動語音應答的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **aa_test@microsoft.com**，則此值會是： **aa_test** |
|AACallerActionCount                     |整數             |摘要：加總<br>來電者在通話期間在自動語音應答中選取的動作數目  |
|AACallFlow                              |文本                     |封裝式顯示自動語音應答通話的不同狀態--可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |文本                     |最終通話結果--可能的值：<br><br>§ failed_to_establish_media (無法建立通話的媒體部分) <br>§ 一般由於系統錯誤) ，failover_to_operator (來電轉接給電信業者<br>§ AA) 中oaa_chain_too_long (過多的雙腳<br>§ oaa_session_too_long (AA 會話太長) <br>§ service_declined (AA 未接受通話) <br>§ service_terminated (AA 設定會中斷通話) <br>§ terminated_automatic_selection (AA 設定會中斷通話) <br>§ terminated_no_operator (呼叫因錯誤而終止，但未定義) 運算子 <br>§ terminated_transfer_failed (呼叫因轉接失敗而終止 - 通常是傳送至外部號碼) <br>***§ transferred_to_operator*** (來電轉接給電信業者 - 通常是因為使用者輸入錯誤) <br>§ transferred_to_receptionist (與 transferred_to_operator) 相同<br>§ transferred_to_self (通話已返回 AA 的開頭 - 通常是從功能表公告選項) <br>§ transferred_to_shared_voicemail (通話已轉接至共用語音信箱) <br>§ transferred_to_user (電話已轉接給使用者 - 包括通話佇列) <br>§ 未知 (發生未知的錯誤) <br>§ user_terminated (來電者掛斷)  |
|AAChainDuration                         |小數           |摘要：加總<br>自動語音應答中的通話持續時間                     |
|AAChainIndex                            |文本                     |                                                                         |
|AAConnectivityType                      |文本                     |通話類型--可能的值：<br><br>§ ExternalCall<br>§ 內部電話 |
|AACount                                 |文本                     |參與通話的自動語音應答數目                               |
|AADirectorySearchMethod                 |文本                     |最後一個通訊錄搜尋方法--可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日期/時間                |自動語音應答通話開始時間                                           |
|AATransferAction                        |文本                     |來電轉接目標型別--可能的值：<br><br>***§ 應用程式 - 語音應用程式實體**_<br> § external_pstn <br>_*_§ hunt_group - 通話佇列實體_* _<br>_ * _§ orgaa - 組織自動語音應答實體_**<br>§ shared_voicemail<br>§ 未知<br>§ 使用者 |
|通話類型<sup>1</sup>                   |文本                     |通話類型--可能的值：<br><br>§ 外部<br>§ 內部         |
|IsAAInvolved                            |文本                     |一律 1                                                                 |
|PSTNMinutes                             |整數             |摘要：加總<br>分鐘總使用量                                     |
|TotalCallCount                          |整數             |摘要：加總<br>一律 1 - 用來提供所有通話的總和            |


### <a name="cloud-call-queue-analytics"></a>雲端通話佇列分析

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|來電來源<sup>1</sup>        |由內部/外部通話來源散播通話              |
|通話音量                             |依通話佇列分派通話                                |
|來電者結果                           |依通話結果分派通話                                |
|逾時/溢出通話總計動作      |未轉接 (已根據通話結果捨棄) 呼叫的分配       |
|轉移/轉寄目標總計          |呼叫結果轉接的呼叫分配                      |
|已放棄通話比例                   |成功與放棄通話計數的比例                        |
|平均會話長度 (秒)         |以已放棄/成功的通話分組的秒數來通話長度       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤         |報表表名稱                                                          |全域篩選 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|通話佇列         |日期<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |無          |
 
|報表表格名稱            |來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|日期                        |日期                        |無             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics， <br>#「Remove Columns」 = Table.RemoveColumns (Source，{「Call Count」， 「Call Queue Call Result」， 「Date」， 「PSTN 連線類型」， 「呼叫佇列目標型別」， 「PSTN 總通話分鐘數」}) ，<br>Distinct = Table.Distinct (#「Removed Columns」)  |
|fCallQueueAnalytics          |CallQueueAnalytics           |無             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |無             |

|報表區段                      |資料表 -> 欄位 () 使用                |已套用篩選       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                       |日期 -> DateTime                     |無                  |
|通話佇列身分識別                 |dCQ-CQIdentity ->通話佇列身分識別 |無                  |
|來電來源<sup>1</sup>    |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話類型    |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|Avg 等待時間                    |fCallQueueFinalStateAction ->平均通話持續時間 (秒)  |轉接之前：通話佇列通話結果agent_joined_conference或transferred_to_agent<br>掛斷之前：通話佇列通話結果不agent_joined_conference或transferred_to_agent |
|通話結果                         |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列通話結果 | 無 |
|逾時/溢出通話總計動作 |fCallQueueFinalStateAction ->通話計數<br>fCallQueueFinalStateAction ->通話佇列最終狀態動作 |未轉接通話佇列最終狀態動作 |
|傳輸/Forard 目標總計       |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列目標型別 |無 |
|通話區                        |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列識別<br>fCallQueueAnalytics -> Date |無 |
|已放棄通話                     |fCallQueueAnalytics -> %放棄通話<br>fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned 為 True |
|平均會話長度 (秒)     |fCallQueueFinalStateAction ->平均通話持續時間<br>fCallQueueFinalStateAction -> Date<br>fCallQueueFinalStateAction -> IsAbandoned |無 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話數                              |整數             |摘要：加總<br>通話數目                                          |
|通話佇列通話結果                  |文本                     |通話佇列通話的最終狀態 -- 可能的值：<br><br>§ agent_joined_conference (接聽的會議模式電話) <br>§ 已拒絕<br>§ 已中斷連線<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 符合溢位 (溢出條件的溢位) <br>§ timed_out (逾時條件符合) <br>§ transferred_to_agent (接聽的 Tranfer 模式通話 {default})  |
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|通話佇列目標型別                  |文本                     |***呼叫重新導向目標型別--可能的值：***<br><br>§ ApplicationEndpoint<br>§ 信箱<br>§ 其他<br>§ 使用者 |
|通話類型<sup>1</sup>                   |文本                     |通話類型--可能的值：<br><br>§ 外部<br>§ 內部           |
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)  (UTC)                            | 
|IsAbandoned                             |True/false               |如果專員未接聽來電，則為 True                                   |
|PSTN 連線類型                  |文本                     |通話類型--可能的值：<br><br>§ ExternalCall<br>§ 內部電話   |
|PSTN 總分鐘數                      |整數             |摘要：加總<br>PSTN 通話的總分鐘數使用量                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 量值描述

|名稱                                    |資料類型                |描述                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***%已放棄通話***                 |百分比               |量值：已放棄的通話數 /總通話數    |
|總通話數                             |整數             |量值：加總專員接聽的電話        |
|TotalCallCount                          |整數             |量值： (通話數) 加總                 |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 欄位描述

|名稱                                    |資料類型                |描述                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話持續時間 (秒)          |小數           |摘要：加總<br>以秒為內的平均通話持續時間 |
|通話數                              |整數             |摘要：加總<br>通話數目                  |
|通話佇列通話結果                  |文本                     |通話佇列通話的最終狀態--可能的值：<br><br>§ agent_joined_conference (接聽的會議模式電話) <br>§ 已拒絕<br>§ 已中斷連線<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 符合溢位 (溢出條件的溢位) <br>§ timed_out (逾時條件符合) <br>§ transferred_to_agent (接聽的轉接模式通話 {default} |
|通話佇列最終狀態動作           |文本                     |通話佇列最終動作--可能的值：<br><br>§ 中斷 (timed_out通話) <br>§ disconnect_with_busy (溢位通話) <br>§ failed_to_accept_call<br>§ forward<br>§ shared_voicemail<br>§ 其他<br>§ 語音信箱 |
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)  (UTC)    |
|IsAbandoned                             |True/false               |如果專員未接聽來電，則為 True           |


### <a name="cloud-call-queue-agent-timeline"></a>雲端通話佇列代理時間軸

#### <a name="report-description"></a>報告描述

|報表區段                                          |描述                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|# 由專員撥打電話                                        |以通話佇列和代理人分派通話                 |
|根據專員和通話佇列) 總通話持續時間 (秒   |專員和通話佇列) 總持續時間 (秒     |
|專員名稱)  (秒的平均通話持續時間           |專員) 通話的平均持續時間 (秒                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>報表至 CQD 資料表和欄位對應

|[報表] 索引標籤         |報表表名稱        |全域篩選 |
|:------------------|:-------------------------|:-------------|
|專員時間軸     |fAgentTimelineAnalytics   |無          |
 
|報表表格名稱            |來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics， <br>#「Changed Type」 = Table.TransformColumnTypes (Source，{{「Call Count」， Int64.Type}， {「Call Duration (Minute) 」， Int64.Type}， {「Average Call Duration (Second) 」， type number}， {「Date」， type date}}) |

|報表區段                                |欄位 (已使用)                          |已套用篩選       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|專員名稱                                    |專員名稱                            |無                  |
|通話佇列名稱                               |通話佇列名稱                       |無                  |
|#Calls依專員                               |專員名稱<br>通話數<br>日期      |無                  |
|由專員和通話佇列發佈          |專員名稱<br>通話數<br>通話持續時間 (分鐘) <br>通話佇列名稱 |無                      |
|左下角                                   |專員名稱<br>第二)  (平均通話持續時間<br>通話數<br>通話持續時間 (分鐘) <br>通話佇列名稱 | 無 |
|[專員名稱] (秒) 的平均通話持續時間 |專員名稱<br>第二)  (平均通話持續時間<br>通話數<br>通話持續時間 (分鐘) <br>通話佇列名稱 | 無 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|專員名稱                              |文本                     |使用者 UPN<br>如果完整使用者名稱 **user@microsoft.com**，則此值為： **使用者** |
|第二)  (平均通話持續時間          |小數           |摘要：加總<br>在幾秒鐘內接聽來電佇列通話的平均持續時間 |
|通話數                              |整數             |摘要：加總<br>撥打給專員的電話數     |
|通話持續時間 (分鐘)                   |整數             |摘要：加總<br>已接聽來電佇列通話的總通話持續時間， (無條件舍位到最接近的分鐘)   |
|通話佇列名稱                         |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|日期                                    |日期                     |                                                    |


> [!NOTE]
> 1) 這份報告會從專員的觀點顯示通話計數，因此此報告中的通話總數通常會高於 **雲端通話佇列分析** 報告中的通話總數。 佇列中的每個通話在接聽電話之前，至少可以向一或多個專員接聽一次。 向專員顯示的每一個通話佇列通話都會計入此報告，即使該專員未接聽。 這兩個報告之間的通話計數差異會更加明顯，因為 **語音應答路由** 選項會撥打每一個來電的代理人。 
> 2) 當通話第一次到達第一個通話佇列時，如果該佇列中已經等待的來電數超過 [ **通話溢位處理** ] 限制，而且如果重新導向選項將電話傳送到第二個通話佇列，則第二個通話佇列中的代理程式會顯示為此報告中的第一個通話佇列中。 

## <a name="known-issues"></a>已知問題

- 通話佇列和自動語音應答會以資源帳戶的識別碼顯示，而不是通話佇列/自動語音應答名稱。  若要顯示自動語音應答或通話佇列的所有流量，您必須選取指派給自動語音應答或通話佇列的所有資源帳戶。

- 儀表板中只提供 28 天歷程記錄，因為通話佇列/自動語音應答資料會被視為個人資料，並受限於資料隱私權保留原則。

- 在某些情況下，雲端通話佇列代理人時程表報告中的代理人接聽來電計數，可能與Teams用戶端通話記錄中顯示的通話數目不同。 Teams用戶端通話記錄正確無誤。 支援正在調查中，但目前沒有可供修復的估計時間。

- <sup>1</sup>自動語音應答和通話佇列圖形中的來 **電來源** 會顯示最後一個通話列源，而不是初始通話列源。 例如，如果自動語音應答接聽外部電話，並將電話轉接到另一個自動語音應答或通話佇列，則來 **電來源** 會被回報為 [內部]。
