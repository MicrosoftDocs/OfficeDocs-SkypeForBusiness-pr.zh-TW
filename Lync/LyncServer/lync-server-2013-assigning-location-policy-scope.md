---
title: Lync Server 2013：指派位置原則範圍
description: Lync Server 2013：指派位置原則範圍。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6c46150241b0b224e8005556c0f2f594d8bce5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563379"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="a398a-103">在 Lync Server 2013 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="a398a-103">Assigning location policy scope in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a398a-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="a398a-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="a398a-105">與其他 Lync Server 原則一樣，位置原則可以指派于多個範圍層級：全域、網站和使用者。</span><span class="sxs-lookup"><span data-stu-id="a398a-105">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="a398a-106">不過，使用者層級位置原則的範圍會與其他 Lync Server 原則的行為稍有不同。</span><span class="sxs-lookup"><span data-stu-id="a398a-106">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="a398a-107">每位使用者的位置原則不僅可以套用至端點物件 (例如使用者和公共區域電話連絡人物件) ，也可以套用至 Lync Server 網路網站。</span><span class="sxs-lookup"><span data-stu-id="a398a-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="a398a-108">網路網站是與地理位置相關聯之用戶端子網的群組 (但不一定是整個中央網站或分支網站) 中的所有子網。</span><span class="sxs-lookup"><span data-stu-id="a398a-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="a398a-109">任何連接至網路網站之子網的用戶端，都會自動挑選指派給該網路網站的位置原則。</span><span class="sxs-lookup"><span data-stu-id="a398a-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="a398a-110">在將使用者層級位置原則指派給使用者和網路網站時，網路網站型位置原則會覆寫任何個別使用者原則設定。</span><span class="sxs-lookup"><span data-stu-id="a398a-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="a398a-111">每個網站都有指派的位置原則，且每個原則都具有指派給它的不同 PSTN 使用方式、通知 URIs 和會議 URIs 值。</span><span class="sxs-lookup"><span data-stu-id="a398a-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a398a-112">這種特殊原則範圍行為的原因在於，當位於一個 office 網站上的集區的使用者要訪問另一個網站並必須撥打緊急電話時，就會套用適當于該網路網站的 E9-1-1 通話路由設定，不論使用者指派的集區或網站為何。</span><span class="sxs-lookup"><span data-stu-id="a398a-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

