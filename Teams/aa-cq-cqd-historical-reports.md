---
title: 已更新自動語音應答和通話佇列歷史報告
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
description: 瞭解如何使用更新的 Teams 自動語音應答&通話佇列歷程報告 Power BI 報告來檢視自動語音應答和通話佇列歷程記錄資料。
ms.openlocfilehash: 0ff8e7d1b5a1b9901c5b8a5da49d67fbf8ac5275
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812730"
---
# <a name="auto-attendant-and-call-queue-historical-reports"></a>自動語音應答和通話佇列歷史報告

>[!NOTE]
> GCC HIgh 和 DOD 客戶應該繼續使用 V1.63 的 [自動語音應答&通話佇列歷史報告 (CQD) ](aa-cq-cqd-historical-reports-v163.md)。

此 Power BI 範本提供三個報告，可讓組織報告自動語音應答和通話佇列處理的通話數目。  它也會提供代理程式效能深入解析。

## <a name="v305-published-on-january-9-2023"></a>V3.0.5 發佈日期：2023 年 1 月 9 日

Teams 自動語音應答&通話佇列歷史報告 Power BI 範本提供下列三個報告：

- 自動 [語音應答](media/aa-cq-historical-report-sample-aa-v305.png) 報告會顯示自動語音應答中來電的分析資料。
- [ [通話佇列](media/aa-cq-historical-report-sample-cq-v305.png) ] 報告會顯示來電進入通話佇列的分析資料。
- [專員時程表](media/aa-cq-historical-report-sample-at-v305.png)報告顯示代理程式在通話佇列通話中作用中的時程表檢視。

這些報告會使用來自 Voice Applications Analytics Collector (VAAC) 服務的資料。

## <a name="v3xx-prerequisites"></a>V3.x.x 必要條件

### <a name="power-bi-desktop"></a>Power BI Desktop

您必須安裝Power BI Desktop。 您可以從 [Microsoft Windows 市](https://aka.ms/pbidesktopstore)集安裝並使用免費版本。

最小相容版本為 2.85.681.0 (2020 年 9 月) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管線的許可權

雖然此版本的報告不會使用 [通話品質儀表板] (CQD) 資料管線，但用來檢視歷史資料的帳戶仍需要存取通話品質儀表板。 如需詳細資訊，請參閱 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

將 [ **檢視報表** ] 和 [ **檢視 EUII] 欄位** 設為 [ **是** ] 的任何 CQD 角色都可運作。

- 此需求將會在未來版本中移除。

## <a name="v3xx-installation"></a>V3.x.x 安裝 

下列步驟假設您已經在電腦上安裝Power BI Desktop，而且您的帳戶擁有存取 CQD 資料管線的必要許可權。

執行下列步驟：

1. 下載並將 [Teams 自動語音應答&通話佇列歷程記錄報告V3.0.5.zip](https://www.microsoft.com/download/details.aspx?id=104623) 檔案儲存在您的電腦上。

2. 開啟 zip 檔案。

3. 開啟 `Teams Auto Attendant & Call Queue Historical Reports V3.0.5.pbit` 範本檔案。 Power BI Desktop應該會啟動。

4. 系統會提示您選取 **[資料來源]**。  選取 `api.interfaces.records.teams.microsoft.com` 專案。

  :::image type="content" source="media/aa-cq-historical-report-01-v305.png" alt-text="選取 [資料 api.interfaces.records.teams.microsoft.com 窗格] 的螢幕擷取畫面":::

5. 系統會提示您使用帳戶登入。 選取 **[組織帳戶**]，然後選取 [ **登入]**。

  :::image type="content" source="media/aa-cq-historical-report-03-v300.png" alt-text="顯示 V3.0.0.0 登入的螢幕擷取畫面。":::

6. 選取 **[連線**]，資料就會重新整理。

> [!NOTE]
> 如果您使用的是 v1.63 或更舊版本，當 v3.x.x 嘗試從 VAAC 擷取資料時，可能會遇到錯誤。  若要解決此錯誤，必須從 Power BI 清除任何先前的認證。
> 
> 1. 開啟 v3.x.x 範本以清除錯誤。 
> 1. 選 **取 [設定****資料來源設定**] &  >  [**檔案**  >  選項]。
> 1. 選取 **[清除許可權] 的** 下拉式清單，然後選取 **[清除擁有權限]**。
> 1. 清除範本之後關閉範本，然後重新開機 Power BI。 系統會要求您再次授權。 

## <a name="data-latency-for-auto-attendant-and-call-queue-analytics"></a>自動語音應答和通話佇列分析的資料延遲

資料通常會在通話完成後的 30 分鐘內取得;不過，在某些情況下，資料可能需要數小時才會顯示。 

您必須重新整理資料，才能看到任何新資料。

## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動語音應答和通話佇列歷史報告定義

### <a name="cloud-auto-attendant-analytics-report"></a>雲端自動語音應答分析報告

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|來電來源                    |以內部/外部通話來源分派通話            |
|目錄搜尋方法                 |依搜尋類型分派通話                              |
|來電者動作計數                     |根據通話期間所用的號碼動作來分派通話       |
|AA 中的平均秒數                   |在 AA 中，來電者花費的平均秒數                 |
|平均來電者動作                  |來電者在 AA 中執行的動作平均數目               |
|通話結果                            |以最終通話狀態分派通話                         |
|報表的下方區段                 |通話流程明細                                               |

#### <a name="report-visual-and-field-mapping"></a>報表視覺和欄位對應

|[報表] 索引標籤            |報表表格名稱     |全域篩選                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動語音應答        |fAutoAttendant        |無                                   |

|報表區段                               |欄位 (已使用)                                                                                     |已套用篩選 |
|:--------------------------------------------|:------------------------------------------------------------------------------------------------|:----------|
|日期選擇器                                |AAStartTime                                                                                      |無       |
|時間範圍選取器                          |AAStartHour                                                                                      |無       |
|自動語音應答資源帳戶             |AA 名稱                                                                                          |無       |
|來電來源                         |通話類型<br>TotalCallCount 的總和         |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|目錄搜尋方法                      |AADirectorySearchMethod<br>AADirectorySearchMethodLegend<br>TotalCallCount  |AADirectorySearchMethod 為 abs_search_dtmf 或 abs_search_name    |
|來電者動作計數                          |AACallerActionCount<br>TotalCallCount                                                            |無       |
|AA 中的平均秒數                        |AAChainDuration                                                                                  |無       |
|平均來電者動作                       |AACallerActionCount                                                                              |無       |
|通話結果                                 |AACallResult<br>AACallResultLegend<br>TotalCallCount                                             |無       |
|報表的下方區段                      |MM-DD<br>AA 名稱<br>AACallFlow<br>通話類型<br>AACallResult<br>TotalCallCount<br>AAChainDuration |無       |

#### <a name="fautoattendant-field-description"></a>fAutoAttendant 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                 |文本                     |附加至自動語音應答的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **aa_test@microsoft.com**，則此值會是： **aa_test** |
|AA 開始時間 UTC                       |日期/時間                |自動語音應答通話開始時間 - UTC                                                     |
|AACallerActionCount                     |整數             |摘要：加總<br>來電者在通話期間在自動語音應答中選取的動作數目  |
|AACallerActionCount (量)            |整數             |與 AACallerActionCount 相同，如果沒有來電而非空白，則會是 0。                |
|AACallFlow                              |文本                     |請參閱自動語音應答尺寸 -> AutoAttendantCallFlow                                   |
|AACallResult                            |文本                     |請參閱自動語音應答尺寸 -> AutoAttendantCallResult                                 |
|AACallResultLegend                      |文本                     |根據 AACallResult 設定圖例專案                                               |
|AAChainDuration                         |小數           |摘要：加總<br>自動語音應答中的通話持續時間                                     |
|AAChainDuration (測量)                |小數           |與 AAChainDuration 相同，如果沒有來電而非空白，則會是 0。                    |
|AAChainIndex                            |整數             |                                                                                         |
|AAConnectivityType                      |文本                     |請參閱通用維度 -> PSTNConnectivityType                                            |
|AACount                                 |整數             |參與通話的自動語音應答數目                                               |
|AADirectorySearchMethod                 |文本                     |請參閱自動語音應答尺寸 -> AutoAttendantDirectorySearchMethod                      |
|AADirectorySearchMethodLegend           |文本                     |根據 AADirectorySearchMethod 設定圖例專案                                    |
|AAStartHour                             |整數             |自動語音應答通話開始時間                                                           |
|AAStartTime                             |日期/時間                |自動語音應答通話開始時間                                                           |
|AATransferAction                        |文本                     |請參閱自動語音應答維度 -> AutoAttendantTransferAction                             |
|通話持續時間秒數                   |整數             |通話持續時間                                                                            |
|通話結束時間：當地時間                     |日期/時間                |通話結束時間 - 根據電腦執行報告的時區 ()                     |
|通話結束時間 UTC                       |日期/時間                |通話結束時間 - UTC                                                                      |
|通話開始時間：本機時間                   |日期/時間                |通話開始時間 - 根據電腦執行報告的時區 ()                   |
|通話開始時間 UTC                     |日期/時間                |通話開始時間 - UTC                                                                    |
|通話類型<sup>1</sup>                   |文本                     |請參閱通用維度 -> PSTNallType                                                    |
|ConferenceID                            |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|DialogID                                |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|DocumentID                              |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|MM-DD                                   |文本                     |自動語音應答每月通話                                                            |
|PSTNMinutes                             |整數             |摘要：加總<br>分鐘總使用量                                                     |
|SumCallCount (Measure)          |整數             |與 TotalCallCount 相同，如果沒有來電，除外則為 0 而非空白                     |
|TotalCallCount                          |整數             |摘要：加總<br>一律 1 - 用來提供所有通話的總和                            |


### <a name="cloud-call-queue-analytics-report"></a>雲端通話佇列分析報告

#### <a name="report-description"></a>報告描述

|報表區段                          |描述                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|來電來源                    |以內部/外部通話來源分派通話             |
|平均等待時間 (秒)              |等待接聽電話和已放棄通話的時間                         |
|通話音量和專員加入宣告計數      |依通話佇列分派通話 /最大代理人加入宣告計數  |
|通話結果                            |依通話結果分派通話                               |
|已放棄通話                         |以通話佇列分派已放棄的通話                     |
|平均會話長度 (秒)         |以通話結果分組的秒數來通話長度                      |
|通話溢位/逾時目的地      |分派逾時或溢出的來電                 |


#### <a name="report-visual-and-field-mapping"></a>報表視覺和欄位對應

|[報表] 索引標籤            |報表表格名稱                                   |全域篩選       |
|:---------------------|:---------------------------------------------------|:-------------------|
|通話佇列            |fCallQueueAnalytics<br>fCallQueueFinalStateAction   |無                |

|報表區段                      |資料表 -> 欄位 () 使用                |已套用篩選       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                       |fCallQueueAnalytics -> Date           |無                  |
|時間範圍選取器                 |fCallQueueAnalytics -> CQHour         |無                  |
|通話佇列資源帳戶         |fCallQueueAnalytics -> CQ 名稱        |無                  |
|來電來源                |fCallQueueAnalytics ->通話次數加總 (量)   |外部通話：通話類型為外部<br>內部通話：通話類型為內部通話 |
|Avg 等待時間 (秒) 答 |fCallQueueFinalStateAction ->平均 CQ 工期 (量的 Avg)  |通話佇列通話結果agent_joined_conference或transferred_to_agent|
|Avg 等待時間 (秒) -之前已放棄 |fCallQueueFinalStateAction ->平均通話持續時間 (量的 Avg)  |通話佇列通話結果不agent_joined_conference、transferred_to_agent、溢位、timed_out |
|通話量和專員Opt-In計數   |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->撥號佇列代理程式加入宣告計數<br>fCallQueueAnalytics -> CQ 名稱<br>fCallQueueAnalytics -> Date |無 |
|已放棄通話                     |fCallQueueAnalytics -> Date<br>fCallQueueAnalytics -> TotalCallCount | 通話佇列通話結果圖例已放棄 |
|平均會話長度 (秒)     |fCallQueueFinalStateAction ->平均通話佇列持續時間 (秒) <br>通話佇列通話結果圖例 |平均通話佇列持續時間 (秒) > 0 |
|通話溢位/逾時目的地  |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列目標型別<br>fCallQueue 目標型別圖例 |通話佇列目標型別圖例不包含已放棄和專員已接聽 |


#### <a name="fcallqueueanalytics-field-description"></a>fCallQueueAnalytics 欄位描述

|名稱                                    |資料類型                |描述                                                                              |
|:---------------------------------------|:------------------------|:----------------------------------------------------------------------------------------|
|通話數                              |整數             |摘要：加總<br>通話數目                                                        |
|通話持續時間秒數                   |整數             |通話持續時間                                                                            |
|通話結束時間：當地時間                     |日期/時間                |通話結束時間 - 根據電腦執行報告的時區 ()                     |
|通話結束時間 UTC                       |日期/時間                |通話結束時間 - UTC                                                                      |
|通話佇列代理人計數                  |整數             |摘要：加總<br>在通話佇列中設定的代理程式數目                          |
|通話佇列代理人加入宣告計數           |整數             |摘要：加總<br>加入宣告通話佇列的專員數目                            |
|通話佇列通話結果                  |文本                     |請參閱通話佇列維度 -> CallQueueCallResult                                         |
|通話佇列通話結果圖例           |文本                     |根據通話佇列結果設定圖例專案                                          |
|通話佇列目標型別                  |文本                     |請參閱通話佇列維度 -> CallQueueTargetType                                         |
|通話佇列目標型別圖例           |文本                     |根據通話佇列目標型別設定圖例專案                                     |
|通話開始時間：本機時間                   |日期/時間                |通話開始時間 - 根據電腦執行報告的時區 ()                   |
|通話開始時間 UTC                     |日期/時間                |通話開始時間 - UTC                                                                    |
|通話類型                               |文本                     |請參閱通用維度 -> PSTNallType                                                    |
|ConferenceID                            |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|CQ 小時                                 |整數             |通話佇列通話開始時間                                                               |
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)                                                | 
|DateTimeCQName                          |文本                     |在 fCallQueueFinalStateAction 上篩選的唯一金鑰                                   |
|DialogID                                |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|DocumentID                              |文本                     |用於疑難排解目的 - 開啟票證時提供此資訊       |
|PSTN 連線類型                  |文本                     |請參閱通用維度 -> PSTNConnectivityType                                            |
|PSTN 總分鐘數                      |整數             |摘要：加總<br>PSTN 通話的總分鐘數使用量                                     |
|通話次數 (量) 總和             |整數             |與通話計數相同，在沒有通話時會是 0                                        |
|TotalCallCount (量)                 |整數             |摘要：加總<br>通話數                                                             |


#### <a name="fcallqueuefinalstateaction-field-description"></a>fCallQueueFinalStateAction 欄位描述

|名稱                                    |資料類型                |描述                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|平均通話持續時間 (秒)          |小數           |摘要：加總<br>已放棄通話的平均通話持續時間為秒內     |
|平均通話佇列持續時間 (秒)        |小數           |摘要：加總<br>以秒為平均等待時間以內接聽來電       |
|平均通話持續時間 (測量)   |整數             |與平均通話持續時間 (秒數) 但是在沒有通話時會是 0    |
|平均 CQ 工期 (量)     |整數             |與平均通話佇列持續時間 (秒) 相同，但是沒有來電時會是 0  |
|通話數                              |整數             |摘要：加總<br>通話數目                                          |
|通話佇列通話結果                  |文本                     |請參閱通話佇列維度 -> CallQueueCallResult                           |
|通話佇列通話結果圖例           |文本                     |根據通話佇列通話結果設定圖例專案                       |
|通話佇列最終狀態動作           |文本                     |請參閱通話佇列維度 -> CallQueueFinaleStateAction                    |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|CQ 小時                                 |數量                   |通話在一小時內進行
|日期                                    |日期/時間                |通話佇列通話開始日期和時間 (小時)                                  |
|DateTimeCQName                          |文本                     |在 fCallQueueFinalStateAction 上篩選的唯一金鑰                     |
|IsAbandoned                             |True/false               |如果專員未接聽來電，則為 True                                    |


### <a name="cloud-call-queue-agent-timeline-report"></a>雲端通話佇列代理時間軸報告

#### <a name="report-description"></a>報告描述

|報表區段                                          |描述                                                         |
|:-------------------------------------------------------|:-------------------------------------------------------------------|
|由專員撥打的通話號碼                                |依通話佇列和代理人分派通話                       |
|由專員和所有佇列發佈                     |由代理人和通話佇列分派通話                       |
|表格 (左下)                                      |由代理人以平均和總通話持續時間分派通話 |
|專員 (右下) ) 的平均通話持續時間 (秒 |專員) 通話的平均持續時間 (秒                         |

#### <a name="report-visual-field-mapping"></a>報表視覺欄位對應

|[報表] 索引標籤            |報表表格名稱           |全域篩選       |
|:---------------------|:---------------------------|:-------------------|
|專員時間軸        |fAgentTimelineAnalytics     |無                |


|報表區段                                |欄位 (已使用)                          |已套用篩選       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                                 |Datetime                              |無                  |
|代理使用者名稱選取器                       |專員名稱                            |無                  |
|呼叫佇列資源帳戶選取器         |CQ 名稱                               |無                  |
|由專員撥打的通話號碼                      |通話數<br>專員名稱<br>日期<br>小時      |無                  |
|由專員和通話佇列發佈          |專員名稱<br>平均通話持續時間 (秒) <br>通話數<br>CQ 名稱 |無                      |
|左下角                                   |專員名稱<br>平均通話持續時間 (秒) <br>通話數<br>通話持續時間 (分鐘) <br>CQ 名稱<br>小時<br>MM-DD | 無 |
|專員)  (秒的平均通話持續時間      |專員名稱<br>平均通話持續時間 (秒)  | 無 |

#### <a name="fagenttimelineanalytics-field-description"></a>fAgentTimelineAnalytics 欄位描述

|名稱                                    |資料類型                |描述                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|專員名稱                              |文本                     |使用者 UPN<br>如果完整使用者名稱 **user@microsoft.com**，則此值為： **使用者** |
|平均通話持續時間 (秒)          |小數           |摘要：加總<br>在幾秒鐘內接聽來電佇列通話的平均持續時間 |
|通話持續時間 (分鐘)                  |整數             |摘要：加總<br>已接聽來電佇列通話的總通話持續時間， (無條件舍位到最接近的分鐘)   |
|接聽的來電                          |整數             |專員接聽的電話數                        |
|未接聽來電                      |整數             |專員未接聽的電話數                    |
|CQ 名稱                                 |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶名稱 **cq_test@microsoft.com**，則此值會是： **cq_test** |
|日期                                    |日期                     |通話日期                                             |
|Datetime                                |Datetime                 |通話日期                                             |
|小時                                    |整數             |通話時間                                             |
|MM-DD                                   |文本                     |月與日通話                                    |
|通話總數                        |整數             |摘要：加總<br>撥打給專員的電話數     |

> [!NOTE]
> 當電話到達第一個通話佇列時，如果該佇列中已經等待的來電數已達到 [ **通話溢位處理** ] 限制，而且如果重新導向選項將新電話傳送到第二個通話佇列，則第二個通話佇列中的代理程式會顯示為此報告中的第一個通話佇列。 

## <a name="known-issues"></a>已知的問題

- [**通話佇列**] 報告中的 [**通話結果**] 視覺效果可能會報告大量 **_未知_** 的通話。 這是因為支援服務正在努力修正通話分類問題所導致。  這只是通話分類的問題，系統已成功處理這些通話。

- 只有第一個自動語音應答或接聽來電的來電佇列中會顯示來電和來電者動作。  當一個自動語音應答轉接至另一個自動語音應答) 或連結的通話佇列 (當一個通話佇列移轉到另一個通話佇列) 未回報時，自動語音應答中的來電和來電動作會 (。 

- 通話佇列和自動語音應答會以資源帳戶的識別碼顯示，而不是通話佇列或自動語音應答名稱。  若要顯示自動語音應答或通話佇列的所有流量，您必須選取指派給自動語音應答或通話佇列的所有資源帳戶。

- 儀表板中僅提供 28 天歷程記錄，因為通話佇列和自動語音應答資料會被視為個人資料，並受限於資料隱私權保留原則。

- 在某些情況下， **雲端通話佇列代理時間軸** 報告中的代理人接聽來電計數可能與 Teams 用戶端通話記錄中顯示的通話數目不同。 Teams 用戶端通話記錄正確無誤。 支援正在調查中，但目前沒有可供修復的估計時間。

## <a name="customization"></a>定制 

您可以自訂報表的特定視覺效果層面，例如新增或移除要顯示在各種視覺效果中的欄位、變更圖表類型等等。

### <a name="change-color-schema"></a>變更色彩架構 

下列步驟假設您已經完成安裝步驟。

執行下列步驟：

1. 選取功能區上的 [ **檢視** ] 索引標籤。

  :::image type="content" source="media/aa-cq-historical-report-04.png" alt-text="選取 [檢視] 索引標籤以變更色彩配置的螢幕擷取畫面。":::

2. 從下拉式清單中選取色彩架構。

  :::image type="content" source="media/aa-cq-historical-report-05.png" alt-text="顯示各種色彩配置的螢幕擷取畫面。":::
  
## <a name="dimensions-and-measurements"></a>維度和度量單位

您可以使用下列維度和度量單位。

### <a name="common-dimensions"></a>一般維度

自動語音應答和通話佇列都有這些維度：

|名稱 (類型)                                             |可能的值                |描述                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|ConferenceId<br> (文字)                                  |Guid                           |通話識別碼                                                   |
|日期<br> (DateTime)                                      |                               | (UTC) 通話日期                                                |
|DialogId<br> (文字)                                      |Guid                           |通話識別碼                                                   |
|DocumentId<br> (文字)                                    |Guid                           |通話識別碼                                                   |
|時間<br> (整數)                              |                               |通話持續時間，以秒為內                                      |
|EndTime<br> (DateTime)                                   |                               |時間通話 (UTC)                                              |
|FirstIsCaller<br> (布林值)                              |                               |[第一個和第二個端點分類](dimensions-and-measures-available-in-call-quality-dashboard.md)     |
|FirstUPN<br> (文字)                                      |                               |第一個端點使用者的 UPN)  (使用者主體名稱        |
|小時<br> (文字)                                          |                               |在 UTC)  (啟動小時通話                                           |
|分鐘<br> (文字)                                        |                               | (UTC) 啟動的分鐘通話                                         |
|PSTNCallDuration<br> (整數)                      |                               |通話持續時間                                              |
|PSTNCallType<br> (文字)                                  |                               |                                                                  |
|                                                       |外部                       |來電來自租使用者外部                            |
|                                                       |內部                       |來電來自租使用者內部                             |
|PSTNConnectivityType<sup>1</sup><br> (文字)              |                               |                                                                  |
|                                                       |CallingPlan                    |                                                                  |
|                                                       |DirectRouting                  |                                                                  |
|第二<br> (文字)                                        |                               |第二次通話 (UTC)                                          |
|SecondUPN<br> (文字)                                     |                               |第二個端點使用者的 UPN)  (使用者主體名稱       |
|TenantId<br> (文字)                                      |                               |租用戶識別碼                                                         |
|時間 戳<br> (DateTime)                                 |                               |時間記錄是 (UTC) 撰寫                                     |
|UserStartTimeUTC<br> (DateTime)                          |                               |UTC)  (啟動時間通話                                           |

- <sup>1</sup> **PSTNConnectivityType** 會顯示最終通話腿源，而不是初始通話列來源。 例如，如果自動語音應答接聽外部來電，並將通話轉接到另一個自動語音應答或通話佇列，則來 **電來源** 會被回報為 **[內部]**。


### <a name="auto-attendant-dimensions"></a>自動語音應答尺寸

|名稱 (類型)                                             |可能的值                |描述                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AutoAttendantCallFlow<br> (文字)                         |                               |封裝式顯示自動語音應答通話的不同狀態          |
|                                                       |abs_search                     |                                                                  |
|                                                       |公告                   |                                                                  |
|                                                       |automatic_menu                 |                                                                  |
|                                                       |call_termination               |                                                                  |
|                                                       |call_transfer                  |                                                                  |
|                                                       |first_level_menu               |                                                                  |
|                                                       |main_menu                      |                                                                  |
|                                                       |speech_input_confirmation      |                                                                  |
|                                                       |user_selection                 |                                                                  |
|AutoAttendantCallResult<br> (文字)                       |                               |最終通話結果                                                 |
|                                                       |failed_to_establish_media      |無法建立通話的媒體部分             |
|                                                       |failover_to_operator           |來電轉接給電信業者通常是因為系統錯誤      |
|                                                       |oaa_chain_too_long             |AA 中的雙腳太多                                           |
|                                                       |oaa_session_too_long           |AA 會話持續太久                                    |
|                                                       |service_declined               |AA 未接受通話                                         |
|                                                       |service_terminated             |AA 設定會中斷通話或掛斷通話             |
|                                                       |terminated_automatic_selection |AA 設定會中斷通話                           |
|                                                       |terminated_no_operator         |全部因未定義運算子的錯誤而終止                   |
|                                                       |terminated_transfer_failed     |呼叫因轉接失敗而終止 - 通常是外部號碼 |
|                                                       |transfer_in_progress           |AA->AA 傳輸                                                   |
|                                                       |transferred_to_operator        |電話已轉接給電信業者                                  |
|                                                       |transferred_to_cq              |已將通話轉移至通話佇列                                |
|                                                       |transferred_to_receptionist    |與 transferred_to_operator 相同                                   |
|                                                       |transferred_to_self            |通話已傳回至 AA 的開頭                          |
|                                                       |transferred_to_shared_voicemail |通話已轉接至共用語音信箱                         |
|                                                       |transferred_to_user            |通話已轉接給使用者                                    |
|                                                       |未知                        |發生未知的條件                                 |
|                                                       |user_terminated                |來電者掛斷                                                    |
|AutoAttendantCallerActionCounts<br> (整數)       |                               |                                                                  |
|AutoAttendantChainDurationInSecs<br> (實數)       |                               |                                                                  |
|AutoAttendantChainIndex<br> (整數)               |                               |                                                                  |
|AutoAttendantChainStartTime<br> (DateTime)               |                               |                                                                  |
|AutoAttendantCount<br> (整數)                    |                               |                                                                  |
|AutoAttendantDirectorySearchMethod<br> (文字)            |                               |目錄搜尋方法                                           |
|                                                       |abs_search_dtmf                |觸控色調                                                        |
|                                                       |abs_search_voice               |語音                                                             |
|AutoAttendantIdentity<br> (文字)                         |                               |已收到資源帳戶 URI 通話                              |
|AutoAttendantTransferAction<br> (文字)                   |                               |來電轉接目標型別                                         |
|                                                       |機 管 局                             |已移轉至 AA                                              |
|                                                       |重慶                             |已移轉至 CQ                                               |
|                                                       |external_pstn                  |移轉到外部號碼                                 |
|                                                       |共用語音信箱               |已移轉至共用語音信箱                                   |
|                                                       |未知                        |未知的動作                                                    |
|HasAA<br> (布林值)                                      |                               |通話中是否包含 AA                                            |


### <a name="call-queue-dimensions"></a>通話佇列維度

|名稱 (類型)                                             |可能的值                |描述                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|CallQueueAgentCount<br> (整數)                   |                               |通話佇列中的代理程式數目                                    |
|CallQueueAgentOptInCount<br> (整數)              |                               |加入宣告通話佇列的專員數目                           |
|CallQueueCallResult<br> (文字)                           |                               |通話佇列通話最終狀態                                       |
|                                                       |agent_joined_conference        |電話接聽 - 會議模式 CQ                                |
|                                                       |拒絕                       |                                                                  |
|                                                       |斷開                   |                                                                  |
|                                                       |error                          |                                                                  |
|                                                       |失敗                         |                                                                  |
|                                                       |無效                        |                                                                  |
|                                                       |溢位                      |符合溢位狀況                                            |
|                                                       |timed_out                      |符合逾時條件                                             |
|                                                       |transferred_to_agent           |接聽來電 - 轉接模式 CQ                                  |
|CallQueueDurationSeconds<br> (實數)               |                               |通話佇列中的通話持續時間                                   |
|CallQueueFinaleStateAction<br> (文字)                    |                               |通話佇列最終動作                                           |
|                                                       |斷開                     |time_out通話                                                    |
|                                                       |disconnect_with_busy           |溢位通話                                                   |
|                                                       |failed_to_accept_call          |                                                                  |
|                                                       |向前                        |呼叫已轉接給使用者或外部                        |
|                                                       |shared_voicemail               |通話已傳送至共用語音信箱                                 |
|                                                       |其他                          |                                                                  |
|                                                       |語音 信箱                      |                                                                  |
|CallQueueIdentity<br> (文字)                             |                               |已收到資源帳戶 URI 通話                              |
|CallQueueTargetType<br> (文字)                           |                               |呼叫重新導向目標                                           |
|                                                       |ApplicationEndpoint            |                                                                  |
|                                                       |郵箱                        |                                                                  |
|                                                       |Other                          |                                                                  |
|                                                       |電話                          |                                                                  |
|                                                       |使用者                           |                                                                  |
|HasCQ<br> (布林值)                                      |                               |通話中是否包含 CQ                                            |
|轉移FromCallQueueIdentity<br> (文字)              |                               |                                                                  |

### <a name="measurements"></a>測量

|名稱 (類型)                                             |可能的值                |描述                                                       |
|:------------------------------------------------------|:------------------------------|:-----------------------------------------------------------------|
|AvgAutoAttendantChainDurationSeconds<br> (實數)   |                               |                                                                  |
|AvgCallDuration<br> (實數)                        |                               |                                                                  |
|AvgCallQueueDurationSeconds<br> (實數)            |                               |                                                                  |
|PSTNTotalMinutes<br> (實數)                       |                               |                                                                  |
|TotalAudioStreamDuration<br> (實數)               |                               |                                                                  |
|TotalCallCount<br> (整數)                        |                               |                                                                  |

### <a name="constructing-a-valid-query"></a>建構有效的查詢

有效的查詢包含 JSON 物件中的數個屬性：

```json
{
   "Filters":[
      {
         "DataModelName":"Date",
         "Value":"2022-04-01",
         "Operand":4
      },
      {
         "DataModelName":"Date",
         "Value":"2022-04-30",
         "Operand":6
      }
   ],
   "Dimensions":[
      {
         "DataModelName":"AutoAttendantIdentity"
      },
      {
         "DataModelName":"AutoAttendantDirectorySearchMethod"
      }
   ],
   "Measurements":[
      {
         "DataModelName":"PSTNTotalMinutes"
      },
      {
         "DataModelName":"TotalCallCount"
      }
   ],
   "Parameters":{
      "UserAgent":"Power BI Desktop"
   },
   "LimitResultRowsCount":100000
}
```

#### <a name="required-fields"></a>必要欄位

- 篩選：用來篩選由 VAAC 傳回的資料
- - DataModelName 應該是其中一個支援的維度
- - 值的格式 (日期時間、字串、數位等應為正確格式) 
- - 操作：
- - - 0 - 等於
- - - 1 - 不等於
- - - 2 - 包含
- - - 3 - 從
- - - 4 - 大於
- - - 5 - 大於或等於
- - - 6 - 小於
- - - 7 - 小於或等於
- - - 8 - 不包含
- - - 9 - 開頭不是

- 尺寸：
- - DataModelName 應該是其中一個支援的維度

- 測量：
- - DataModelName 應為支援的度量值之一

- 參數：目前僅支援 UserAgent。

- LimitResultRowsCount：VAAC 傳回的列數上限

## <a name="accessing-vaac-outside-of-power-bi"></a>在 Power BI 外部存取 VAAC

VAAC API 可以由任何可存取 RESTful 應用程式的應用程式存取。  在下面的範例中，將會使用 [Postman](https://www.postman.com/) 。

### <a name="preparation"></a>製備

下載 [「郵遞員」](https://www.postman.com/)。

下載存放庫： [sync_pstn_avs分析](https://skype.visualstudio.com/SBS/_git/sync_pstn_avs-analytics) 並解壓縮。

將資料夾匯入 Postman。 

:::image type="content" source="media/aa-cq-historical-report-postman-01.png" alt-text="顯示已完成匯入的螢幕擷取畫面":::

### <a name="accessing-vaac-using-postman"></a>使用郵遞員存取 VAAC

1. 選取右上角 [**_無環境_**] 下拉式清單上的 **[VAAC - msit**]。
2. 選 **取** 左側軌軌功能表上的 [環境]。
3. 選取 [**全域**] 底下的 **[VAAC - msit**]。
4. 使用適用的認證取代 **userName**、 **password** 和 **tenantId** 。
5. 按一下右上角的 [ **全部重設** ]。
6. 按一下 [儲存]。

:::image type="content" source="media/aa-cq-historical-report-postman-02.png" alt-text="顯示已設定使用者名稱、密碼和租使用者識別碼欄位的螢幕擷取畫面":::


7. 選取左側軌軌功能表上的 **[集錦** ]。
8. 選 **取 [設定 API 存取權杖 - Prod** ]，然後流覽至 [ **本文]** 索引標籤。
9. 按一下 [ **傳送]**。

系統會傳回存取權杖。

:::image type="content" source="media/aa-cq-historical-report-postman-03.png" alt-text="顯示傳回存取權杖之結果的螢幕擷取畫面":::

如果沒有傳回存取權杖，請檢查您的認證，使其 [有足夠的許可權](#permissions-to-access-the-cqd-pipeline)。

10. 選 **取 [VAAC ConfigAPI Prod]** 並流覽至 [ **Params] 索** 引標籤。

- [如下](#compress-the-json-query) 所述壓縮查詢
- 下方概述的將壓縮結果[編碼的 URL](#url-encode-the-compressed-json-query)

11. 填入 [查詢](#constructing-a-valid-query) 字串。
12. 按一下 [ **傳送]**。

### <a name="reading-the-result"></a>朗讀結果

提交輸入之後，將會出現一些可能的結果：

- 如果輸入無效，會傳回含有實際原因的錯誤訊息
- 如果輸入有效，結果看起來會像這樣：

:::image type="content" source="media/aa-cq-historical-report-postman-04.png" alt-text="顯示含有 dataResult 欄位之查詢結果的螢幕擷取畫面":::

在此情況下，資料會以查詢維度和度量屬性中要求的相同順序，位於 [dataResult] 欄位中。


### <a name="compress-the-json-query"></a>壓縮 JSON 查詢

VAAC API 只接受 GZip 壓縮或 Base64 編碼字串作為輸入。

尋找任何使用 GZIP 或 Base64 壓縮 JSON blob 的網站。

- GZIP： (https://www.multiutil.com/text-to-gzip-compress/)
- Base64： (https://www.multiutil.com/text-to-base64-converter/)

GZIP 輸出看起來應該像這樣：
````
H4sIAAAAAAAACq2SQWsCMRCF7/6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif+9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf+xJLIGhIo12CjXKPM0o+2cLn2BjEjKVZQM1Gqjhhfy+QQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3/hUBqPKya/WyD41bpCXpP+tzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa/Y2Tk/wI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA=
````

Base64 輸出看起來應該像這樣：
````
ew==
IkZpbHRlcnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0wMSIs
Ik9wZXJhbmQiOjQ=
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw=
IlZhbHVlIjoiMjAyMi0wNC0zMCIs
Ik9wZXJhbmQiOjY=
fQ==
XSw=
IkRpbWVuc2lvbnMiOls=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg==
fQ==
XSw=
Ik1lYXN1cmVtZW50cyI6Ww==
ew==
IkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg==
fSw=
ew==
IkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI=
fQ==
XSw=
IlBhcmFtZXRlcnMiOns=
IlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai
fSw=
IkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA=
fQ==
````

### <a name="url-encode-the-compressed-json-query"></a>URL-Encode壓縮的 JSON 查詢

GZIP 或 Base64 壓縮的 JSON 查詢必須 [以 URL 編碼](https://meyerweb.com/eric/tools/dencoder/)。

GZIP URL 編碼輸出看起來會像這樣：
````
H4sIAAAAAAAACq2SQWsCMRCF7%2F6KkLNC3EoPe9u6FISuFbW9lB4GM9TQbEaSCSLif%2B9mV4uCBwXnMkze5L0vkH1PCCFfjWX0QeZfaWxqf%2BxJLIGhIo12CjXKPM0o%2B2cLn2BjEjKVZQM1Gqjhhfy%2BQQ9Oy3x0PDz0H5HypK6nPJ9SUv9uV2RpanTBkLvxiUVkKpjRaXA80ejY8E7eg3%2FhUBqPKya%2FWyD41bpCXpP%2BtzvjrBBC9NjA8o2ks8VyuiQGWxkXGcNdkO3FMVg7puj4GtAMfLPa%2FY2Tk%2FwI6IufhjHl0xa9eJmIEsMv06Y16cLlm6kNzzFEy3Pahi4kH6pUvcMfrAhUU3oCAAA%3D
````

Base64 URL 編碼輸出看起來會像這樣：
````
%0Aew%3D%3D%0AIkZpbHRlcnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0wMSIs%0AIk9wZXJhbmQiOjQ%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJEYXRlIiw%3D%0AIlZhbHVlIjoiMjAyMi0wNC0zMCIs%0AIk9wZXJhbmQiOjY%3D%0AfQ%3D%3D%0AXSw%3D%0AIkRpbWVuc2lvbnMiOls%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50SWRlbnRpdHki%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJBdXRvQXR0ZW5kYW50RGlyZWN0b3J5U2VhcmNoTWV0aG9kIg%3D%3D%0AfQ%3D%3D%0AXSw%3D%0AIk1lYXN1cmVtZW50cyI6Ww%3D%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJQU1ROVG90YWxNaW51dGVzIg%3D%3D%0AfSw%3D%0Aew%3D%3D%0AIkRhdGFNb2RlbE5hbWUiOiJUb3RhbENhbGxDb3VudCI%3D%0AfQ%3D%3D%0AXSw%3D%0AIlBhcmFtZXRlcnMiOns%3D%0AIlVzZXJBZ2VudCI6IlBvd2VyIEJJIERlc2t0b3Ai%0AfSw%3D%0AIkxpbWl0UmVzdWx0Um93c0NvdW50IjoxMDAwMDA%3D%0AfQ%3D%3D
````

## <a name="version-3xx-history"></a>版本 3.x.x 歷程記錄

參考：Teams 自動語音應答&通話佇列歷程記錄報告 - 變更下載 zip 檔案中的Log.docx，以取得詳細的變更清單 

|版本  |發佈日期     |檔案名                                                    |描述                                                             |
|:--------|:------------------|:-----------------------------------------------------------|:-----------------------------------------------------------------------|
|3.0.5    |2023 年 1 月 9 日    |Teams 自動語音應答&通話佇列歷史報告 V3.0.5 |改良的通話溢位/逾時目的地和專員時程表視覺效果  |
|3.0.4    |2022 年 11 月 18 日  |Teams 自動語音應答&通話佇列歷史報告 V3.0.4 |已修正錯誤、改善通話分類、新增圖例             |
|3.0.3    |2022 年 11 月 8 日   |Teams 自動語音應答&通話佇列歷史報告 V3.0.3 |修正錯誤、新增檔連結、優化查詢            |
|3.0.1    |2022 年 10 月 26 日   |Teams 自動語音應答&通話佇列歷史報告 V3.0.1 |已移除測試資料來源專案                                       |
|3.0.0    |2022 年 10 月 25 日   |Teams 自動語音應答&通話佇列歷史報告 V3.0.0 |新的後端資料來源                                                 |
