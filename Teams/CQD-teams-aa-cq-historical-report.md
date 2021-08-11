---
title: 使用 CQD Power BI報表來查看自動&通話佇列歷史記錄報表
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
description: 瞭解如何使用通話品質儀表板Power BI報表來查看自動通話和通話佇列歷史資料。
ms.openlocfilehash: 844ab5caee23cb504420925c9f13bc261d4d839cce19f7ae557d4637562a963e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331085"
---
# <a name="what-are-the-requirements"></a>需求是什麼？ 
您必須安裝Power BI Desktop。 您可以從 Microsoft Windows [Store 安裝](https://aka.ms/pbidesktopstore)。

您可以使用免費版本的 Power BI Desktop。 最低相容版本為 2020 年 9 月 2020 (2.85.681.0) 。

## <a name="permissions-to-access-the-cqd-pipeline"></a>存取 CQD 管道的許可權
您用於查看 AA & CQ 分析歷史報表的帳戶必須擁有存取 CQD 資料管道的許可權。 如需詳細資訊，請參閱 [CQD 存取](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 角色。

## <a name="installation"></a>安裝 
下列步驟假設您已經在電腦上Power BI Desktop，而且您的帳戶具有存取 CQD 資料管道的必要許可權。

請執行下列步驟：
- 下載[CQD Teams自動&佇列歷史報表範本](./aa-cq-cqd-historical-reports.md)，並將其儲存到您電腦的目錄。

- 按兩下範本，Power BI Desktop啟動。

- 系統會提示您選取 CQD 資料管道區域。 選取租使用者所在的地區。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-01.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::

 - 您可以使用 Get-CsTenant 商務用 Skype Online PS Cmdlet (查看) 。ServiceInstance 輸出。 
 此範例中的 /like 之後會顯示區域： 
 
   地區為 noam 的 microsoftcommunicationsonline/noam-4a-s7。
   
 - 報告會以範例資料啟動。
 
 - 若要查看您自己的資料，請按一下 [查詢中查詢> 下的 [首頁Power BI Desktop。

   :::image type="content" source="media/cqd-teams-aa-cq-historical-report-02.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::

- 系統隨即會提示您進行登錄。 選取 **組織帳戶**，**然後選取**

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-03.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::

- 選取 **連線** 並觀看資料重新更新。

## <a name="data-latency-any-aa--cq-analytics"></a>資料延遲 任何 AA & CQ 分析
資料將在 30 分鐘內于 CQD 資料管道中提供。

您必須重新更新資料，以查看新的分析資料。 

## <a name="customization"></a>定制 
您可以自訂報表的某些視覺效果層面，例如新增或移除要顯示在各種視覺效果中的欄位、變更圖表類型等。

除了報告中提供的資料欄位外，您無法新增其他資料欄位。

### <a name="change-color-schema"></a>變更色彩架構 
下列步驟假設您已完成安裝步驟。

請執行下列步驟：
- 選取 **功能區上的** View Tab。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-04.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::

- 從下拉式清單中選取色彩架構。

  :::image type="content" source="media/cqd-teams-aa-cq-historical-report-05.png" alt-text="系統管理中心中通話品質儀表板按鈕Teams螢幕擷取畫面":::


## <a name="cqd-fields-description"></a>CQD 欄位描述

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|自動助理身分識別                 |字串                   |附加至 AA 的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|自動總機鏈開始時間         |Datetime                 |AA 鏈開始時間                    |
|自動助理目錄搜尋方法  |字串                   |上次通訊錄搜尋方法        |
|自動助理轉接動作          |字串                   |來電轉接目標型別<br>可能的值：<br>§ 未知 - 未指定實體類型<br>§ 使用者 - 使用者實體<br>§ orgaa - 組織自動助理實體<br>§ hunt_group - 通話佇列實體<br>§ 應用程式 - 語音應用程式實體<br>§ external_pstn - 外部 PSTN 實體<br>§ shared_voicemail - 共用語音信箱實體|
|自動通話結果              |字串                   |通話結果：<br>§ 未知 - 通話設定或傳輸失敗，服務未收到任何有意義的失敗原因 <br>§ transferred_to_user - 透過撥號名稱/分機或已配置的功能表選項轉接給使用者的通話 <br>§ transferred_to_operator - 通話已轉接至已配置的接線員，例如，如果 AA 已與接線員在數小時後進行配置 <br>§ failover_to_operator - 傳輸失敗或名稱識別三次之後無法工作的運算子<br>§ user_terminated - 來電者已終止通話 <br>§ service_declined - 服務拒絕通話時，如果服務無法提取自動助理組 <br>§ service_terminated - 後端服務已終止通話，如果移轉目標失敗，且未將運算子配置為後備份，則可能是 <br>§ failed_to_establish_media - 來電者與服務之間的媒體建立失敗 <br>§ terminated_no_operator - 三次嘗試後名稱識別失敗，且未配置運算子 <br>§ terminated_transfer_failed - 移轉目標失敗，且未配置運算子 <br>§ terminated_automatic_selection - 如果數小時或數小時後未進行任何動作，通話預設會終止 <br>§ transferred_to_shared_voicemail - 已轉接到共用語音信箱的通話 ，如果已配置為目標 <br>§ oaa_chain_too_long - 當自動總機鏈連續超過五個自動總機時，通話會終止以避免可能的通話迴圈 <br>§ oaa_session_too_long - 通話超過允許的會話長度上限，且已超出通話時間 |
|自動電話Flow                |字串                   |封裝自動通話的不同狀態<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>§ 公告|
|是否涉及自動助理              |Boolean                  |指出 AA 是否參與通話 |
|自動語音回應本機號碼計數      |Int                      |來電者已使用動作的計數         |
|自動助理鏈持續時間秒數   |Int                      |AA 中的通話持續時間                 |
|通話佇列通話結果                  |String                   |通話佇列通話的最後狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ 溢出<br>§ 失敗<br>§ timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference|
|呼叫佇列最終狀態動作           |String                   |通話佇列最後動作<br>可能的值：<br>§ 轉場<br>§ 中斷連接<br>§ 語音信箱<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 其他|
|通話佇列身分識別                     |String                   |附加至 CQ 的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|通話佇列是會議模式           |Boolean                  |在 CQ 上啟用會議模式時，設為 1 |
|通話佇列目標型別                  |String                   |預期的通話重新導向目標型別     |
|從通話佇列身分識別傳輸    |Boolean                  |此通話從 CQ 附加的資源帳戶名稱<br>範例：aa_test@microsoft.com|
|通話佇列代理人員加入宣告計數           |Int                      |通話時此佇列可用的代理程式數量 |
|通話佇列代理程式計數                  |Int                      |通話時指派給此佇列的代理人計數 |
|是否涉及通話佇列                  |Boolean                  |如果參與此通話的通話佇列等於 1 |


### <a name="powerbi-data-model-dimensions"></a>PowerBI 資料模型維度

|名稱                                    |資料類型                |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AA 名稱                                   |字串                   |自動助理識別碼 (資源帳戶識別碼)  |
|AACallFlow                              |字串                   |封裝自動通話的不同狀態<br>§ abs_search<br>§ call_termination<br>§ call_transfer<br>§ main_menu<br>§ user_selection<br>§ speech_input_confirmation<br>§ first_level_menu<br>§ automatic_menu<br>公告 |
|AACallResult                            |字串                   |自動電話機通話的結果：<br>§ 未知<br>§ transferred_to_user<br>§ transferred_to_operator<br>§ failover_to_operator<br>§ user_terminated<br>§ service_declined – AA 組組錯誤<br>§ service_terminated – 內部 AA 錯誤<br>§ failed_to_establish_media<br> terminated_no_operator<br>§ terminated_transfer_failed<br>§ terminated_automatic_selection<br>§ transferred_to_shared_voicemail<br>§ oaa_chain_too_long<br>§ oaa_session_too_long          |
|AAChainDuration                         |字串                   |自動總機通話的持續時間 ，以秒數表示  |
|AACount                                 |字串                   |自動電話機參與通話的 #         |
|AADirectorySearchMethod                 |字串                   |通話中使用的搜尋方法：<br>§ abs_search_dtmf<br>§ abs_search_extension<br>§ abs_search_name|
|AAStartTime                             |字串                   |以 UTC 表示的通話時間                            |
|AATransferAction                        |字串                   |通話收聽者：<br>§ 未知 - 未指定實體類型<br>§ 使用者 - 使用者實體<br>§ AA - 組織自動助理實體<br>§ CQ - 通話佇列實體<br>§ 應用程式 - 語音應用程式實體<br>§ external_pstn - 外部 PSTN 實體<br>§ shared_voicemail - 共用語音信箱實體      |
|PSTNMinutes                             |Int                      |總分鐘使用量                          |
|通話佇列通話結果                  |字串                   |通話佇列通話的最後狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ 溢出<br>§ 失敗<br> timed_out<br>§ transferred_to_agent<br>§ agent_joined_conference    |
|通話佇列身分識別                     |字串                   |附加至 CQ 的資源帳戶名稱     |
|通話佇列目標型別                  |字串                   |預期的通話重新導向目標型別：<br>§ 使用者<br>§ 應用程式端點<br>§ 其他     |
|通話佇列通話結果                  |字串                   |通話佇列通話的最後狀態<br>可能的值：<br>§ 錯誤<br>§ 已拒絕<br>§ 溢出<br>§ 失敗<br> timed_out<br>§ transferred_to_agent<br>agent_joined_conference           |
|呼叫佇列最終狀態動作           |字串                   |通話佇列最後動作<br>可能的值：<br>§ 轉場<br>§ 中斷連接<br>§ 語音信箱<br>§ disconnect_with_busy<br>§ shared_voicemail<br>§ failed_to_accept_call<br>§ 其他             |
|代理人名稱                              |字串                   |使用者 UPN               |


### <a name="measures"></a>措施

|名稱                                      |類型                       |描述                            |
|:---------------------------------------|:------------------------|:--------------------------------------|
|AACallerActionCount                     |Int                        |通話期間 AA 中使用者選取的動作數  |
|PSTNMinutes                             |Int                      |總分鐘使用量                                  |
|TotalCallCount                          |Int                      |通話數                                          |
|平均通話持續時間 (秒)          |Int                      |通話佇列通話的總持續時間 ，以秒數表示     |


### <a name="power-bi-graph-description-auto-attendant"></a>Power BI圖形描述自動助理

|名稱                                      |描述                            |
|:---------------------------------------|:--------------------------------------|
|來電來源                    |按內部/外部通話來源分配通話      |
|目錄搜尋方法總計          |按搜尋類型分配通話                         |
|來電者動作                           |按電話接收者撥打的通話分配                       |
|通話結果                             |按最終通話狀態分配通話                    |
|來電者動作計數                     |通話期間使用之號碼動作的通話分配  |


### <a name="call-queue"></a>通話佇列

|名稱                                      |描述                            |
|:---------------------------------------|:--------------------------------------|
|來電來源                    |按內部/外部通話來源分配通話         |
|通話音量                             |按通話佇列分配通話                            |
|本機號碼結果                           |按通話結果分配通話                            |
|超時/溢出通話總計動作      |根據通話結果 (未) 呼叫的分配   |
|轉移/轉出目標總計          |根據通話結果轉呼叫的分配                  |
|已放棄通話比率                   |成功與放棄通話計數的比例                    |
|平均會話長度 (秒)         |以放棄/成功通話分組的通話長度 ，以秒數分組   |



### <a name="agent-timeline"></a>代理人時程表

|名稱                                                      |描述                            |
|:-------------------------------------------------------|:--------------------------------------|
|按代理人撥打的電話                                        |呼叫佇列和代理人的通話分配                 |
|由代理 (通話) 通話總通話持續時間   |代理 (通話) 通話的總持續時間     |
|按代理人名稱 (通話) 通話持續時間平均) 秒數            |代理 (通話) 通話的平均持續時間                  |



## <a name="known-issues"></a>已知問題
- 目前，通話佇列和自動話務員會顯示資源帳戶識別碼，而不是通話佇列/自動話務員名稱。  若要顯示自動總機或通話佇列的所有流量，您必須選取指派給自動話務員或通話佇列的所有資源帳戶。

- 目前儀表板中只有 28 天的歷程記錄可用，因為通話佇列/自動總機資料被視為使用者識別資訊，且受資料隱私權保留政策所影響。
