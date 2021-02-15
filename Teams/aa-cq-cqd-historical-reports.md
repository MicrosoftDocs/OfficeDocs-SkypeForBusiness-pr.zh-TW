---
title: 自動 Attendant &通話佇列歷史記錄報告
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
description: 瞭解如何使用通話品質儀表板 Power BI 報表來查看自動 Attendant 和通話佇列歷史資料。
ms.openlocfilehash: ee54941150a5ba4ade64d6a54cb066f50df2e0a8
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196237"
---
# <a name="auto-attendant--call-queue-historical-report"></a>自動 Attendant &通話佇列歷史記錄報告

CQD Teams 自動&通話佇列歷史報告 Power BI 範本提供下列三個報告：

- 自動 Attendant – 顯示進入自動 Attendant 之通話的分析。
- 通話佇列 – 顯示來電進入通話佇列的分析。
- 代理程式時程表 – 顯示在通話佇列通話中作用中的代理程式時程表。

這些報告會使用來自通話品質 [儀表板](CQD-Power-BI-query-templates.md) 資料存放區的資料，並允許組織報告自動電話機和通話佇列正在處理的通話數量，以及通話佇列中的代理者表現。

## <a name="what-are-the-requirements"></a>需求是什麼？ 

您必須安裝 Power BI Desktop。 您可以從 [Microsoft Windows 市商店安裝](https://aka.ms/pbidesktopstore)。

您可以使用免費版的 Power BI Desktop。 最低相容版本為 2020 年 9 月 (2.85.681.0) 。

## <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管線的許可權

您用於查看 AA 或 CQ 分析&報告的帳戶必須擁有存取 CQD 資料管道的許可權。 如需詳細資訊，請參閱 [CQD 存取](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 角色。

## <a name="installation"></a>安裝 

下列步驟假設您已經在電腦上安裝 Power BI Desktop，而且您的帳戶具有存取 CQD 資料管線的必要許可權。

請執行下列步驟：

- 下載 [CQD Power BI 查詢範本](https://www.microsoft.com/download/details.aspx?id=102291) ，將 zip 檔案儲存到您電腦的目錄。

- 按兩下 zip 檔案以開啟該檔案。

- 按兩下 「CQ 和 AA 合併分析 20201105.pbit」範本檔案，Power BI Desktop 應該會啟動。

- 系統會提示您選取 CQD 資料管線區域。 選取租使用者所在的地區。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="選取 CQD 資料管線區域之螢幕擷取畫面":::

 - 您可以使用商務用 Skype Online PowerShell Cmdlet (Get-CsTenant) 。ServiceInstance 輸出。 
 在此範例中，區域會顯示在 / like 之後：

   地區為 noam 的 microsoftcommunicationsonline/noam-4a-s7。
 
 - 報告會以範例資料啟動。
 
 - 若要查看您自己的資料，請按一下 Power  BI Desktop 中的 [查詢> 下的 [首頁索引鍵中重新更新。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="選取重新更新選項的螢幕擷取畫面":::

- 接著，系統會提示您進行註冊。 選取 **組織帳戶**，然後選取 **"Sign in in"。**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="顯示登入的螢幕擷取畫面":::

- 選取 **連接** 並觀看資料重新更新。

## <a name="data-latency-and-aa--cq-analytics"></a>資料延遲和 AA & CQ 分析

資料將在 30 分鐘內于 CQD 資料管線中提供。

您必須重新更新資料，以查看新的分析資料。 

## <a name="customization"></a>定制 

您可以自訂報表的某些視覺效果，例如新增或移除要顯示在各種視覺效果中的欄位、變更圖表類型等等。

除了報告中提供的資料欄位外，您無法新增其他資料欄位。

### <a name="change-color-schema"></a>變更色彩架構 

下列步驟假設您已完成安裝步驟。

請執行下列步驟：
- 選取 **功能區上的 View** Tab。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="選取的螢幕擷取畫面，選取了可變更色彩的顯示畫面":::

- 從下拉式清單中選取色彩架構。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="顯示各種色彩的螢幕擷取畫面":::

## <a name="cqd-fields-description"></a>CQD 欄位描述

|名稱                                    |資料類型                |說明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自動 Attendant 身分識別                 |字串                   |附加至 AA 的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|自動 Attendant 連結開始時間         |Datetime                 |AA 鏈式開始時間                    |
|自動 Attendant 目錄搜尋方法  |字串                   |上次通訊錄搜尋方法        |
|自動 Attendant 傳輸動作          |字串                   |來電轉接目標型別<br>可能的值：<br>§ 未知 - 未指定實體類型<br>§ 使用者 - 使用者實體<br>§ orgaa - 組織自動 Attendant 實體<br>§ hunt_group - 通話佇列實體<br>§ 應用程式 - 語音應用程式實體<br>§ external_pstn - 外部 PSTN 實體<br>§ shared_voicemail - 共用語音信箱實體|
|自動 Attendant 通話結果              |字串                   |通話結果：<br>§ 未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自動 Attendant 通話流程                |字串                   |封裝自動 Attendant 通話的不同狀態<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 公告|
|是否涉及自動 Attendant              |Boolean                  |如果 AA 與通話有關，表示 |
|自動語音回應本機號碼計數      |Int                      |來電者已使用動作的計數         |
|自動 Attendant 連結持續時間秒數   |Int                      |AA 中的通話持續時間                 |
|通話佇列通話結果                  |String                   |通話佇列通話的最終狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ overflown<br>§ 失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|通話佇列最終狀態動作           |String                   |通話佇列最終動作<br>可能的值：<br>§ 轉場<br>§ 中斷連接<br>§ 語音信箱<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 其他|
|通話佇列身分識別                     |String                   |附加至 CQ 的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|通話佇列為會議模式           |Boolean                  |如果 CQ 上啟用會議模式，設定為 1 |
|通話佇列目標型別                  |String                   |預期的通話重新導向目標型別     |
|從通話佇列身分識別傳輸    |Boolean                  |此呼叫從 CQ 附加的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|通話佇列代理程式加入宣告計數           |Int                      |通話時可進入此佇列的代理程式計數 |
|通話佇列代理程式計數                  |Int                      |在通話時指派給此佇列的代理程式計數 |
|是否涉及通話佇列                  |Boolean                  |如果參與此通話的通話佇列等於 1 |


### <a name="power-bi-data-model-dimensions"></a>Power BI 資料模型維度

|名稱                                    |資料類型                |說明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                   |字串                   |自動 Attendant 識別碼 (資源帳戶識別碼)  |
|AACallFlow                              |字串                   |封裝自動 Attendant 通話的不同狀態<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 公告 |
|AACallResult                            |字串                   |自動 Attendant 通話的結果：<br>§ 未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 組配置錯誤<br>§ service_terminated – 內部 AA 錯誤<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |字串                   |自動 Attendant 通話的持續時間 ，以碼錶示  |
|AACount                                 |字串                   |自動 Attendant 參與通話的 #         |
|AADirectorySearchMethod                 |字串                   |通話中使用的搜尋方法：<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name<br>
|AAStartTime                             |字串                   |以 UTC 表示的通話時間      |
|AATransferAction                        |字串                   |通話的收聽者：<br>§ 未知 - 未指定實體類型<br>§ 使用者 - 使用者實體<br>§ AA - 組織自動 Attendant 實體<br>§ CQ - 通話佇列實體<br>§ 應用程式 - 語音應用程式實體<br>§ external_pstn - 外部 PSTN 實體<br>§ shared_voicemail - 共用語音信箱實體      |
|PSTNMinutes                             |Int                      |總分鐘數使用量                          |
|通話佇列通話結果                  |字串                   |通話佇列通話的最終狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ overflown<br>§ 失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|通話佇列身分識別                     |字串                   |附加至 CQ 的資源帳戶名稱     |
|通話佇列目標型別                  |字串                   |預期的通話重新導向目標型別：<br>§ 使用者<br>§ 應用程式端點<br>§ 其他     |
|通話佇列通話結果                  |字串                   |通話佇列通話的最終狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ overflown<br>§ 失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference           |
|通話佇列最終狀態動作           |字串                   |通話佇列最終動作<br>可能的值：<br>§ 轉場<br>§ 中斷連接<br>§ 語音信箱<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 其他             |
|代理人名稱                              |字串                   |使用者 UPN               |


### <a name="measures"></a>措施

|名稱                                      |類型                       |說明                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |Int                        |通話期間使用者在 AA 中選取的動作 #  |
|PSTNMinutes                             |Int                      |總分鐘數使用量                                  |
|TotalCallCount                          |Int                      |通話數                                          |
|平均通話持續時間 ( 秒)          |Int                      |通話佇列通話的總持續時間 ，以碼錶示     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI 圖形描述自動 Attendant

|名稱                                      |說明                            |
|:---------------------------------------|:--------------------------------------|
|來電來源                    |按內部/外部通話來源<sup>1</sup>的通話分配|
|目錄搜尋方法總計          |按搜尋類型分配通話                         |
|來電者動作                           |按電話接收者分配通話                       |
|通話結果                             |根據最終通話狀態分配通話                    |
|來電者動作計數                     |通話期間使用之號碼動作的通話分配  |


### <a name="call-queue"></a>通話佇列

|名稱                                      |說明                            |
|:---------------------------------------|:--------------------------------------|
|來電來源                    |按內部/外部通話來源<sup>1</sup>的通話分佈   |
|通話音量                             |按通話佇列分配通話                            |
|本機號碼結果                           |按通話結果分配通話                            |
|Timeout/Overflow 通話總計動作      |未轉 (呼叫) 通話結果的分佈   |
|轉帳/轉出目標總計          |根據通話結果轉場的呼叫分佈                  |
|已放棄的通話比例                   |成功與放棄通話計數的比例                    |
|平均會話長度 (秒)         |以放棄/成功通話分組的通話長度 ，以碼錶示   |



### <a name="agent-timeline"></a>代理人時程表

|名稱                                                      |說明                            |
|:-------------------------------------------------------|:--------------------------------------|
|按代理人撥打的號碼                                        |按通話佇列和代理程式分配通話                 |
|總通話持續時間 (代理) 通話佇列   |由代理人 (通話) 通話總持續時間     |
|按代理人名稱 (通話) 秒數            |代理 (通話) 平均持續時間) 秒數                  |



## <a name="known-issues"></a>已知問題

- 通話佇列和自動 Attendant 會以資源帳戶的識別碼顯示，而不是以通話佇列/自動 attendant 名稱顯示。  若要顯示自動 Attendant 或通話佇列的所有流量，您必須選取指派給自動 Attendant 或通話佇列的所有資源帳戶。

- 儀表板僅提供 28 天歷程記錄，因為通話佇列/自動 Attendant 資料會被視為使用者識別資訊，並受資料隱私權保留政策所保護。

- <sup>1</sup> **自動接聽電話和** 通話佇列圖表中的來電來源會顯示最終通話的通話時間來源，而不是初始的通話號號來源。 例如，如果自動電話機接到外部電話，並且將電話轉接到另一個自動電話機或通話佇列，來電來源會以內部方式報告。
