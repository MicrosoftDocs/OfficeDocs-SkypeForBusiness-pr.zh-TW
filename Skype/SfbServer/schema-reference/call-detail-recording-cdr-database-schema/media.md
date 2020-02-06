---
title: 媒體資料表格
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每個記錄代表點對點工作階段中所使用的一種媒體類型。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815041"
---
# <a name="media-table"></a><span data-ttu-id="d1dbb-104">媒體資料表格</span><span class="sxs-lookup"><span data-stu-id="d1dbb-104">Media table</span></span>
 
<span data-ttu-id="d1dbb-105">每個記錄代表點對點工作階段中所使用的一種媒體類型。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-105">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d1dbb-106">如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1dbb-107">媒體資料表不應該用來計算會話的媒體持續時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-107">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="d1dbb-108">此表格包含會話中媒體交換的信號詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-108">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="d1dbb-109">媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在 sessionee 接受會話之後才會啟動。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="d1dbb-110">[EndTime] 通常代表這個會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-110">The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="d1dbb-111">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-111">**Column**</span></span>|<span data-ttu-id="d1dbb-112">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-112">**Data Type**</span></span>|<span data-ttu-id="d1dbb-113">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-113">**Key/Index**</span></span>|<span data-ttu-id="d1dbb-114">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1dbb-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d1dbb-116">datetime</span><span class="sxs-lookup"><span data-stu-id="d1dbb-116">datetime</span></span>  <br/> |<span data-ttu-id="d1dbb-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d1dbb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1dbb-118">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-118">Time of session request.</span></span> <span data-ttu-id="d1dbb-119">與**SessionIdSeq**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="d1dbb-120">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d1dbb-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d1dbb-122">int</span><span class="sxs-lookup"><span data-stu-id="d1dbb-122">int</span></span>  <br/> |<span data-ttu-id="d1dbb-123">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d1dbb-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1dbb-124">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-124">ID number to identify the session.</span></span> <span data-ttu-id="d1dbb-125">與**SessionIdTime**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="d1dbb-126">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d1dbb-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-127">**MediaId**</span></span> <br/> |<span data-ttu-id="d1dbb-128">Tinyint</span><span class="sxs-lookup"><span data-stu-id="d1dbb-128">tinyint</span></span>  <br/> |<span data-ttu-id="d1dbb-129">主要、外部</span><span class="sxs-lookup"><span data-stu-id="d1dbb-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="d1dbb-130">識別這個媒體類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-130">Unique number identifying this media type.</span></span> <span data-ttu-id="d1dbb-131">如需詳細資訊，請參閱[MediaList 資料表](medialist.md)。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d1dbb-132">**開始**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-132">**StartTime**</span></span> <br/> |<span data-ttu-id="d1dbb-133">datetime</span><span class="sxs-lookup"><span data-stu-id="d1dbb-133">datetime</span></span>  <br/> |<span data-ttu-id="d1dbb-134">首選</span><span class="sxs-lookup"><span data-stu-id="d1dbb-134">Primary</span></span>  <br/> |<span data-ttu-id="d1dbb-135">這是傳送媒體要求的時間，而不是真正的媒體啟動時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-135">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="d1dbb-136">**StartTime**包含會話設定時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-136">**StartTime** includes the session setup time.</span></span> <br/> |
|<span data-ttu-id="d1dbb-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="d1dbb-137">**EndTime**</span></span> <br/> |<span data-ttu-id="d1dbb-138">datetime</span><span class="sxs-lookup"><span data-stu-id="d1dbb-138">datetime</span></span>  <br/> ||<span data-ttu-id="d1dbb-139">這是會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="d1dbb-139">This is the end time of the session.</span></span>  <br/> |
   

