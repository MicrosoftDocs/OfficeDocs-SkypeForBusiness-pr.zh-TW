---
title: 取得子項目
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：瞭解 Sub-Items 作業，也就是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832503"
---
# <a name="get-sub-items"></a><span data-ttu-id="8f0f8-105">取得子項目</span><span class="sxs-lookup"><span data-stu-id="8f0f8-105">Get Sub-Items</span></span>
 
<span data-ttu-id="8f0f8-106">**摘要：** 深入瞭解 Sub-Items 作業，也就是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="8f0f8-107">專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8f0f8-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8f0f8-109">Get Sub-Items 作業是用於通話品質儀表板之存放庫 API 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="8f0f8-110">取得子項目</span><span class="sxs-lookup"><span data-stu-id="8f0f8-110">Get Sub-Items</span></span>

<span data-ttu-id="8f0f8-111">Get Sub-Items 會傳回特定專案的子專案。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="8f0f8-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="8f0f8-112">**Method**</span></span>|<span data-ttu-id="8f0f8-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="8f0f8-113">**Request URI**</span></span>|<span data-ttu-id="8f0f8-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="8f0f8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f0f8-115">GET</span><span class="sxs-lookup"><span data-stu-id="8f0f8-115">GET</span></span>  <br/> |<span data-ttu-id="8f0f8-116">HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="8f0f8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="8f0f8-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="8f0f8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8f0f8-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8f0f8-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8f0f8-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8f0f8-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8f0f8-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="8f0f8-123">如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="8f0f8-124">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8f0f8-125">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8f0f8-126">會傳回 Item 物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-126">An array of Item object is returned.</span></span> 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="8f0f8-127">Sub-Items 作業所傳回的 Item 物件只包含下列三個欄位。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="8f0f8-128">*itemId*  -專案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="8f0f8-129">*userId*  -擁有此專案之使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="8f0f8-130">*type*  -內容類型。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-130">*type*  - The type of the content.</span></span> <span data-ttu-id="8f0f8-131">此欄位是由應用程式所設定。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8f0f8-132">`Content` 和 `subItems` 欄位不會包含在回應中，以減少透過網路傳輸的資料量。</span><span class="sxs-lookup"><span data-stu-id="8f0f8-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

