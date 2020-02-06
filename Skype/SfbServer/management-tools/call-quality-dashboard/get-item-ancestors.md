---
title: 取得項目上階
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 摘要：瞭解 [取得專案上級] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 7beaffbb670f664ec7181482dbceb120a8b7d9e8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816802"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="8d931-105">取得項目上階</span><span class="sxs-lookup"><span data-stu-id="8d931-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="8d931-106">**摘要：** 瞭解 [取得專案上級] 作業，該作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d931-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="8d931-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d931-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8d931-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="8d931-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8d931-109">[取得專案上級] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d931-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="8d931-110">取得項目上階</span><span class="sxs-lookup"><span data-stu-id="8d931-110">Get Item Ancestors</span></span>

<span data-ttu-id="8d931-111">取得專案上級會傳回知識庫中的特定專案上級。</span><span class="sxs-lookup"><span data-stu-id="8d931-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="8d931-112">**法**</span><span class="sxs-lookup"><span data-stu-id="8d931-112">**Method**</span></span>|<span data-ttu-id="8d931-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="8d931-113">**Request URI**</span></span>|<span data-ttu-id="8d931-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="8d931-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8d931-115">獲取</span><span class="sxs-lookup"><span data-stu-id="8d931-115">GET</span></span>  <br/> |<span data-ttu-id="8d931-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="8d931-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="8d931-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="8d931-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8d931-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="8d931-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8d931-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8d931-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8d931-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="8d931-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8d931-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8d931-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8d931-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="8d931-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="8d931-123">如果找不到指定的使用者識別碼，則會傳回狀態碼404（找不到）。</span><span class="sxs-lookup"><span data-stu-id="8d931-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="8d931-124">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8d931-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8d931-125">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="8d931-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="8d931-126">*Item1* -專案識別碼。</span><span class="sxs-lookup"><span data-stu-id="8d931-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="8d931-127">*Item2* -深度是專案的距離。</span><span class="sxs-lookup"><span data-stu-id="8d931-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="8d931-128">0是直接父項。</span><span class="sxs-lookup"><span data-stu-id="8d931-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="8d931-129">*Item3* -專案標題。</span><span class="sxs-lookup"><span data-stu-id="8d931-129">*Item3*  - Title of the item.</span></span>
  

