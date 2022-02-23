---
title: 呼叫佇列&自動助理
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
description: 瞭解如何使用通話品質儀表板Power BI報表來查看自動通話和通話佇列歷史資料。
ms.openlocfilehash: bb83a31b083387bc945f7f4b4388ee6643c00f10
ms.sourcegitcommit: d8dba15c520de3894d1781e17acb2c75fb38ed49
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/23/2022
ms.locfileid: "62921871"
---
# <a name="auto-attendant--call-queue-historical-report"></a>呼叫佇列&自動助理

呼叫Teams自動&通話佇列歷史Power BI範本提供下列三個報告：

- [自動助理](media/cqd-teams-aa-cq-historical-report-sample-aa.png) – 顯示自動助理來電的分析。
- [通話佇列](media/cqd-teams-aa-cq-historical-report-sample-cq.png) – 顯示來電佇列來電的分析。
- [代理人時程表](media/cqd-teams-aa-cq-historical-report-sample-at.png) - 顯示在通話佇列通話中作用中的代理人時程表視圖。

這些報告使用來自通話 [品質儀表板資料](CQD-Power-BI-query-templates.md) 存放區的資料。 報告允許組織報告自動電話機和通話佇列正在處理的通話數目。  報告也會提供呼叫佇列中的代理人績效深入資訊。

## <a name="prerequisites"></a>必要條件

### <a name="power-bi-desktop"></a>Power BI Desktop
您必須安裝Power BI Desktop。 您可以從[Microsoft Windows Store 安裝](https://aka.ms/pbidesktopstore)。

您可以使用免費版本的 Power BI Desktop。 最低相容版本為 2020 年 9 月 (2.85.681.0) 。

### <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管道的許可權

您用於查看歷史報表的帳戶必須擁有存取 CQD 資料管道的許可權。 詳細資訊，請參閱 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)。

## <a name="installation"></a>安裝 

下列步驟假設您已經在電腦上Power BI Desktop，而且您的帳戶具有存取 CQD 資料管道的必要許可權。

執行下列步驟：

- 下載[CQD Power BI查詢範本，](https://www.microsoft.com/download/details.aspx?id=102291)然後將 zip 檔案儲存到您電腦的目錄。

- 按兩下 zip 檔案以開啟它。

- 按兩下「CQ 和 AA 合併分析 20201105.pbit」範本檔案。 系統Power BI Desktop啟動。

- 系統會提示您選取 CQD 資料管道區域。 選取租使用者所在的地區。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="選取 CQD 資料管道區域之螢幕擷取畫面。":::

- 您可以使用 [Get-CsTenant Cmdlet](/powershell/module/skype/get-cstenant) 取得租使用者所在的區域。

    ```PowerShell
    (Get-CsTenant).ServiceInstance


    microsoftcommunicationsonline/noam-4a-s7
    ```

    - 區域會顯示在上方 **/** 範例中的 as 之後，其中區域為：noam

 - 報告會以範例資料啟動。
 
 - To see your own data, select **Refresh** in the Home tab under Queries in Power BI Desktop.

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="選取重新更新選項的螢幕擷取畫面。":::

- 系統隨即會提示您進行登錄。 選取 **組織帳戶** ，然後選取 **登錄**。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="顯示登入的螢幕擷取畫面。":::

- 選取 **連線** 並觀看資料重新更新。

## <a name="data-latency-and-aa--cq-analytics"></a>資料延遲和 AA & CQ 分析

資料將在 30 分鐘內于 CQD 資料管道中提供。

您必須重新更新資料，以查看新的分析資料。 

## <a name="customization"></a>定制 

您可以自訂報表的某些視覺效果層面，例如新增或移除要顯示在各種視覺效果中的欄位、變更圖表類型等等。

您無法在報表新增其他資料欄位。

### <a name="change-color-schema"></a>變更色彩架構 

下列步驟假設您已完成安裝步驟。

執行下列步驟：
- 選取 **功能區上的** View Tab。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="選取可變更色彩配色的螢幕擷取畫面。選取的畫面顯示畫面。":::

- 從下拉式清單中選取色彩架構。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="顯示各種色彩圖的螢幕擷取畫面。":::
  
## <a name="auto-attendant-and-call-queue-historical-reports-definitions"></a>自動通話和通話佇列歷史報告定義

### <a name="cloud-auto-attendant-analytics"></a>雲端自動助理分析

#### <a name="report-description"></a>報表描述

|報表區段                          |描述                                                       |
|:---------------------------------------|:-----------------------------------------------------------------|
|來電來源<sup>1</sup>        |按內部/外部通話來源分配通話             |
|目錄搜尋方法總計          |按搜尋類型分配通話                               |
|本機號碼動作                           |按電話接收者撥打的通話分配                             |
|通話結果                             |按最終通話狀態分配通話                          |
|來電者動作計數                     |通話期間使用之號碼動作的通話分配        |


#### <a name="report-to-cqd-table-and-field-mapping"></a>報告至 CQD 資料表和欄位映射

|報表 Tab            |報表資料表名稱     |全域篩選                          |
|:---------------------|:---------------------|:--------------------------------------|
|自動助理        |fAutoAttendant        |AAStartTime 是在前 28 天內 |


|報表資料表名稱            |來來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|fAutoAttendant               |自動附加                |Source = AutoAttendant， <br>#"篩選的列" = Table.SelectRows (來源，每個 true) ， <br>#"自動助理" = Table.AddColumn (#"篩選的列"，"AA Name"，每個清單。首先 (Text.Split ([AAIdentity]，"@") ) ) ， <br>#"已變更類型" = Table.TransformColumnTypes (#"Auto Attendant"，{{"AAStartTime"，輸入 datetime}}) ， <br>#"已移除的欄" = Table.RemoveColumns (#"Changed Type"，{"AAIdentity"})  |


|報表區段                                  |已 (欄位) 欄位                              |已應用篩選     |
|:-----------------------------------------------|:------------------------------------------|:-------------------|
|日期選擇器                                   |AAStartTime                                |無                |
|自動助理                                  |AA 名稱                                    |無                |
|來電來源<sup>1</sup>                |通話類型<br>TotalCallCount                |外部通話：通話類型為外部通話<br>內部通話：通話類型為內部通話 |
|目錄搜尋方法總計                  |AADirectorySearchMethod<br>TotalCallCount  |AADirectorySearchMethod abs_search_dtmf或abs_search_name    |
|本機號碼動作                                  |AATransferAction<br>TotalCallCount         |無                                                             |
|AA 中的平均秒數<br>平均本機號碼動作 |AAChainDuration<br>AACallerActionCount     |無                                                             |
|通話結果                                    |AACallResult<br>TotalCallCount             |無                                                             |
|本機號碼動作計數                            |AACallerActionCount<br>TotalCallCount      |無                                                             |
|報表的下半部                         |AA 名稱<br>AACallFlow<br>AACallResult<br>AAChainDuration<br>通話類型<br>TotalCallCount |無                |

#### <a name="fautoattendant-cqd-fields-description"></a>fAutoAttendant CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                 |文本                     |附加到自動助理的資源帳戶名稱<br><br>如果完整資源帳戶 **名稱 aa_test@microsoft.com 此值****為：aa_test** |
|AACallerActionCount                     |全數位             |摘要：加總<br>來電者在通話期間自動語音回應中選取的動作計數  |
|AACallFlow                              |文本                     |封裝自動通話的不同狀態 - 可能的值：<br><br>§ abs_search<br>§ 公告<br>§ automatic_menu<br>§ call_termination<br>§ call_transfer<br>§ first_level_menu<br>§ main_menu<br>§ speech_input_confirmation<br>§ user_selection |
|AACallResult                            |文本                     |最終通話結果 -- 可能的值：<br><br>§ failed_to_establish_media<br>§ failover_to_operator<br>§ oaa_chain_too_long<br>§ oaa_session_too_long<br>§ service_declined<br>§ service_terminated<br>§ terminated_automatic_selection<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>***§ transferred_to_operator***<br>§ transferred_to_receptionist<br>§ transferred_to_self<br>§ transferred_to_shared_voicemail<br>§ transferred_to_user<br>§ 未知<br>§ user_terminated |
|AAChainDuration                         |十進位數           |摘要：加總<br>自動通話的通話持續時間                     |
|AAChainIndex                            |文本                     |                                                                         |
|AAConnectivityType                      |文本                     |通話類型 -- 可能的值：<br><br>§ ExternalCall<br>§ 內部Call |
|AACount                                 |文本                     |通話中涉及的自動總機數目                               |
|AADirectorySearchMethod                 |文本                     |上次通訊錄搜尋方法 -- 可能的值：<br><br>§ abs_search_dtmf<br>§ abs_search_extension_x<br>§ abs_search_name |
|AAStartTime                             |日期/時間                |自動通話開始時間                                           |
|AATransferAction                        |文本                     |來電轉接目標型別 -- 可能的值：<br><br>***§ 應用程式 - 語音應用程式實體**_<br> § external_pstn <br> §_ *_hunt_group - 通話佇列_* _<br>_ * 實體 _§ orgaa - 組織自動語音服務實體_**<br>§ shared_voicemail<br>§ 未知<br>§ 使用者 |
|通話類型<sup>1</sup>                   |文本                     |通話類型 -- 可能的值：<br><br>§ 外部<br>§ 內部         |
|IsAAInvolved                            |文本                     |永遠 1                                                                 |
|PSTNMinutes                             |全數位             |摘要：加總<br>總分鐘使用量                                     |
|TotalCallCount                          |全數位             |摘要：加總<br>永遠 1 - 用來提供所有通話的總和            |


### <a name="cloud-call-queue-analytics"></a>雲端通話佇列分析

#### <a name="report-description"></a>報表描述

|報表區段                          |描述                                                        |
|:---------------------------------------|:------------------------------------------------------------------|
|來電來源<sup>1</sup>        |按內部/外部通話來源分配通話              |
|通話音量                             |按通話佇列分配通話                                |
|本機號碼結果                           |按通話結果分配通話                                |
|超時/溢出通話總計動作      |根據通話結果 (已) 呼叫的 NOT 轉轉通訊       |
|轉移/轉出目標總計          |根據通話結果轉呼叫的分配                      |
|已放棄通話比率                   |成功與放棄通話計數的比例                        |
|平均會話長度 (秒)         |以放棄/成功通話分組的通話長度 ，以秒數分組       |

#### <a name="report-to-cqd-table-and-field-mapping"></a>報告至 CQD 資料表和欄位映射

|報表 Tab         |報表資料表名稱                                                          |全域篩選 |
|:------------------|:---------------------------------------------------------------------------|:-------------|
|通話佇列         |日期<br>dCQ-CQIdenity<br>fCallQueueAnalytics<br>fCallQueueFinalStateAction |無          |
 
|報表資料表名稱            |來來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|日期                        |日期                        |無             |
|dCQ-CQIdentity               |CallQueueAnalytics           |Source = CallQueueAnalytics， <br>#"已移除的欄" = Table.RemoveColumns (Source，{"通話計數"，"通話佇列通話結果"，"Date"，"PSTN 連線類型"，"通話佇列目標型別"，"PSTN 總計分鐘數"}) ，<br>Distinct = Table.Distinct (#"已移除的欄")  |
|fCallQueueAnalytics          |CallQueueAnalytics           |無             |
|fCallQueueFinalStateAction   |CallQueueFinalStateAction    |無             |

|報表區段                      |表格 ->欄位 (使用) 欄位                |已應用篩選       |
|:-----------------------------------|:-------------------------------------|:---------------------|
|日期選擇器                       |日期 -> DateTime                     |無                  |
|通話佇列身分識別                 |dCQ-CQIdentity ->通話佇列身分識別 |無                  |
|來電來源<sup>1</sup>    |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話類型    |外部通話：通話類型為外部通話<br>內部通話：通話類型為內部通話 |
|Avg 等待時間                    |fCallQueueFinalStateAction ->平均通話持續時間 (秒)  |轉接前：通話佇列通話結果agent_joined_conference或transferred_to_agent<br>掛斷前：通話佇列通話結果agent_joined_conference或transferred_to_agent |
|通話結果                         |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列通話結果 | 無 |
|超時/溢出通話總計動作 |fCallQueueFinalStateAction ->通話計數<br>fCallQueueFinalStateAction ->通話佇列最終狀態動作 |呼叫佇列最終狀態動作未轉出 |
|傳輸/Forard 目標總計       |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列目標型別 |無 |
|通話音量                        |fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->通話佇列識別<br>fCallQueueAnalytics ->日期 |無 |
|已放棄通話                     |fCallQueueAnalytics -> %放棄通話<br>fCallQueueAnalytics ->通話計數<br>fCallQueueAnalytics ->日期<br>fCallQueueAnalytics -> IsAbandoned |IsAbandoned 為 True |
|平均會話長度 (秒)     |fCallQueueFinalStateAction ->通話平均持續時間<br>fCallQueueFinalStateAction ->日期<br>fCallQueueFinalStateAction -> IsAbandoned |無 |

#### <a name="dcq-cqidenity-cqd-fields-description"></a>dCQ-CQIdenity CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶 **名稱 cq_test@microsoft.com 此值****為：cq_test** |

#### <a name="fcallqueueanalytics-cqd-fields-description"></a>fCallQueueAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                                                |
|:---------------------------------------|:------------------------|:--------------------------------------------------------------------------|
|通話計數                              |全數位             |摘要：加總<br>通話次數                                          |
|通話佇列通話結果                  |文本                     |呼叫佇列通話的最後狀態 -- 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒絕<br>§ 已中斷連接<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 溢出<br>§ timed_out<br>§ transferred_to_agent |
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶 **名稱 cq_test@microsoft.com 此值****為：cq_test** |
|通話佇列目標型別                  |文本                     |***呼叫重新導向目標型別 -- 可能的值：***<br><br>§ ApplicationEndpoint<br>§ 信箱<br>§ 其他<br>§ 使用者 |
|通話類型<sup>1</sup>                   |文本                     |通話類型 -- 可能的值：<br><br>§ 外部<br>§ 內部           |
|日期                                    |日期/時間                |呼叫佇列通話開始時間 (UTC)  (時間)                            | 
|IsAbandoned                             |True/false               |如果代理人未接聽來電，則為 True                                   |
|PSTN 連線類型                  |文本                     |通話類型 -- 可能的值：<br><br>§ ExternalCall<br>§ 內部Call   |
|PSTN 總分鐘數                      |全數位             |摘要：加總<br>PSTN 通話的總通話分鐘數                       |

#### <a name="fcallqueueanalytics-measures-description"></a>fCallQueueAnalytics 度量描述

|名稱                                    |資料類型                |描述                              |
|:---------------------------------------|:------------------------|:----------------------------------------|
|***已放棄通話百分比***                 |百分比               |量值：已放棄通話數 / 通話總數    |
|通話總數                             |全數位             |量值：加總代理已接聽來電        |
|TotalCallCount                          |全數位             |量值：加 (通話)                  |

#### <a name="fcallqueuefinalstateaction--cqd-fields-description"></a>fCallQueueFinalStateAction CQD 欄位描述

|名稱                                    |資料類型                |描述                                        |
|:---------------------------------------|:------------------------|:--------------------------------------------------|
|平均通話持續時間 (秒)          |十進位數           |摘要：加總<br>平均通話持續時間 ，以秒計算 |
|通話計數                              |全數位             |摘要：加總<br>通話次數                  |
|通話佇列通話結果                  |文本                     |呼叫佇列通話的最後狀態 -- 可能的值：<br><br>§ agent_joined_conference<br>§ 已拒絕<br>§ 已中斷連接<br>§ 錯誤<br>§ 失敗<br>§ 無效<br>§ 溢出<br>§ timed_out<br>§ transferred_to_agent |
|呼叫佇列最終狀態動作           |文本                     |呼叫佇列最終動作 -- 可能的值：<br><br>§ 中斷 (timed_out通話) <br>§ disconnect_with_busy (溢出) <br>§ failed_to_accept_call<br>§ 轉場<br>§ shared_voicemail<br>§ 其他<br>§ 語音信箱 |
|通話佇列身分識別                     |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶 **名稱 cq_test@microsoft.com 此值****為：cq_test** |
|日期                                    |日期/時間                |在 UTC 或 UTC (撥打)  (通話)    |
|IsAbandoned                             |True/false               |如果代理人未接聽來電，則為 True           |


### <a name="cloud-call-queue-agent-timeline"></a>雲端通話佇列代理程式時程表

#### <a name="report-description"></a>報表描述

|報表區段                                          |描述                                                  |
|:-------------------------------------------------------|:------------------------------------------------------------|
|按代理人撥打的電話                                        |呼叫佇列和代理人的通話分配                 |
|由代理人和 (通話) 通話總通話持續時間   |代理 (通話) 通話的總持續時間     |
|按代理人名稱 (通話) 通話持續時間           |代理 (通話) 通話的平均持續時間                  |

#### <a name="report-to-cqd-table-and-field-mapping"></a>報告至 CQD 資料表和欄位映射

|報表 Tab         |報表資料表名稱        |全域篩選 |
|:------------------|:-------------------------|:-------------|
|代理人時程表     |fAgentTimelineAnalytics   |無          |
 
|報表資料表名稱            |來來源資料表名稱            |處理       |
|:----------------------------|:----------------------------|:----------------|
|fAgentTimelineAnalytics      |AgentTimelineAnalytics       |Source = AgentTimelineAnalytics， <br>#"已變更類型" = Table.TransformColumnTypes (Source，{{{"通話計數"，Int64.Type}，{"通話持續時間 (分鐘) "，Int64.Type}，{"平均通話持續時間 (秒) "，輸入 number}，{"Date"，輸入 date}}) |

|報表區段                                |已 (欄位) 欄位                         |已應用篩選       |
|:---------------------------------------------|:-------------------------------------|:---------------------|
|代理人名稱                                    |代理人名稱                            |無                  |
|通話佇列名稱                               |通話佇列名稱                       |無                  |
|#Calls代理程式                               |代理人名稱<br>通話計數<br>日期      |無                  |
|按代理人和通話佇列發佈          |代理人名稱<br>通話計數<br>通話持續時間 (分鐘) <br>通話佇列名稱 |無                      |
|左下角                                   |代理人名稱<br>平均通話持續時間 (秒) <br>通話計數<br>通話持續時間 (分鐘) <br>通話佇列名稱 | 無 |
|按代理人名稱 (通話持續時間) 秒數 |代理人名稱<br>平均通話持續時間 (秒) <br>通話計數<br>通話持續時間 (分鐘) <br>通話佇列名稱 | 無 |

#### <a name="fagenttimelineanalytics-cqd-fields-description"></a>fAgentTimelineAnalytics CQD 欄位描述

|名稱                                    |資料類型                |描述                                         |
|:---------------------------------------|:------------------------|:---------------------------------------------------|
|代理人名稱                              |文本                     |使用者 UPN<br>如果完整使用者 **名稱 user@microsoft.com 此值** 為： **user** |
|平均通話持續時間 (秒)           |十進位數           |摘要：加總<br>通話佇列通話的平均持續時間 ，以秒計算 |
|通話計數                              |全數位             |摘要：加總<br>由代理人處理的通話數目                    |
|通話持續時間 (分鐘)                   |全數位             |摘要：加總<br>通話佇列通話的總通話持續時間以分鐘數表示  |
|通話佇列名稱                         |文本                     |附加至通話佇列的資源帳戶名稱<br><br>如果完整資源帳戶 **名稱 cq_test@microsoft.com 此值****為：cq_test** |
|日期                                    |日期                     |                                                    |


> [!NOTE]
> 1) 此報表從代理人的角度顯示通話計數，因此此報表上的通話總數通常會高於雲端通話佇列分析報表上的通話總數。**** 佇列中的每一個通話，在接聽之前，可能會至少向一或多個代理人顯示一次。 呈現給代理人的每一個通話佇列通話都會計入此報告，即使代理人並未接聽。 這兩個報表之間的通話計數差異會隨著每一個通話響鈴每個代理人的 **Attendant 路由** 選項而更加明顯。 
> 2) 當通話第一次到達第一個通話佇列時，如果已在該佇列中等候的通話數超過呼叫溢出處理限制，而且重新導向選項將呼叫傳送至第二個通話佇列，則第二個通話佇列中的代理人會顯示為此報表的第一個通話佇列。 

## <a name="known-issues"></a>已知問題

- 通話佇列和自動話務員會以資源帳戶的識別碼顯示，而不是以通話佇列/自動話務員名稱顯示。  若要顯示自動電話機或通話佇列的所有流量，您必須選取指派給自動電話機或通話佇列的所有資源帳戶。

- 儀表板中只有 28 天的歷程記錄可用，因為通話佇列/自動話務資料被視為個人資料，並受資料隱私權保留政策所影響。

- 在某些情況下，代理程式在雲端通話佇列代理程式時程表報表上接聽的通話計數，可能會與用戶端通話記錄中顯示的Teams數不同。 用戶端Teams記錄正確無誤。 支援人員正在調查，但目前沒有預估的修復時間。

- <sup>1</sup> **自動話務員和** 通話佇列圖表中的來電來源會顯示最終的通話支線來源，而不是初始的通話支線來源。 例如，如果自動話務員收到外部通話，並且將通話轉接到另一個自動話務員或通話佇列，則來電來源會報告為內部。
