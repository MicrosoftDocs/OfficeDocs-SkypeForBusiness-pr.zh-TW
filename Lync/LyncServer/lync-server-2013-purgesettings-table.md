---
title: Lync Server 2013： PurgeSettings 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="16f6f-102">Lync Server 2013 中的 PurgeSettings 表格</span><span class="sxs-lookup"><span data-stu-id="16f6f-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16f6f-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="16f6f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="16f6f-104">PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。</span><span class="sxs-lookup"><span data-stu-id="16f6f-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="16f6f-105">請注意，您也可以透過執行下列命令，在 Microsoft Lync Server 2013 管理命令介面中取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="16f6f-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="16f6f-106">系統管理員應該將 PurgeSettings 資料表視為唯讀：只有使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[Set CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet，才能對通話詳細資料清除設定進行變更。</span><span class="sxs-lookup"><span data-stu-id="16f6f-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="16f6f-107">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="16f6f-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16f6f-108">左欄</span><span class="sxs-lookup"><span data-stu-id="16f6f-108">Column</span></span></th>
<th><span data-ttu-id="16f6f-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="16f6f-109">Data Type</span></span></th>
<th><span data-ttu-id="16f6f-110">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="16f6f-110">Key/Index</span></span></th>
<th><span data-ttu-id="16f6f-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="16f6f-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-112"><strong>標識號</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-113">int</span><span class="sxs-lookup"><span data-stu-id="16f6f-113">int</span></span></p></td>
<td><p><span data-ttu-id="16f6f-114">首選</span><span class="sxs-lookup"><span data-stu-id="16f6f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="16f6f-115">CDR 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="16f6f-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-117">稍微</span><span class="sxs-lookup"><span data-stu-id="16f6f-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="16f6f-118">當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="16f6f-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="16f6f-119">[清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。</span><span class="sxs-lookup"><span data-stu-id="16f6f-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="16f6f-120">如果設定為 False （0），則不會自動從資料庫清除記錄。</span><span class="sxs-lookup"><span data-stu-id="16f6f-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="16f6f-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="16f6f-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-123">int</span><span class="sxs-lookup"><span data-stu-id="16f6f-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="16f6f-124">指定將從資料庫清除的 CDR 記錄（天數）的存留期：如果已啟用清除，則早于此值的 CDR 記錄將會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="16f6f-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="16f6f-125">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="16f6f-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16f6f-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-127">int</span><span class="sxs-lookup"><span data-stu-id="16f6f-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="16f6f-128">指定將從資料庫清除的錯誤報表記錄（天數）的存留期：如果已啟用清除，則超過此值的錯誤報表記錄將會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="16f6f-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="16f6f-129">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="16f6f-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16f6f-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="16f6f-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="16f6f-131">int</span><span class="sxs-lookup"><span data-stu-id="16f6f-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="16f6f-132">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="16f6f-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="16f6f-133">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="16f6f-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="16f6f-134">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="16f6f-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="16f6f-135">預設值為 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="16f6f-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

