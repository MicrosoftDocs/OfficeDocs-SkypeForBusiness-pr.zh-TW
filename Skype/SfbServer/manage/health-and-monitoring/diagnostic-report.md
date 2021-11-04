---
title: 商務用 Skype Server 中的診斷報告
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 摘要：瞭解商務用 Skype Server 中的診斷報告。
ms.openlocfilehash: 84274659a45d33a144324334cec8b9f1b25c471b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740629"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>商務用 Skype Server 中的診斷報告
 
**摘要：** 深入瞭解商務用 Skype Server 中的診斷報告。
  
診斷報告可提供失敗會話的診斷與疑難排解資訊。 此資訊包含會話失敗時所報告的診斷識別碼和診斷標頭。 診斷 ID 是與 SIP 郵件相連的 ms diagnostics 標頭) 形式的唯一識別碼 (，而診斷標頭則提供診斷識別碼的附帶描述。 報告可能也包含報告元件所知道的有用疑難排解詳細資料。 例如：
  
- 產生失敗之 PSTN 閘道所提供的原因碼。 PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。
    
- 連接失敗的對等 FQDN、埠和 Winsock 錯誤。
    
- 要尋找以進行 DNS 解析失敗的名稱。 DNS 解析會在用戶端接觸名稱伺服器時進行，並要求對應至指定裝置名稱的 IP 位址。
    
## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

您可以在商務用 Skype Server 或會議詳細資料包告的 [ [Peer-to-Peer 會話詳細資料](peer-to-peer-session-detail-report.md)] 報告中，按一下 [診斷報告] (詳細資料) 度量，即可存取診斷報告。
  
## <a name="filters"></a>篩選

無。 您無法篩選診斷報告。
  
## <a name="metrics"></a>度量

下表列出每個會話的診斷報告中提供的資訊。
  
**診斷報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**報告時間** <br/> |否  <br/> |報告的記錄日期與時間。  <br/> |
|**回應碼** <br/> |否  <br/> |會話失敗時傳送的 SIP 回應碼。  <br/> |
|**要求類型** <br/> |否  <br/> |失敗的 SIP 要求類型。 例如，邀請、再見或服務。  <br/> |
|**Source** <br/> |否  <br/> |錯誤來源。  <br/> |
|**從使用者 URI** <br/> |否  <br/> |啟動工作階段之使用者的 SIP 位址。  <br/> |
|**從使用者代理程式** <br/> |否  <br/> |啟動會話之使用者端點所使用的軟體。  <br/> |
|**診斷識別碼** <br/> |否  <br/> |附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。  <br/> |
|**內容類型** <br/> |否  <br/> |失敗的媒體內容類型。 例如，常見的內容類型為 Application/sdp。 Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。  <br/> |
|**應用程式** <br/> |否  <br/> |錯誤所涉及的應用程式。  <br/> |
|**至使用者 URI** <br/> |否  <br/> |獲邀加入會話之使用者的 SIP 位址。  <br/> |
|**會議加入時間 (毫秒)** <br/> |否  <br/> |使用者加入會議所需的時間（以毫秒為單位）)  (量。  <br/> |
|**診斷標頭** <br/> |否  <br/> |診斷識別碼描述。  <br/> |
   
您可以在 [Ms Diagnostics 頁首頁面](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)上找到診斷錯誤的清單。
