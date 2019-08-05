---
title: '[會話] 視圖'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: '[會話] 視圖儲存在資料庫中有記錄之會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: b24afdff32b5223725aa4f8ff0b7d875199713c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192636"
---
# <a name="session-view"></a>[會話] 視圖
 
[會話] 視圖儲存在資料庫中有記錄之會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |從 MediaLine 資料表中參照。  <br/> |
|ConferenceURI  <br/> |Nvarchar (450)  <br/> |會議 URI (如果這是會議), 或 DialogID (如果這是點對點工作階段的話)。  <br/> |
|相關  <br/> |Varchar (max)  <br/> |會話的相關識別碼。  <br/> |
|DialogCategory  <br/> |稍微  <br/> |對話方塊類別;0是商務用 Skype 伺服器以轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。  <br/> |
|MediationServerBypassFlag  <br/> |稍微  <br/> |指出是否已略過通話。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |此欄位 (如果有的話) 會指出即使繞過的旁路 Id, 也不會避開通話。 針對商務用 Skype Server, 只定義一個值:  <br/> 0x0001-預設網路介面卡的旁路識別碼  <br/> |
|開始  <br/> |datetime  <br/> |呼叫開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |通話結束時間。  <br/> |
|CallerPool  <br/> |Nvarchar (256)  <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar (256)  <br/> |被呼叫方池 FQDN。  <br/> |
|CallerPAI  <br/> |Nvarchar (450)  <br/> |來電者 p 斷言身分識別 URI。  <br/> |
|CalleePAI  <br/> |Nvarchar (450)  <br/> |被呼叫者的 p 聲明身分識別 URI。  <br/> |
|CallerEndpoint  <br/> |Nvarchar (256)  <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar (256)  <br/> |來電者的端點名稱。  <br/> |
|CallerUserAgent  <br/> |Nvarchar (256)  <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |呼叫者的使用者代理程式類型。 如需詳細資訊, 請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar (64)  <br/> |呼叫者的使用者代理類別。 如需詳細資訊, 請參閱[UserAgentDef 資料表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar (256)  <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |被呼叫者的使用者代理程式類型。 如需詳細資訊, 請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar (64)  <br/> |被呼叫者的使用者代理類別。 如需詳細資訊, 請參閱[UserAgentDef 資料表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CallerURI  <br/> |Nvarchar (450)  <br/> |來電者的 URI。  <br/> |
|CalleeURI  <br/> |Nvarchar (450)  <br/> |被呼叫者的 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |通話的優先順序。  <br/> |
   

