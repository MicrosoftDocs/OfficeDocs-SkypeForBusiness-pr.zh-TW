---
title: 取得使用者設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：瞭解 [取得使用者設定] 作業，該操作是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992640"
---
# <a name="get-user-setting"></a><span data-ttu-id="52ec7-105">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="52ec7-105">Get User Setting</span></span>
 
<span data-ttu-id="52ec7-106">**摘要：** 瞭解 [取得使用者設定] 作業，該操作是 [使用者設定] 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="52ec7-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="52ec7-107">[使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="52ec7-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="52ec7-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="52ec7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="52ec7-109">[取得使用者設定] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的 [使用者設定] 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="52ec7-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="52ec7-110">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="52ec7-110">Get User Setting</span></span>

<span data-ttu-id="52ec7-111">[取得使用者] 設定會傳回單一使用者設定。</span><span class="sxs-lookup"><span data-stu-id="52ec7-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="52ec7-112">**法**</span><span class="sxs-lookup"><span data-stu-id="52ec7-112">**Method**</span></span>|<span data-ttu-id="52ec7-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="52ec7-113">**Request URI**</span></span>|<span data-ttu-id="52ec7-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="52ec7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52ec7-115">獲取</span><span class="sxs-lookup"><span data-stu-id="52ec7-115">GET</span></span>  <br/> |<span data-ttu-id="52ec7-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="52ec7-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="52ec7-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="52ec7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="52ec7-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="52ec7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="52ec7-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="52ec7-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="52ec7-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="52ec7-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="52ec7-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="52ec7-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="52ec7-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="52ec7-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="52ec7-123">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="52ec7-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="52ec7-124">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="52ec7-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="52ec7-125">*userId* -使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="52ec7-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="52ec7-126">設定的*索引鍵。*</span><span class="sxs-lookup"><span data-stu-id="52ec7-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="52ec7-127">設定的*value* （值）。</span><span class="sxs-lookup"><span data-stu-id="52ec7-127">*value*  - Value of the setting.</span></span>
  

