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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 摘要：瞭解 [取得使用者設定] 作業，該作業是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992630"
---
# <a name="get-user-settings"></a><span data-ttu-id="9100b-105">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="9100b-105">Get User Settings</span></span>
 
<span data-ttu-id="9100b-106">**摘要：** 瞭解 [取得使用者設定] 作業，該作業是 [使用者設定] 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="9100b-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="9100b-107">[使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9100b-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9100b-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="9100b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9100b-109">[取得使用者設定] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的 [使用者設定] 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="9100b-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="9100b-110">取得使用者設定</span><span class="sxs-lookup"><span data-stu-id="9100b-110">Get User Settings</span></span>

<span data-ttu-id="9100b-111">[取得使用者設定] 會傳回指定使用者的設定清單。</span><span class="sxs-lookup"><span data-stu-id="9100b-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="9100b-112">**法**</span><span class="sxs-lookup"><span data-stu-id="9100b-112">**Method**</span></span>|<span data-ttu-id="9100b-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="9100b-113">**Request URI**</span></span>|<span data-ttu-id="9100b-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="9100b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9100b-115">獲取</span><span class="sxs-lookup"><span data-stu-id="9100b-115">GET</span></span>  <br/> |<span data-ttu-id="9100b-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}/setting</span><span class="sxs-lookup"><span data-stu-id="9100b-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="9100b-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="9100b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9100b-118">**URI 參數**</span><span class="sxs-lookup"><span data-stu-id="9100b-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="9100b-119">*有效*-選用。</span><span class="sxs-lookup"><span data-stu-id="9100b-119">*effective*  - Optional.</span></span> <span data-ttu-id="9100b-120">這個參數只有在使用特殊的使用者識別碼預設值時才適用。</span><span class="sxs-lookup"><span data-stu-id="9100b-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="9100b-121">在其他情況下，它會被忽略。</span><span class="sxs-lookup"><span data-stu-id="9100b-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="9100b-122">`True`傳回有效的使用者設定`false`並只傳回使用者設定（預設）。</span><span class="sxs-lookup"><span data-stu-id="9100b-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="9100b-123">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9100b-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9100b-124">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="9100b-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="9100b-125">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="9100b-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="9100b-126">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="9100b-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="9100b-127">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="9100b-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="9100b-128">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="9100b-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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
