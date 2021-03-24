---
title: PurgeSettings 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。 請注意，您也可以透過執行下列命令，在商務用 Skype Server 2015 中取得清除相關資訊：
ms.openlocfilehash: 2e834f64ca5500f8d8bab1d89fb263d2708fa60c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098659"
---
# <a name="purgesettings-table"></a><span data-ttu-id="66a55-104">PurgeSettings 表格</span><span class="sxs-lookup"><span data-stu-id="66a55-104">PurgeSettings table</span></span>
 
<span data-ttu-id="66a55-105">PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="66a55-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="66a55-106">請注意，您也可以透過執行下列命令，在商務用 Skype Server 2015 中取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="66a55-106">Note that purging-related information can also be obtained from within the Skype for Business Server 2015 by running the following command:</span></span>
  
```PowerShell
Get-CsCdrConfiguration
```

<span data-ttu-id="66a55-107">管理員應該將 PurgeSettings 表格視為唯讀：只有在使用 [新的-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 時，才應進行通話詳細資料清除設定的變更。</span><span class="sxs-lookup"><span data-stu-id="66a55-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) or [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlets.</span></span>
  
<span data-ttu-id="66a55-108">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="66a55-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="66a55-109">**欄**</span><span class="sxs-lookup"><span data-stu-id="66a55-109">**Column**</span></span>|<span data-ttu-id="66a55-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="66a55-110">**Data Type**</span></span>|<span data-ttu-id="66a55-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="66a55-111">**Key/Index**</span></span>|<span data-ttu-id="66a55-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="66a55-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66a55-113">**Id**</span><span class="sxs-lookup"><span data-stu-id="66a55-113">**Id**</span></span> <br/> |<span data-ttu-id="66a55-114">int</span><span class="sxs-lookup"><span data-stu-id="66a55-114">int</span></span>  <br/> |<span data-ttu-id="66a55-115">主要</span><span class="sxs-lookup"><span data-stu-id="66a55-115">Primary</span></span>  <br/> |<span data-ttu-id="66a55-116">CDR 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="66a55-116">Unique identifier for the collection of CDR purge settings.</span></span>  <br/> |
|<span data-ttu-id="66a55-117">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="66a55-117">**EnablePurge**</span></span> <br/> |<span data-ttu-id="66a55-118">位</span><span class="sxs-lookup"><span data-stu-id="66a55-118">bit</span></span>  <br/> ||<span data-ttu-id="66a55-119">設為 True 時 (1) 商務用 Skype Server 2015 會定期從 CDR 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="66a55-119">When set to True (1) Skype for Business Server 2015 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="66a55-120">清除動作會每天在 PurgeHour 設定中指定的時間加以執行。</span><span class="sxs-lookup"><span data-stu-id="66a55-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="66a55-121">若設為 False (0)，就不會從資料庫自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="66a55-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="66a55-122">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="66a55-122">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="66a55-123">**KeepCallDetailForDays**</span><span class="sxs-lookup"><span data-stu-id="66a55-123">**KeepCallDetailForDays**</span></span> <br/> |<span data-ttu-id="66a55-124">int</span><span class="sxs-lookup"><span data-stu-id="66a55-124">int</span></span>  <br/> ||<span data-ttu-id="66a55-125">會指定要從資料庫中清除之 CDR 記錄的保留天數)  (：如果啟用清除，則舊于此值以上的 CDR 記錄會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="66a55-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="66a55-126">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="66a55-126">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="66a55-127">**KeepErrorReportForDays**</span><span class="sxs-lookup"><span data-stu-id="66a55-127">**KeepErrorReportForDays**</span></span> <br/> |<span data-ttu-id="66a55-128">int</span><span class="sxs-lookup"><span data-stu-id="66a55-128">int</span></span>  <br/> ||<span data-ttu-id="66a55-129">指定要從資料庫中清除的錯誤報表記錄 (天數) ：若啟用清除功能，則會從資料庫中移除比此值還舊的錯誤報表記錄。</span><span class="sxs-lookup"><span data-stu-id="66a55-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="66a55-130">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="66a55-130">The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="66a55-131">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="66a55-131">**PurgeHour**</span></span> <br/> |<span data-ttu-id="66a55-132">int</span><span class="sxs-lookup"><span data-stu-id="66a55-132">int</span></span>  <br/> ||<span data-ttu-id="66a55-133">指定要執行資料庫清除的時間。</span><span class="sxs-lookup"><span data-stu-id="66a55-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="66a55-134">時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。</span><span class="sxs-lookup"><span data-stu-id="66a55-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="66a55-135">請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。</span><span class="sxs-lookup"><span data-stu-id="66a55-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="66a55-136">預設值為 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="66a55-136">The default value is 2 (2:00 AM).</span></span>  <br/> |
