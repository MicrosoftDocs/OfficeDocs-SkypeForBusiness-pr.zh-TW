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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援資料表。 每個記錄代表一台伺服器。
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192635"
---
# <a name="server-table"></a><span data-ttu-id="ce0ea-104">Server 表格</span><span class="sxs-lookup"><span data-stu-id="ce0ea-104">Server table</span></span>
 
<span data-ttu-id="ce0ea-105">伺服器資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-105">The Server table is a supporting table.</span></span> <span data-ttu-id="ce0ea-106">每個記錄代表一台伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="ce0ea-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-107">**Column**</span></span>|<span data-ttu-id="ce0ea-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-108">**Data Type**</span></span>|<span data-ttu-id="ce0ea-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-109">**Key/Index**</span></span>|<span data-ttu-id="ce0ea-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce0ea-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="ce0ea-112">int</span><span class="sxs-lookup"><span data-stu-id="ce0ea-112">int</span></span>  <br/> |<span data-ttu-id="ce0ea-113">首選</span><span class="sxs-lookup"><span data-stu-id="ce0ea-113">Primary</span></span>  <br/> |<span data-ttu-id="ce0ea-114">識別伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="ce0ea-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="ce0ea-116">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ce0ea-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ce0ea-117">index</span><span class="sxs-lookup"><span data-stu-id="ce0ea-117">index</span></span>  <br/> |<span data-ttu-id="ce0ea-118">MAC 位址字串。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="ce0ea-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-119">**ServerType**</span></span> <br/> |<span data-ttu-id="ce0ea-120">int</span><span class="sxs-lookup"><span data-stu-id="ce0ea-120">int</span></span>  <br/> |<span data-ttu-id="ce0ea-121">外</span><span class="sxs-lookup"><span data-stu-id="ce0ea-121">Foreign</span></span>  <br/> |<span data-ttu-id="ce0ea-122">1: 中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="ce0ea-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="ce0ea-123">2: a/V 會議 Server16394: A/V 邊緣 service32769: 閘道</span><span class="sxs-lookup"><span data-stu-id="ce0ea-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="ce0ea-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-124">**PoolName**</span></span> <br/> |<span data-ttu-id="ce0ea-125">Nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="ce0ea-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="ce0ea-126">伺服器所屬的池。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-126">Pool the server belongs to.</span></span> <span data-ttu-id="ce0ea-127">僅適用于 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="ce0ea-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ce0ea-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ce0ea-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ce0ea-129">datetime</span></span>  <br/> ||<span data-ttu-id="ce0ea-130">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="ce0ea-130">For internal use only.</span></span>  <br/> |
   

