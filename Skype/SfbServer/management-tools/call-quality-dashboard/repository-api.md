---
title: 用於通話品質儀表板的存放庫 API (CQD) 商務用 Skype Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：瞭解適用于通話品質儀表板的存放庫 API。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 19d1f456afdf9f72721d1a246b206ad4f7259f14
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386571"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>用於通話品質儀表板的存放庫 API (CQD) 商務用 Skype Server
 
**總結：** 瞭解適用于通話品質儀表板的存放庫 API。 通話品質儀表板是商務用 Skype Server 的工具。
  
存放庫 API 為商務用 Skype Server 提供通話品質儀表板的程式設計存取。
  
## <a name="repository-api-for-call-quality-dashboard"></a>通話品質儀表板的存放庫 API

存放庫 API 提供存放庫資料庫的資料存取介面。 存放庫允許內容以樹狀或圖形結構的方式組織，這樣使用者就能以對使用者有意義的方式來群組內容。 存放庫支援兩種一般類型的使用者：系統使用者，也就是代表存放庫的內建使用者，以及代表存放庫之授權使用者的一般使用者。
  
存放庫 API 由三個一般服務組成： 
  
- [CQD 的使用者服務](user-service.md) -用於存取使用者。
    
- [通話品質儀表板 (CQD) 的專案服務 ](item-service.md) -用於存取專案和儲存在專案中的內容。
    
- [通話品質儀表板的使用者設定服務 (CQD) ](user-settings-service.md) -用於存取使用者設定。
    
通話品質儀表板使用存放庫 API 來管理下列資訊： 
  
- 可存取存放庫之使用者的 **使用者** 表示。
    
- **Report** -包含查詢的清單，儲存為存放庫專案中的內容。
    
- **查詢** -用於從資料 API 中取得資料，並儲存為存放庫專案中的內容。
    
- **使用者設定** -為使用者描述選用的應用程式行為。
    
  **跨原始資源分享 (用於存放庫 API 的 CORS) 支援**
  
存放庫 API 支援跨原始資源分享 (CORS) 。 CORS 是一種 HTTP 功能，可讓在一個網域下執行的 web 應用程式存取另一個網域中的資源。 網頁瀏覽器會執行稱為 [相同原始來源原則](https://www.w3.org/Security/wiki/Same_Origin_Policy) 的安全性限制，以防止網頁撥打不同網域中的 APIs。 CORS 提供一種安全的方法，可讓一個網域 (原始網域) 呼叫另一個網域中的 APIs。 請參閱 [cors 規格](https://www.w3.org/TR/cors/) 以取得 cors 的詳細資料。
  
 **啟用存放庫 API 的 CORS**
  
 以下是存放庫 API web.config 的摘選，顯示 corsTrustedOrigin 應用程式設定中所列的兩個網域。 從這些伺服器載入之腳本所進行的所有要求，都是由存放庫 API 所信任。
  
如果有任何) ，請記得包含確切的通訊協定、主機名稱和埠 (。 請勿將任何正斜線字元 (/) 在結尾。 您可以指定多個專案，並以逗號分隔。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


