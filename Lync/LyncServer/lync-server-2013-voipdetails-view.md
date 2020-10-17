---
title: Lync Server 2013： VoIPDetails view
description: Lync Server 2013： VoIPDetails view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566199"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="2a694-103">Lync Server 2013 中的 VoIPDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="2a694-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a694-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2a694-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2a694-105">VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="2a694-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="2a694-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2a694-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a694-107">VoIPDetails view 包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。</span><span class="sxs-lookup"><span data-stu-id="2a694-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a694-108">欄</span><span class="sxs-lookup"><span data-stu-id="2a694-108">Column</span></span></th>
<th><span data-ttu-id="2a694-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="2a694-109">Data Type</span></span></th>
<th><span data-ttu-id="2a694-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2a694-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a694-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-112">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2a694-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2a694-113">起始工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2a694-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a694-114"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-115">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2a694-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2a694-116">參加工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2a694-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a694-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-118">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2a694-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2a694-119">中斷連線工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="2a694-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a694-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-121">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-122">中斷連線工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="2a694-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="2a694-123">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2a694-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a694-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-125">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-126">中斷連線工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="2a694-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a694-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-128">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2a694-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2a694-129">中斷連線工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="2a694-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a694-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-132">起始工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2a694-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a694-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-134">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-135">參加工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="2a694-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a694-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-137">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-138">起始工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="2a694-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a694-139"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2a694-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2a694-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2a694-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a694-141">參加工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="2a694-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

