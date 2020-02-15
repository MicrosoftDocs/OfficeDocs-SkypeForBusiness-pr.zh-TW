---
title: Lync Server 2013： 規劃撥出語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fbcb976ed4f3d1464b6b956ef60dc1d00bd6907
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="1d646-102">規劃 Lync Server 2013 中的撥出語音路由</span><span class="sxs-lookup"><span data-stu-id="1d646-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d646-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="1d646-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1d646-p101">撥出電話路由適用於以公用交換電話網路 (PSTN) 閘道、主幹或專用交換機 (PBX) 為目的地的電話。當使用者撥打電話時，伺服器就會在必要時將電話號碼正規化成 E.164 格式，並嘗試比對電話號碼與 SIP URI。如果伺服器無法成功進行比對，就會根據提供的撥號字串套用撥出電話的路由邏輯。您可以依下表所述進行伺服器設定，以便定義該邏輯。</span><span class="sxs-lookup"><span data-stu-id="1d646-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="1d646-108">Lync Server 撥出電話路由設定</span><span class="sxs-lookup"><span data-stu-id="1d646-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d646-109">物件</span><span class="sxs-lookup"><span data-stu-id="1d646-109">Object</span></span></th>
<th><span data-ttu-id="1d646-110">描述</span><span class="sxs-lookup"><span data-stu-id="1d646-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d646-111">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="1d646-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="1d646-112">撥號對應表是一個具名的正規化規則集，可將具名位置、個別使用者或連絡人物件的電話號碼轉譯成單一標準 (E.164) 格式，以便進行電話授權和電話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="1d646-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d646-113">正規化規則</span><span class="sxs-lookup"><span data-stu-id="1d646-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="1d646-p102">正規化規則會針對每個指定位置、使用者或連絡人物件，定義要如何路由傳送以各種格式表達的電話號碼。相同的撥號字串可能會因撥號地點的位置，以及撥打電話的人員或連絡人物件而有不同的解譯和轉譯。撥號對應表即是一組與特定位置相關的正規化規則。</span><span class="sxs-lookup"><span data-stu-id="1d646-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d646-117">語音原則</span><span class="sxs-lookup"><span data-stu-id="1d646-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="1d646-p103">語音原則會讓一個或多個 PSTN 使用方式記錄與一個使用者或使用者群組產生關聯。語音原則也會提供您可啟用或停用之撥號功能的清單。</span><span class="sxs-lookup"><span data-stu-id="1d646-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d646-120">PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="1d646-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="1d646-121">PSTN 使用方式記錄會指定組織內的各個使用者或使用者群組可以進行的通話等級 (例如內線、當地或長途電話)。</span><span class="sxs-lookup"><span data-stu-id="1d646-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d646-122">電話路由</span><span class="sxs-lookup"><span data-stu-id="1d646-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="1d646-p104">電話路由會讓目的地電話號碼與特定主幹和 PSTN 使用方式記錄產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1d646-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="1d646-125">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1d646-125">In This Section</span></span>

<span data-ttu-id="1d646-126">本節提供設定下列撥出電話路由伺服器設定的指導方針：</span><span class="sxs-lookup"><span data-stu-id="1d646-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="1d646-127">撥號對應表和 Lync Server 2013 中的正規化規則</span><span class="sxs-lookup"><span data-stu-id="1d646-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="1d646-128">Lync Server 2013 中的語音原則</span><span class="sxs-lookup"><span data-stu-id="1d646-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="1d646-129">Lync Server 2013 中的 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="1d646-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="1d646-130">Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="1d646-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d646-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1d646-131">See Also</span></span>


[<span data-ttu-id="1d646-132">Lync Server 2013 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="1d646-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="1d646-133">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="1d646-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

