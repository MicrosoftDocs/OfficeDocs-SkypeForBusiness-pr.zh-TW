---
title: Lync Server 2013： 通話許可控制和中繼伺服器
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
ms.openlocfilehash: 6cbf738bbd0bd66834082983f78de56bb23bfc33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="355e4-102">通話許可控制和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="355e4-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="355e4-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="355e4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="355e4-104">通話許可控制 (CAC)、 第一次導入在 Lync Server 2010 中，管理即時工作階段建立，根據可用頻寬，以協助防止不佳的經驗品質 (QoE) 擁塞網路上的使用者。</span><span class="sxs-lookup"><span data-stu-id="355e4-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="355e4-105">若要支援此功能，中繼伺服器，可提供企業語音基礎結構和閘道或 SIP 主幹提供者之間的訊號和媒體轉譯，負責在 Lync 其兩個互動的頻寬管理左側與閘道端伺服器。</span><span class="sxs-lookup"><span data-stu-id="355e4-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="355e4-106">在通話許可控制服務中，通話的終端實體負責處理頻寬保留。</span><span class="sxs-lookup"><span data-stu-id="355e4-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="355e4-107">中繼伺服器與閘道端互動閘道對等 （PSTN 閘道、 IP PBX、 SBC） 不支援 Lync Server 2013 通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="355e4-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="355e4-108">因此，中繼伺服器已處理代表其閘道對等網路頻寬互動。</span><span class="sxs-lookup"><span data-stu-id="355e4-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="355e4-109">請盡可能中繼伺服器將會事先預約頻寬。</span><span class="sxs-lookup"><span data-stu-id="355e4-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="355e4-110">如果情況不允許 (例如，撥出至閘道對等時，如果閘道端上最終媒體端點的位置不明)，則會在撥打電話時保留頻寬。</span><span class="sxs-lookup"><span data-stu-id="355e4-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="355e4-111">此行為可能會導致頻寬超額的情況，但這是防止撥號錯誤的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="355e4-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="355e4-112">媒體旁路與頻寬保留是互斥的。</span><span class="sxs-lookup"><span data-stu-id="355e4-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="355e4-113">如果對某通電話使用了媒體旁路，即無法再對其執行通話許可控制服務。</span><span class="sxs-lookup"><span data-stu-id="355e4-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="355e4-114">此處是假設與電話有關的連結都沒有頻寬受限的情形。</span><span class="sxs-lookup"><span data-stu-id="355e4-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="355e4-115">如果使用牽涉到中繼伺服器的特定呼叫的通話許可控制，則該通話無法使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="355e4-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="355e4-116">如需詳細資訊的媒體旁路或通話許可控制，請參閱[規劃媒體旁路 Lync Server 2013 中](lync-server-2013-planning-for-media-bypass.md)or [Planning for Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md)中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="355e4-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

