---
title: 使用 CQD Power BI 報表來查看自動語音應答 & 通話佇列歷史報告
ms.author: colongma
author: clyvr
manager: roykuntz
ms.reviewer: mikedav, siunies, gageames
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
- seo-marvel-apr2020
description: 瞭解如何使用通話品質儀表板 Power BI 報表來查看自動語音應答及呼叫佇列中的記錄資料。
ms.openlocfilehash: 874bb87a32895bdec29aab1b0aaee20bdecb0fc2
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908770"
---
# <a name="what-are-the-requirements"></a>需求為何？ 
您必須已安裝 Power BI 桌面。 您可以從 [Microsoft Windows 網上商店](https://aka.ms/pbidesktopstore)安裝它。

您可以使用免費的 Power BI 桌上出版。 最低相容版本為 2.85.681.0 2020 年9月 () 。

## <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管線的許可權
您用來查看 AA & CQ 分析的帳戶需要有權存取 CQD 資料管線。 如需詳細資訊，請參閱 [CQD 存取角色](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) 。

## <a name="installation"></a>安裝 
下列步驟假設您已在電腦上安裝 Power BI Desktop，且您的帳戶具有存取 CQD 資料管道的必要許可權。

請執行下列步驟：
- 下載 [CQD 小組自動語音應答 & 通話佇列中記錄報告範本](https://aka.ms/TAPAACQAnalytics) ，並將其儲存到電腦上的目錄。
- 按兩下範本，然後啟動 Power BI 桌面。
- 系統會提示您選取 CQD 資料管線區域。 選取租使用者所在的地區。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

 - 您可以使用商務用 Skype Online Cmdlet (CsTenant) 來查看地區。ServiceInstance 輸出。 
 該區域將會顯示在此範例中的/贊後： microsoftcommunicationsonline/noam-4a-s7，其中區域是 noam。
 - 報告將會啟動並提供範例資料。
 - 若要查看您自己的資料， **請按一下 [** 常用] 索引標籤中 [Power BI 桌面查詢] 底下的 [重新整理]

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

- 接著系統會提示您登入。 選取 [ **組織帳戶** ]，然後選取 [登 **入** ]。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

- 選取 **[** 連線並查看資料重新整理]。

## <a name="data-latency-any-aa--cq-analytics"></a>資料延遲任何 AA & CQ 分析
資料將在30分鐘內提供給 CQD 資料管線。

您將需要重新整理資料，才能查看新的分析資料。 

## <a name="customization"></a>自訂 
您可以自訂報表的特定視覺效果，例如新增或移除要顯示在各種視覺效果、變更圖表類型等內容中的欄位。

您無法新增報表中提供的其他資料欄位。

### <a name="change-color-schema"></a>變更色彩架構 
下列步驟假設您已完成安裝步驟。

請執行下列步驟：
- 選取功能區上的 [ **視圖]** 索引標籤。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

- 從下拉式清單中選取 [色彩模式]。

:::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::


## <a name="cqd-fields-description"></a>CQD 欄位描述

|名稱                                    |資料類型                |說明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|自動助理身分識別                 |字串                   |附加至 AA 的資源帳戶名稱<br>範例： aa_test@microsoft.com|
|自動助理鏈式開始時間         |datetime                 |AA 鏈式開始時間                    |
|自動助理目錄搜尋方法  |字串                   |最後一個通訊錄搜尋方法        |
|自動助理轉接動作          |字串                   |來電轉接目標型別<br>可能的值：<br>§未知-未指定實體類型<br>§使用者-使用者實體<br>§ orgaa-組織自動助理實體<br>§ hunt_group 通話佇列實體<br>§應用程式-語音應用程式實體<br>§ external_pstn-外部 PSTN 實體<br>§ shared_voicemail 共用的語音信箱實體|
|自動語音應答呼叫結果              |字串                   |呼叫結果：<br>§未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined<br>§ service_terminated<br>§ failed_to_establish_media<br>§ terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long|
|自動語音應答通話流程                |字串                   |封裝自動語音應答呼叫的不同狀態<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§宣告|
|是否參與自動助理              |Boolean                  |指示在通話中是否涉及 AA |
|自動語音應答本機號碼      |int                      |呼叫者所使用的動作計數         |
|自動助理連鎖的持續時間秒   |int                      |在 AA 中通話的持續時間                 |
|呼叫佇列呼叫結果                  |String                   |通話佇列呼叫最終狀態<br>可能的值：<br>§錯誤<br>§已拒絕<br>§ overflown<br>§失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|呼叫佇列最終狀態動作           |String                   |呼叫佇列最終動作<br>可能的值：<br>§轉寄<br>§中斷連線<br>§語音信箱<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§其他|
|通話佇列身分識別                     |String                   |附加至 CQ 的資源帳戶名稱<br>範例： aa_test@microsoft.com|
|通話佇列為會議模式           |Boolean                  |在 CQ 上啟用會議模式時，設定為1 |
|呼叫佇列目標型別                  |String                   |預期的呼叫重新導向目標型別     |
|從通話佇列識別轉移    |Boolean                  |附加到此通話轉移之 CQ 的資源帳戶名稱<br>範例： aa_test@microsoft.com|
|通話佇列代理選擇人數           |int                      |通話時可在此佇列中使用之代理程式的數目 |
|通話佇列代理程式計數                  |int                      |通話時指派給此佇列的代理計數 |
|參與通話佇列                  |Boolean                  |如果呼叫佇列包含在這個呼叫等於1 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI 資料模型維度

|名稱                                    |資料類型                |說明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AA 名稱                                   |字串                   |自動語音應答 Id (資源帳戶識別碼)  |
|AACallFlow                              |字串                   |封裝自動語音應答呼叫的不同狀態<br> abs_search<br> call_termination<br> call_transfer<br> main_menu<br> user_selection<br> speech_input_confirmation<br> first_level_menu<br> automatic_menu<br>公告 |
|AACallResult                            |字串                   |自動語音通話的結果：<br>未知<br> transferred_to_user<br> transferred_to_operator<br> failover_to_operator<br> user_terminated<br> service_declined-AA 設定的錯誤<br> service_terminated-內部 AA 錯誤<br> failed_to_establish_media<br> terminated_no_operator<br> terminated_transfer_failed<br> terminated_automatic_selection<br> transferred_to_shared_voicemail<br> oaa_chain_too_long<br> oaa_session_too_long          |
|AAChainDuration                         |字串                   |自動語音通話的持續時間（以秒為單位）  |
|AACount                                 |字串                   |自動語音應答數涉及通話         |
|AADirectorySearchMethod                 |字串                   |通話中使用的搜尋方法：<br> abs_search_dtmf<br> abs_search_extension<br> abs_search_name<br>AAStartTime 字串通話時間（UTC）      |
|AATransferAction                        |字串                   |來電接收器：<br>未知-未指定實體類型<br>使用者-使用者實體<br> AA-組織的自動助理實體<br> CQ-通話佇列實體<br>應用程式-語音應用程式實體<br> external_pstn-外部 PSTN 實體<br>shared_voicemail 共用的語音信箱實體      |
|PSTNMinutes                             |int                      |總分鐘使用量                          |
|呼叫佇列呼叫結果                  |字串                   |通話佇列呼叫最終狀態<br>可能的值：<br>錯誤<br>已拒絕<br> overflown<br>失敗<br> timed_out<br> transferred_to_agent<br>agent_joined_conference    |
|通話佇列身分識別                     |字串                   |附加至 CQ 的資源帳戶名稱     |
|呼叫佇列目標型別                  |字串                   |預期的呼叫重新導向目標型別：<br>使用者<br>應用程式端點<br>其他     |
|呼叫佇列呼叫結果                  |字串                   |通話佇列呼叫最終狀態<br>可能的值：<br>錯誤<br>已拒絕<br> overflown<br>失敗<br> timed_out<br> transferred_to_agent<br>agent_joined_conference           |
|呼叫佇列最終狀態動作           |字串                   |呼叫佇列最終動作<br>可能的值：<br>轉寄<br>中斷連線<br>語音信箱<br> disconnect_with_busy<br> shared_voicemail<br> failed_to_accept_call<br>換句話說             |
|代理程式名稱                              |字串                   |使用者 UPN               |


### <a name="measures"></a>機制

|名稱                                      |類型                       |說明                            |
|---------------------------------------:|:-----------------------:|:-------------------------------------:|
|AACallerActionCount                     |int                        |呼叫期間，在 AA 中使用者選取的動作數量  |
|PSTNMinutes                             |int                      |總分鐘使用量                                  |
|TotalCallCount                          |int                      |來電次數                                          |
|平均通話持續時間 ( 秒)          |int                      |通話佇列通話的總持續時間（以秒為單位）     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI 圖形描述自動語音應答

|名稱                                      |說明                            |
|---------------------------------------:|:-------------------------------------:|
|來電來源                    |由內部/外部通話來源進行通話的發佈      |
|目錄搜尋方法總計          |依搜尋類型進行呼叫的發佈                         |
|來電者動作                           |由呼叫接收器進行呼叫的發佈                       |
|呼叫結果                             |依最終通話狀態進行呼叫的發佈                    |
|呼叫者動作計數                     |通話期間使用的電話號碼動作的發佈  |


### <a name="call-queue"></a>通話佇列

|名稱                                      |說明                            |
|---------------------------------------:|:-------------------------------------:|
|來電來源                    |由內部/外部通話來源進行通話的發佈         |
|通話量                             |通話佇列通話的發佈                            |
|本機號碼結果                           |依呼叫結果進行呼叫的發佈                            |
|超時/溢出通話總動作      |未轉寄 (的傳播) 呼叫結果中放棄呼叫   |
|轉移/轉寄目標合計          |呼叫結果轉寄呼叫的發佈                  |
|已放棄通話比率                   |成功放棄通話計數的比率                    |
|平均會話長度 (秒)         |依已放棄/成功呼叫分組的通話長度（秒）   |



### <a name="agent-timeline"></a>替代時程表

|名稱                                                      |說明                            |
|-------------------------------------------------------:|:-------------------------------------:|
|[由代理程式撥打電話]                                        |通話佇列與代理商通話的發佈                 |
|每個代理和通話佇列) 的通話持續時間 (秒數   |由代理程式和通話佇列呼叫的總持續時間 (秒)      |
|每個代理名稱 (秒的平均通話持續時間)             |代理呼叫的平均持續時間 (秒)                   |



## <a name="known-issues"></a>已知問題
- 目前，通話佇列和自動語音應答會顯示資源帳戶識別碼，而不是通話佇列/自動助理名稱。  若要顯示自動語音應答或通話佇列的所有流量，您必須選取指派給自動語音應答或通話佇列的所有資源帳戶。
- 目前，儀表板中僅有28天的歷史記錄，因為呼叫佇列/自動語音應答資料被視為使用者身分識別的資訊，且受到資料隱私權保留原則的制約。
