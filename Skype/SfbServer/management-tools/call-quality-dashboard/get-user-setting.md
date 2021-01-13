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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：瞭解 [建立使用者] 設定作業，這是使用者設定服務的一部分。 使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832483"
---
# <a name="get-user-setting"></a><span data-ttu-id="fa585-105">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="fa585-105">Get User Setting</span></span>
 
<span data-ttu-id="fa585-106">**摘要：** 深入瞭解 [使用者設定] 服務的 [取得] 使用者設定作業。</span><span class="sxs-lookup"><span data-stu-id="fa585-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="fa585-107">使用者設定服務是用於通話品質儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="fa585-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fa585-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="fa585-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fa585-109">「取得使用者設定」作業是「用於通話品質」儀表板的 [儲存庫 API] 中的 [使用者設定] 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="fa585-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="fa585-110">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="fa585-110">Get User Setting</span></span>

<span data-ttu-id="fa585-111">取得使用者設定會傳回單一使用者設定。</span><span class="sxs-lookup"><span data-stu-id="fa585-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="fa585-112">**方法**</span><span class="sxs-lookup"><span data-stu-id="fa585-112">**Method**</span></span>|<span data-ttu-id="fa585-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="fa585-113">**Request URI**</span></span>|<span data-ttu-id="fa585-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="fa585-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa585-115">GET</span><span class="sxs-lookup"><span data-stu-id="fa585-115">GET</span></span>  <br/> |<span data-ttu-id="fa585-116">HTTPs:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="fa585-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="fa585-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="fa585-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fa585-118">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="fa585-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fa585-119">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="fa585-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fa585-120">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="fa585-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="fa585-121">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="fa585-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fa585-122">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="fa585-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="fa585-123">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="fa585-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="fa585-124">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="fa585-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="fa585-125">*userId*  -使用者的識別碼。</span><span class="sxs-lookup"><span data-stu-id="fa585-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="fa585-126">索引 *鍵* 的設定。</span><span class="sxs-lookup"><span data-stu-id="fa585-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="fa585-127">*值*  -設定值。</span><span class="sxs-lookup"><span data-stu-id="fa585-127">*value*  - Value of the setting.</span></span>
  

