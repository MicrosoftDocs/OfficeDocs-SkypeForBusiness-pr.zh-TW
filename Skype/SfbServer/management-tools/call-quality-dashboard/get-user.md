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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 摘要：瞭解 [取得使用者] 作業（這是使用者服務的一部分）。 使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992620"
---
# <a name="get-user"></a><span data-ttu-id="0f810-105">取得使用者</span><span class="sxs-lookup"><span data-stu-id="0f810-105">Get User</span></span>
 
<span data-ttu-id="0f810-106">**摘要：** 瞭解 [取得使用者] 作業，該操作是使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="0f810-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="0f810-107">使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="0f810-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0f810-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="0f810-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0f810-109">[取得使用者] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的使用者服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="0f810-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="0f810-110">取得使用者</span><span class="sxs-lookup"><span data-stu-id="0f810-110">Get User</span></span>

<span data-ttu-id="0f810-111">[取得使用者] 會從儲存庫傳回使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="0f810-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="0f810-112">**法**</span><span class="sxs-lookup"><span data-stu-id="0f810-112">**Method**</span></span>|<span data-ttu-id="0f810-113">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="0f810-113">**Request URI**</span></span>|<span data-ttu-id="0f810-114">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="0f810-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f810-115">獲取</span><span class="sxs-lookup"><span data-stu-id="0f810-115">GET</span></span>  <br/> |<span data-ttu-id="0f810-116">HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}</span><span class="sxs-lookup"><span data-stu-id="0f810-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="0f810-117">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="0f810-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0f810-118">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="0f810-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0f810-119">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="0f810-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0f810-120">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="0f810-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0f810-121">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="0f810-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0f810-122">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="0f810-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="0f810-123">如果找不到指定的使用者識別碼，則會傳回狀態碼404（找不到）。</span><span class="sxs-lookup"><span data-stu-id="0f810-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="0f810-124">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="0f810-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0f810-125">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="0f810-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="0f810-126">*userId* -使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="0f810-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="0f810-127">*loginName* -一般使用者的外部使用者識別。</span><span class="sxs-lookup"><span data-stu-id="0f810-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="0f810-128">如果使用 Windows 驗證來驗證使用者，則這可能是使用者的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0f810-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="0f810-129">*defaultItemId* -此使用者的預設專案識別碼。</span><span class="sxs-lookup"><span data-stu-id="0f810-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="0f810-130">預設專案是與使用者相關聯的最上方專案。</span><span class="sxs-lookup"><span data-stu-id="0f810-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="0f810-131">此使用者擁有的所有其他專案都可以從預設專案中流覽。</span><span class="sxs-lookup"><span data-stu-id="0f810-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f810-132">提供`defaultItemId`值以取得專案操作，以取得預設專案的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0f810-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

