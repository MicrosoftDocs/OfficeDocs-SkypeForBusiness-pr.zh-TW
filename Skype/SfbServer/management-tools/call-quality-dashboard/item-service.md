---
title: 通話品質儀表板 (CQD) 的專案服務
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要：瞭解專案服務，這是適用于通話品質儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827703"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="b5093-104">通話品質儀表板 (CQD) 的專案服務</span><span class="sxs-lookup"><span data-stu-id="b5093-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="b5093-105">**摘要：** 瞭解專案服務，這是適用于通話品質儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5093-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b5093-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="b5093-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b5093-107">專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5093-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="b5093-108">項目服務</span><span class="sxs-lookup"><span data-stu-id="b5093-108">Item Service</span></span>

<span data-ttu-id="b5093-109">存放庫 API 提供簡單的內容管理服務（稱為「專案服務」），可用來儲存使用者的任何應用程式定義內容。</span><span class="sxs-lookup"><span data-stu-id="b5093-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="b5093-110">系統內容是由系統使用者所擁有，且由具有唯讀許可權的所有使用者共用。</span><span class="sxs-lookup"><span data-stu-id="b5093-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="b5093-111">「專用使用者」內容是由一般使用者所擁有，而且只有擁有者可以修改或刪除它們，但所有使用者仍具有對這些使用者的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="b5093-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5093-112">此 API 檔涵蓋存放庫 API 的唯讀作業。</span><span class="sxs-lookup"><span data-stu-id="b5093-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="b5093-113">通話品質儀表板會將報告和查詢儲存為存放庫資料庫中的專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="b5093-114">專案可以具有選擇性子專案，而通話品質儀表板會使用子專案功能，以階層結構組織報表和查詢。</span><span class="sxs-lookup"><span data-stu-id="b5093-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="b5093-115">專案服務包含下列概念：</span><span class="sxs-lookup"><span data-stu-id="b5093-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="b5093-116">**Item** -存放庫的基本元素。</span><span class="sxs-lookup"><span data-stu-id="b5093-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="b5093-117">每個專案都只歸一個使用者所有。</span><span class="sxs-lookup"><span data-stu-id="b5093-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="b5093-118">**子專案** -存放庫的基本組織結構。</span><span class="sxs-lookup"><span data-stu-id="b5093-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="b5093-119">專案可以有零個、一或多個從屬專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="b5093-120">**專案上級** -從最頂端專案開始的清單，該專案是使用者的預設專案，會前置至指定的專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="b5093-121">**專案內容** -儲存在專案中的應用程式特定內容。</span><span class="sxs-lookup"><span data-stu-id="b5093-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="b5093-122">通話品質儀表板會儲存報告和查詢內容中的 JSON 標記法。</span><span class="sxs-lookup"><span data-stu-id="b5093-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="b5093-123">其餘的作業包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="b5093-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="b5093-124">**作業**</span><span class="sxs-lookup"><span data-stu-id="b5093-124">**Operation**</span></span>|<span data-ttu-id="b5093-125">**描述**</span><span class="sxs-lookup"><span data-stu-id="b5093-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b5093-126">取得項目</span><span class="sxs-lookup"><span data-stu-id="b5093-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="b5093-127">取得專案會傳回存放庫中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="b5093-128">取得項目</span><span class="sxs-lookup"><span data-stu-id="b5093-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="b5093-129">取得專案會傳回特定專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="b5093-130">取得子項目</span><span class="sxs-lookup"><span data-stu-id="b5093-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="b5093-131">Get Sub-Items 會傳回特定專案的子專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="b5093-132">取得項目上階</span><span class="sxs-lookup"><span data-stu-id="b5093-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="b5093-133">取得專案祖先會傳回特定專案的祖先。</span><span class="sxs-lookup"><span data-stu-id="b5093-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="b5093-134">更新項目</span><span class="sxs-lookup"><span data-stu-id="b5093-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="b5093-135">更新存放庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="b5093-135">Update a specific item in the repository.</span></span>  <br/> |
   

