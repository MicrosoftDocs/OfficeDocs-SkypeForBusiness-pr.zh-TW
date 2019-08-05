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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: '[會議] 表格是支援表格。 每個記錄代表一個會議或點對點工作階段。'
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192683"
---
# <a name="conference-table"></a><span data-ttu-id="74d2b-104">Conference 表格</span><span class="sxs-lookup"><span data-stu-id="74d2b-104">Conference table</span></span>
 
<span data-ttu-id="74d2b-105">[會議] 表格是支援表格。</span><span class="sxs-lookup"><span data-stu-id="74d2b-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="74d2b-106">每個記錄代表一個會議或點對點工作階段。</span><span class="sxs-lookup"><span data-stu-id="74d2b-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="74d2b-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="74d2b-107">**Column**</span></span>|<span data-ttu-id="74d2b-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="74d2b-108">**Data Type**</span></span>|<span data-ttu-id="74d2b-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="74d2b-109">**Key/Index**</span></span>|<span data-ttu-id="74d2b-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="74d2b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="74d2b-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="74d2b-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="74d2b-112">int</span><span class="sxs-lookup"><span data-stu-id="74d2b-112">int</span></span>  <br/> |<span data-ttu-id="74d2b-113">首選</span><span class="sxs-lookup"><span data-stu-id="74d2b-113">Primary</span></span>  <br/> |<span data-ttu-id="74d2b-114">標識此會議記錄的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="74d2b-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="74d2b-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="74d2b-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="74d2b-116">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74d2b-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="74d2b-117">唯一</span><span class="sxs-lookup"><span data-stu-id="74d2b-117">unique</span></span>  <br/> |<span data-ttu-id="74d2b-118">會議 URI (如果這是會議), 或 DialogID (如果這是點對點工作階段的話)。</span><span class="sxs-lookup"><span data-stu-id="74d2b-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="74d2b-119">**求和**</span><span class="sxs-lookup"><span data-stu-id="74d2b-119">**Checksum**</span></span> <br/> |<span data-ttu-id="74d2b-120">int</span><span class="sxs-lookup"><span data-stu-id="74d2b-120">int</span></span>  <br/> |<span data-ttu-id="74d2b-121">index</span><span class="sxs-lookup"><span data-stu-id="74d2b-121">index</span></span>  <br/> |<span data-ttu-id="74d2b-122">會議 URI 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="74d2b-122">Checksum of the conference URI.</span></span> <span data-ttu-id="74d2b-123">這會在內部使用。</span><span class="sxs-lookup"><span data-stu-id="74d2b-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="74d2b-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="74d2b-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="74d2b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="74d2b-125">datetime</span></span>  <br/> ||<span data-ttu-id="74d2b-126">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="74d2b-126">For internal use only.</span></span>  <br/> |
   

