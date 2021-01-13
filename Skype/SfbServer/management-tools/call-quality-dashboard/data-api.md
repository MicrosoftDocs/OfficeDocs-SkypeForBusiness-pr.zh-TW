---
title: 商務用 Skype Server 中的通話品質儀表板 (CQD) 的資料 API
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 摘要：瞭解通話品質儀表板的資料 API。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832693"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="57426-104">商務用 Skype Server 中的通話品質儀表板 (CQD) 的資料 API</span><span class="sxs-lookup"><span data-stu-id="57426-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="57426-105">**摘要：** 深入瞭解通話品質儀表板的資料 API。</span><span class="sxs-lookup"><span data-stu-id="57426-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="57426-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="57426-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="57426-107">Data API 為商務用 Skype 伺服器提供通話品質儀表板的程式設計存取。</span><span class="sxs-lookup"><span data-stu-id="57426-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="57426-108">通話品質儀表板的資料 API</span><span class="sxs-lookup"><span data-stu-id="57426-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="57426-109">Data API 提供查詢介面給 QoE Cube。</span><span class="sxs-lookup"><span data-stu-id="57426-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="57426-110">Data API 是用於使用多維度資料庫的 REST API，它會根據指定的維度和篩選，提供匯總的 QoE 度量。</span><span class="sxs-lookup"><span data-stu-id="57426-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="57426-111">其餘的作業包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="57426-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="57426-112">**作業**</span><span class="sxs-lookup"><span data-stu-id="57426-112">**Operation**</span></span>|<span data-ttu-id="57426-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="57426-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="57426-114">取得 Cube</span><span class="sxs-lookup"><span data-stu-id="57426-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="57426-115">取得可用的維度和度量清單。</span><span class="sxs-lookup"><span data-stu-id="57426-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="57426-116">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="57426-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="57426-117">取得維度成員操作傳回特定維度的成員清單。</span><span class="sxs-lookup"><span data-stu-id="57426-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="57426-118">它也可讓您篩選成員清單並取得子集，以降低線路傳輸成本。</span><span class="sxs-lookup"><span data-stu-id="57426-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="57426-119">執行查詢</span><span class="sxs-lookup"><span data-stu-id="57426-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="57426-120">執行查詢作業可讓您根據指定的維度、度量及篩選，對 cube 執行查詢，並傳回資料。</span><span class="sxs-lookup"><span data-stu-id="57426-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="57426-121">清除快取</span><span class="sxs-lookup"><span data-stu-id="57426-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="57426-122">清除快取作業會在伺服器上刪除查詢和資料的快取。</span><span class="sxs-lookup"><span data-stu-id="57426-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="57426-123">這將會重設快取，我們會在新的要求之後，從 QoE Cube 取得新的資料。</span><span class="sxs-lookup"><span data-stu-id="57426-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="57426-124">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="57426-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="57426-125">取得整合記錄作業會傳回描述 QoE Cube 處理中之活動的記錄專案清單。</span><span class="sxs-lookup"><span data-stu-id="57426-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="57426-126">取得上次整合資料</span><span class="sxs-lookup"><span data-stu-id="57426-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="57426-127">取得來自 cube 的最後整合資料。</span><span class="sxs-lookup"><span data-stu-id="57426-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="57426-128">**跨原始資源分享 (對資料 API 的 CORS) 支援**</span><span class="sxs-lookup"><span data-stu-id="57426-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="57426-129">資料 API 支援跨原始資源分享 (CORS) 。</span><span class="sxs-lookup"><span data-stu-id="57426-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="57426-130">CORS 是一種 HTTP 功能，可讓在一個網域下執行的 web 應用程式存取另一個網域中的資源。</span><span class="sxs-lookup"><span data-stu-id="57426-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="57426-131">網頁瀏覽器會執行稱為 [相同原始來源原則](https://www.w3.org/Security/wiki/Same_Origin_Policy) 的安全性限制，以防止網頁撥打不同網域中的 APIs。</span><span class="sxs-lookup"><span data-stu-id="57426-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="57426-132">CORS 提供一種安全的方法，可讓一個網域 (原始網域) 呼叫另一個網域中的 APIs。</span><span class="sxs-lookup"><span data-stu-id="57426-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="57426-133">請參閱 [cors 規格](https://www.w3.org/TR/cors/) 以取得 cors 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="57426-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="57426-134">**啟用資料 API 的 CORS**</span><span class="sxs-lookup"><span data-stu-id="57426-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="57426-135">以下是資料 API web.config 的節選，顯示 corsTrustedOrigin 應用程式設定中所列的兩個網域。</span><span class="sxs-lookup"><span data-stu-id="57426-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="57426-136">從這些伺服器載入之腳本所進行的所有要求，都是由資料 API 所信任。</span><span class="sxs-lookup"><span data-stu-id="57426-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="57426-137">如果有任何) ，請記得包含確切的通訊協定、主機名稱和埠 (。</span><span class="sxs-lookup"><span data-stu-id="57426-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="57426-138">請勿將任何正斜線字元 (/) 在結尾。</span><span class="sxs-lookup"><span data-stu-id="57426-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="57426-139">您可以指定多個專案，並以逗號分隔。</span><span class="sxs-lookup"><span data-stu-id="57426-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


