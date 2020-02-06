---
title: User 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: '[使用者] 資料表是一個支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者清單。 資料表中的每一筆記錄代表一個使用者。'
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805091"
---
# <a name="user-table"></a><span data-ttu-id="c2496-104">User 表格</span><span class="sxs-lookup"><span data-stu-id="c2496-104">User table</span></span>
 
<span data-ttu-id="c2496-105">[使用者] 資料表是一個支援資料表，可儲存已參與資料庫中記錄之會話的各種使用者清單。</span><span class="sxs-lookup"><span data-stu-id="c2496-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c2496-106">資料表中的每一筆記錄代表一個使用者。</span><span class="sxs-lookup"><span data-stu-id="c2496-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="c2496-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c2496-107">**Column**</span></span>|<span data-ttu-id="c2496-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c2496-108">**Data Type**</span></span>|<span data-ttu-id="c2496-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c2496-109">**Key/Index**</span></span>|<span data-ttu-id="c2496-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c2496-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2496-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="c2496-111">**UserKey**</span></span> <br/> |<span data-ttu-id="c2496-112">int</span><span class="sxs-lookup"><span data-stu-id="c2496-112">int</span></span>  <br/> |<span data-ttu-id="c2496-113">首選</span><span class="sxs-lookup"><span data-stu-id="c2496-113">Primary</span></span>  <br/> |<span data-ttu-id="c2496-114">標識此使用者的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="c2496-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c2496-115">**URL**</span><span class="sxs-lookup"><span data-stu-id="c2496-115">**URI**</span></span> <br/> |<span data-ttu-id="c2496-116">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="c2496-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2496-117">唯一</span><span class="sxs-lookup"><span data-stu-id="c2496-117">Unique</span></span>  <br/> |<span data-ttu-id="c2496-118">URI 字串。</span><span class="sxs-lookup"><span data-stu-id="c2496-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="c2496-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="c2496-119">**URIType**</span></span> <br/> |<span data-ttu-id="c2496-120">int</span><span class="sxs-lookup"><span data-stu-id="c2496-120">int</span></span>  <br/> ||<span data-ttu-id="c2496-121">1是未知的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="c2496-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="c2496-122">2是使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="c2496-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="c2496-123">4是會議 URI。</span><span class="sxs-lookup"><span data-stu-id="c2496-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="c2496-124">8是電話 URI。</span><span class="sxs-lookup"><span data-stu-id="c2496-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="c2496-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="c2496-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="c2496-126">int</span><span class="sxs-lookup"><span data-stu-id="c2496-126">int</span></span>  <br/> |<span data-ttu-id="c2496-127">外</span><span class="sxs-lookup"><span data-stu-id="c2496-127">Foreign</span></span>  <br/> |<span data-ttu-id="c2496-128">使用者的租使用者，從租使用者資料表參考。</span><span class="sxs-lookup"><span data-stu-id="c2496-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="c2496-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="c2496-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="c2496-130">datetime</span><span class="sxs-lookup"><span data-stu-id="c2496-130">datetime</span></span>  <br/> ||<span data-ttu-id="c2496-131">當使用者的語音通話不佳時，請使用最新的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="c2496-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="c2496-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c2496-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c2496-133">datetime</span><span class="sxs-lookup"><span data-stu-id="c2496-133">datetime</span></span>  <br/> ||<span data-ttu-id="c2496-134">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="c2496-134">For internal use only.</span></span>  <br/> |
   

