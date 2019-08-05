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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 端點資料表是一個支援資料表, 可儲存已參與在資料庫中記錄會話之端點的相關資訊。 資料表中的每一筆記錄代表一個端點。
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192675"
---
# <a name="endpoint-table"></a><span data-ttu-id="f7be4-104">Endpoint 表格</span><span class="sxs-lookup"><span data-stu-id="f7be4-104">Endpoint table</span></span>
 
<span data-ttu-id="f7be4-105">端點資料表是一個支援資料表, 可儲存已參與在資料庫中記錄會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f7be4-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f7be4-106">資料表中的每一筆記錄代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="f7be4-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="f7be4-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f7be4-107">**Column**</span></span>|<span data-ttu-id="f7be4-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f7be4-108">**Data Type**</span></span>|<span data-ttu-id="f7be4-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f7be4-109">**Key/Index**</span></span>|<span data-ttu-id="f7be4-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f7be4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7be4-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="f7be4-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="f7be4-112">int</span><span class="sxs-lookup"><span data-stu-id="f7be4-112">int</span></span>  <br/> |<span data-ttu-id="f7be4-113">首選</span><span class="sxs-lookup"><span data-stu-id="f7be4-113">Primary</span></span>  <br/> |<span data-ttu-id="f7be4-114">標識此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f7be4-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="f7be4-115">**名稱**</span><span class="sxs-lookup"><span data-stu-id="f7be4-115">**Name**</span></span> <br/> |<span data-ttu-id="f7be4-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f7be4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f7be4-117">唯一</span><span class="sxs-lookup"><span data-stu-id="f7be4-117">Unique</span></span>  <br/> |<span data-ttu-id="f7be4-118">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="f7be4-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="f7be4-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="f7be4-119">**OS**</span></span> <br/> |<span data-ttu-id="f7be4-120">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="f7be4-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="f7be4-121">端點的作業系統 (OS)。</span><span class="sxs-lookup"><span data-stu-id="f7be4-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f7be4-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="f7be4-122">**CPUName**</span></span> <br/> |<span data-ttu-id="f7be4-123">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="f7be4-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="f7be4-124">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="f7be4-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f7be4-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="f7be4-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="f7be4-126">Smallint</span><span class="sxs-lookup"><span data-stu-id="f7be4-126">smallint</span></span>  <br/> ||<span data-ttu-id="f7be4-127">端點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="f7be4-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f7be4-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="f7be4-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="f7be4-129">int</span><span class="sxs-lookup"><span data-stu-id="f7be4-129">int</span></span>  <br/> ||<span data-ttu-id="f7be4-130">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="f7be4-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f7be4-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="f7be4-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="f7be4-132">Tinyint</span><span class="sxs-lookup"><span data-stu-id="f7be4-132">tinyint</span></span>  <br/> || <span data-ttu-id="f7be4-133">表示系統是否正在虛擬化環境中執行的位標誌:</span><span class="sxs-lookup"><span data-stu-id="f7be4-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="f7be4-134">0x0000-無</span><span class="sxs-lookup"><span data-stu-id="f7be4-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="f7be4-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="f7be4-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="f7be4-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="f7be4-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="f7be4-137">0x0004-虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="f7be4-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="f7be4-138">0x0008-Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="f7be4-138">0x0008 - Xen PC</span></span> <br/> |
   

