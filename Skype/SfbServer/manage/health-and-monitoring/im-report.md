---
title: Peer-to-Peer 商務用 Skype Server 中的 IM 報表
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 19ec0145-2398-437b-8989-f780c179b798
description: 摘要：瞭解商務用 Skype Server 中的 Peer-to-Peer IM 報表。
---

# <a name="peer-to-peer-im-report-in-skype-for-business-server"></a>Peer-to-Peer 商務用 Skype Server 中的 IM 報表
 
**總結：** 瞭解商務用 Skype Server 中的 Peer-to-Peer IM 報表。
  
對等 IM 報告會提供對等立即訊息 (IM) 工作階段的趨勢資訊 (依集區和驗證類型細分)。此報告可以顯示指定時段內 (例如，每天或每小時) 主控的工作階段總數，或者可以顯示該時段內傳送的立即訊息總數。
  
## <a name="accessing-the-peer-to-peer-im-report"></a>存取對等 IM 報告

您可以只[在商務用 Skype Server 中開啟 Peer-to-Peer 活動摘要報表](peer-to-peer-activity-summary-report.md)，然後按一下下列其中一個計量，才能存取 Peer-to-Peer IM 報告：
  
- 對等 IM 工作階段總數
    
- 對等 IM 訊息總數
    
## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>善加利用對等 IM 報告

依預設，對等 IM 報告會顯示每小時 (或每天，視您的設定而定) 的訊息計數。不過，您也可以選擇依每小時的工作階段來檢視那一天。若要執行這項作業，請按一下報告視窗右上角的 [隱藏/顯示參數]，然後從 [報告者] 清單按一下 [工作階段計數]。
  
## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。下表列出您可以搭配對等 IM 報告的篩選器。
  
**對等 IM 報告篩選器**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份查看，請輸入當週或該月內的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**Interval** <br/> | 時間間隔。請選取下列其中一項： <br/>  每小時 (最多可以顯示 25 個小時) <br/>  每日 (最多可以顯示 31 天) <br/>  每週 (最多可以顯示 12 週) <br/>  每月 (最多可以顯示 12 個月) <br/>  若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。 例如，如果您選取 [開始日期 7/7/2015] 和 [結束2/28/2015 日期] 的 [每日間隔]，將會顯示 8/7/2015 12:00 AM 到 9/7/2015 12:00 AM (的資料，也就是有31天的資料) 總計。 <br/> |
|**報告依據** <br/> | 指定報告中所要使用的值。請選取下列其中一項： <br/>  工作階段計數 <br/>  訊息計數 <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>對等 IM 工作階段計量 (依集區)

下表列出對等 IM 報告提供的資訊。
  
**對等 IM 工作階段計量 (依集區)**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**集區** <br/> |否  <br/> |註冊機構集區或 Edge Server 的名稱。  <br/> |
|**日期/時間** <br/> |否  <br/> |工作階段的執行日期與時間。  <br/> |
|**Total** <br/> |否  <br/> |工作階段總數或訊息總數。  <br/> |
   
## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>對等 IM 工作階段計量 (依驗證類型)

下表列出對等 IM 報告針對參與者在對等工作階段中使用之每項驗證類型所提供的資訊。
  
**對等 IM 工作階段計量 (依驗證類型)**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**驗證類型** <br/> |否  <br/> | 工作階段參與者所使用的驗證類型。一般來說，值都是下列其中之一： <br/>  企業 <br/>  聯邦 <br/>  PIC <br/> |
|**日期/時間** <br/> |否  <br/> |工作階段的執行日期與時間。  <br/> |
|**Total** <br/> |否  <br/> |工作階段總數或訊息總數。  <br/> |
   

