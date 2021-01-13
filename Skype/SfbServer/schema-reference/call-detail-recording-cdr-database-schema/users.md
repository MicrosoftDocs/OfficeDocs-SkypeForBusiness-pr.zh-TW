---
title: Users 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 表格是支援表格。 資料表中的每一筆記錄都儲存在具有資料庫中記錄的通話或會話中的一個使用者相關資訊。'
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831613"
---
# <a name="users-table"></a><span data-ttu-id="348b6-104">Users 表格</span><span class="sxs-lookup"><span data-stu-id="348b6-104">Users table</span></span>
 
<span data-ttu-id="348b6-105">[使用者] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="348b6-105">The Users table is a supporting table.</span></span> <span data-ttu-id="348b6-106">資料表中的每一筆記錄都儲存在具有資料庫中記錄的通話或會話中的一個使用者相關資訊。</span><span class="sxs-lookup"><span data-stu-id="348b6-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="348b6-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="348b6-107">**Column**</span></span>|<span data-ttu-id="348b6-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="348b6-108">**Data Type**</span></span>|<span data-ttu-id="348b6-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="348b6-109">**Key/Index**</span></span>|<span data-ttu-id="348b6-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="348b6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="348b6-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="348b6-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="348b6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="348b6-112">datetime</span></span>  <br/> ||<span data-ttu-id="348b6-113">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="348b6-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="348b6-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="348b6-114">**UserId**</span></span> <br/> |<span data-ttu-id="348b6-115">int</span><span class="sxs-lookup"><span data-stu-id="348b6-115">int</span></span>  <br/> |<span data-ttu-id="348b6-116">主要</span><span class="sxs-lookup"><span data-stu-id="348b6-116">Primary</span></span>  <br/> |<span data-ttu-id="348b6-117">用於識別此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="348b6-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="348b6-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="348b6-118">**UserUri**</span></span> <br/> |<span data-ttu-id="348b6-119">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="348b6-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="348b6-120">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="348b6-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="348b6-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="348b6-121">**TenantId**</span></span> <br/> |<span data-ttu-id="348b6-122">int</span><span class="sxs-lookup"><span data-stu-id="348b6-122">int</span></span>  <br/> |<span data-ttu-id="348b6-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="348b6-123">Foreign</span></span>  <br/> |<span data-ttu-id="348b6-124">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="348b6-124">This user's Tenant ID.</span></span> <span data-ttu-id="348b6-125">如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。</span><span class="sxs-lookup"><span data-stu-id="348b6-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="348b6-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="348b6-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="348b6-127">int</span><span class="sxs-lookup"><span data-stu-id="348b6-127">int</span></span>  <br/> |<span data-ttu-id="348b6-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="348b6-128">Foreign</span></span>  <br/> |<span data-ttu-id="348b6-129">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="348b6-129">This user's URI type.</span></span> <span data-ttu-id="348b6-130">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="348b6-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

