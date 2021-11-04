---
title: 通話品質儀表板的資料 API (CQD) 商務用 Skype Server
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
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：瞭解通話品質儀表板的資料 API。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 3a305ce3c6b4a1bbfcc0fbdedbb575477f76d62c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742039"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>通話品質儀表板的資料 API (CQD) 商務用 Skype Server
 
**摘要：** 深入瞭解通話品質儀表板的資料 API。 通話品質儀表板是商務用 Skype Server 的工具。
  
Data API 為商務用 Skype Server 提供通話品質儀表板的程式設計存取。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質儀表板的資料 API

Data API 提供查詢介面給 QoE Cube。 Data API 是用於使用多維度資料庫的 REST API，它會根據指定的維度和篩選，提供匯總的 QoE 度量。
  
其餘的作業包含在下表中。
  

|**作業**|**描述**|
|:-----|:-----|
|[取得 Cube](get-cube.md) <br/> |取得可用的維度和度量清單。  <br/> |
|[取得維度成員](get-dimension-members.md) <br/> |取得維度成員操作傳回特定維度的成員清單。 它也可讓您篩選成員清單並取得子集，以降低線路傳輸成本。  <br/> |
|[執行查詢](run-query.md) <br/> |執行查詢作業可讓您根據指定的維度、度量及篩選，對 cube 執行查詢，並傳回資料。  <br/> |
|[清除快取](clear-cache.md) <br/> |清除快取作業會在伺服器上刪除查詢和資料的快取。 這將會重設快取，我們會在新的要求之後，從 QoE Cube 取得新的資料。  <br/> |
|[取得整合記錄](get-integration-log.md) <br/> |取得整合記錄作業會傳回描述 QoE Cube 處理中之活動的記錄專案清單。  <br/> |
|[取得上次整合資料](get-last-integration-data.md) <br/> |取得來自 cube 的最後整合資料。  <br/> |
   
 **跨原始資源分享 (對資料 API 的 CORS) 支援**
  
資料 API 支援跨原始資源分享 (CORS) 。 CORS 是一種 HTTP 功能，可讓在一個網域下執行的 web 應用程式存取另一個網域中的資源。 網頁瀏覽器會執行稱為 [相同原始來源原則](https://www.w3.org/Security/wiki/Same_Origin_Policy) 的安全性限制，以防止網頁撥打不同網域中的 APIs。 CORS 提供一種安全的方法，可讓一個網域 (原始網域) 呼叫另一個網域中的 APIs。 請參閱 [cors 規格](https://www.w3.org/TR/cors/) 以取得 cors 的詳細資料。
  
 **啟用資料 API 的 CORS**
  
 以下是資料 API web.config 的節選，顯示 corsTrustedOrigin 應用程式設定中所列的兩個網域。 從這些伺服器載入之腳本所進行的所有要求，都是由資料 API 所信任。
  
如果有任何) ，請記得包含確切的通訊協定、主機名稱和埠 (。 請勿將任何正斜線字元 (/) 在結尾。 您可以指定多個專案，並以逗號分隔。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


