---
title: Lync Server 2013：通話許可控制和中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="c6434-102">Lync Server 2013 中的通話許可控制和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c6434-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6434-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c6434-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c6434-104">呼叫許可控制（CAC），第一次在 Lync Server 2010 中引入，可根據可用的頻寬來管理即時會話建立，以協助避免使用者在擁擠的網路上出現品質欠佳（QoE）。</span><span class="sxs-lookup"><span data-stu-id="c6434-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="c6434-105">若要支援這項功能，您可以在企業語音結構和閘道或 SIP 中繼提供者之間提供信號與媒體翻譯的中繼伺服器，負責在 Lync 上的兩個互動進行頻寬管理伺服器端和閘道端。</span><span class="sxs-lookup"><span data-stu-id="c6434-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="c6434-106">在 [呼叫許可控制] 中，通話的終止實體會處理頻寬保留。</span><span class="sxs-lookup"><span data-stu-id="c6434-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="c6434-107">在閘道端與中繼伺服器互動的閘道對等（PSTN 閘道、IP PBX、SBC）不支援 Lync Server 2013 通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="c6434-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="c6434-108">因此，中繼伺服器必須代表其閘道對等來處理頻寬互動。</span><span class="sxs-lookup"><span data-stu-id="c6434-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="c6434-109">只要有可能，中繼伺服器就會提前保留頻寬。</span><span class="sxs-lookup"><span data-stu-id="c6434-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="c6434-110">如果無法這樣做（例如，如果閘道端的最終媒體端點的位置不適供撥出電話到閘道對等），則會在撥打電話時保留頻寬。</span><span class="sxs-lookup"><span data-stu-id="c6434-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="c6434-111">這種行為可能會導致過度訂閱頻寬，但這是避免誤報的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="c6434-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="c6434-112">[媒體旁路] 和 [頻寬保留] 是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="c6434-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="c6434-113">如果使用媒體旁路進行通話，就不會針對該通話執行呼叫許可控制。</span><span class="sxs-lookup"><span data-stu-id="c6434-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="c6434-114">這裡的假設是通話中沒有受限制頻寬的連結。</span><span class="sxs-lookup"><span data-stu-id="c6434-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="c6434-115">如果呼叫許可控制是用於涉及轉送伺服器的特定通話，該呼叫無法使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="c6434-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="c6434-116">如需媒體旁路或呼叫許可控制的詳細資料，請參閱規劃檔中的[lync server 2013 規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)或在[lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c6434-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

