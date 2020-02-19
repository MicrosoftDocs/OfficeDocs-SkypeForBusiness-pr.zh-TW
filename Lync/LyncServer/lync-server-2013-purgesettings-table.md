---
title: 'Lync Server 2013: PurgeSettings 表'
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
ms.openlocfilehash: c44ad3541b4de3ac45169a01b14b2d571ed11b23
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="2d1c6-102">Lync Server 2013 中的 PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="2d1c6-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d1c6-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="2d1c6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2d1c6-104">PurgeSettings 表包含指定是否 （時） 的資訊從 CDR 資料庫會自動刪除過期的通話詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="2d1c6-105">請注意，清除的相關資訊，還可以取得從 Microsoft Lync Server 2013 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2d1c6-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="2d1c6-106">系統管理員應將 PurgeSettings 表格視為唯讀： 通話詳細資料的清除設定應該只會變更使用[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="2d1c6-107">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d1c6-108">欄</span><span class="sxs-lookup"><span data-stu-id="2d1c6-108">Column</span></span></th>
<th><span data-ttu-id="2d1c6-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="2d1c6-109">Data Type</span></span></th>
<th><span data-ttu-id="2d1c6-110">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="2d1c6-110">Key/Index</span></span></th>
<th><span data-ttu-id="2d1c6-111">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2d1c6-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d1c6-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="2d1c6-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="2d1c6-113">int</span><span class="sxs-lookup"><span data-stu-id="2d1c6-113">int</span></span></p></td>
<td><p><span data-ttu-id="2d1c6-114">主要</span><span class="sxs-lookup"><span data-stu-id="2d1c6-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="2d1c6-115">唯一識別項集合的 CDR 清除設定。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d1c6-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="2d1c6-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="2d1c6-117">位元</span><span class="sxs-lookup"><span data-stu-id="2d1c6-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d1c6-118">當設為 True （1) Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過期的記錄。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="2d1c6-119">清除動作會每天在 PurgeHour 設定中指定的時間加以執行。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="2d1c6-120">若設為 False (0)，就不會從資料庫自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="2d1c6-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d1c6-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="2d1c6-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="2d1c6-123">int</span><span class="sxs-lookup"><span data-stu-id="2d1c6-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d1c6-124">指定的保留天數會從資料庫中清除的 CDR 記錄 （以天數）： 如果啟用 [清除]，將會從資料庫中移除 CDR 記錄超過此值。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="2d1c6-125">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d1c6-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="2d1c6-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="2d1c6-127">int</span><span class="sxs-lookup"><span data-stu-id="2d1c6-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d1c6-128">指定錯誤報告中的記錄 （天），將會從資料庫中清除存留期： 如果啟用 [清除]，將會從資料庫中移除錯誤報告的記錄超過此值。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="2d1c6-129">預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d1c6-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="2d1c6-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="2d1c6-131">int</span><span class="sxs-lookup"><span data-stu-id="2d1c6-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d1c6-132">指定要執行資料庫清除的時間。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="2d1c6-133">時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="2d1c6-134">請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="2d1c6-135">預設值為 2 (2:00 AM)。</span><span class="sxs-lookup"><span data-stu-id="2d1c6-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

