---
title: 商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 摘要：瞭解商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告。
ms.openlocfilehash: fe49c455391583a02f873769a75d86da62fe2a25
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829967"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告
 
**摘要：** 深入瞭解商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告。
  
Peer-to-Peer 會話詳細資料包告會傳回點對點工作階段的詳細資訊。 例如，如果您選取立即訊息會話，該報告將會告訴您會話中的兩位使用者所傳送的郵件數目。
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>存取 Peer-to-Peer 會話詳細資料包告

您可以從下列任何報告中存取 Peer-to-Peer 會話詳細資料包告 (所有可從監控報告首頁存取的報告) ：
  
- IP 電話清查報告
    
- 使用者活動報告
    
- 通話許可控制報告
    
- 失敗清單報告 
    
在 [Peer-to-Peer 會話詳細資料包告] 中，按一下 [診斷報告 (詳細資料]) 度量，即可存取[商務用 Skype Server 中的診斷報告](diagnostic-report.md)。 您也可以按一下下列兩個度量，以存取最上層失敗報告：
  
- 回應
    
- 診斷識別碼
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Peer-to-Peer 會話詳細資料包告的最佳用法

「Peer-to-Peer 會話詳細資料包告」包括大量的計量，許多系統管理員可能都不熟悉。 不過，您通常可以查看工具提示，只要將滑鼠放在「規格」標籤上方，就能提供該度量的簡短描述。
  
請注意，顯示在特定報告上的實際度量值將取決於您所選取的點對點工作階段類型。 音訊/視頻會話會報告一組不同于立即訊息會話的計量。
  
您也可以將滑鼠停留在回應程式碼和診斷識別碼計量中，以取得這些值的描述：
  
## <a name="filters"></a>篩選

無。 您無法篩選 Peer-to-Peer 會話詳細資料包告。
  
## <a name="session-information-metrics"></a>會話資訊計量

下表列出每個會話的 Peer-to-Peer 會話詳細資料包告中提供的資訊。
  
**會話資訊計量**

|**名稱**|**描述**|
|:-----|:-----|
|**集區 FQDN** <br/> |與會話有關之註冊區集區或 Edge Server 的完整功能變數名稱 (FQDN) 。  <br/> |
|**邀請時間** <br/> |最初傳送會話邀請的日期和時間。  <br/> |
|**回應時間** <br/> |收到邀請接受的日期和時間。  <br/> |
|**來源使用者** <br/> |啟動工作階段之使用者的 SIP 位址。  <br/> |
|**從使用者代理程式** <br/> |啟動會話之使用者端點所使用的軟體。  <br/> |
|**來自使用者內部** <br/> |會指出起始會話的使用者是否登入內部網路。  <br/> |
|**來源於與電話機整合的使用者** <br/> |會指出起始會話之使用者所使用的端點是否與他或她的桌面電話整合。  <br/> |
|**會話優先順序** <br/> |指派給會話的優先順序。 有效的優先順序如下： Unknown;非緊急;一般緊迫和緊急。  <br/> |
|**回應碼** <br/> |會話失敗時傳送的 SIP 回應碼。  <br/> |
|**前端** <br/> |會議中所使用的前端伺服器名稱。  <br/> |
|**拍攝時間** <br/> |記錄會話資訊的日期和時間。  <br/> |
|**結束時間** <br/> |會話結束的日期和時間。  <br/> |
|**目標使用者** <br/> |獲邀加入會話之使用者的 SIP 位址。  <br/> |
|**至使用者代理程式** <br/> |受邀加入會話之使用者的端點所使用的軟體。  <br/> |
|**是使用者內部使用者** <br/> |會指出被邀加入會話的使用者是否登入內部網路。  <br/> |
|**是與電話機整合的使用者** <br/> |會指出受邀加入會話之使用者所使用的端點是否與他或她的桌面電話整合。  <br/> |
|**會重試會話** <br/> |會指出會話是否嘗試重試先前失敗的會話。  <br/> |
|**診斷識別碼** <br/> |附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。 將滑鼠停留在識別碼號碼上方，以查看有關該識別碼的其他資訊。  <br/> |
   
## <a name="metrics-for-modalities"></a>形式的計量

下表列出每個會話模態的 Peer-to-Peer 會話詳細資料包告中提供的資訊。
  
**形式的計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**方式** <br/> |否  <br/> |會話中使用的形式。 例如，立即訊息 (IM) 或檔案傳輸。  <br/> |
|**從使用者郵件** <br/> |否  <br/> |啟動會話之使用者所傳送的訊息數。  <br/> |
|**使用者訊息** <br/> |否  <br/> |受邀加入會話之使用者所傳送的郵件數目。  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>診斷報告的計量

下表列出每個診斷報告的 Peer-to-Peer 會話詳細資料包告中提供的資訊。
  
**診斷報告的計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**Detail** <br/> |否  <br/> |當您按一下此專案時，報告會顯示會話的診斷報告。  <br/> |
|**報告時間** <br/> |否  <br/> |報告的記錄日期與時間。  <br/> |
|**請求** <br/> |否  <br/> |SIP 要求類型。 例如，INVITE 或再見。  <br/> |
|**診斷識別碼** <br/> |否  <br/> |附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。  <br/> |
|**內容類型** <br/> |否  <br/> |會議中所使用的媒體內容類型。 例如，常見的內容類型為 Application/sdp。 Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。  <br/> |
|**報告者** <br/> |否  <br/> |電腦 (，也就是報告問題的用戶端或伺服器) 。  <br/> |
   

