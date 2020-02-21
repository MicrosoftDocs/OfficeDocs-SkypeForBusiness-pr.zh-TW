---
title: Lync Server 2013： 指派位置原則範圍
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
ms.openlocfilehash: b436c52b89ce9e396d93669c09cdadeef10260e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="9ec55-102">指派 Lync Server 2013 中的位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="9ec55-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ec55-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="9ec55-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="9ec55-104">為以其他 Lync Server 的原則，可以位置原則指派多個範圍層級： 全域、 網站及使用者。</span><span class="sxs-lookup"><span data-stu-id="9ec55-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="9ec55-105">不過，使用者層級位置原則範圍行為與其他 Lync Server 原則元方式不同。</span><span class="sxs-lookup"><span data-stu-id="9ec55-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="9ec55-106">不僅可以個別使用者位置原則套用至端點物件 （例如使用者和一般區域電話連絡人物件），它們也可以套用至 Lync Server 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="9ec55-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="9ec55-107">網路網站相關聯的地理位置的子網路會分組的用戶端 （但不是一定是在整個中央站台或分支網站中的所有子網路）。</span><span class="sxs-lookup"><span data-stu-id="9ec55-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="9ec55-108">自動連線至網路網站中的子網路的任何用戶端中挑選指派給該網路站台的位置原則。</span><span class="sxs-lookup"><span data-stu-id="9ec55-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="9ec55-109">在使用者層級位置原則指派給使用者與網路網站的情況下，網路網站為基礎的位置原則會覆寫任何個別使用者原則設定。</span><span class="sxs-lookup"><span data-stu-id="9ec55-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="9ec55-110">各網站皆位置原則指派給它，而每個原則會有不同的 PSTN 使用方式、 通知 Uri、 以及會議 Uri 值指派給它。</span><span class="sxs-lookup"><span data-stu-id="9ec55-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ec55-111">此特殊原則範圍行為是，這樣當使用者某一集區在某辦公室網站瀏覽其他網站且需撥打緊急電話，E9-1-1 通話路由設定適用於該網路站台的原因會套用不論何種集區或網站 user 為指派給。</span><span class="sxs-lookup"><span data-stu-id="9ec55-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

