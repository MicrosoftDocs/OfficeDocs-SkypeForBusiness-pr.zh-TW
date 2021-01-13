---
title: 伺服器表格
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援的表格。 每筆記錄代表一部伺服器。
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802703"
---
# <a name="server-table"></a><span data-ttu-id="f48c2-104">伺服器表格</span><span class="sxs-lookup"><span data-stu-id="f48c2-104">Server table</span></span>
 
<span data-ttu-id="f48c2-105">伺服器資料表是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="f48c2-105">The Server table is a supporting table.</span></span> <span data-ttu-id="f48c2-106">每筆記錄代表一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="f48c2-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="f48c2-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="f48c2-107">**Column**</span></span>|<span data-ttu-id="f48c2-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f48c2-108">**Data Type**</span></span>|<span data-ttu-id="f48c2-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f48c2-109">**Key/Index**</span></span>|<span data-ttu-id="f48c2-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f48c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f48c2-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="f48c2-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="f48c2-112">int</span><span class="sxs-lookup"><span data-stu-id="f48c2-112">int</span></span>  <br/> |<span data-ttu-id="f48c2-113">主要</span><span class="sxs-lookup"><span data-stu-id="f48c2-113">Primary</span></span>  <br/> |<span data-ttu-id="f48c2-114">用於識別伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f48c2-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="f48c2-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="f48c2-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="f48c2-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f48c2-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f48c2-117">index</span><span class="sxs-lookup"><span data-stu-id="f48c2-117">index</span></span>  <br/> |<span data-ttu-id="f48c2-118">MAC 位址字串。</span><span class="sxs-lookup"><span data-stu-id="f48c2-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="f48c2-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="f48c2-119">**ServerType**</span></span> <br/> |<span data-ttu-id="f48c2-120">int</span><span class="sxs-lookup"><span data-stu-id="f48c2-120">int</span></span>  <br/> |<span data-ttu-id="f48c2-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="f48c2-121">Foreign</span></span>  <br/> |<span data-ttu-id="f48c2-122">1：轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="f48c2-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="f48c2-123">2： A/V 會議 Server16394： A/V Edge service32769：閘道</span><span class="sxs-lookup"><span data-stu-id="f48c2-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="f48c2-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="f48c2-124">**PoolName**</span></span> <br/> |<span data-ttu-id="f48c2-125">Nvarchar (512) </span><span class="sxs-lookup"><span data-stu-id="f48c2-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="f48c2-126">伺服器所屬的集區。</span><span class="sxs-lookup"><span data-stu-id="f48c2-126">Pool the server belongs to.</span></span> <span data-ttu-id="f48c2-127">僅適用于 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="f48c2-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="f48c2-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="f48c2-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="f48c2-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f48c2-129">datetime</span></span>  <br/> ||<span data-ttu-id="f48c2-130">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="f48c2-130">For internal use only.</span></span>  <br/> |
   

