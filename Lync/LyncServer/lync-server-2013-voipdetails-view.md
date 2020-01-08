---
title: Lync Server 2013： VoIPDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="aa416-102">Lync Server 2013 中的 [VoIPDetails] 視圖</span><span class="sxs-lookup"><span data-stu-id="aa416-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa416-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="aa416-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="aa416-104">[VoIPDetails] 視圖儲存點對點工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="aa416-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="aa416-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="aa416-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa416-106">[VoIPDetails] 視圖會包含 [ <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013</A> ] 的 [SessionDetails] 視圖中的所有資料行，以及下列所列的欄。</span><span class="sxs-lookup"><span data-stu-id="aa416-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa416-107">左欄</span><span class="sxs-lookup"><span data-stu-id="aa416-107">Column</span></span></th>
<th><span data-ttu-id="aa416-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="aa416-108">Data Type</span></span></th>
<th><span data-ttu-id="aa416-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="aa416-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa416-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-111">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aa416-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa416-112">啟動會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="aa416-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa416-113"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-114">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aa416-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa416-115">加入會話之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="aa416-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa416-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-117">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aa416-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa416-118">中斷會話的使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="aa416-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa416-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-120">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-121">中斷會話的使用者 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="aa416-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="aa416-122">如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</span><span class="sxs-lookup"><span data-stu-id="aa416-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa416-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-124">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-125">中斷會話的使用者租使用者。</span><span class="sxs-lookup"><span data-stu-id="aa416-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa416-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-127">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="aa416-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa416-128">中斷會話的使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="aa416-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa416-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-130">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-131">啟動會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="aa416-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa416-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-133">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-134">加入會話的使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="aa416-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa416-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-136">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-137">啟動會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="aa416-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa416-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="aa416-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="aa416-139">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="aa416-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa416-140">加入會話的使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="aa416-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

