---
title: 取得項目上階
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：瞭解屬於專案服務的「取得專案祖先」作業。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832573"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="88f3a-105">取得項目上階</span><span class="sxs-lookup"><span data-stu-id="88f3a-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="88f3a-106">**摘要：** 瞭解 [取得專案] 上級作業，這是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="88f3a-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="88f3a-107">專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="88f3a-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="88f3a-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="88f3a-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="88f3a-109">「取得專案祖先」作業是存放庫 API for a Call Quality 儀表板的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="88f3a-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="88f3a-110">取得項目上階</span><span class="sxs-lookup"><span data-stu-id="88f3a-110">Get Item Ancestors</span></span>

<span data-ttu-id="88f3a-111">取得專案祖先會傳回存放庫中的特定專案祖先。</span><span class="sxs-lookup"><span data-stu-id="88f3a-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="88f3a-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="88f3a-112">**Method**</span></span>|<span data-ttu-id="88f3a-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="88f3a-113">**Request URI**</span></span>|<span data-ttu-id="88f3a-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="88f3a-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88f3a-115">GET</span><span class="sxs-lookup"><span data-stu-id="88f3a-115">GET</span></span>  <br/> |<span data-ttu-id="88f3a-116">HTTPs:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="88f3a-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="88f3a-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="88f3a-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="88f3a-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="88f3a-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="88f3a-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="88f3a-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="88f3a-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="88f3a-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="88f3a-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="88f3a-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="88f3a-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="88f3a-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="88f3a-123">如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。</span><span class="sxs-lookup"><span data-stu-id="88f3a-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="88f3a-124">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="88f3a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="88f3a-125">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="88f3a-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="88f3a-126">*Item1*  -專案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="88f3a-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="88f3a-127">*Item2*  -深度是指從專案的距離。</span><span class="sxs-lookup"><span data-stu-id="88f3a-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="88f3a-128">0是直接父項。</span><span class="sxs-lookup"><span data-stu-id="88f3a-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="88f3a-129">*Item3*  -專案的標題。</span><span class="sxs-lookup"><span data-stu-id="88f3a-129">*Item3*  - Title of the item.</span></span>
  

