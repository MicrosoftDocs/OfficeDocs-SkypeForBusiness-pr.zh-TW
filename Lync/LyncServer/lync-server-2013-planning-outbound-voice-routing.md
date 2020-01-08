---
title: Lync Server 2013：規劃撥出語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5315b18e83b84980ff6d61e5385626e104a5e1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="33142-102">在 Lync Server 2013 中規劃撥出語音路由</span><span class="sxs-lookup"><span data-stu-id="33142-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33142-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="33142-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="33142-104">[輸出呼叫路由] 適用于發往公用交換電話網絡（PSTN）閘道、幹線或私人分支 exchange （PBX）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="33142-104">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX).</span></span> <span data-ttu-id="33142-105">當使用者撥打電話時，伺服器會根據需要將電話號碼標準化為. 164 格式，並嘗試將它與 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="33142-105">When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="33142-106">如果伺服器無法進行相符，就會根據所提供的撥號字串來套用輸出呼叫路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="33142-106">If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string.</span></span> <span data-ttu-id="33142-107">您可以透過設定下表所述的伺服器設定，來定義該邏輯。</span><span class="sxs-lookup"><span data-stu-id="33142-107">You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="33142-108">Lync Server 輸出呼叫路由設定</span><span class="sxs-lookup"><span data-stu-id="33142-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33142-109">面向</span><span class="sxs-lookup"><span data-stu-id="33142-109">Object</span></span></th>
<th><span data-ttu-id="33142-110">描述</span><span class="sxs-lookup"><span data-stu-id="33142-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33142-111">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="33142-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="33142-112">撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="33142-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33142-113">正常化規則</span><span class="sxs-lookup"><span data-stu-id="33142-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="33142-114">正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。</span><span class="sxs-lookup"><span data-stu-id="33142-114">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="33142-115">根據撥號位置，以及進行通話的人員或連絡人物件，可能會以不同方式來轉譯和翻譯相同的撥號字串。</span><span class="sxs-lookup"><span data-stu-id="33142-115">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call.</span></span> <span data-ttu-id="33142-116">與特定位置相關聯的一組正常化規則會構成撥號方案。</span><span class="sxs-lookup"><span data-stu-id="33142-116">A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33142-117">語音原則</span><span class="sxs-lookup"><span data-stu-id="33142-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="33142-118">語音原則會將一或多個 PSTN 使用記錄與一位使用者或一組使用者相關聯。</span><span class="sxs-lookup"><span data-stu-id="33142-118">A voice policy associates one or more PSTN usage records with one user or a group of users.</span></span> <span data-ttu-id="33142-119">語音原則也提供您可以啟用或停用的通話功能清單。</span><span class="sxs-lookup"><span data-stu-id="33142-119">A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33142-120">PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="33142-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="33142-121">PSTN 使用記錄會指定呼叫類別（例如內部、當地或長途），這些使用者可以由不同的使用者或使用者群組在組織中進行。</span><span class="sxs-lookup"><span data-stu-id="33142-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33142-122">通話路線</span><span class="sxs-lookup"><span data-stu-id="33142-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="33142-123">通話路由會將目的地電話號碼與特定的 trunks 和 PSTN 使用狀況記錄建立關聯。</span><span class="sxs-lookup"><span data-stu-id="33142-123">A call route associates destination phone numbers with particular trunks and PSTN usage records.</span></span> <span data-ttu-id="33142-124">PSTN 閘道被視為幹線。</span><span class="sxs-lookup"><span data-stu-id="33142-124">A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="33142-125">本節內容</span><span class="sxs-lookup"><span data-stu-id="33142-125">In This Section</span></span>

<span data-ttu-id="33142-126">本節提供設定下列出站呼叫路由伺服器設定的指導方針：</span><span class="sxs-lookup"><span data-stu-id="33142-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="33142-127">Lync Server 2013 中的撥號方案和正常化規則</span><span class="sxs-lookup"><span data-stu-id="33142-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="33142-128">Lync Server 2013 中的語音原則</span><span class="sxs-lookup"><span data-stu-id="33142-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="33142-129">Lync Server 2013 中的 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="33142-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="33142-130">Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="33142-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33142-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="33142-131">See Also</span></span>


[<span data-ttu-id="33142-132">Lync Server 2013 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="33142-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="33142-133">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="33142-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

