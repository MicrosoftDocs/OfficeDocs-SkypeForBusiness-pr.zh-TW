---
title: Lync Server 2013： PurgeSettings table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46516be447fa3099afe492e5edc4f4008ea5a079
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="1e4de-102">Lync Server 2013 中的 PurgeSettings table （QoE）</span><span class="sxs-lookup"><span data-stu-id="1e4de-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e4de-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1e4de-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1e4de-104">PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。</span><span class="sxs-lookup"><span data-stu-id="1e4de-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="1e4de-105">請注意，您也可以透過執行下列命令，在 Microsoft Lync Server 2013 管理命令介面中取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="1e4de-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="1e4de-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="1e4de-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e4de-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1e4de-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1e4de-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1e4de-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e4de-111"><strong>標識號</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1e4de-112">int</span><span class="sxs-lookup"><span data-stu-id="1e4de-112">int</span></span></p></td>
<td><p><span data-ttu-id="1e4de-113">首選</span><span class="sxs-lookup"><span data-stu-id="1e4de-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1e4de-114">QoE 清除設定集合的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1e4de-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e4de-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="1e4de-116">稍微</span><span class="sxs-lookup"><span data-stu-id="1e4de-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e4de-117">當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 QoE 資料庫清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="1e4de-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="1e4de-118">[清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。</span><span class="sxs-lookup"><span data-stu-id="1e4de-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="1e4de-119">如果設定為 False （0），則不會自動從資料庫清除記錄。</span><span class="sxs-lookup"><span data-stu-id="1e4de-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="1e4de-120">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="1e4de-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e4de-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="1e4de-122">int</span><span class="sxs-lookup"><span data-stu-id="1e4de-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e4de-123">指定將從資料庫清除的 QoE 記錄（天）期限：如果已啟用清除，則會從資料庫中移除超過此值的 QoE 記錄。</span><span class="sxs-lookup"><span data-stu-id="1e4de-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="1e4de-124">預設值為60天。</span><span class="sxs-lookup"><span data-stu-id="1e4de-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e4de-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="1e4de-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="1e4de-126">int</span><span class="sxs-lookup"><span data-stu-id="1e4de-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1e4de-127">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="1e4de-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="1e4de-128">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="1e4de-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="1e4de-129">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="1e4de-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="1e4de-130">預設值為1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="1e4de-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="1e4de-131">指定要在進行資料庫清除時的當地時間。</span><span class="sxs-lookup"><span data-stu-id="1e4de-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="1e4de-132">時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。</span><span class="sxs-lookup"><span data-stu-id="1e4de-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="1e4de-133">請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="1e4de-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="1e4de-134">預設值為1（1:00 AM）。</span><span class="sxs-lookup"><span data-stu-id="1e4de-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

