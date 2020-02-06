---
title: PurgeSettings 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。 請注意，您也可以透過執行下列命令，在商務用 Skype Server 2015 中取得清除相關資訊：
ms.openlocfilehash: 81e702a4d62b4c85fb849a768c97428719ddc391
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814961"
---
# <a name="purgesettings-table"></a><span data-ttu-id="a9537-104">PurgeSettings 資料表</span><span class="sxs-lookup"><span data-stu-id="a9537-104">PurgeSettings table</span></span>
 
<span data-ttu-id="a9537-105">PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。</span><span class="sxs-lookup"><span data-stu-id="a9537-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="a9537-106">請注意，您也可以透過執行下列命令，在商務用 Skype Server 2015 中取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="a9537-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="a9537-107">系統管理員應該將 PurgeSettings 資料表視為唯讀：只有使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[Set CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet，才能對通話詳細資料清除設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="a9537-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="a9537-108">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a9537-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a9537-109">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a9537-109">**Column**</span></span>|<span data-ttu-id="a9537-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a9537-110">**Data Type**</span></span>|<span data-ttu-id="a9537-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a9537-111">**Key/Index**</span></span>|<span data-ttu-id="a9537-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a9537-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9537-113">**標識號**</span><span class="sxs-lookup"><span data-stu-id="a9537-113">**Id**</span></span> <br/> |<span data-ttu-id="a9537-114">int</span><span class="sxs-lookup"><span data-stu-id="a9537-114">int</span></span>  <br/> |<span data-ttu-id="a9537-115">首選</span><span class="sxs-lookup"><span data-stu-id="a9537-115">Primary</span></span>  <br/> |<span data-ttu-id="a9537-116">CDR 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a9537-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="a9537-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="a9537-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="a9537-118">稍微</span><span class="sxs-lookup"><span data-stu-id="a9537-118">bit</span></span>  <br/> ||<span data-ttu-id="a9537-119">當設定為 True （1）商務用 Skype Server 2015 時，會定期從 CDR 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="a9537-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="a9537-120">[清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。</span><span class="sxs-lookup"><span data-stu-id="a9537-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="a9537-121">如果設定為 False （0），則不會自動從資料庫清除記錄。</span><span class="sxs-lookup"><span data-stu-id="a9537-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="a9537-122">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="a9537-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="a9537-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="a9537-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="a9537-124">int</span><span class="sxs-lookup"><span data-stu-id="a9537-124">int</span></span>  <br/> ||<span data-ttu-id="a9537-125">指定將從資料庫清除的 CDR 記錄（天數）的存留期：如果已啟用清除，則早于此值的 CDR 記錄將會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="a9537-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="a9537-126">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="a9537-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="a9537-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="a9537-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="a9537-128">int</span><span class="sxs-lookup"><span data-stu-id="a9537-128">int</span></span>  <br/> ||<span data-ttu-id="a9537-129">指定將從資料庫清除的錯誤報表記錄（天數）的存留期：如果已啟用清除，則超過此值的錯誤報表記錄將會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="a9537-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="a9537-130">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="a9537-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="a9537-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="a9537-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="a9537-132">int</span><span class="sxs-lookup"><span data-stu-id="a9537-132">int</span></span>  <br/> ||<span data-ttu-id="a9537-133">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="a9537-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="a9537-134">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="a9537-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="a9537-135">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="a9537-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="a9537-136">預設值為 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="a9537-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
   

