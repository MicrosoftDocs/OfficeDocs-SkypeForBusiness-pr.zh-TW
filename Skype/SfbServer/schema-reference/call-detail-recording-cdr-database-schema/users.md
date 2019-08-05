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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: '[使用者] 資料表是支援表格。 資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。'
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192779"
---
# <a name="users-table"></a><span data-ttu-id="9bb4b-104">Users 表格</span><span class="sxs-lookup"><span data-stu-id="9bb4b-104">Users table</span></span>
 
<span data-ttu-id="9bb4b-105">[使用者] 資料表是支援表格。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-105">The Users table is a supporting table.</span></span> <span data-ttu-id="9bb4b-106">資料表中的每一筆記錄都儲存有關在資料庫中有記錄的通話或會話中涉及之一個使用者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="9bb4b-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-107">**Column**</span></span>|<span data-ttu-id="9bb4b-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-108">**Data Type**</span></span>|<span data-ttu-id="9bb4b-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-109">**Key/Index**</span></span>|<span data-ttu-id="9bb4b-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9bb4b-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9bb4b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9bb4b-112">datetime</span></span>  <br/> ||<span data-ttu-id="9bb4b-113">內部使用的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="9bb4b-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-114">**UserId**</span></span> <br/> |<span data-ttu-id="9bb4b-115">int</span><span class="sxs-lookup"><span data-stu-id="9bb4b-115">int</span></span>  <br/> |<span data-ttu-id="9bb4b-116">首選</span><span class="sxs-lookup"><span data-stu-id="9bb4b-116">Primary</span></span>  <br/> |<span data-ttu-id="9bb4b-117">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="9bb4b-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-118">**UserUri**</span></span> <br/> |<span data-ttu-id="9bb4b-119">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bb4b-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="9bb4b-120">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="9bb4b-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-121">**TenantId**</span></span> <br/> |<span data-ttu-id="9bb4b-122">int</span><span class="sxs-lookup"><span data-stu-id="9bb4b-122">int</span></span>  <br/> |<span data-ttu-id="9bb4b-123">外</span><span class="sxs-lookup"><span data-stu-id="9bb4b-123">Foreign</span></span>  <br/> |<span data-ttu-id="9bb4b-124">此使用者的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-124">This user's Tenant ID.</span></span> <span data-ttu-id="9bb4b-125">如需詳細資訊, 請參閱[承租人資料表](tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9bb4b-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="9bb4b-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="9bb4b-127">int</span><span class="sxs-lookup"><span data-stu-id="9bb4b-127">int</span></span>  <br/> |<span data-ttu-id="9bb4b-128">外</span><span class="sxs-lookup"><span data-stu-id="9bb4b-128">Foreign</span></span>  <br/> |<span data-ttu-id="9bb4b-129">此使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-129">This user's URI type.</span></span> <span data-ttu-id="9bb4b-130">如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="9bb4b-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

