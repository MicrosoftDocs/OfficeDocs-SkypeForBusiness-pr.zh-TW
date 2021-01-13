---
title: 取得使用者
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 摘要：瞭解「使用者服務」的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832423"
---
# <a name="get-users"></a><span data-ttu-id="f3ec3-105">取得使用者</span><span class="sxs-lookup"><span data-stu-id="f3ec3-105">Get Users</span></span>
 
<span data-ttu-id="f3ec3-106">**摘要：** 深入瞭解 User Service 的「取得使用者」作業。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="f3ec3-107">使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="f3ec3-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f3ec3-109">「取得使用者」作業是「用於通話品質」儀表板之存放庫 API 中使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="f3ec3-110">取得使用者</span><span class="sxs-lookup"><span data-stu-id="f3ec3-110">Get Users</span></span>

<span data-ttu-id="f3ec3-111">取得使用者會傳回存放庫中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="f3ec3-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="f3ec3-112">**Method**</span></span>|<span data-ttu-id="f3ec3-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="f3ec3-113">**Request URI**</span></span>|<span data-ttu-id="f3ec3-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="f3ec3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3ec3-115">GET</span><span class="sxs-lookup"><span data-stu-id="f3ec3-115">GET</span></span>  <br/> |<span data-ttu-id="f3ec3-116">HTTPs:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="f3ec3-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="f3ec3-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="f3ec3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f3ec3-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f3ec3-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f3ec3-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f3ec3-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f3ec3-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f3ec3-123">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f3ec3-124">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3ec3-125">傳回使用者物件的陣列。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-125">An array of User objects is returned.</span></span> <span data-ttu-id="f3ec3-126">如需使用者物件的詳細資訊，請參閱 Get User。</span><span class="sxs-lookup"><span data-stu-id="f3ec3-126">For details about the User object, see Get User.</span></span> 
  
```json
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


