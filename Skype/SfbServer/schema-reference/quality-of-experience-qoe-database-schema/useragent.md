---
title: UserAgent 表格
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄都代表一個使用者代理程式
ms.openlocfilehash: a2480131b224dfe0469b39e34296b7848461bb33bd71c39c313016f8203f6266
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301249"
---
# <a name="useragent-table"></a>UserAgent 表格
 
UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄都代表一個使用者代理程式
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |主要  <br/> |用於識別此使用者代理程式的唯一號碼。  <br/> |
|**UserAgent** <br/> |Nvarchar (256)   <br/> |Unique  <br/> |使用者代理程式字串。  <br/> |
|**UAType** <br/> |Smallint  <br/> | <br/> |1是轉送伺服器。  <br/> 2是 A/V 的會議服務器。  <br/> 4為商務用 Skype。  <br/> 8是 IP 電話。  <br/> 16是 Live Meeting 主控台。  <br/> 32是部署驗證工具 (DVT) 。  <br/> 64是在 Macintosh 電腦上商務用 Skype Server。  <br/> 128為商務用 Skype Server 的語音應答。  <br/> 256為會議宣告服務。  <br/> 512為會議自動語音應答。  <br/> 1024是回應群組應用程式。  <br/> 2048超出語音控制。  <br/> |
   

