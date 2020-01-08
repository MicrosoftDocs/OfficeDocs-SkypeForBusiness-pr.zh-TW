---
title: Lync Server 2013：指派位置原則範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c44bef383690856d873d64ab6218b0f14219e73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="0cbff-102">在 Lync Server 2013 中指派位置原則範圍</span><span class="sxs-lookup"><span data-stu-id="0cbff-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cbff-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="0cbff-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="0cbff-104">與其他 Lync 伺服器原則一樣，位置原則可以在多個範圍層級指派：全域、網站和使用者。</span><span class="sxs-lookup"><span data-stu-id="0cbff-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="0cbff-105">不過，使用者層級位置原則的運作方式比其他 Lync 伺服器原則稍有不同。</span><span class="sxs-lookup"><span data-stu-id="0cbff-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="0cbff-106">您不僅可以將每個使用者的位置原則套用到端點物件（例如使用者和常見的區域電話連絡人物件），也可以將它們套用至 Lync Server network 網站。</span><span class="sxs-lookup"><span data-stu-id="0cbff-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="0cbff-107">網路網站是與地理位置相關聯的用戶端子網群組（但不一定是整個中央網站或分支網站中的所有子網）。</span><span class="sxs-lookup"><span data-stu-id="0cbff-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="0cbff-108">連接至網路網站中子網的任何用戶端，都會自動挑選指派給該網路網站的位置原則。</span><span class="sxs-lookup"><span data-stu-id="0cbff-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="0cbff-109">在使用者層級位置原則指派給使用者和網路網站的情況下，網路網站的位置原則會覆寫任何每個使用者的原則設定。</span><span class="sxs-lookup"><span data-stu-id="0cbff-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="0cbff-110">每個網路網站都有一個指派的位置原則，而每個原則都有不同的 PSTN 用法、通知 Uri 以及指派給它的會議 Uri 值。</span><span class="sxs-lookup"><span data-stu-id="0cbff-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cbff-111">這個特殊原則範圍行為的原因是，當使用者位於某個 office 網站上的某個召集人造訪另一個網站，而且必須撥打電話時，無論該網路網站是哪個池或網站，都不需要使用 E9-1-1 呼叫路由設定ser 指派給您。</span><span class="sxs-lookup"><span data-stu-id="0cbff-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

