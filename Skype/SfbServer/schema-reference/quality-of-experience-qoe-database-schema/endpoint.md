---
title: Endpoint 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。 資料表中的每一筆記錄都代表一個端點。
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823063"
---
# <a name="endpoint-table"></a><span data-ttu-id="f44a9-104">Endpoint 表</span><span class="sxs-lookup"><span data-stu-id="f44a9-104">Endpoint table</span></span>
 
<span data-ttu-id="f44a9-105">端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f44a9-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f44a9-106">資料表中的每一筆記錄都代表一個端點。</span><span class="sxs-lookup"><span data-stu-id="f44a9-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="f44a9-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="f44a9-107">**Column**</span></span>|<span data-ttu-id="f44a9-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f44a9-108">**Data Type**</span></span>|<span data-ttu-id="f44a9-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f44a9-109">**Key/Index**</span></span>|<span data-ttu-id="f44a9-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f44a9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f44a9-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="f44a9-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="f44a9-112">int</span><span class="sxs-lookup"><span data-stu-id="f44a9-112">int</span></span>  <br/> |<span data-ttu-id="f44a9-113">主要</span><span class="sxs-lookup"><span data-stu-id="f44a9-113">Primary</span></span>  <br/> |<span data-ttu-id="f44a9-114">用於識別此端點的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f44a9-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="f44a9-115">**名稱**</span><span class="sxs-lookup"><span data-stu-id="f44a9-115">**Name**</span></span> <br/> |<span data-ttu-id="f44a9-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f44a9-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f44a9-117">Unique</span><span class="sxs-lookup"><span data-stu-id="f44a9-117">Unique</span></span>  <br/> |<span data-ttu-id="f44a9-118">端點名稱。</span><span class="sxs-lookup"><span data-stu-id="f44a9-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="f44a9-119">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="f44a9-119">**OS**</span></span> <br/> |<span data-ttu-id="f44a9-120">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f44a9-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="f44a9-121">端點 (作業系統) 。</span><span class="sxs-lookup"><span data-stu-id="f44a9-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f44a9-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="f44a9-122">**CPUName**</span></span> <br/> |<span data-ttu-id="f44a9-123">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f44a9-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="f44a9-124">端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="f44a9-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f44a9-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="f44a9-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="f44a9-126">Smallint</span><span class="sxs-lookup"><span data-stu-id="f44a9-126">smallint</span></span>  <br/> ||<span data-ttu-id="f44a9-127">端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="f44a9-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f44a9-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="f44a9-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="f44a9-129">int</span><span class="sxs-lookup"><span data-stu-id="f44a9-129">int</span></span>  <br/> ||<span data-ttu-id="f44a9-130">端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="f44a9-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="f44a9-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="f44a9-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="f44a9-132">Tinyint</span><span class="sxs-lookup"><span data-stu-id="f44a9-132">tinyint</span></span>  <br/> || <span data-ttu-id="f44a9-133">指出系統是否在虛擬化環境中執行的位旗標：</span><span class="sxs-lookup"><span data-stu-id="f44a9-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="f44a9-134">0x0000-無</span><span class="sxs-lookup"><span data-stu-id="f44a9-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="f44a9-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="f44a9-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="f44a9-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="f44a9-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="f44a9-137">0x0004-虛擬 PC</span><span class="sxs-lookup"><span data-stu-id="f44a9-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="f44a9-138">0x0008-Xen 電腦</span><span class="sxs-lookup"><span data-stu-id="f44a9-138">0x0008 - Xen PC</span></span> <br/> |
   

