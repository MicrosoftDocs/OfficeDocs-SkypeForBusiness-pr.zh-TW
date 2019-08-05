---
title: 商務用 Skype Server 中的通話品質儀表板 (CQD) 的知識庫 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '摘要: 瞭解通話品質儀表板的知識庫 API。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 723b7a9340737e3f1cec47112b33ff1175597cd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186871"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>商務用 Skype Server 中的通話品質儀表板 (CQD) 的知識庫 API
 
**摘要:** 瞭解 [通話品質] 儀表板的 [知識庫 API]。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
知識庫 API 提供以程式設計方式存取商務用 Skype Server 的通話品質儀表板。
  
## <a name="repository-api-for-call-quality-dashboard"></a>通話品質儀表板的知識庫 API

知識庫 API 提供了知識庫資料庫的資料存取介面。 儲存庫可將內容組織在樹狀結構或圖形結構中, 讓使用者能以對使用者有意義的方式將其組成群組。 儲存庫支援兩種一般類型的使用者: 系統使用者, 這是代表存放庫的內建使用者, 以及代表儲存庫授權使用者的一般使用者。
  
[知識庫 API] 包含三個一般服務: 
  
- [CQD 的使用者服務](user-service.md)-用於存取使用者。
    
- [通話品質儀表板 (CQD) 的專案服務](item-service.md)-用於存取專案及儲存在專案中的內容。
    
- [通話品質儀表板 (CQD) 的使用者設定服務](user-settings-service.md)-用於存取使用者設定。
    
通話品質儀表板使用知識庫 API 來管理下列資訊: 
  
- 可存取儲存庫之使用者的**使用者**代表。
    
- **報表**-包含一份查詢清單, 並儲存為文件庫專案中的內容。
    
- **Query** -用於從資料 API 中檢索資料, 並儲存為儲存在文件庫專案中的內容。
    
- **使用者設定**-為使用者描述選用的應用程式行為。
    
  **針對知識庫 API 的跨來源資源分享 (CORS) 支援**
  
知識庫 API 支援跨來源資源分享 (CORS)。 CORS 是一項 HTTP 功能, 可讓在一個網域下執行的 web 應用程式存取其他網域中的資源。 網頁瀏覽器會執行稱為相同來源[原則](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制, 以避免網頁在其他網域中呼叫 api。 CORS 提供安全的方法, 可讓一個網域 (原始網域) 呼叫另一個網域中的 Api。 如需 CORS 的詳細資料, 請參閱[CORS 規格](https://www.w3.org/TR/cors/)。
  
 **為知識庫 API 啟用 CORS**
  
 下列是知識庫 API web.config 的節選, 顯示兩個網域列在 corsTrustedOrigin 應用程式設定中。 從這些伺服器載入之腳本所做的所有要求, 都受知識庫 API 信任。
  
請記得包含確切的通訊協定、主機名稱和埠 (如果有的話)。 不要將任何正斜線字元 (/) 放在結尾處。 您可以使用逗號分隔來指定多個專案。
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


