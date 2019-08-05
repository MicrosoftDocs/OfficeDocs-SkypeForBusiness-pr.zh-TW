---
title: 取得使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: '摘要: 瞭解 [取得使用者] 作業 (這是使用者服務的一部分)。 使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186886"
---
# <a name="get-users"></a><span data-ttu-id="e5fee-105">取得使用者</span><span class="sxs-lookup"><span data-stu-id="e5fee-105">Get Users</span></span>
 
<span data-ttu-id="e5fee-106">**摘要:** 瞭解 [取得使用者] 作業, 這是使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5fee-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="e5fee-107">使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5fee-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e5fee-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="e5fee-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e5fee-109">[取得使用者] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="e5fee-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="e5fee-110">取得使用者</span><span class="sxs-lookup"><span data-stu-id="e5fee-110">Get Users</span></span>

<span data-ttu-id="e5fee-111">[取得使用者] 會傳回文件庫中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="e5fee-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="e5fee-112">**法**</span><span class="sxs-lookup"><span data-stu-id="e5fee-112">**Method**</span></span>|<span data-ttu-id="e5fee-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="e5fee-113">**Request URI**</span></span>|<span data-ttu-id="e5fee-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="e5fee-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5fee-115">獲取</span><span class="sxs-lookup"><span data-stu-id="e5fee-115">GET</span></span>  <br/> |<span data-ttu-id="e5fee-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="e5fee-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="e5fee-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="e5fee-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e5fee-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="e5fee-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e5fee-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="e5fee-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e5fee-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="e5fee-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e5fee-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="e5fee-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e5fee-122">**狀態碼**-成功的操作會傳回狀態碼 200 (確定)。</span><span class="sxs-lookup"><span data-stu-id="e5fee-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="e5fee-123">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="e5fee-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e5fee-124">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="e5fee-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5fee-125">傳回使用者物件陣列。</span><span class="sxs-lookup"><span data-stu-id="e5fee-125">An array of User objects is returned.</span></span> <span data-ttu-id="e5fee-126">如需使用者物件的詳細資訊, 請參閱取得使用者。</span><span class="sxs-lookup"><span data-stu-id="e5fee-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


