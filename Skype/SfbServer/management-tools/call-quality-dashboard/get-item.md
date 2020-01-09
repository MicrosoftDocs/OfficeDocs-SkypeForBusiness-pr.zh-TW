---
title: 取得項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 摘要：瞭解 [取得專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992670"
---
# <a name="get-item"></a><span data-ttu-id="9c8c5-105">取得項目</span><span class="sxs-lookup"><span data-stu-id="9c8c5-105">Get Item</span></span>
 
<span data-ttu-id="9c8c5-106">**摘要：** 瞭解 [取得專案] 作業，該作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="9c8c5-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9c8c5-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9c8c5-109">[取得專案] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="9c8c5-110">取得項目</span><span class="sxs-lookup"><span data-stu-id="9c8c5-110">Get Item</span></span>

<span data-ttu-id="9c8c5-111">[取得專案] 會傳回文件庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="9c8c5-112">**法**</span><span class="sxs-lookup"><span data-stu-id="9c8c5-112">**Method**</span></span>|<span data-ttu-id="9c8c5-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="9c8c5-113">**Request URI**</span></span>|<span data-ttu-id="9c8c5-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="9c8c5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c8c5-115">獲取</span><span class="sxs-lookup"><span data-stu-id="9c8c5-115">GET</span></span>  <br/> |<span data-ttu-id="9c8c5-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="9c8c5-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="9c8c5-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="9c8c5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9c8c5-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9c8c5-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9c8c5-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9c8c5-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9c8c5-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="9c8c5-123">如果找不到指定的專案識別碼，則會傳回狀態碼404（找不到）。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="9c8c5-124">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9c8c5-125">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="9c8c5-126">*itemId* -專案識別碼。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="9c8c5-127">*userId* -擁有此專案的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="9c8c5-128">*內容*-應用程式特定的內容。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="9c8c5-129">*類型*-內容的類型。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-129">*type*  - The type of the content.</span></span> <span data-ttu-id="9c8c5-130">這個欄位是由應用程式所設定。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="9c8c5-131">*subItemIds* -子專案的識別碼（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="9c8c5-132">這是 [取得子專案] 作業的短路，以儲存通話。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="9c8c5-133">應用程式也可以使用 [取得子專案] 作業來取得相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="9c8c5-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

