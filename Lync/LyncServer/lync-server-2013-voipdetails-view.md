---
title: Lync Server 2013： VoIPDetails view
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
ms.openlocfilehash: 0dc01632579c6455c47113f34e181f6598b7c781
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535380"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="d527c-102">Lync Server 2013 中的 VoIPDetails 視圖</span><span class="sxs-lookup"><span data-stu-id="d527c-102">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d527c-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d527c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d527c-104">VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。</span><span class="sxs-lookup"><span data-stu-id="d527c-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="d527c-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d527c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d527c-106">VoIPDetails view 包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。</span><span class="sxs-lookup"><span data-stu-id="d527c-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d527c-107">欄</span><span class="sxs-lookup"><span data-stu-id="d527c-107">Column</span></span></th>
<th><span data-ttu-id="d527c-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="d527c-108">Data Type</span></span></th>
<th><span data-ttu-id="d527c-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="d527c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d527c-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-111">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d527c-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d527c-112">起始工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="d527c-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d527c-113"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-114">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d527c-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d527c-115">參加工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="d527c-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d527c-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-117">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d527c-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d527c-118">中斷連線工作階段之使用者的 URI。</span><span class="sxs-lookup"><span data-stu-id="d527c-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d527c-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-120">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-121">中斷連線工作階段之使用者的 URI 類型。</span><span class="sxs-lookup"><span data-stu-id="d527c-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="d527c-122">如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="d527c-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d527c-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-124">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-125">中斷連線工作階段之使用者的租用戶。</span><span class="sxs-lookup"><span data-stu-id="d527c-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d527c-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-127">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d527c-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d527c-128">中斷連線工作階段之使用者的電話 URI。</span><span class="sxs-lookup"><span data-stu-id="d527c-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d527c-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-130">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-131">起始工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d527c-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d527c-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-133">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-134">參加工作階段之使用者所使用的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d527c-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d527c-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-136">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-137">起始工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="d527c-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d527c-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="d527c-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="d527c-139">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d527c-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d527c-140">參加工作階段之使用者所使用的閘道。</span><span class="sxs-lookup"><span data-stu-id="d527c-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

