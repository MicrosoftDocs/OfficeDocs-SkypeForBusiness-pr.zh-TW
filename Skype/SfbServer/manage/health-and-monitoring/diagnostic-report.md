---
title: Skype for Business Server 的診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 摘要： 了解 skype for Business Server 診斷報告。
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041990"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Skype for Business Server 的診斷報告
 
**摘要：** 了解 skype for Business Server 診斷報告。
  
診斷報告提供失敗工作階段的診斷與疑難排解的資訊。 此資訊包括診斷識別碼及工作階段失敗時，所報告的診斷標頭。 診斷識別碼是取得附加至 SIP 郵件，而診斷標頭提供隨附的說明診斷識別碼的唯一識別碼 （以毫秒診斷標頭的形式） 報告也可能包含重要已知的報告元件的疑難排解詳細資料。 例如：
  
- 原因程式碼提供者產生失敗的 PSTN 閘道。 PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。
    
- 對等 FQDN、 連接埠與 Winsock 錯誤的連線失敗。
    
- 正在進行查閱 DNS 解析失敗的名稱。 DNS 解析任何用戶端的連絡人名稱伺服器的時間，並要求的 IP 位址會對應至指定的裝置名稱。
    
## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

可以按一下[skype for Business 伺服器端對端工作階段詳細資料報表](peer-to-peer-session-detail-report.md)或會議詳細資料報表上的 [診斷報告 （詳細資料）] 計量來存取診斷報告。
  
## <a name="filters"></a>篩選

無。 您無法篩選診斷報告。
  
## <a name="metrics"></a>計量

下表列出診斷報告針對每個工作階段所提供的資訊。
  
**診斷報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**報告時間** <br/> |否  <br/> |日期和時間報告的記錄。  <br/> |
|**回應碼** <br/> |否  <br/> |SIP 工作階段失敗時傳送的回應碼。  <br/> |
|**要求類型** <br/> |否  <br/> |SIP 失敗的要求類型。 例如，邀請、 BYE 或服務。  <br/> |
|**Source** <br/> |否  <br/> |錯誤的來源。  <br/> |
|**來源使用者 URI** <br/> |否  <br/> |啟動工作階段之使用者的 SIP 位址。  <br/> |
|**來源使用者代理程式** <br/> |否  <br/> |起始工作階段之使用者端點所用的軟體。  <br/> |
|**診斷識別碼** <br/> |否  <br/> |唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。  <br/> |
|**內容類型** <br/> |否  <br/> |失敗的媒體內容類型。 例如，常見的內容類型是應用程式/sdp。 工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。  <br/> |
|**Application** <br/> |否  <br/> |應用程式發生錯誤的。  <br/> |
|**目標使用者 URI** <br/> |否  <br/> |獲邀加入工作階段之使用者的 SIP 位址。  <br/> |
|**會議加入時間 （毫秒）** <br/> |否  <br/> |量花使用者加入會議的時間 （以毫秒為單位）。  <br/> |
|**診斷標頭** <br/> |否  <br/> |診斷識別碼的描述。  <br/> |
   
[Ms-diagnostics 標頭] 頁面](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx)上，可以找到診斷錯誤清單。
  

