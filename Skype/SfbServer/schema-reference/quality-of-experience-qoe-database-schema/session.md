---
title: Session 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每筆記錄代表一個包含音訊或音訊和影片的會話。 包含有關會話的整體資訊。 會話是在兩個端點之間的 (SIP) ] 對話方塊中定義為音訊或視頻會話初始通訊協定。
ms.openlocfilehash: 749f151def046abdb5169b39ccbd81ea5f07f5d4ee3d1c971ac112a2d4b90cce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340029"
---
# <a name="session-table"></a>Session 表格
 
每筆記錄代表一個包含音訊或音訊和影片的會話。 包含有關會話的整體資訊。 會話是在兩個端點之間的 (SIP) ] 對話方塊中定義為音訊或視頻會話初始通訊協定。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [對話方塊表格](dialog.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [對話方塊表格](dialog.md)中參照。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Foreign  <br/> |會議金鑰。 從 [會議表格](conference.md)參考。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Foreign  <br/> |相關機碼。 從 [SessionCorrelation 表格](sessioncorrelation.md)中參照。  <br/> |
|**DialogCategory** <br/> |位  <br/> | <br/> |對話方塊類別;0商務用 Skype Server 轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。  <br/> |
|**MediationServerBypassFlag** <br/> |位  <br/> ||指示是否略過呼叫的旗標。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。 商務用 Skype Server，只會定義一個值。  <br/> 0x0001-預設網路介面卡的未知旁路識別碼。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |通話開始時間。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |通話結束時間。  <br/> |
|**CallerPool** <br/> |int  <br/> |Foreign  <br/> |來電者的集區。 從集區 [資料表](pool.md)中參照。  <br/> |
|**CalleePool** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器的集區。 從集區 [資料表](pool.md)中參照。  <br/> |
|**CalleePAI** <br/> |int  <br/> |Foreign  <br/> |SIP p-宣稱身分識別 (PAI) 接收方端點的 SIP URI。 從 [使用者資料表](user-0.md)中參照。  <br/> |
|**CallerURI** <br/> |int  <br/> |Foreign  <br/> |來電者的 URI。 從 [使用者資料表](user-0.md)中參照。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Foreign  <br/> |來電者的端點。 從 [端點表](endpoint.md)參考。  <br/> |
|**CallerUserAgent** <br/> |位  <br/> |Foreign  <br/> |來電者的使用者代理程式。 從 [UserAgent 表格](useragent.md)中參照。  <br/> |
|**CallPriority** <br/> |Smallint  <br/> ||此通話的優先順序。  <br/> |
|**ClassifiedPoorCall** <br/> |位  <br/> ||此欄已被取代，不會用於商務用 Skype Server。 相反地，會在每個媒體行基礎上報告此資訊。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|**CallerPAI** <br/> |int  <br/> |Foreign  <br/> |撥打通話之使用者的 P-Asserted-Identity。 P-Asserted-Identity (PAI) 是用來傳達撥打通話之使用者的真實身分識別。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Foreign  <br/> |接收通話的端點。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Foreign  <br/> |接收通話之使用者所採用的使用者代理程式。 使用者代理程式代表用戶端端點裝置。  <br/> |
|**CalleeUri** <br/> |int  <br/> |Foreign  <br/> |接收通話之使用者的 SIP URI。  <br/> |
   

