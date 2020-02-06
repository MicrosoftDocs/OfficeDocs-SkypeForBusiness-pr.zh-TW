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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。 [會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815391"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b70d6-104">商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="b70d6-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b70d6-105">ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。</span><span class="sxs-lookup"><span data-stu-id="b70d6-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="b70d6-106">[會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：</span><span class="sxs-lookup"><span data-stu-id="b70d6-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="b70d6-107">少於2秒。</span><span class="sxs-lookup"><span data-stu-id="b70d6-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="b70d6-108">介於2秒和5秒之間。</span><span class="sxs-lookup"><span data-stu-id="b70d6-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="b70d6-109">介於5秒和10秒之間。</span><span class="sxs-lookup"><span data-stu-id="b70d6-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="b70d6-110">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="b70d6-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="b70d6-111">ConferenceJoinTimeThresholds 資料表包含2秒、5秒和10秒的分類值。</span><span class="sxs-lookup"><span data-stu-id="b70d6-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="b70d6-112">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b70d6-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b70d6-113">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b70d6-113">**Column**</span></span>|<span data-ttu-id="b70d6-114">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b70d6-114">**Data Type**</span></span>|<span data-ttu-id="b70d6-115">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="b70d6-115">**Key/Index**</span></span>|<span data-ttu-id="b70d6-116">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="b70d6-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b70d6-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="b70d6-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="b70d6-118">int</span><span class="sxs-lookup"><span data-stu-id="b70d6-118">int</span></span>  <br/> |<span data-ttu-id="b70d6-119">首選</span><span class="sxs-lookup"><span data-stu-id="b70d6-119">Primary</span></span>  <br/> |<span data-ttu-id="b70d6-120">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b70d6-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="b70d6-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="b70d6-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="b70d6-122">int</span><span class="sxs-lookup"><span data-stu-id="b70d6-122">int</span></span>  <br/> || <span data-ttu-id="b70d6-123">分類的上限。</span><span class="sxs-lookup"><span data-stu-id="b70d6-123">Upper limit for the classification.</span></span> <span data-ttu-id="b70d6-124">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b70d6-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="b70d6-125">2</span><span class="sxs-lookup"><span data-stu-id="b70d6-125">2</span></span> <br/>  <span data-ttu-id="b70d6-126">500</span><span class="sxs-lookup"><span data-stu-id="b70d6-126">5</span></span> <br/>  <span data-ttu-id="b70d6-127">第</span><span class="sxs-lookup"><span data-stu-id="b70d6-127">10</span></span> <br/> |
   

