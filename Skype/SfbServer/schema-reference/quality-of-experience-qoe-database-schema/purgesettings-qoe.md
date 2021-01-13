---
title: 'PurgeSettings table (QoE) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 資料表包含指定在經驗品質記錄過期時，會自動從 QoE 資料庫加以刪除的資訊。 請注意，您也可以透過執行下列命令，在商務用 Skype Server 管理命令介面中取得清除相關資訊：
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815803"
---
# <a name="purgesettings-table-qoe"></a><span data-ttu-id="f7e50-104">PurgeSettings table (QoE) </span><span class="sxs-lookup"><span data-stu-id="f7e50-104">PurgeSettings table (QoE)</span></span>
 
<span data-ttu-id="f7e50-105">PurgeSettings 資料表包含指定在經驗品質記錄過期時，會自動從 QoE 資料庫加以刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="f7e50-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="f7e50-106">請注意，您也可以透過執行下列命令，在商務用 Skype Server 管理命令介面中取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="f7e50-106">Note that purging-related information can also be obtained from within the Skype for Business Server Management Shell by running the following command:</span></span>
  
```PowerShell
Get-CsQoEConfiguration
```

<span data-ttu-id="f7e50-107">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f7e50-107">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f7e50-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="f7e50-108">**Column**</span></span>|<span data-ttu-id="f7e50-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f7e50-109">**Data Type**</span></span>|<span data-ttu-id="f7e50-110">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f7e50-110">**Key/Index**</span></span>|<span data-ttu-id="f7e50-111">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f7e50-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7e50-112">**識別碼**</span><span class="sxs-lookup"><span data-stu-id="f7e50-112">**ID**</span></span> <br/> |<span data-ttu-id="f7e50-113">int</span><span class="sxs-lookup"><span data-stu-id="f7e50-113">int</span></span>  <br/> |<span data-ttu-id="f7e50-114">主要</span><span class="sxs-lookup"><span data-stu-id="f7e50-114">Primary</span></span>  <br/> |<span data-ttu-id="f7e50-115">QoE 清除設定集的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f7e50-115">Unique identifier for the collection of QoE purge settings.</span></span>  <br/> |
|<span data-ttu-id="f7e50-116">**EnablePurge**</span><span class="sxs-lookup"><span data-stu-id="f7e50-116">**EnablePurge**</span></span> <br/> |<span data-ttu-id="f7e50-117">位</span><span class="sxs-lookup"><span data-stu-id="f7e50-117">bit</span></span>  <br/> ||<span data-ttu-id="f7e50-118">設為 True 時 (1) Microsoft Lync Server 2013 會定期從 QoE 資料庫中清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="f7e50-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="f7e50-119">清除動作會每天在 PurgeHour 設定中指定的時間加以執行。</span><span class="sxs-lookup"><span data-stu-id="f7e50-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="f7e50-120">若設為 False (0)，就不會從資料庫自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="f7e50-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="f7e50-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="f7e50-121">The default value is True.</span></span>  <br/> |
|<span data-ttu-id="f7e50-122">**KeepQoEDataForDays**</span><span class="sxs-lookup"><span data-stu-id="f7e50-122">**KeepQoEDataForDays**</span></span> <br/> |<span data-ttu-id="f7e50-123">int</span><span class="sxs-lookup"><span data-stu-id="f7e50-123">int</span></span>  <br/> ||<span data-ttu-id="f7e50-p104">指定要從資料庫清除之 QoE 記錄的存留期 (以天數為單位)：若啟用清除，就會從資料庫移除舊於此值的 QoE。預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="f7e50-p104">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span>  <br/> |
|<span data-ttu-id="f7e50-126">**PurgeHour**</span><span class="sxs-lookup"><span data-stu-id="f7e50-126">**PurgeHour**</span></span> <br/> |<span data-ttu-id="f7e50-127">int</span><span class="sxs-lookup"><span data-stu-id="f7e50-127">int</span></span>  <br/> ||<span data-ttu-id="f7e50-p105">指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。</span><span class="sxs-lookup"><span data-stu-id="f7e50-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span>  <br/> |
   

