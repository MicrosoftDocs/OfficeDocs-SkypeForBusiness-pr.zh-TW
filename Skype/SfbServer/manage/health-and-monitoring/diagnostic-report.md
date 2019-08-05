---
title: 商務用 Skype Server 中的診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '摘要: 瞭解商務用 Skype 伺服器中的診斷報告。'
ms.openlocfilehash: d71906f2407a0daadc04417ab60a23c86f5eeb52
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193748"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>商務用 Skype Server 中的診斷報告
 
**摘要:** 瞭解商務用 Skype Server 中的診斷報告。
  
診斷報告提供失敗會話的診斷與疑難排解資訊。 此資訊包括在會話失敗時所報告的診斷 ID 和診斷標頭。 診斷 ID 是附加至 SIP 訊息的唯一識別碼 (以 ms 診斷標頭形式), 而診斷標頭則提供診斷識別碼的隨附描述。 報告可能也包含報告元件已知的有用疑難排解詳細資料。 例如：
  
- PSTN 閘道產生失敗時所提供的原因代碼。 PSTN 網路上的撥出電話失敗時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，指出沒有電路或通道可以完成通話。
    
- 針對連接失敗的對等 FQDN、埠和 Winsock 錯誤。
    
- 尋找 DNS 解析失敗的名稱。 只要用戶端與名稱伺服器聯絡, 並要求對應至指定裝置名稱的 IP 位址, 就會發生 DNS 解析。
    
## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

按一下 [商務用 Skype 伺服器] 或 [會議詳細資料] 報表[中的點對點工作階段詳細資料包告](peer-to-peer-session-detail-report.md)上的 [診斷報告 (詳細資料)] 度量, 即可存取診斷報告。
  
## <a name="filters"></a>濾鏡

無。 您無法篩選診斷報告。
  
## <a name="metrics"></a>指標

下表列出每個會話的診斷報告所提供的資訊。
  
**診斷報告度量單位**

|**名稱**|**您可以針對此專案進行排序嗎？**|**說明**|
|:-----|:-----|:-----|
|**報告時間** <br/> |不  <br/> |記錄報告的日期和時間。  <br/> |
|**回應代碼** <br/> |不  <br/> |在會話失敗時傳送 SIP 回應代碼。  <br/> |
|**要求類型** <br/> |不  <br/> |失敗的 SIP 要求類型。 例如, [邀請]、[再見] 或 [服務]。  <br/> |
|**從源** <br/> |不  <br/> |錯誤來源。  <br/> |
|**從使用者 URI** <br/> |不  <br/> |啟動會話之使用者的 SIP 位址。  <br/> |
|**從使用者代理程式** <br/> |不  <br/> |啟動會話之使用者的端點所使用的軟體。  <br/> |
|**診斷識別碼** <br/> |不  <br/> |附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。  <br/> |
|**內容類型** <br/> |不  <br/> |失敗的媒體內容類型。 例如, 常見的內容類型是 Application/sdp。 會話描述通訊協定 (SDP) 是一種標準的網際網路通訊協定, 用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。  <br/> |
|**應用程式** <br/> |不  <br/> |錯誤中涉及的應用程式。  <br/> |
|**使用者 URI** <br/> |不  <br/> |受邀者加入會話之使用者的 SIP 位址。  <br/> |
|**會議加入時間 (毫秒)** <br/> |不  <br/> |使用者加入會議所需的時間量 (以毫秒為單位)。  <br/> |
|**診斷標頭** <br/> |不  <br/> |診斷識別碼描述。  <br/> |
   
您可以在[Ms Diagnostics 頁首頁面](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)找到診斷錯誤清單。
  

