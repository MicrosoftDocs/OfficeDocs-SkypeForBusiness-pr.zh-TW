---
title: Lync Server 2013：通話許可控制和轉送伺服器
description: Lync Server 2013：通話許可控制和轉送伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e4b12a11f941923d50f3ffcab7a8f9b6a9edc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569219"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="4fb6c-103">Lync Server 2013 中的通話許可控制和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="4fb6c-103">Call admission control and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fb6c-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4fb6c-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4fb6c-105">通話許可控制 (CAC) ，第一次引進于 Lync Server 2010，它會根據可用的頻寬來管理即時會話建立，以協助避免使用者在擁擠的網路上 (QoE) 的品質欠佳。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-105">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="4fb6c-106">為了支援此功能，在企業語音基礎結構與閘道或 SIP 主幹提供者之間提供信號和媒體翻譯的轉送伺服器，負責其在 Lync Server 端和閘道端的兩個互動的頻寬管理。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-106">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="4fb6c-107">在通話許可控制服務中，通話的終端實體負責處理頻寬保留。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-107">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="4fb6c-108">轉送伺服器與閘道端互動的「閘道對等」 (PSTN 閘道、IP-PBX、SBC) ，都不支援 Lync Server 2013 通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-108">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="4fb6c-109">因此，轉送伺服器必須代表其閘道對等處理頻寬互動。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-109">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="4fb6c-110">轉送伺服器會在任何可能的情況下，預先保留頻寬。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-110">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="4fb6c-111">如果情況不允許 (例如，撥出至閘道對等時，如果閘道端上最終媒體端點的位置不明)，則會在撥打電話時保留頻寬。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-111">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="4fb6c-112">此行為可能會導致頻寬超額的情況，但這是防止撥號錯誤的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-112">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="4fb6c-113">媒體旁路與頻寬保留是互斥的。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-113">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="4fb6c-114">如果對某通電話使用了媒體旁路，即無法再對其執行通話許可控制服務。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-114">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="4fb6c-115">此處是假設與電話有關的連結都沒有頻寬受限的情形。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-115">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="4fb6c-116">如果通話許可控制用於涉及轉送伺服器的特定通話，則該呼叫無法使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-116">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="4fb6c-117">如需媒體旁路或通話許可控制的詳細資訊，請參閱規劃檔中的在 lync server [2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md) 或 [在 lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="4fb6c-117">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

