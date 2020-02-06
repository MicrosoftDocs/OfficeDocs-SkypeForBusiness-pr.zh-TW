---
title: PurgeSettings table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。 請注意，您也可以透過執行下列命令，在商務用 Skype Server Management 命令介面內取得清除相關資訊：
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807330"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="e90a4-104">PurgeSettings table （QoE）</span><span class="sxs-lookup"><span data-stu-id="e90a4-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="e90a4-105">PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="e90a4-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="e90a4-106">請注意，您也可以透過執行下列命令，在商務用 Skype Server Management 命令介面內取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="e90a4-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="e90a4-107">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="e90a4-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e90a4-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e90a4-108">**Column**</span></span>|<span data-ttu-id="e90a4-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e90a4-109">**Data Type**</span></span>|<span data-ttu-id="e90a4-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="e90a4-110">**Key/Index**</span></span>|<span data-ttu-id="e90a4-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e90a4-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e90a4-112">**標識號**</span><span class="sxs-lookup"><span data-stu-id="e90a4-112">**ID**</span></span> <br/> |<span data-ttu-id="e90a4-113">int</span><span class="sxs-lookup"><span data-stu-id="e90a4-113">int</span></span>  <br/> |<span data-ttu-id="e90a4-114">首選</span><span class="sxs-lookup"><span data-stu-id="e90a4-114">Primary</span></span>  <br/> |<span data-ttu-id="e90a4-115">QoE 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e90a4-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="e90a4-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="e90a4-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="e90a4-117">稍微</span><span class="sxs-lookup"><span data-stu-id="e90a4-117">bit</span></span>  <br/> ||<span data-ttu-id="e90a4-118">當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 QoE 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="e90a4-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="e90a4-119">[清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。</span><span class="sxs-lookup"><span data-stu-id="e90a4-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="e90a4-120">如果設定為 False （0），則不會自動從資料庫清除記錄。</span><span class="sxs-lookup"><span data-stu-id="e90a4-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="e90a4-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="e90a4-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="e90a4-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="e90a4-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="e90a4-123">int</span><span class="sxs-lookup"><span data-stu-id="e90a4-123">int</span></span>  <br/> ||<span data-ttu-id="e90a4-124">指定將從資料庫清除的 QoE 記錄（天）期限：如果已啟用清除，則會從資料庫中移除超過此值的 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="e90a4-124">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="e90a4-125">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="e90a4-125">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="e90a4-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="e90a4-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="e90a4-127">int</span><span class="sxs-lookup"><span data-stu-id="e90a4-127">int</span></span>  <br/> ||<span data-ttu-id="e90a4-128">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="e90a4-128">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e90a4-129">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="e90a4-129">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e90a4-130">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="e90a4-130">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e90a4-131">預設值為1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="e90a4-131">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="e90a4-132">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="e90a4-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="e90a4-133">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="e90a4-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="e90a4-134">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="e90a4-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="e90a4-135">預設值為1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="e90a4-135">The default value is 1 (1:00 AM).</span></span>  <br/> |
   

