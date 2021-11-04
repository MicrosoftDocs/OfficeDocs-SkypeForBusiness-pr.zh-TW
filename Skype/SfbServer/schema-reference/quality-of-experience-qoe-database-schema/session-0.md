---
title: 會話視圖
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 22ad5fdc02eb7b3dc7531a18f4b40bee0334ce09
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776013"
---
# <a name="session-view"></a>會話視圖
 
「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |參考來源為 MediaLine 表格。  <br/> |
|ConferenceURI  <br/> |Nvarchar (450)   <br/> |如果是會議則為會議 URI，如果是對等工作階段則為 DialogID。  <br/> |
|Correlation  <br/> |Varchar (max)   <br/> |工作階段的關聯 ID。  <br/> |
|DialogCategory  <br/> |位  <br/> |對話方塊類別;0商務用 Skype Server 轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。  <br/> |
|MediationServerBypassFlag  <br/> |位  <br/> |指出通話是否經旁路處理。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。 商務用 Skype Server，只會定義一個值：  <br/> 0x0001-預設網路介面卡的未知旁路識別碼  <br/> |
|StartTime  <br/> |datetime  <br/> |通話開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |通話結束時間。  <br/> |
|CallerPool  <br/> |Nvarchar (256)   <br/> |發話者集區 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar (256)   <br/> |受話者集區 FQDN。  <br/> |
|CallerPAI  <br/> |Nvarchar (450)   <br/> |來電者的 p 宣稱身分識別 URI。  <br/> |
|CalleePAI  <br/> |Nvarchar (450)   <br/> |被呼叫者的 p 宣稱身分識別 URI。  <br/> |
|CallerEndpoint  <br/> |Nvarchar (256)   <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar (256)   <br/> |來電者的端點名稱。  <br/> |
|CallerUserAgent  <br/> |Nvarchar (256)   <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |來電者使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼叫者的使用者代理類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar (256)   <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |受話者的使用者代理程式類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |受話者的使用者代理程式類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CallerURI  <br/> |Nvarchar (450)   <br/> |來電者的 URI。  <br/> |
|CalleeURI  <br/> |Nvarchar (450)   <br/> |被呼叫者的 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |通話的優先順序。  <br/> |
   

