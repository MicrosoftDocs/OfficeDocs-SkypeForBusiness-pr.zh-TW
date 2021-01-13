---
title: CQD 的使用者服務
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：瞭解使用者服務，它是「呼叫品質」儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803073"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="42943-104">CQD 的使用者服務</span><span class="sxs-lookup"><span data-stu-id="42943-104">User Service for CQD</span></span>
 
<span data-ttu-id="42943-105">**摘要：** 深入瞭解使用者服務，此服務是「呼叫品質」儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="42943-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="42943-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="42943-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="42943-107">使用者服務屬於「呼叫品質」儀表板的存放庫 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="42943-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="42943-108">使用者服務</span><span class="sxs-lookup"><span data-stu-id="42943-108">User Service</span></span>

<span data-ttu-id="42943-109">存放庫 API 提供簡化的使用者管理模型，其中使用者布建 (建立新的使用者帳戶) 為自動和隱含。</span><span class="sxs-lookup"><span data-stu-id="42943-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="42943-110">當使用者第一次對存放庫 API 提出要求時，存放庫便會建立新的使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="42943-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="42943-111">通話品質儀表板也會自動為新使用者建立使用者專用專案。</span><span class="sxs-lookup"><span data-stu-id="42943-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="42943-112">新的使用者專用專案是系統使用者之專案的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="42943-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="42943-113">如此一來，使用者可以立即開始自訂的報表和查詢副本開始進行自訂。</span><span class="sxs-lookup"><span data-stu-id="42943-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="42943-114">使用 [通話品質] 儀表板，使用者可以隨時重設他們的專屬專案。</span><span class="sxs-lookup"><span data-stu-id="42943-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="42943-115">**特殊使用者 IDs**</span><span class="sxs-lookup"><span data-stu-id="42943-115">**Special User IDs**</span></span>
  
<span data-ttu-id="42943-116">存放庫 API 包括 REST API URIs，需要整數值來指定特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="42943-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="42943-117">範例：  `https://<portal>/QoERepositoryService/repository/user/{userId}` 。</span><span class="sxs-lookup"><span data-stu-id="42943-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="42943-118">在這裡，{userId} 應該以整數值取代，例如0，1，etc。</span><span class="sxs-lookup"><span data-stu-id="42943-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="42943-119">此外，知識庫 API 會在 URIs 中接受兩個特殊使用者 IDs {userId}。</span><span class="sxs-lookup"><span data-stu-id="42943-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="42943-120">*default*  -代表目前與 API 互動的使用者。</span><span class="sxs-lookup"><span data-stu-id="42943-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="42943-121">這可讓應用程式存取目前使用者的內容，而不需要追蹤實際的使用者識別碼值。</span><span class="sxs-lookup"><span data-stu-id="42943-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="42943-122">範例： `https://<portal>/QoERepositoryService/repository/user/default` 。</span><span class="sxs-lookup"><span data-stu-id="42943-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="42943-123">*system*  -代表系統使用者。</span><span class="sxs-lookup"><span data-stu-id="42943-123">*system*  - represents the system user.</span></span> <span data-ttu-id="42943-124">這可讓應用程式在不知道實際使用者識別碼值的情況下，存取系統使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="42943-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="42943-125">範例： `https://<portal>/QoERepositoryService/repository/user/system` 。</span><span class="sxs-lookup"><span data-stu-id="42943-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="42943-126">除非另有說明，否則可以在 URIs {userId} 中使用特殊使用者 IDs。</span><span class="sxs-lookup"><span data-stu-id="42943-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="42943-127">其餘的作業包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="42943-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="42943-128">**作業**</span><span class="sxs-lookup"><span data-stu-id="42943-128">**Operation**</span></span>|<span data-ttu-id="42943-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="42943-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="42943-130">取得使用者</span><span class="sxs-lookup"><span data-stu-id="42943-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="42943-131">傳回存放庫中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="42943-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="42943-132">取得使用者</span><span class="sxs-lookup"><span data-stu-id="42943-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="42943-133">傳回使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="42943-133">Returns a user record.</span></span>  <br/> |
   

