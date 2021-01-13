---
title: 取得項目
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：瞭解 [取得專案] 作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832563"
---
# <a name="get-item"></a><span data-ttu-id="78273-105">取得項目</span><span class="sxs-lookup"><span data-stu-id="78273-105">Get Item</span></span>
 
<span data-ttu-id="78273-106">**摘要：** 瞭解 [取得專案] 作業，這是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="78273-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="78273-107">專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="78273-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="78273-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="78273-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="78273-109">[取得專案] 作業是「用於通話品質」儀表板之 [存放庫 API] 中專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="78273-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="78273-110">取得項目</span><span class="sxs-lookup"><span data-stu-id="78273-110">Get Item</span></span>

<span data-ttu-id="78273-111">取得專案會傳回存放庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="78273-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="78273-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="78273-112">**Method**</span></span>|<span data-ttu-id="78273-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="78273-113">**Request URI**</span></span>|<span data-ttu-id="78273-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="78273-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78273-115">GET</span><span class="sxs-lookup"><span data-stu-id="78273-115">GET</span></span>  <br/> |<span data-ttu-id="78273-116">HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="78273-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="78273-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="78273-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="78273-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="78273-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="78273-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="78273-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="78273-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="78273-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="78273-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="78273-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="78273-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="78273-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="78273-123">如果找不到指定的專案識別碼，它會傳回狀態碼 404 (找不到) 。</span><span class="sxs-lookup"><span data-stu-id="78273-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="78273-124">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="78273-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="78273-125">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="78273-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="78273-126">*itemId*  -專案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="78273-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="78273-127">*userId*  -擁有此專案之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="78273-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="78273-128">*content*  -應用程式特定的內容。</span><span class="sxs-lookup"><span data-stu-id="78273-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="78273-129">*type*  -內容類型。</span><span class="sxs-lookup"><span data-stu-id="78273-129">*type*  - The type of the content.</span></span> <span data-ttu-id="78273-130">此欄位是由應用程式所設定。</span><span class="sxs-lookup"><span data-stu-id="78273-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="78273-131">*subItemIds*  -子專案的 IDs （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="78273-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="78273-132">這是用來儲存通話的「取得 Sub-Items 運作的短路。</span><span class="sxs-lookup"><span data-stu-id="78273-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="78273-133">應用程式也可以使用 [取得 Sub-Items] 作業取得相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="78273-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

