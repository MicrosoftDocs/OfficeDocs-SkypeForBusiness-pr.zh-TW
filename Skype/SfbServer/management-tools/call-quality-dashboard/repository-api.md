---
title: 商務用 Skype Server 中的通話品質儀表板 (CQD) 的存放庫 API
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：瞭解適用于通話品質儀表板的存放庫 API。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803123"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="1e7f4-104">商務用 Skype Server 中的通話品質儀表板 (CQD) 的存放庫 API</span><span class="sxs-lookup"><span data-stu-id="1e7f4-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="1e7f4-105">**摘要：** 瞭解適用于通話品質儀表板的存放庫 API。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1e7f4-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1e7f4-107">存放庫 API 為商務用 Skype 伺服器提供通話品質儀表板的程式設計存取。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="1e7f4-108">通話品質儀表板的存放庫 API</span><span class="sxs-lookup"><span data-stu-id="1e7f4-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="1e7f4-109">存放庫 API 提供存放庫資料庫的資料存取介面。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="1e7f4-110">存放庫允許內容以樹狀或圖形結構的方式組織，這樣使用者就能以對使用者有意義的方式來群組內容。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="1e7f4-111">存放庫支援兩種一般類型的使用者：系統使用者，也就是代表存放庫的內建使用者，以及代表存放庫之授權使用者的一般使用者。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="1e7f4-112">存放庫 API 由三個一般服務組成：</span><span class="sxs-lookup"><span data-stu-id="1e7f4-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="1e7f4-113">[CQD 的使用者服務](user-service.md) -用於存取使用者。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="1e7f4-114">[通話品質儀表板 (CQD) 的專案服務 ](item-service.md) -用於存取專案和儲存在專案中的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="1e7f4-115">[通話品質儀表板 (CQD) 的使用者設定服務 ](user-settings-service.md) -用於存取使用者設定。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="1e7f4-116">通話品質儀表板使用存放庫 API 來管理下列資訊：</span><span class="sxs-lookup"><span data-stu-id="1e7f4-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="1e7f4-117">可存取存放庫之使用者的 **使用者** 表示。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="1e7f4-118">**Report** -包含查詢的清單，儲存為存放庫專案中的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1e7f4-119">**查詢** -用於從資料 API 中取得資料，並儲存為存放庫專案中的內容。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1e7f4-120">**使用者設定** -為使用者描述選用的應用程式行為。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="1e7f4-121">**跨原始資源分享 (用於存放庫 API 的 CORS) 支援**</span><span class="sxs-lookup"><span data-stu-id="1e7f4-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="1e7f4-122">存放庫 API 支援跨原始資源分享 (CORS) 。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="1e7f4-123">CORS 是一種 HTTP 功能，可讓在一個網域下執行的 web 應用程式存取另一個網域中的資源。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="1e7f4-124">網頁瀏覽器會執行稱為 [相同原始來源原則](https://www.w3.org/Security/wiki/Same_Origin_Policy) 的安全性限制，以防止網頁撥打不同網域中的 APIs。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="1e7f4-125">CORS 提供一種安全的方法，可讓一個網域 (原始網域) 呼叫另一個網域中的 APIs。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="1e7f4-126">請參閱 [cors 規格](https://www.w3.org/TR/cors/) 以取得 cors 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="1e7f4-127">**啟用存放庫 API 的 CORS**</span><span class="sxs-lookup"><span data-stu-id="1e7f4-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="1e7f4-128">以下是存放庫 API web.config 的摘選，顯示 corsTrustedOrigin 應用程式設定中所列的兩個網域。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="1e7f4-129">從這些伺服器載入之腳本所進行的所有要求，都是由存放庫 API 所信任。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="1e7f4-130">如果有任何) ，請記得包含確切的通訊協定、主機名稱和埠 (。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="1e7f4-131">請勿將任何正斜線字元 (/) 在結尾。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="1e7f4-132">您可以指定多個專案，並以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="1e7f4-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


