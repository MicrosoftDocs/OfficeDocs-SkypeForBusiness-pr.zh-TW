---
title: 'Lync Server 2013： PurgeSettings table (QoE) '
description: Lync Server 2013： PurgeSettings table (QoE) 。
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
ms.openlocfilehash: d515d799a7cc442dc6d34f2ece1a968de51cdad6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571439"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="8eabe-103">在 Lync Server 2013 中 PurgeSettings table (QoE) </span><span class="sxs-lookup"><span data-stu-id="8eabe-103">PurgeSettings table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8eabe-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8eabe-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8eabe-105">PurgeSettings 資料表包含指定在經驗品質記錄過期時，會自動從 QoE 資料庫加以刪除的資訊。</span><span class="sxs-lookup"><span data-stu-id="8eabe-105">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="8eabe-106">請注意，您也可以在 Microsoft Lync Server 2013 管理命令介面中執行下列命令，以取得清除相關資訊：</span><span class="sxs-lookup"><span data-stu-id="8eabe-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="8eabe-107">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8eabe-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8eabe-108"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8eabe-109"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8eabe-110"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8eabe-111"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8eabe-112"><strong>識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-112"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8eabe-113">int</span><span class="sxs-lookup"><span data-stu-id="8eabe-113">int</span></span></p></td>
<td><p><span data-ttu-id="8eabe-114">主要</span><span class="sxs-lookup"><span data-stu-id="8eabe-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="8eabe-115">QoE 清除設定集的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="8eabe-115">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eabe-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="8eabe-117">位</span><span class="sxs-lookup"><span data-stu-id="8eabe-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8eabe-118">設為 True 時 (1) Microsoft Lync Server 2013 會定期從 QoE 資料庫中清除過時的記錄。</span><span class="sxs-lookup"><span data-stu-id="8eabe-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="8eabe-119">清除動作會每天在 PurgeHour 設定中指定的時間加以執行。</span><span class="sxs-lookup"><span data-stu-id="8eabe-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="8eabe-120">若設為 False (0)，就不會從資料庫自動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="8eabe-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="8eabe-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="8eabe-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8eabe-122"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-122"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="8eabe-123">int</span><span class="sxs-lookup"><span data-stu-id="8eabe-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8eabe-p103">指定要從資料庫清除之 QoE 記錄的存留期 (以天數為單位)：若啟用清除，就會從資料庫移除舊於此值的 QoE。預設值為 60 天。</span><span class="sxs-lookup"><span data-stu-id="8eabe-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8eabe-126"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="8eabe-126"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="8eabe-127">int</span><span class="sxs-lookup"><span data-stu-id="8eabe-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8eabe-p104">指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。指定要執行資料庫清除的時間。時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。預設值為 1 (上午 1:00)。</span><span class="sxs-lookup"><span data-stu-id="8eabe-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

