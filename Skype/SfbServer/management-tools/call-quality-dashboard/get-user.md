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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：瞭解使用者服務中的「取得使用者」作業。 使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832413"
---
# <a name="get-user"></a><span data-ttu-id="a3975-105">取得使用者</span><span class="sxs-lookup"><span data-stu-id="a3975-105">Get User</span></span>
 
<span data-ttu-id="a3975-106">**摘要：** 深入瞭解 User Service 的「取得使用者」作業。</span><span class="sxs-lookup"><span data-stu-id="a3975-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="a3975-107">使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3975-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a3975-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="a3975-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a3975-109">「取得使用者」作業是「用於通話品質」儀表板之存放庫 API 中使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3975-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="a3975-110">取得使用者</span><span class="sxs-lookup"><span data-stu-id="a3975-110">Get User</span></span>

<span data-ttu-id="a3975-111">[取得] 使用者從存放庫傳回使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="a3975-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="a3975-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="a3975-112">**Method**</span></span>|<span data-ttu-id="a3975-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="a3975-113">**Request URI**</span></span>|<span data-ttu-id="a3975-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="a3975-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3975-115">GET</span><span class="sxs-lookup"><span data-stu-id="a3975-115">GET</span></span>  <br/> |<span data-ttu-id="a3975-116">HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="a3975-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="a3975-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="a3975-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a3975-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="a3975-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a3975-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="a3975-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a3975-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="a3975-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a3975-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="a3975-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a3975-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="a3975-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="a3975-123">如果找不到指定的使用者識別碼，它會傳回狀態碼 404 (找不到) 。</span><span class="sxs-lookup"><span data-stu-id="a3975-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="a3975-124">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="a3975-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a3975-125">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="a3975-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="a3975-126">*userId*  -使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="a3975-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="a3975-127">*loginName*  -一般使用者的外部使用者識別。</span><span class="sxs-lookup"><span data-stu-id="a3975-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="a3975-128">如果使用 Windows 驗證來驗證使用者，則這可能是使用者的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a3975-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="a3975-129">*defaultItemId*  -此使用者之預設專案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="a3975-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="a3975-130">預設專案是與使用者相關聯的最上層專案。</span><span class="sxs-lookup"><span data-stu-id="a3975-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="a3975-131">您可以從預設專案流覽此使用者擁有的所有其他專案。</span><span class="sxs-lookup"><span data-stu-id="a3975-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3975-132">提供  `defaultItemId` 值以取得專案作業，以取得預設專案的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a3975-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

