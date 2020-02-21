---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds 表'
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
ms.openlocfilehash: 6d6ce43adee4c00a945325cf31c4194816e7ee14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="4458a-102">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="4458a-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4458a-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="4458a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4458a-p101">ConferenceJoinTimeThresholds 表格中包含「會議加入時間摘要報告」所使用的分類界限。「會議加入時間摘要報告」摘要說明了使用者成功加入會議所需的時間；在報告中這些時間值會以平均值及下列其中一項類別表示：</span><span class="sxs-lookup"><span data-stu-id="4458a-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="4458a-106">少於 2 秒。</span><span class="sxs-lookup"><span data-stu-id="4458a-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="4458a-107">介於 2 秒和 5 秒之間。</span><span class="sxs-lookup"><span data-stu-id="4458a-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="4458a-108">介於 5 秒和 10 秒之間。</span><span class="sxs-lookup"><span data-stu-id="4458a-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="4458a-109">超過 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4458a-109">More than 10 seconds.</span></span>

<span data-ttu-id="4458a-110">ConferenceJoinTimeThresholds 表格包含 2 秒、5 秒及 10 秒的分類值。</span><span class="sxs-lookup"><span data-stu-id="4458a-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="4458a-111">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="4458a-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4458a-112">欄</span><span class="sxs-lookup"><span data-stu-id="4458a-112">Column</span></span></th>
<th><span data-ttu-id="4458a-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="4458a-113">Data Type</span></span></th>
<th><span data-ttu-id="4458a-114">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="4458a-114">Key/Index</span></span></th>
<th><span data-ttu-id="4458a-115">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4458a-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4458a-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="4458a-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="4458a-117">int</span><span class="sxs-lookup"><span data-stu-id="4458a-117">int</span></span></p></td>
<td><p><span data-ttu-id="4458a-118">主要</span><span class="sxs-lookup"><span data-stu-id="4458a-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4458a-119">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="4458a-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4458a-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="4458a-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="4458a-121">int</span><span class="sxs-lookup"><span data-stu-id="4458a-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4458a-p102">分類的上限。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="4458a-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="4458a-124">2</span><span class="sxs-lookup"><span data-stu-id="4458a-124">2</span></span></p></li>
<li><p><span data-ttu-id="4458a-125">5</span><span class="sxs-lookup"><span data-stu-id="4458a-125">5</span></span></p></li>
<li><p><span data-ttu-id="4458a-126">10 </span><span class="sxs-lookup"><span data-stu-id="4458a-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

