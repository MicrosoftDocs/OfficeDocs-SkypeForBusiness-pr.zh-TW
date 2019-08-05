---
title: 商務用 Skype Server 2015 中的 ConferenceUris 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 資料表是一個支援資料表, 可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。 資料表中的每一筆記錄代表一個會議 URI。
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192880"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cab66-104">商務用 Skype Server 2015 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="cab66-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cab66-105">ConfereneUris 資料表是一個支援資料表, 可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。</span><span class="sxs-lookup"><span data-stu-id="cab66-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="cab66-106">資料表中的每一筆記錄代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="cab66-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="cab66-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="cab66-107">**Column**</span></span>|<span data-ttu-id="cab66-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="cab66-108">**Data Type**</span></span>|<span data-ttu-id="cab66-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="cab66-109">**Key/Index**</span></span>|<span data-ttu-id="cab66-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="cab66-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cab66-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="cab66-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="cab66-112">datetime</span><span class="sxs-lookup"><span data-stu-id="cab66-112">datetime</span></span>  <br/> |<span data-ttu-id="cab66-113">首選</span><span class="sxs-lookup"><span data-stu-id="cab66-113">Primary</span></span>  <br/> |<span data-ttu-id="cab66-114">時間戳記, 內部使用。</span><span class="sxs-lookup"><span data-stu-id="cab66-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="cab66-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="cab66-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="cab66-116">int</span><span class="sxs-lookup"><span data-stu-id="cab66-116">int</span></span>  <br/> |<span data-ttu-id="cab66-117">首選</span><span class="sxs-lookup"><span data-stu-id="cab66-117">Primary</span></span>  <br/> |<span data-ttu-id="cab66-118">標識此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="cab66-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="cab66-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="cab66-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="cab66-120">Nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cab66-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="cab66-121">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="cab66-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="cab66-122">**求和**</span><span class="sxs-lookup"><span data-stu-id="cab66-122">**Checksum**</span></span> <br/> |<span data-ttu-id="cab66-123">int</span><span class="sxs-lookup"><span data-stu-id="cab66-123">int</span></span>  <br/> ||<span data-ttu-id="cab66-124">ConferenceUri 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="cab66-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="cab66-125">用來提高資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="cab66-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="cab66-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="cab66-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="cab66-127">int</span><span class="sxs-lookup"><span data-stu-id="cab66-127">int</span></span>  <br/> |<span data-ttu-id="cab66-128">外</span><span class="sxs-lookup"><span data-stu-id="cab66-128">Foreign</span></span>  <br/> |<span data-ttu-id="cab66-129">URI 類型, 例如會議: IM 會議的聊天或會議: 音訊/視訊會議的音訊-視頻。</span><span class="sxs-lookup"><span data-stu-id="cab66-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="cab66-130">如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)表格。</span><span class="sxs-lookup"><span data-stu-id="cab66-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

