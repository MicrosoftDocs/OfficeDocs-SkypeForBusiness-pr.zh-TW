---
title: 商務用 Skype Server中適用于通話品質儀表板 (CQD) 的資料 API
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：瞭解通話品質儀表板的資料 API。 通話品質儀表板是商務用 Skype Server的工具。
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675735"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>商務用 Skype Server中適用于通話品質儀表板 (CQD) 的資料 API
 
**總結：** 瞭解通話品質儀表板的資料 API。 通話品質儀表板是商務用 Skype Server的工具。
  
資料 API 可為商務用 Skype Server提供通話品質儀表板的程式設計存取。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質儀表板的資料 API

資料 API 提供 QoE Cube 的查詢介面。 資料 API 是一種 REST API，用於使用多維度資料庫，以根據指定的維度和篩選準則提供匯總的 QoE 計量。
  
下表包含 REST 作業。
  

|**作業**|**描述**|
|:-----|:-----|
|[取得 Cube](get-cube.md) <br/> |取得可用維度和度量的清單。  <br/> |
|[取得維度成員](get-dimension-members.md) <br/> |取得維度成員作業會傳回特定維度的成員清單。 它也可讓您篩選成員清單並取得子集，以降低電匯成本。  <br/> |
|[執行查詢](run-query.md) <br/> |執行查詢作業可讓您根據指定的維度、度量和篩選準則，在 Cube 上執行查詢，並傳回資料。  <br/> |
|[清除快取](clear-cache.md) <br/> |清除快取作業會刪除伺服器上查詢和資料的快取。 這會重設快取，之後我們會從 QoE Cube 取得新要求的全新資料。  <br/> |
|[取得整合記錄](get-integration-log.md) <br/> |取得整合記錄作業會傳回描述 QoE Cube 處理中活動的記錄專案清單。  <br/> |
|[取得上次整合資料](get-last-integration-data.md) <br/> |從 Cube 取得最後一個整合資料。  <br/> |
   
 **跨原始來源資源分享 (CORS) 資料 API 支援**
  
資料 API 支援跨原始來源資源分享 (CORS) 。 CORS 是一項 HTTP 功能，可讓在一個網域下執行的 Web 應用程式存取另一個網域中的資源。 網頁瀏覽器會實作稱為 [「相同原始](https://www.w3.org/Security/wiki/Same_Origin_Policy) 來源原則」相同原始來源原則的安全性限制，以防止網頁呼叫不同網域中的 API。 CORS 提供安全的方式，讓一個網域 (原始網域) 在另一個網域中呼叫 API。 如需 CORS 的詳細資訊，請參閱 [CORS 規格](https://www.w3.org/TR/cors/) 。
  
 **啟用資料 API 的 CORS**
  
 以下是資料 API web.config的摘錄，其中顯示 corsTrustedOrigin 應用程式設定中列出的兩個網域。 資料 API 會信任從這些伺服器載入之腳本所提出的所有要求。
  
如果有任何) ，請記得包含確切的通訊協定、主機名稱和埠 (。 請勿將任何正斜線字元放在結尾 (/) 。 您可以使用逗號分隔，以指定多個專案。
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


