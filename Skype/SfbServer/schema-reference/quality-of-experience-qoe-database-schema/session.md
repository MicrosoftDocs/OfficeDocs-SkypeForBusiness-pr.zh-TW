---
title: Session 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每個記錄代表一個涉及音訊或音訊與影片的會話。 它包含有關會話的整體資訊。 會話是在兩個端點之間定義為音訊或視頻會話初始通訊協定（SIP）對話方塊。
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805771"
---
# <a name="session-table"></a>Session 表格
 
每個記錄代表一個涉及音訊或音訊與影片的會話。 它包含有關會話的整體資訊。 會話是在兩個端點之間定義為音訊或視頻會話初始通訊協定（SIP）對話方塊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[對話方塊表格](dialog.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[對話方塊表格](dialog.md)中參照。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外  <br/> |[會議金鑰]。 從[會議表格](conference.md)中參照。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外  <br/> |[關聯金鑰]。 從[SessionCorrelation 資料表](sessioncorrelation.md)中參照。  <br/> |
|**DialogCategory** <br/> |稍微  <br/> | <br/> |對話方塊類別;0是商務用 Skype 伺服器以轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。  <br/> |
|**MediationServerBypassFlag** <br/> |稍微  <br/> ||該旗標指出通話是否被略過。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||此欄位（如果有的話）會指出即使繞過的旁路 Id，也不會避開通話。 針對商務用 Skype Server，只會定義一個值。  <br/> 0x0001-預設網路介面卡的旁路 ID 為未知。  <br/> |
|**開始** <br/> |datetime  <br/> | <br/> |呼叫開始時間。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |通話結束時間。  <br/> |
|**CallerPool** <br/> |int  <br/> |外  <br/> |來電者的池子。 從 [Pool] （[池）資料表](pool.md)中參照。  <br/> |
|**CalleePool** <br/> |int  <br/> |外  <br/> |呼叫接收器的池子。 從 [Pool] （[池）資料表](pool.md)中參照。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外  <br/> |接收端點的 SIP p 斷言身分識別（PAI）中的 SIP URI。 從[使用者資料表](user-0.md)中參照。  <br/> |
|**CallerURI** <br/> |int  <br/> |外  <br/> |來電者的 URI。 從[使用者資料表](user-0.md)中參照。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外  <br/> |來電者的端點。 從[端點資料表](endpoint.md)中參照。  <br/> |
|**CallerUserAgent** <br/> |稍微  <br/> |外  <br/> |來電者的使用者代理程式。 從[UserAgent 資料表](useragent.md)中參照。  <br/> |
|**CallPriority** <br/> |Smallint  <br/> ||此通話的優先順序。  <br/> |
|**ClassifiedPoorCall** <br/> |稍微  <br/> ||此欄已被棄用，且不會用於商務用 Skype 伺服器。 相反地，此資訊是在每個媒體的行基底報告。 如需詳細資訊，請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外  <br/> |P-已斷言-撥打電話之使用者的身分識別。 P 斷言身分識別（PAI）是用來傳達撥打電話之使用者的真實身分識別。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外  <br/> |接收通話的端點。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外  <br/> |由接收通話的使用者所使用的使用者代理程式。 使用者代理代表用戶端端點裝置。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外  <br/> |接收通話之使用者的 SIP URI。  <br/> |
   

