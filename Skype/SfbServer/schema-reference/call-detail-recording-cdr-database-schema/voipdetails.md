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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: '[VoIPDetails] 視圖儲存點對點工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814771"
---
# <a name="voipdetails-view"></a><span data-ttu-id="bbd01-104">VoIPDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="bbd01-104">VoIPDetails view</span></span>
 
<span data-ttu-id="bbd01-105">[VoIPDetails] 視圖儲存點對點工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="bbd01-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="bbd01-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="bbd01-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbd01-107">[VoIPDetails] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行，以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="bbd01-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="bbd01-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="bbd01-108">**Column**</span></span>|<span data-ttu-id="bbd01-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bbd01-109">**Data Type**</span></span>|<span data-ttu-id="bbd01-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bbd01-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bbd01-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="bbd01-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="bbd01-112">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="bbd01-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="bbd01-113">啟動會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="bbd01-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="bbd01-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="bbd01-115">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="bbd01-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="bbd01-116">加入會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="bbd01-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="bbd01-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="bbd01-118">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="bbd01-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="bbd01-119">中斷會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="bbd01-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="bbd01-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="bbd01-121">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-122">中斷會話的使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="bbd01-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="bbd01-123">如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="bbd01-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="bbd01-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="bbd01-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="bbd01-125">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-126">中斷會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="bbd01-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="bbd01-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="bbd01-128">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="bbd01-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="bbd01-129">中斷會話的使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="bbd01-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="bbd01-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="bbd01-131">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-132">啟動會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbd01-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="bbd01-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="bbd01-134">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-135">加入會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="bbd01-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="bbd01-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="bbd01-137">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-138">啟動會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="bbd01-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="bbd01-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="bbd01-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="bbd01-140">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bbd01-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bbd01-141">加入會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="bbd01-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

