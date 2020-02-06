---
title: 商務用 Skype Server 中的通話品質儀表板（CQD）的資料 API
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
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：瞭解通話品質儀表板的資料 API。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: e302c04dee298f9e5d2f33c908b5421ecff4de9a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816862"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>商務用 Skype Server 中的通話品質儀表板（CQD）的資料 API
 
**摘要：** 瞭解通話品質儀表板的資料 API。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
資料 API 提供以程式設計方式存取商務用 Skype Server 的通話品質儀表板。
  
## <a name="data-api-for-call-quality-dashboard"></a>通話品質儀表板的資料 API

資料 API 提供 QoE Cube 的查詢介面。 資料 API 是一個 REST API，可讓您使用多維度的資料庫，這些資料庫提供根據指定的維度與篩選的匯總 QoE 指標。
  
其餘的作業包括在下表中。
  

|**一道**|**說明**|
|:-----|:-----|
|[取得 Cube](get-cube.md) <br/> |取得可用尺寸與測量的清單。  <br/> |
|[取得維度成員](get-dimension-members.md) <br/> |[取得維度成員] 操作會傳回特定維度之成員的清單。 它也提供篩選成員清單及取得子集的功能，以減少線路傳輸成本。  <br/> |
|[執行查詢](run-query.md) <br/> |[執行查詢] 作業能根據指定的尺寸、測量及篩選，在立方體上執行查詢，並傳回資料。  <br/> |
|[清除快取](clear-cache.md) <br/> |[清除快取] 操作會刪除查詢和資料在伺服器上的快取。 這將會重設快取，然後從 QoE Cube 取得新的資料，之後就會出現新的要求。  <br/> |
|[取得整合記錄](get-integration-log.md) <br/> |取得整合記錄作業會傳回說明 QoE Cube 處理中之活動的記錄專案清單。  <br/> |
|[取得上次整合資料](get-last-integration-data.md) <br/> |取得來自多維資料集的最後一個整合資料。  <br/> |
   
 **資料 API 的跨來源資源分享（CORS）支援**
  
資料 API 支援跨來源資源分享（CORS）。 CORS 是一項 HTTP 功能，可讓在一個網域下執行的 web 應用程式存取其他網域中的資源。 網頁瀏覽器會執行稱為相同來源[原則](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制，以避免網頁在其他網域中呼叫 api。 CORS 提供安全的方法，可讓一個網域（原始網域）呼叫另一個網域中的 Api。 如需 CORS 的詳細資料，請參閱[CORS 規格](https://www.w3.org/TR/cors/)。
  
 **啟用資料 API 的 CORS**
  
 下列是資料 API web.config 的節選，顯示兩個網域列在 corsTrustedOrigin 應用程式設定中。 從這些伺服器載入之腳本所進行的所有要求，都受資料 API 信任。
  
請記得包含確切的通訊協定、主機名稱和埠（如果有的話）。 不要將任何正斜線字元（/）放在結尾處。 您可以使用逗號分隔來指定多個專案。
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


