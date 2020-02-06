---
title: Endpoint 表格
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 端點資料表是一個支援資料表，可儲存已參與在資料庫中記錄會話之端點的相關資訊。 資料表中的每一筆記錄代表一個端點。
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809551"
---
# <a name="endpoint-table"></a><span data-ttu-id="89619-104">Endpoint 表格</span><span class="sxs-lookup"><span data-stu-id="89619-104">Endpoint table</span></span>
 
<span data-ttu-id="89619-105">端點資料表是一個支援資料表，可儲存已參與在資料庫中記錄會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="89619-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="89619-106">資料表中的每一筆記錄代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="89619-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="89619-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="89619-107">**Column**</span></span>|<span data-ttu-id="89619-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="89619-108">**Data Type**</span></span>|<span data-ttu-id="89619-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="89619-109">**Key/Index**</span></span>|<span data-ttu-id="89619-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="89619-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89619-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="89619-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="89619-112">int</span><span class="sxs-lookup"><span data-stu-id="89619-112">int</span></span>  <br/> |<span data-ttu-id="89619-113">首選</span><span class="sxs-lookup"><span data-stu-id="89619-113">Primary</span></span>  <br/> |<span data-ttu-id="89619-114">標識此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="89619-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="89619-115">**名稱**</span><span class="sxs-lookup"><span data-stu-id="89619-115">**Name**</span></span> <br/> |<span data-ttu-id="89619-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="89619-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="89619-117">唯一</span><span class="sxs-lookup"><span data-stu-id="89619-117">Unique</span></span>  <br/> |<span data-ttu-id="89619-118">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="89619-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="89619-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="89619-119">**OS**</span></span> <br/> |<span data-ttu-id="89619-120">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="89619-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="89619-121">端點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="89619-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="89619-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="89619-122">**CPUName**</span></span> <br/> |<span data-ttu-id="89619-123">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="89619-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="89619-124">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="89619-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="89619-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="89619-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="89619-126">Smallint</span><span class="sxs-lookup"><span data-stu-id="89619-126">smallint</span></span>  <br/> ||<span data-ttu-id="89619-127">端點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="89619-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="89619-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="89619-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="89619-129">int</span><span class="sxs-lookup"><span data-stu-id="89619-129">int</span></span>  <br/> ||<span data-ttu-id="89619-130">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="89619-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="89619-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="89619-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="89619-132">Tinyint</span><span class="sxs-lookup"><span data-stu-id="89619-132">tinyint</span></span>  <br/> || <span data-ttu-id="89619-133">表示系統是否正在虛擬化環境中執行的位標誌：</span><span class="sxs-lookup"><span data-stu-id="89619-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="89619-134">0x0000-無</span><span class="sxs-lookup"><span data-stu-id="89619-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="89619-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="89619-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="89619-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="89619-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="89619-137">0x0004-虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="89619-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="89619-138">0x0008-Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="89619-138">0x0008 - Xen PC</span></span> <br/> |
   

