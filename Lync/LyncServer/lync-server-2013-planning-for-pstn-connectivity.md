---
title: Lync Server 2013：規劃 PSTN 連線性
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
ms.openlocfilehash: ec12aa5e579aed30e61c7cd34eab444e807c628f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="8d87b-102">在 Lync Server 2013 規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="8d87b-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d87b-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8d87b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8d87b-104">企業級 VoIP 解決方案必須提供呼叫及從公開的交換電話網絡（PSTN）撥打電話，而不會拒絕服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="8d87b-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="8d87b-105">撥打及接聽來電的使用者不應該知道基礎技術：從使用者的角度來看，企業語音結構和 PSTN 之間的通話看起來就像是另一個電話撥。</span><span class="sxs-lookup"><span data-stu-id="8d87b-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="8d87b-106">Lync Server 2013 使用下列選項提供可靠、可伸縮的 PSTN 連線：</span><span class="sxs-lookup"><span data-stu-id="8d87b-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="8d87b-107">**SIP trunks**至網際網路電話服務提供者（ITSP）</span><span class="sxs-lookup"><span data-stu-id="8d87b-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="8d87b-108">**直接將 SIP**連線至 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="8d87b-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="8d87b-109">**直接將 SIP**連線至 PBX</span><span class="sxs-lookup"><span data-stu-id="8d87b-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="8d87b-110">根據其大小、地理覆蓋及現有的語音基礎結構，企業可能會在不同的位置使用其中一個、兩個以上的選項。</span><span class="sxs-lookup"><span data-stu-id="8d87b-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8d87b-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="8d87b-111">In This Section</span></span>

  - [<span data-ttu-id="8d87b-112">Lync Server 2013 中的 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="8d87b-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="8d87b-113">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="8d87b-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="8d87b-114">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="8d87b-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="8d87b-115">Lync Server 2013 中的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="8d87b-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="8d87b-116">在 Lync Server 2013 中規劃撥出語音路由</span><span class="sxs-lookup"><span data-stu-id="8d87b-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

