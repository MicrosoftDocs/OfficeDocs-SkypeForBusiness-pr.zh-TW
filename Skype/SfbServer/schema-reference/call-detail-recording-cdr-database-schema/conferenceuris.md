---
title: 商務用 Skype Server 2015 中的 ConferenceUris 表格
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。 表格中的每一筆記錄都代表一個會議 URI。
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816133"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4b4a5-104">商務用 Skype Server 2015 中的 ConferenceUris 表格</span><span class="sxs-lookup"><span data-stu-id="4b4a5-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b4a5-105">ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="4b4a5-106">表格中的每一筆記錄都代表一個會議 URI。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="4b4a5-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-107">**Column**</span></span>|<span data-ttu-id="4b4a5-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-108">**Data Type**</span></span>|<span data-ttu-id="4b4a5-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-109">**Key/Index**</span></span>|<span data-ttu-id="4b4a5-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b4a5-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4b4a5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4b4a5-112">datetime</span></span>  <br/> |<span data-ttu-id="4b4a5-113">主要</span><span class="sxs-lookup"><span data-stu-id="4b4a5-113">Primary</span></span>  <br/> |<span data-ttu-id="4b4a5-114">時間戳記，內部使用。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="4b4a5-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="4b4a5-116">int</span><span class="sxs-lookup"><span data-stu-id="4b4a5-116">int</span></span>  <br/> |<span data-ttu-id="4b4a5-117">主要</span><span class="sxs-lookup"><span data-stu-id="4b4a5-117">Primary</span></span>  <br/> |<span data-ttu-id="4b4a5-118">用於識別此會議 URI 的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="4b4a5-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="4b4a5-120">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="4b4a5-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="4b4a5-121">會議 URI。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="4b4a5-122">**校驗**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-122">**Checksum**</span></span> <br/> |<span data-ttu-id="4b4a5-123">int</span><span class="sxs-lookup"><span data-stu-id="4b4a5-123">int</span></span>  <br/> ||<span data-ttu-id="4b4a5-124">ConferenceUri 的檢驗。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="4b4a5-125">用於增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="4b4a5-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="4b4a5-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="4b4a5-127">int</span><span class="sxs-lookup"><span data-stu-id="4b4a5-127">int</span></span>  <br/> |<span data-ttu-id="4b4a5-128">Foreign</span><span class="sxs-lookup"><span data-stu-id="4b4a5-128">Foreign</span></span>  <br/> |<span data-ttu-id="4b4a5-129">URI 類型，例如會議：適用于 IM 會議或會議：音訊/視訊會議的音訊-影片。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="4b4a5-130">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="4b4a5-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

