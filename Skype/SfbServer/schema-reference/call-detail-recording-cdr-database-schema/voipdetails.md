---
title: VoIPDetails view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813073"
---
# <a name="voipdetails-view"></a><span data-ttu-id="10e93-104">VoIPDetails view</span><span class="sxs-lookup"><span data-stu-id="10e93-104">VoIPDetails view</span></span>
 
<span data-ttu-id="10e93-105">VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="10e93-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="10e93-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="10e93-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="10e93-107">VoIPDetails view 包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄，此外還會包含下列欄。</span><span class="sxs-lookup"><span data-stu-id="10e93-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="10e93-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="10e93-108">**Column**</span></span>|<span data-ttu-id="10e93-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="10e93-109">**Data Type**</span></span>|<span data-ttu-id="10e93-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="10e93-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10e93-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="10e93-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="10e93-112">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="10e93-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="10e93-113">起始工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="10e93-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="10e93-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="10e93-115">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="10e93-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="10e93-116">參加工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="10e93-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="10e93-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="10e93-118">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="10e93-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="10e93-119">中斷連線工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="10e93-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="10e93-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="10e93-121">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-122">中斷連線工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="10e93-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="10e93-123">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="10e93-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="10e93-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="10e93-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="10e93-125">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-126">中斷連線工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="10e93-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="10e93-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="10e93-128">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="10e93-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="10e93-129">中斷連線工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="10e93-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="10e93-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="10e93-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-132">起始工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="10e93-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="10e93-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="10e93-134">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-135">參加工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="10e93-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="10e93-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="10e93-137">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-138">起始工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="10e93-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="10e93-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="10e93-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="10e93-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="10e93-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="10e93-141">參加工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="10e93-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

