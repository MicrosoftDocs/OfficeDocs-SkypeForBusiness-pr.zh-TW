---
title: Lync Server 2013： PurgeSettings 表格
description: Lync Server 2013： PurgeSettings 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559179"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="74e58-103">Lync Server 2013 中的 PurgeSettings 表格</span><span class="sxs-lookup"><span data-stu-id="74e58-103">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74e58-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="74e58-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74e58-105">PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="74e58-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="74e58-106">請注意，您也可以在 Microsoft Lync Server 2013 管理命令介面中執行下列命令，以取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="74e58-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="74e58-107">管理員應該將 PurgeSettings 表格視為唯讀：只有在使用 [新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 或 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 時，才應進行通話詳細資料清除設定的變更。</span><span class="sxs-lookup"><span data-stu-id="74e58-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="74e58-108">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="74e58-108">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74e58-109">欄</span><span class="sxs-lookup"><span data-stu-id="74e58-109">Column</span></span></th>
<th><span data-ttu-id="74e58-110">資料類型</span><span class="sxs-lookup"><span data-stu-id="74e58-110">Data Type</span></span></th>
<th><span data-ttu-id="74e58-111">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="74e58-111">Key/Index</span></span></th>
<th><span data-ttu-id="74e58-112">詳細資料</span><span class="sxs-lookup"><span data-stu-id="74e58-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74e58-113"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="74e58-113"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="74e58-114">int</span><span class="sxs-lookup"><span data-stu-id="74e58-114">int</span></span></p></td>
<td><p><span data-ttu-id="74e58-115">主要</span><span class="sxs-lookup"><span data-stu-id="74e58-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="74e58-116">CDR 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="74e58-116">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e58-117"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="74e58-117"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="74e58-118">位</span><span class="sxs-lookup"><span data-stu-id="74e58-118">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74e58-119">設為 True 時 (1) Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="74e58-119">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="74e58-120">清除動作會每天在 PurgeHour 設定中指定的時間加以執行。</span><span class="sxs-lookup"><span data-stu-id="74e58-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="74e58-121">若設為 False (0)，就不會從資料庫自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="74e58-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="74e58-122">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="74e58-122">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e58-123"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="74e58-123"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="74e58-124">int</span><span class="sxs-lookup"><span data-stu-id="74e58-124">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74e58-125">會指定要從資料庫中清除之 CDR 記錄的保留天數)  (：如果啟用清除，則舊于此值以上的 CDR 記錄會從資料庫中移除。</span><span class="sxs-lookup"><span data-stu-id="74e58-125">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="74e58-126">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="74e58-126">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e58-127"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="74e58-127"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="74e58-128">int</span><span class="sxs-lookup"><span data-stu-id="74e58-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74e58-129">指定要從資料庫中清除的錯誤報表記錄 (天數) ：若啟用清除功能，則會從資料庫中移除比此值還舊的錯誤報表記錄。</span><span class="sxs-lookup"><span data-stu-id="74e58-129">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="74e58-130">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="74e58-130">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e58-131"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="74e58-131"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="74e58-132">int</span><span class="sxs-lookup"><span data-stu-id="74e58-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="74e58-133">指定要執行資料庫清除的時間。</span><span class="sxs-lookup"><span data-stu-id="74e58-133">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="74e58-134">時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。</span><span class="sxs-lookup"><span data-stu-id="74e58-134">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="74e58-135">請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。</span><span class="sxs-lookup"><span data-stu-id="74e58-135">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="74e58-136">預設值為 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="74e58-136">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

