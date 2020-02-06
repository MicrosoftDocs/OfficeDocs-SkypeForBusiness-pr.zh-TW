---
title: Server 表格
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援資料表。 每個記錄代表一台伺服器。
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806131"
---
# <a name="server-table"></a><span data-ttu-id="7dbbf-104">Server 表格</span><span class="sxs-lookup"><span data-stu-id="7dbbf-104">Server table</span></span>
 
<span data-ttu-id="7dbbf-105">伺服器資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-105">The Server table is a supporting table.</span></span> <span data-ttu-id="7dbbf-106">每個記錄代表一台伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="7dbbf-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-107">**Column**</span></span>|<span data-ttu-id="7dbbf-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-108">**Data Type**</span></span>|<span data-ttu-id="7dbbf-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-109">**Key/Index**</span></span>|<span data-ttu-id="7dbbf-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7dbbf-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="7dbbf-112">int</span><span class="sxs-lookup"><span data-stu-id="7dbbf-112">int</span></span>  <br/> |<span data-ttu-id="7dbbf-113">首選</span><span class="sxs-lookup"><span data-stu-id="7dbbf-113">Primary</span></span>  <br/> |<span data-ttu-id="7dbbf-114">識別伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="7dbbf-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="7dbbf-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7dbbf-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7dbbf-117">index</span><span class="sxs-lookup"><span data-stu-id="7dbbf-117">index</span></span>  <br/> |<span data-ttu-id="7dbbf-118">MAC 位址字串。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="7dbbf-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-119">**ServerType**</span></span> <br/> |<span data-ttu-id="7dbbf-120">int</span><span class="sxs-lookup"><span data-stu-id="7dbbf-120">int</span></span>  <br/> |<span data-ttu-id="7dbbf-121">外</span><span class="sxs-lookup"><span data-stu-id="7dbbf-121">Foreign</span></span>  <br/> |<span data-ttu-id="7dbbf-122">1：中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="7dbbf-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="7dbbf-123">2： a/V 會議 Server16394： A/V 邊緣 service32769：閘道</span><span class="sxs-lookup"><span data-stu-id="7dbbf-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="7dbbf-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-124">**PoolName**</span></span> <br/> |<span data-ttu-id="7dbbf-125">Nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="7dbbf-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="7dbbf-126">伺服器所屬的池。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-126">Pool the server belongs to.</span></span> <span data-ttu-id="7dbbf-127">僅適用于 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7dbbf-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7dbbf-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7dbbf-129">datetime</span><span class="sxs-lookup"><span data-stu-id="7dbbf-129">datetime</span></span>  <br/> ||<span data-ttu-id="7dbbf-130">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="7dbbf-130">For internal use only.</span></span>  <br/> |
   

