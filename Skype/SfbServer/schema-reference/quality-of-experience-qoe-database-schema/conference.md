---
title: Conference 表格
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: '[會議] 表格是支援表格。 每個記錄代表一個會議或點對點工作階段。'
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810301"
---
# <a name="conference-table"></a><span data-ttu-id="23ce7-104">Conference 表格</span><span class="sxs-lookup"><span data-stu-id="23ce7-104">Conference table</span></span>
 
<span data-ttu-id="23ce7-105">[會議] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="23ce7-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="23ce7-106">每個記錄代表一個會議或點對點工作階段。</span><span class="sxs-lookup"><span data-stu-id="23ce7-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="23ce7-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="23ce7-107">**Column**</span></span>|<span data-ttu-id="23ce7-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="23ce7-108">**Data Type**</span></span>|<span data-ttu-id="23ce7-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="23ce7-109">**Key/Index**</span></span>|<span data-ttu-id="23ce7-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="23ce7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="23ce7-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="23ce7-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="23ce7-112">int</span><span class="sxs-lookup"><span data-stu-id="23ce7-112">int</span></span>  <br/> |<span data-ttu-id="23ce7-113">首選</span><span class="sxs-lookup"><span data-stu-id="23ce7-113">Primary</span></span>  <br/> |<span data-ttu-id="23ce7-114">標識此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="23ce7-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="23ce7-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="23ce7-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="23ce7-116">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="23ce7-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="23ce7-117">唯一</span><span class="sxs-lookup"><span data-stu-id="23ce7-117">unique</span></span>  <br/> |<span data-ttu-id="23ce7-118">會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。</span><span class="sxs-lookup"><span data-stu-id="23ce7-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="23ce7-119">**求和**</span><span class="sxs-lookup"><span data-stu-id="23ce7-119">**Checksum**</span></span> <br/> |<span data-ttu-id="23ce7-120">int</span><span class="sxs-lookup"><span data-stu-id="23ce7-120">int</span></span>  <br/> |<span data-ttu-id="23ce7-121">index</span><span class="sxs-lookup"><span data-stu-id="23ce7-121">index</span></span>  <br/> |<span data-ttu-id="23ce7-122">會議 URI 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="23ce7-122">Checksum of the conference URI.</span></span> <span data-ttu-id="23ce7-123">這會在內部使用。</span><span class="sxs-lookup"><span data-stu-id="23ce7-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="23ce7-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="23ce7-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="23ce7-125">datetime</span><span class="sxs-lookup"><span data-stu-id="23ce7-125">datetime</span></span>  <br/> ||<span data-ttu-id="23ce7-126">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="23ce7-126">For internal use only.</span></span>  <br/> |
   

