---
title: 取得子項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 摘要：瞭解 [取得子專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 75fc4fcd331925c224d8dfb72c681d25e3485eb6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992650"
---
# <a name="get-sub-items"></a><span data-ttu-id="6b31b-105">取得子項目</span><span class="sxs-lookup"><span data-stu-id="6b31b-105">Get Sub-Items</span></span>
 
<span data-ttu-id="6b31b-106">**摘要：** 瞭解 [取得子專案] 作業，該作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b31b-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="6b31b-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b31b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6b31b-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="6b31b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6b31b-109">[取得子專案] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b31b-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="6b31b-110">取得子項目</span><span class="sxs-lookup"><span data-stu-id="6b31b-110">Get Sub-Items</span></span>

<span data-ttu-id="6b31b-111">[取得子專案] 會傳回特定專案的子專案。</span><span class="sxs-lookup"><span data-stu-id="6b31b-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="6b31b-112">**法**</span><span class="sxs-lookup"><span data-stu-id="6b31b-112">**Method**</span></span>|<span data-ttu-id="6b31b-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="6b31b-113">**Request URI**</span></span>|<span data-ttu-id="6b31b-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="6b31b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b31b-115">獲取</span><span class="sxs-lookup"><span data-stu-id="6b31b-115">GET</span></span>  <br/> |<span data-ttu-id="6b31b-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="6b31b-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="6b31b-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="6b31b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6b31b-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="6b31b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6b31b-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="6b31b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6b31b-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="6b31b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6b31b-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="6b31b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6b31b-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="6b31b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="6b31b-123">如果找不到指定的使用者識別碼，則會傳回狀態碼404（找不到）。</span><span class="sxs-lookup"><span data-stu-id="6b31b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="6b31b-124">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="6b31b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6b31b-125">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="6b31b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b31b-126">傳回 Item 物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="6b31b-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="6b31b-127">子專案操作所傳回的專案物件只包含下列三個欄位。</span><span class="sxs-lookup"><span data-stu-id="6b31b-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="6b31b-128">*itemId* -專案識別碼。</span><span class="sxs-lookup"><span data-stu-id="6b31b-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="6b31b-129">*userId* -擁有此專案的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6b31b-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="6b31b-130">*類型*-內容的類型。</span><span class="sxs-lookup"><span data-stu-id="6b31b-130">*type*  - The type of the content.</span></span> <span data-ttu-id="6b31b-131">這個欄位是由應用程式所設定。</span><span class="sxs-lookup"><span data-stu-id="6b31b-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6b31b-132">`Content`而且`subItems`欄位不會包含在回應中，以減少網路上傳輸的資料量。</span><span class="sxs-lookup"><span data-stu-id="6b31b-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

