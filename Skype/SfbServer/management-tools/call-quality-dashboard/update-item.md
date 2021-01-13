---
title: 更新項目
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：瞭解更新專案作業，此作業是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803083"
---
# <a name="update-item"></a><span data-ttu-id="ebeb3-105">更新項目</span><span class="sxs-lookup"><span data-stu-id="ebeb3-105">Update Item</span></span>
 
<span data-ttu-id="ebeb3-106">**摘要：** 瞭解更新專案作業，此作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="ebeb3-107">專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ebeb3-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ebeb3-109">更新專案作業是「用於通話品質」儀表板之存放庫 API 中專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="ebeb3-110">更新項目</span><span class="sxs-lookup"><span data-stu-id="ebeb3-110">Update Item</span></span>

<span data-ttu-id="ebeb3-111">更新專案會更新存放庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="ebeb3-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="ebeb3-112">**Method**</span></span>|<span data-ttu-id="ebeb3-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="ebeb3-113">**Request URI**</span></span>|<span data-ttu-id="ebeb3-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="ebeb3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebeb3-115">把</span><span class="sxs-lookup"><span data-stu-id="ebeb3-115">PUT</span></span>  <br/> |<span data-ttu-id="ebeb3-116">HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="ebeb3-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="ebeb3-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="ebeb3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ebeb3-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ebeb3-119">**要求標頭** -Content-Type： application/json。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="ebeb3-120">**要求主體** -JSON。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="ebeb3-121">範例要求負載：</span><span class="sxs-lookup"><span data-stu-id="ebeb3-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="ebeb3-122">*內容*  要儲存成現有子專案之新內容的 JSON 格式化資料。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="ebeb3-123">從技術上看，存放庫可以儲存任何架構的任何內容，但用於通話品質儀表板時，它應該是報告或查詢。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="ebeb3-124">*類型*  請務必為通話品質儀表板指定 "application/json"。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="ebeb3-125">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ebeb3-126">**狀態碼** -成功的作業會傳回狀態碼 204 (沒有內容) 。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="ebeb3-127">如果找不到指定的專案識別碼，它會傳回狀態碼 404 (找不到) 。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebeb3-128">[無內容] 不是錯誤狀態。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-128">"No Content" is not an error status.</span></span> <span data-ttu-id="ebeb3-129">這表示回應並未傳回本文中的任何專案 (相比之下，200 OK 會傳回 Body) 中的內容。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="ebeb3-130">這表示專案已成功更新。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="ebeb3-131">**回應標頭** -無。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="ebeb3-132">**回應主體** -無。</span><span class="sxs-lookup"><span data-stu-id="ebeb3-132">**Response Body** - None.</span></span>
  

