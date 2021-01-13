---
title: 媒體表格
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800103"
---
# <a name="media-table"></a><span data-ttu-id="ce37d-104">媒體表格</span><span class="sxs-lookup"><span data-stu-id="ce37d-104">Media table</span></span>
 
<span data-ttu-id="ce37d-p102">每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。</span><span class="sxs-lookup"><span data-stu-id="ce37d-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce37d-p103">您不應使用媒體資料表來計算工作階段的媒體持續期間。此資料表包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。EndTime 通常是指此工作階段的結束時間。</span><span class="sxs-lookup"><span data-stu-id="ce37d-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="ce37d-111">**欄**</span><span class="sxs-lookup"><span data-stu-id="ce37d-111">**Column**</span></span>|<span data-ttu-id="ce37d-112">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ce37d-112">**Data Type**</span></span>|<span data-ttu-id="ce37d-113">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ce37d-113">**Key/Index**</span></span>|<span data-ttu-id="ce37d-114">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ce37d-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce37d-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ce37d-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ce37d-116">datetime</span><span class="sxs-lookup"><span data-stu-id="ce37d-116">datetime</span></span>  <br/> |<span data-ttu-id="ce37d-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ce37d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ce37d-118">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="ce37d-118">Time of session request.</span></span> <span data-ttu-id="ce37d-119">其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ce37d-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="ce37d-120">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="ce37d-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ce37d-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ce37d-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ce37d-122">int</span><span class="sxs-lookup"><span data-stu-id="ce37d-122">int</span></span>  <br/> |<span data-ttu-id="ce37d-123">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ce37d-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ce37d-124">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="ce37d-124">ID number to identify the session.</span></span> <span data-ttu-id="ce37d-125">會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="ce37d-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="ce37d-126">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="ce37d-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ce37d-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="ce37d-127">**MediaId**</span></span> <br/> |<span data-ttu-id="ce37d-128">Tinyint</span><span class="sxs-lookup"><span data-stu-id="ce37d-128">tinyint</span></span>  <br/> |<span data-ttu-id="ce37d-129">主要，外部</span><span class="sxs-lookup"><span data-stu-id="ce37d-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ce37d-130">用於識別此媒體類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="ce37d-130">Unique number identifying this media type.</span></span> <span data-ttu-id="ce37d-131">如需詳細資訊，請參閱 [MediaList 表格](medialist.md) 。</span><span class="sxs-lookup"><span data-stu-id="ce37d-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ce37d-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="ce37d-132">**StartTime**</span></span> <br/> |<span data-ttu-id="ce37d-133">datetime</span><span class="sxs-lookup"><span data-stu-id="ce37d-133">datetime</span></span>  <br/> |<span data-ttu-id="ce37d-134">主要</span><span class="sxs-lookup"><span data-stu-id="ce37d-134">Primary</span></span>  <br/> |<span data-ttu-id="ce37d-p107">這是媒體要求傳送出來的時間，而不是實際的媒體開始時間。**StartTime** 會指出工作階段開始時間。</span><span class="sxs-lookup"><span data-stu-id="ce37d-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="ce37d-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="ce37d-137">**EndTime**</span></span> <br/> |<span data-ttu-id="ce37d-138">datetime</span><span class="sxs-lookup"><span data-stu-id="ce37d-138">datetime</span></span>  <br/> ||<span data-ttu-id="ce37d-139">這是工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="ce37d-139">This is the end time of the session.</span></span>  <br/> |
   

