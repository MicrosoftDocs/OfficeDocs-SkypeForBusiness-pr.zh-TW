---
title: Lync Server 2013：媒體視圖
description: Lync Server 2013：媒體視圖。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558009"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="469f8-103">Lync Server 2013 中的媒體視圖</span><span class="sxs-lookup"><span data-stu-id="469f8-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="469f8-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="469f8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="469f8-105">媒體檢視可儲存對等工作階段中所使用之一種媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="469f8-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="469f8-106">若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。</span><span class="sxs-lookup"><span data-stu-id="469f8-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="469f8-107">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="469f8-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="469f8-p102">您不應使用媒體檢視來計算工作階段的媒體持續期間。此檢視包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。</span><span class="sxs-lookup"><span data-stu-id="469f8-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="469f8-111">Media view 包含下列的所有欄，也就是 [Lync Server 2013](lync-server-2013-sessiondetails-view.md) 中的 [SessionDetails] 視圖。</span><span class="sxs-lookup"><span data-stu-id="469f8-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="469f8-112">欄</span><span class="sxs-lookup"><span data-stu-id="469f8-112">Column</span></span></th>
<th><span data-ttu-id="469f8-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="469f8-113">Data Type</span></span></th>
<th><span data-ttu-id="469f8-114">詳細資料</span><span class="sxs-lookup"><span data-stu-id="469f8-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="469f8-115"><strong>媒體</strong></span><span class="sxs-lookup"><span data-stu-id="469f8-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="469f8-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="469f8-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="469f8-117">媒體類型。</span><span class="sxs-lookup"><span data-stu-id="469f8-117">Media type.</span></span> <span data-ttu-id="469f8-118">如需詳細資訊，請參閱 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="469f8-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="469f8-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="469f8-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="469f8-120">datetime</span><span class="sxs-lookup"><span data-stu-id="469f8-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="469f8-121">媒體要求傳送出來的時間。</span><span class="sxs-lookup"><span data-stu-id="469f8-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="469f8-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="469f8-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="469f8-123">datetime</span><span class="sxs-lookup"><span data-stu-id="469f8-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="469f8-124">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="469f8-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

