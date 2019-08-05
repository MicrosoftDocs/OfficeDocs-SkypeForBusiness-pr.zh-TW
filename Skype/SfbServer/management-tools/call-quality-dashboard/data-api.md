---
title: 商務用 Skype Server 中的通話品質儀表板 (CQD) 的資料 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '摘要: 瞭解通話品質儀表板的 Rata API。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: f74f581a3d46ba7cf75daf92df5ade16dab510d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186973"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="fd156-104">商務用 Skype Server 中的通話品質儀表板 (CQD) 的資料 API</span><span class="sxs-lookup"><span data-stu-id="fd156-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="fd156-105">**摘要:** 瞭解通話品質儀表板的 Rata API。</span><span class="sxs-lookup"><span data-stu-id="fd156-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="fd156-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="fd156-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fd156-107">資料 API 提供以程式設計方式存取商務用 Skype Server 的通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="fd156-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="fd156-108">通話品質儀表板的資料 API</span><span class="sxs-lookup"><span data-stu-id="fd156-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="fd156-109">資料 API 提供 QoE Cube 的查詢介面。</span><span class="sxs-lookup"><span data-stu-id="fd156-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="fd156-110">資料 API 是一個 REST API, 可讓您使用多維度的資料庫, 這些資料庫提供根據指定的維度與篩選的匯總 QoE 指標。</span><span class="sxs-lookup"><span data-stu-id="fd156-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="fd156-111">其餘的作業包括在下表中。</span><span class="sxs-lookup"><span data-stu-id="fd156-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="fd156-112">**一道**</span><span class="sxs-lookup"><span data-stu-id="fd156-112">**Operation**</span></span>|<span data-ttu-id="fd156-113">**說明**</span><span class="sxs-lookup"><span data-stu-id="fd156-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fd156-114">取得立方體</span><span class="sxs-lookup"><span data-stu-id="fd156-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="fd156-115">取得可用尺寸與測量的清單。</span><span class="sxs-lookup"><span data-stu-id="fd156-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="fd156-116">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="fd156-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="fd156-117">[取得維度成員] 操作會傳回特定維度之成員的清單。</span><span class="sxs-lookup"><span data-stu-id="fd156-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="fd156-118">它也提供篩選成員清單及取得子集的功能, 以減少線路傳輸成本。</span><span class="sxs-lookup"><span data-stu-id="fd156-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="fd156-119">執行查詢</span><span class="sxs-lookup"><span data-stu-id="fd156-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="fd156-120">[執行查詢] 作業能根據指定的尺寸、測量及篩選, 在立方體上執行查詢, 並傳回資料。</span><span class="sxs-lookup"><span data-stu-id="fd156-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="fd156-121">清除快取</span><span class="sxs-lookup"><span data-stu-id="fd156-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="fd156-122">[清除快取] 操作會刪除查詢和資料在伺服器上的快取。</span><span class="sxs-lookup"><span data-stu-id="fd156-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="fd156-123">這將會重設快取, 然後從 QoE Cube 取得新的資料, 之後就會出現新的要求。</span><span class="sxs-lookup"><span data-stu-id="fd156-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="fd156-124">取得整合記錄</span><span class="sxs-lookup"><span data-stu-id="fd156-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="fd156-125">取得整合記錄作業會傳回說明 QoE Cube 處理中之活動的記錄專案清單。</span><span class="sxs-lookup"><span data-stu-id="fd156-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="fd156-126">取得上次整合資料</span><span class="sxs-lookup"><span data-stu-id="fd156-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="fd156-127">取得來自多維資料集的最後一個整合資料。</span><span class="sxs-lookup"><span data-stu-id="fd156-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="fd156-128">**資料 API 的跨來源資源分享 (CORS) 支援**</span><span class="sxs-lookup"><span data-stu-id="fd156-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="fd156-129">資料 API 支援跨來源資源分享 (CORS)。</span><span class="sxs-lookup"><span data-stu-id="fd156-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="fd156-130">CORS 是一項 HTTP 功能, 可讓在一個網域下執行的 web 應用程式存取其他網域中的資源。</span><span class="sxs-lookup"><span data-stu-id="fd156-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="fd156-131">網頁瀏覽器會執行稱為相同來源[原則](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制, 以避免網頁在其他網域中呼叫 api。</span><span class="sxs-lookup"><span data-stu-id="fd156-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="fd156-132">CORS 提供安全的方法, 可讓一個網域 (原始網域) 呼叫另一個網域中的 Api。</span><span class="sxs-lookup"><span data-stu-id="fd156-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="fd156-133">如需 CORS 的詳細資料, 請參閱[CORS 規格](https://www.w3.org/TR/cors/)。</span><span class="sxs-lookup"><span data-stu-id="fd156-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="fd156-134">**啟用資料 API 的 CORS**</span><span class="sxs-lookup"><span data-stu-id="fd156-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="fd156-135">下列是資料 API web.config 的節選, 顯示兩個網域列在 corsTrustedOrigin 應用程式設定中。</span><span class="sxs-lookup"><span data-stu-id="fd156-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="fd156-136">從這些伺服器載入之腳本所進行的所有要求, 都受資料 API 信任。</span><span class="sxs-lookup"><span data-stu-id="fd156-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="fd156-137">請記得包含確切的通訊協定、主機名稱和埠 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="fd156-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="fd156-138">不要將任何正斜線字元 (/) 放在結尾處。</span><span class="sxs-lookup"><span data-stu-id="fd156-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="fd156-139">您可以使用逗號分隔來指定多個專案。</span><span class="sxs-lookup"><span data-stu-id="fd156-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


