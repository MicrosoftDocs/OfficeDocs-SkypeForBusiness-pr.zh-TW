---
title: 商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。 [會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192895"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="95f3c-104">商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="95f3c-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95f3c-105">ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。</span><span class="sxs-lookup"><span data-stu-id="95f3c-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="95f3c-106">[會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告:</span><span class="sxs-lookup"><span data-stu-id="95f3c-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="95f3c-107">少於2秒。</span><span class="sxs-lookup"><span data-stu-id="95f3c-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="95f3c-108">介於2秒和5秒之間。</span><span class="sxs-lookup"><span data-stu-id="95f3c-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="95f3c-109">介於5秒和10秒之間。</span><span class="sxs-lookup"><span data-stu-id="95f3c-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="95f3c-110">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="95f3c-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="95f3c-111">ConferenceJoinTimeThresholds 資料表包含2秒、5秒和10秒的分類值。</span><span class="sxs-lookup"><span data-stu-id="95f3c-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="95f3c-112">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="95f3c-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="95f3c-113">**左欄**</span><span class="sxs-lookup"><span data-stu-id="95f3c-113">**Column**</span></span>|<span data-ttu-id="95f3c-114">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="95f3c-114">**Data Type**</span></span>|<span data-ttu-id="95f3c-115">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="95f3c-115">**Key/Index**</span></span>|<span data-ttu-id="95f3c-116">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="95f3c-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95f3c-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="95f3c-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="95f3c-118">int</span><span class="sxs-lookup"><span data-stu-id="95f3c-118">int</span></span>  <br/> |<span data-ttu-id="95f3c-119">首選</span><span class="sxs-lookup"><span data-stu-id="95f3c-119">Primary</span></span>  <br/> |<span data-ttu-id="95f3c-120">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="95f3c-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="95f3c-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="95f3c-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="95f3c-122">int</span><span class="sxs-lookup"><span data-stu-id="95f3c-122">int</span></span>  <br/> || <span data-ttu-id="95f3c-123">分類的上限。</span><span class="sxs-lookup"><span data-stu-id="95f3c-123">Upper limit for the classification.</span></span> <span data-ttu-id="95f3c-124">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="95f3c-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="95f3c-125">pplx-2</span><span class="sxs-lookup"><span data-stu-id="95f3c-125">2</span></span> <br/>  <span data-ttu-id="95f3c-126">500</span><span class="sxs-lookup"><span data-stu-id="95f3c-126">5</span></span> <br/>  <span data-ttu-id="95f3c-127">第</span><span class="sxs-lookup"><span data-stu-id="95f3c-127">10</span></span> <br/> |
   

