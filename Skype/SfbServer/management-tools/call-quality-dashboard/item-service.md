---
title: 通話品質儀表板 (CQD) 的專案服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '摘要: 瞭解 [通話品質] 儀表板的 [知識庫 API] 中的專案服務。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186880"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="99278-104">通話品質儀表板 (CQD) 的專案服務</span><span class="sxs-lookup"><span data-stu-id="99278-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="99278-105">**摘要:** 瞭解 [通話品質] 儀表板的 [知識庫 API] 中的專案服務。</span><span class="sxs-lookup"><span data-stu-id="99278-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="99278-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="99278-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="99278-107">專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="99278-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="99278-108">專案服務</span><span class="sxs-lookup"><span data-stu-id="99278-108">Item Service</span></span>

<span data-ttu-id="99278-109">知識庫 API 提供簡單的內容管理服務 (稱為「專案服務」), 可用來儲存任何應用程式定義的內容供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="99278-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="99278-110">系統內容是由系統使用者所擁有, 且由所有擁有唯讀存取權的使用者共用。</span><span class="sxs-lookup"><span data-stu-id="99278-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="99278-111">專用的使用者內容是由一般使用者所擁有, 而且只有擁有者可以修改或刪除, 但所有使用者仍能以唯讀方式存取。</span><span class="sxs-lookup"><span data-stu-id="99278-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99278-112">這個 API 檔涵蓋知識庫 API 的唯讀作業。</span><span class="sxs-lookup"><span data-stu-id="99278-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="99278-113">通話品質儀表板將報表和查詢儲存為知識庫資料庫中的專案。</span><span class="sxs-lookup"><span data-stu-id="99278-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="99278-114">專案可以有選用的子專案, 而 [通話品質儀表板] 會使用 [子專案] 功能來組織階層結構中的報告和查詢。</span><span class="sxs-lookup"><span data-stu-id="99278-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="99278-115">專案服務包含下列概念:</span><span class="sxs-lookup"><span data-stu-id="99278-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="99278-116">**專案**-知識庫的基本元素。</span><span class="sxs-lookup"><span data-stu-id="99278-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="99278-117">每個專案都是由恰好一個使用者所擁有。</span><span class="sxs-lookup"><span data-stu-id="99278-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="99278-118">**子專案**-知識庫的基本組織結構。</span><span class="sxs-lookup"><span data-stu-id="99278-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="99278-119">專案可以有零個、一或多個從屬專案。</span><span class="sxs-lookup"><span data-stu-id="99278-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="99278-120">**專案上級**(專案的清單), 從最上方的專案開始, 這是使用者的預設專案, 會引出至指定專案。</span><span class="sxs-lookup"><span data-stu-id="99278-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="99278-121">**專案內容**-儲存在專案中的特定應用程式內容。</span><span class="sxs-lookup"><span data-stu-id="99278-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="99278-122">[通話品質儀表板] 會將報表和查詢的 JSON 表示形式儲存在內容中。</span><span class="sxs-lookup"><span data-stu-id="99278-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="99278-123">其餘的作業包括在下表中。</span><span class="sxs-lookup"><span data-stu-id="99278-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="99278-124">**一道**</span><span class="sxs-lookup"><span data-stu-id="99278-124">**Operation**</span></span>|<span data-ttu-id="99278-125">**說明**</span><span class="sxs-lookup"><span data-stu-id="99278-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="99278-126">取得專案</span><span class="sxs-lookup"><span data-stu-id="99278-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="99278-127">[取得專案] 會傳回知識庫中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="99278-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="99278-128">取得專案</span><span class="sxs-lookup"><span data-stu-id="99278-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="99278-129">[取得專案] 會傳回特定專案。</span><span class="sxs-lookup"><span data-stu-id="99278-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="99278-130">取得子專案</span><span class="sxs-lookup"><span data-stu-id="99278-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="99278-131">[取得子專案] 會傳回特定專案的子專案。</span><span class="sxs-lookup"><span data-stu-id="99278-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="99278-132">取得專案上級</span><span class="sxs-lookup"><span data-stu-id="99278-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="99278-133">取得專案上級會傳回特定專案的上級。</span><span class="sxs-lookup"><span data-stu-id="99278-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="99278-134">更新專案</span><span class="sxs-lookup"><span data-stu-id="99278-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="99278-135">更新存儲庫中的特定專案。</span><span class="sxs-lookup"><span data-stu-id="99278-135">Update a specific item in the repository.</span></span>  <br/> |
   

