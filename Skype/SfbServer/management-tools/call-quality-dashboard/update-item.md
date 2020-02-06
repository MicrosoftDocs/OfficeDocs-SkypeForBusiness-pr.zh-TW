---
title: 更新項目
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：瞭解 [更新專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816672"
---
# <a name="update-item"></a><span data-ttu-id="f4015-105">更新項目</span><span class="sxs-lookup"><span data-stu-id="f4015-105">Update Item</span></span>
 
<span data-ttu-id="f4015-106">**摘要：** 瞭解 [更新專案] 作業，該作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4015-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="f4015-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4015-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f4015-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="f4015-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f4015-109">[更新專案] 作業是 [通話品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4015-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="f4015-110">更新項目</span><span class="sxs-lookup"><span data-stu-id="f4015-110">Update Item</span></span>

<span data-ttu-id="f4015-111">更新專案會更新儲存庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="f4015-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="f4015-112">**法**</span><span class="sxs-lookup"><span data-stu-id="f4015-112">**Method**</span></span>|<span data-ttu-id="f4015-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="f4015-113">**Request URI**</span></span>|<span data-ttu-id="f4015-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="f4015-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4015-115">將</span><span class="sxs-lookup"><span data-stu-id="f4015-115">PUT</span></span>  <br/> |<span data-ttu-id="f4015-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="f4015-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="f4015-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="f4015-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f4015-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="f4015-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f4015-119">**要求標頭**-內容類型： application/json。</span><span class="sxs-lookup"><span data-stu-id="f4015-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="f4015-120">**要求主體**-JSON。</span><span class="sxs-lookup"><span data-stu-id="f4015-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="f4015-121">範例要求負載：</span><span class="sxs-lookup"><span data-stu-id="f4015-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="f4015-122">*內容* 要儲存為現有子專案的新內容的 JSON 格式資料。</span><span class="sxs-lookup"><span data-stu-id="f4015-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="f4015-123">從技術角度來看，知識庫可以儲存任何架構的內容，但在通話品質儀表板中使用時，必須是報表或查詢。</span><span class="sxs-lookup"><span data-stu-id="f4015-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="f4015-124">*類型* 針對 [通話品質] 儀表板，請務必指定 "application/json"。</span><span class="sxs-lookup"><span data-stu-id="f4015-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="f4015-125">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="f4015-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f4015-126">**狀態碼**-成功的操作會傳回狀態碼204（無內容）。</span><span class="sxs-lookup"><span data-stu-id="f4015-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="f4015-127">如果找不到指定的專案識別碼，則會傳回狀態碼404（找不到）。</span><span class="sxs-lookup"><span data-stu-id="f4015-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f4015-128">"無內容" 不是錯誤狀態。</span><span class="sxs-lookup"><span data-stu-id="f4015-128">"No Content" is not an error status.</span></span> <span data-ttu-id="f4015-129">這表示回應並未傳回本文中的任何內容（相反，200 OK 會傳回本文中的內容）。</span><span class="sxs-lookup"><span data-stu-id="f4015-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="f4015-130">它表示專案已成功更新。</span><span class="sxs-lookup"><span data-stu-id="f4015-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="f4015-131">**回應標題**-無。</span><span class="sxs-lookup"><span data-stu-id="f4015-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="f4015-132">**回應主體**-無。</span><span class="sxs-lookup"><span data-stu-id="f4015-132">**Response Body** - None.</span></span>
  

