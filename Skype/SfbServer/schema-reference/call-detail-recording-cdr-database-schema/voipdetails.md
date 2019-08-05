---
title: VoIPDetails 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: '[VoIPDetails] 視圖儲存點對點工作階段的相關資訊, 其中至少有一個使用者是 VoIP 使用者。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192773"
---
# <a name="voipdetails-view"></a><span data-ttu-id="238b4-104">VoIPDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="238b4-104">VoIPDetails view</span></span>
 
<span data-ttu-id="238b4-105">[VoIPDetails] 視圖儲存點對點工作階段的相關資訊, 其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="238b4-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="238b4-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="238b4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="238b4-107">[VoIPDetails] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行, 以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="238b4-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="238b4-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="238b4-108">**Column**</span></span>|<span data-ttu-id="238b4-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="238b4-109">**Data Type**</span></span>|<span data-ttu-id="238b4-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="238b4-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="238b4-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="238b4-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="238b4-112">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="238b4-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="238b4-113">啟動會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="238b4-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="238b4-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="238b4-115">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="238b4-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="238b4-116">加入會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="238b4-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="238b4-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="238b4-118">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="238b4-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="238b4-119">中斷會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="238b4-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="238b4-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="238b4-121">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-122">中斷會話的使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="238b4-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="238b4-123">如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="238b4-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="238b4-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="238b4-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="238b4-125">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-126">中斷會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="238b4-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="238b4-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="238b4-128">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="238b4-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="238b4-129">中斷會話的使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="238b4-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="238b4-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="238b4-131">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-132">啟動會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="238b4-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="238b4-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="238b4-134">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-135">加入會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="238b4-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="238b4-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="238b4-137">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-138">啟動會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="238b4-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="238b4-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="238b4-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="238b4-140">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="238b4-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="238b4-141">加入會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="238b4-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

