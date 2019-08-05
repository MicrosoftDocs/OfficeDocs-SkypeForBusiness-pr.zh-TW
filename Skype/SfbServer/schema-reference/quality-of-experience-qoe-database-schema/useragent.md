---
title: UserAgent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 資料表是一種支援資料表, 可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄代表一個使用者代理程式
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192622"
---
# <a name="useragent-table"></a>UserAgent 表格
 
UserAgent 資料表是一種支援資料表, 可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄代表一個使用者代理程式
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |首選  <br/> |標識此使用者代理程式的唯一號碼。  <br/> |
|**UserAgent** <br/> |Nvarchar (256)  <br/> |唯一  <br/> |使用者代理程式字串。  <br/> |
|**UAType** <br/> |Smallint  <br/> | <br/> |1是中繼伺服器。  <br/> 2是 A/V 會議伺服器。  <br/> 4是商務用 Skype。  <br/> 8為 IP 電話。  <br/> 16為 Live Meeting 主控台。  <br/> 32是部署驗證工具 (DVT)。  <br/> 64是 Macintosh 電腦上的商務用 Skype 伺服器。  <br/> 128是商務用 Skype Server 的相關 Skype。  <br/> 256是會議宣告服務。  <br/> 512是會議自動語音應答。  <br/> 1024為回應群組應用程式。  <br/> 2048超出語音控制。  <br/> |
   

