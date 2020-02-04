---
title: Lync Server 2013： ConferenceJoinTimeThresholds 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="b98cf-102">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="b98cf-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b98cf-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b98cf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b98cf-104">ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。</span><span class="sxs-lookup"><span data-stu-id="b98cf-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="b98cf-105">[會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：</span><span class="sxs-lookup"><span data-stu-id="b98cf-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="b98cf-106">少於2秒。</span><span class="sxs-lookup"><span data-stu-id="b98cf-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="b98cf-107">介於2秒和5秒之間。</span><span class="sxs-lookup"><span data-stu-id="b98cf-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="b98cf-108">介於5秒和10秒之間。</span><span class="sxs-lookup"><span data-stu-id="b98cf-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="b98cf-109">10秒以上。</span><span class="sxs-lookup"><span data-stu-id="b98cf-109">More than 10 seconds.</span></span>

<span data-ttu-id="b98cf-110">ConferenceJoinTimeThresholds 資料表包含2秒、5秒和10秒的分類值。</span><span class="sxs-lookup"><span data-stu-id="b98cf-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="b98cf-111">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="b98cf-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b98cf-112">左欄</span><span class="sxs-lookup"><span data-stu-id="b98cf-112">Column</span></span></th>
<th><span data-ttu-id="b98cf-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="b98cf-113">Data Type</span></span></th>
<th><span data-ttu-id="b98cf-114">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="b98cf-114">Key/Index</span></span></th>
<th><span data-ttu-id="b98cf-115">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b98cf-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b98cf-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="b98cf-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="b98cf-117">int</span><span class="sxs-lookup"><span data-stu-id="b98cf-117">int</span></span></p></td>
<td><p><span data-ttu-id="b98cf-118">首選</span><span class="sxs-lookup"><span data-stu-id="b98cf-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="b98cf-119">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b98cf-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b98cf-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="b98cf-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="b98cf-121">int</span><span class="sxs-lookup"><span data-stu-id="b98cf-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b98cf-122">分類的上限。</span><span class="sxs-lookup"><span data-stu-id="b98cf-122">Upper limit for the classification.</span></span> <span data-ttu-id="b98cf-123">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b98cf-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="b98cf-124">2</span><span class="sxs-lookup"><span data-stu-id="b98cf-124">2</span></span></p></li>
<li><p><span data-ttu-id="b98cf-125">500</span><span class="sxs-lookup"><span data-stu-id="b98cf-125">5</span></span></p></li>
<li><p><span data-ttu-id="b98cf-126">第</span><span class="sxs-lookup"><span data-stu-id="b98cf-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

