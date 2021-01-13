---
title: 取得使用者設定
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：瞭解「使用者設定」作業，這是使用者設定服務的一部分。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832473"
---
# <a name="get-user-settings"></a><span data-ttu-id="9a0aa-105">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="9a0aa-105">Get User Settings</span></span>
 
<span data-ttu-id="9a0aa-106">**摘要：** 深入瞭解 user settings Service 的「取得使用者設定」作業。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="9a0aa-107">使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9a0aa-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9a0aa-109">「取得使用者設定」作業是用於通話品質儀表板之存放庫 API 中使用者設定服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="9a0aa-110">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="9a0aa-110">Get User Settings</span></span>

<span data-ttu-id="9a0aa-111">取得使用者設定會傳回指定使用者的設定清單。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="9a0aa-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="9a0aa-112">**Method**</span></span>|<span data-ttu-id="9a0aa-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="9a0aa-113">**Request URI**</span></span>|<span data-ttu-id="9a0aa-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="9a0aa-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a0aa-115">GET</span><span class="sxs-lookup"><span data-stu-id="9a0aa-115">GET</span></span>  <br/> |<span data-ttu-id="9a0aa-116">HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="9a0aa-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="9a0aa-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="9a0aa-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9a0aa-118">**URI 參數**</span><span class="sxs-lookup"><span data-stu-id="9a0aa-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="9a0aa-119">*有效*  -選用。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-119">*effective*  - Optional.</span></span> <span data-ttu-id="9a0aa-120">只有在使用特殊使用者識別碼預設值時，此參數才適用。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="9a0aa-121">在其他情況下，它會被忽略。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="9a0aa-122">`True` 會傳回有效的使用者設定，並 `false` 只傳回使用者設定 (預設) 。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="9a0aa-123">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9a0aa-124">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="9a0aa-125">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="9a0aa-126">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="9a0aa-127">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9a0aa-128">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="9a0aa-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
