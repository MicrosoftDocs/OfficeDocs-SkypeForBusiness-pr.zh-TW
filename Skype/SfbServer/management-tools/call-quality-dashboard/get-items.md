---
title: 取得項目
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要：瞭解 [取得專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 6345201fe3843e3fe8cf6671f01d2db30fb4e22e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816782"
---
# <a name="get-items"></a><span data-ttu-id="43893-105">取得項目</span><span class="sxs-lookup"><span data-stu-id="43893-105">Get Items</span></span>
 
<span data-ttu-id="43893-106">**摘要：** 瞭解 [取得專案] 作業，該作業是專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="43893-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="43893-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="43893-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="43893-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="43893-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="43893-109">[取得專案] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="43893-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="43893-110">取得項目</span><span class="sxs-lookup"><span data-stu-id="43893-110">Get Items</span></span>

<span data-ttu-id="43893-111">[取得專案] 會傳回知識庫中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="43893-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="43893-112">**法**</span><span class="sxs-lookup"><span data-stu-id="43893-112">**Method**</span></span>|<span data-ttu-id="43893-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="43893-113">**Request URI**</span></span>|<span data-ttu-id="43893-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="43893-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="43893-115">獲取</span><span class="sxs-lookup"><span data-stu-id="43893-115">GET</span></span>  <br/> |<span data-ttu-id="43893-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="43893-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="43893-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="43893-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="43893-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="43893-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="43893-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="43893-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="43893-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="43893-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="43893-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="43893-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="43893-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="43893-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="43893-123">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="43893-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="43893-124">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="43893-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="43893-125">傳回 Item 物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="43893-125">An array of Item objects is returned.</span></span> <span data-ttu-id="43893-126">如需專案物件的詳細資訊，請參閱取得專案。</span><span class="sxs-lookup"><span data-stu-id="43893-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
