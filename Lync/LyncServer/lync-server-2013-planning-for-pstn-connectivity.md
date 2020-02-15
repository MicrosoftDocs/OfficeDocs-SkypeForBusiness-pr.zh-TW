---
title: Lync Server 2013： 規劃 PSTN 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f69e8286e341b7769a58d03c42d0a43e63075
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="626dc-102">規劃 Lync Server 2013 中的 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="626dc-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="626dc-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="626dc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="626dc-104">企業等級的 VoIP 解決方案必須提供與公用交換電話網路 (PSTN) 之間的往來通話，且不犧牲任何服務品質 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="626dc-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="626dc-105">撥打及接聽通話的使用者不應該要知道的基礎技術： 從使用者觀點來看，Enterprise Voice 基礎結構與 PSTN 之間的通話應該看起來像另一個電話。</span><span class="sxs-lookup"><span data-stu-id="626dc-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="626dc-106">Lync Server 2013 提供可靠而具擴充性的 PSTN 連線使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="626dc-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="626dc-107">網際網路電話語音服務提供者 (ITSP) 的 **SIP 主幹**</span><span class="sxs-lookup"><span data-stu-id="626dc-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="626dc-108">對 PSTN 閘道的**直接 SIP 連線**</span><span class="sxs-lookup"><span data-stu-id="626dc-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="626dc-109">對 PBX 的**直接 SIP 連線**</span><span class="sxs-lookup"><span data-stu-id="626dc-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="626dc-110">視企業的規模、地理環境與現有語音基礎結構之不同，企業在不同的位置可使用其中一或兩個選項，甚至三個都使用。</span><span class="sxs-lookup"><span data-stu-id="626dc-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="626dc-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="626dc-111">In This Section</span></span>

  - [<span data-ttu-id="626dc-112">Lync Server 2013 中的 SIP 主幹</span><span class="sxs-lookup"><span data-stu-id="626dc-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="626dc-113">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="626dc-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="626dc-114">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="626dc-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="626dc-115">Lync Server 2013 中的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="626dc-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="626dc-116">規劃 Lync Server 2013 中的撥出語音路由</span><span class="sxs-lookup"><span data-stu-id="626dc-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

