---
title: CQD 的使用者服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 摘要：瞭解使用者服務，這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816652"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="ad163-104">CQD 的使用者服務</span><span class="sxs-lookup"><span data-stu-id="ad163-104">User Service for CQD</span></span>
 
<span data-ttu-id="ad163-105">**摘要：** 瞭解使用者服務，這是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ad163-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ad163-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="ad163-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ad163-107">使用者服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ad163-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="ad163-108">使用者服務</span><span class="sxs-lookup"><span data-stu-id="ad163-108">User Service</span></span>

<span data-ttu-id="ad163-109">[知識庫 API] 提供簡化的使用者管理模型，使用者的提供（建立新的使用者帳戶）是自動及隱式的。</span><span class="sxs-lookup"><span data-stu-id="ad163-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="ad163-110">當使用者第一次針對知識庫 API 提出要求時，知識庫會建立新的使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="ad163-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="ad163-111">[通話品質儀表板] 也會自動為新使用者建立使用者專用專案。</span><span class="sxs-lookup"><span data-stu-id="ad163-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="ad163-112">新的使用者專用專案是系統使用者專案的完整克隆。</span><span class="sxs-lookup"><span data-stu-id="ad163-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="ad163-113">如此一來，使用者就能立即開始自訂其自己的報表和查詢複本。</span><span class="sxs-lookup"><span data-stu-id="ad163-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ad163-114">使用者可以使用 [通話品質儀表板] 隨時重設他們的專用專案。</span><span class="sxs-lookup"><span data-stu-id="ad163-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="ad163-115">**特殊的使用者識別碼**</span><span class="sxs-lookup"><span data-stu-id="ad163-115">**Special User IDs**</span></span>
  
<span data-ttu-id="ad163-116">[知識庫 API] 包含需要整數值來指定特定使用者的 REST API Uri。</span><span class="sxs-lookup"><span data-stu-id="ad163-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="ad163-117">範例： `https://<portal>/QoERepositoryService/repository/user/{userId}`。</span><span class="sxs-lookup"><span data-stu-id="ad163-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="ad163-118">在這裡，{userId} 應該由整數值（例如0、1等）取代。</span><span class="sxs-lookup"><span data-stu-id="ad163-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="ad163-119">此外，知識庫 API 將會在 Uri 中的 {userId} 接受兩個特殊的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad163-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="ad163-120">*預設值*-代表目前與 API 互動的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad163-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="ad163-121">這可讓應用程式存取目前使用者的內容，而不需追蹤實際的 [使用者識別碼] 值。</span><span class="sxs-lookup"><span data-stu-id="ad163-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="ad163-122">範例： `https://<portal>/QoERepositoryService/repository/user/default`。</span><span class="sxs-lookup"><span data-stu-id="ad163-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="ad163-123">*system* -代表系統使用者。</span><span class="sxs-lookup"><span data-stu-id="ad163-123">*system*  - represents the system user.</span></span> <span data-ttu-id="ad163-124">這可讓應用程式無需知道實際的 [使用者識別碼] 值即可存取系統使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="ad163-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="ad163-125">範例： `https://<portal>/QoERepositoryService/repository/user/system`。</span><span class="sxs-lookup"><span data-stu-id="ad163-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="ad163-126">除非另有說明，否則可以在 Uri 中 {userId} 使用特殊的使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad163-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="ad163-127">其餘的作業包括在下表中。</span><span class="sxs-lookup"><span data-stu-id="ad163-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="ad163-128">**一道**</span><span class="sxs-lookup"><span data-stu-id="ad163-128">**Operation**</span></span>|<span data-ttu-id="ad163-129">**說明**</span><span class="sxs-lookup"><span data-stu-id="ad163-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ad163-130">取得使用者</span><span class="sxs-lookup"><span data-stu-id="ad163-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="ad163-131">傳回文件庫中的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="ad163-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="ad163-132">取得使用者</span><span class="sxs-lookup"><span data-stu-id="ad163-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="ad163-133">傳回使用者記錄。</span><span class="sxs-lookup"><span data-stu-id="ad163-133">Returns a user record.</span></span>  <br/> |
   

