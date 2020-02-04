---
title: Lync Server 2013：媒體視圖
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
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="9e170-102">Lync Server 2013 中的媒體視圖</span><span class="sxs-lookup"><span data-stu-id="9e170-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e170-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9e170-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9e170-104">媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9e170-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="9e170-105">如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。</span><span class="sxs-lookup"><span data-stu-id="9e170-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="9e170-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="9e170-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e170-107">媒體視圖不應該用來計算會話的媒體持續時間。</span><span class="sxs-lookup"><span data-stu-id="9e170-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="9e170-108">此視圖包含會話中媒體交換的信號詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9e170-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="9e170-109">媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在接受會話之後才會啟動。</span><span class="sxs-lookup"><span data-stu-id="9e170-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="9e170-110">媒體視圖在[Lync Server 2013](lync-server-2013-sessiondetails-view.md)的 [SessionDetails] 視圖中，除了下面所列的所有欄之外，還有其中一個資料行。</span><span class="sxs-lookup"><span data-stu-id="9e170-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e170-111">左欄</span><span class="sxs-lookup"><span data-stu-id="9e170-111">Column</span></span></th>
<th><span data-ttu-id="9e170-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="9e170-112">Data Type</span></span></th>
<th><span data-ttu-id="9e170-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9e170-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e170-114"><strong>媒體</strong></span><span class="sxs-lookup"><span data-stu-id="9e170-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="9e170-115">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="9e170-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9e170-116">媒體類型。</span><span class="sxs-lookup"><span data-stu-id="9e170-116">Media type.</span></span> <span data-ttu-id="9e170-117">如需詳細資訊，請參閱<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中</a>的 [MediaList] 資料表。</span><span class="sxs-lookup"><span data-stu-id="9e170-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e170-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9e170-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9e170-119">datetime</span><span class="sxs-lookup"><span data-stu-id="9e170-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="9e170-120">媒體要求的傳送時間。</span><span class="sxs-lookup"><span data-stu-id="9e170-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e170-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9e170-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9e170-122">datetime</span><span class="sxs-lookup"><span data-stu-id="9e170-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="9e170-123">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="9e170-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

