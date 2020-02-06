---
title: Users 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。'
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814801"
---
# <a name="users-table"></a><span data-ttu-id="41593-104">Users 表格</span><span class="sxs-lookup"><span data-stu-id="41593-104">Users table</span></span>
 
<span data-ttu-id="41593-105">[使用者] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="41593-105">The Users table is a supporting table.</span></span> <span data-ttu-id="41593-106">資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="41593-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="41593-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="41593-107">**Column**</span></span>|<span data-ttu-id="41593-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="41593-108">**Data Type**</span></span>|<span data-ttu-id="41593-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="41593-109">**Key/Index**</span></span>|<span data-ttu-id="41593-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="41593-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41593-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="41593-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="41593-112">datetime</span><span class="sxs-lookup"><span data-stu-id="41593-112">datetime</span></span>  <br/> ||<span data-ttu-id="41593-113">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="41593-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="41593-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="41593-114">**UserId**</span></span> <br/> |<span data-ttu-id="41593-115">int</span><span class="sxs-lookup"><span data-stu-id="41593-115">int</span></span>  <br/> |<span data-ttu-id="41593-116">首選</span><span class="sxs-lookup"><span data-stu-id="41593-116">Primary</span></span>  <br/> |<span data-ttu-id="41593-117">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="41593-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="41593-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="41593-118">**UserUri**</span></span> <br/> |<span data-ttu-id="41593-119">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="41593-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="41593-120">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="41593-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="41593-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="41593-121">**TenantId**</span></span> <br/> |<span data-ttu-id="41593-122">int</span><span class="sxs-lookup"><span data-stu-id="41593-122">int</span></span>  <br/> |<span data-ttu-id="41593-123">外</span><span class="sxs-lookup"><span data-stu-id="41593-123">Foreign</span></span>  <br/> |<span data-ttu-id="41593-124">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="41593-124">This user's Tenant ID.</span></span> <span data-ttu-id="41593-125">如需詳細資訊，請參閱[承租人資料表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="41593-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="41593-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="41593-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="41593-127">int</span><span class="sxs-lookup"><span data-stu-id="41593-127">int</span></span>  <br/> |<span data-ttu-id="41593-128">外</span><span class="sxs-lookup"><span data-stu-id="41593-128">Foreign</span></span>  <br/> |<span data-ttu-id="41593-129">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="41593-129">This user's URI type.</span></span> <span data-ttu-id="41593-130">如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="41593-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

